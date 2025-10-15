---
title: Utiliser des tableaux d’objets
description: Découvrez comment Customer Journey Analytics crée des rapports sur les hiérarchies de données.
exl-id: 59318da7-5408-4a9d-82aa-8bcbec7f7364
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: aff01f4fc3520d461ca800382cc24d8d948d9cbc
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 61%

---

# Utilisation de tableaux d’objets

Certains schémas de plateforme peuvent avoir des tableaux d’objets. Adobe Customer Journey Analytics prend en charge l’ingestion et le compte rendu des performances des tableaux d’objets dans les données d’événement, de recherche et de profil. Un des exemples les plus courants est celui du panier, qui contient plusieurs produits. Chaque produit a un nom, un SKU, une catégorie, un prix, une quantité et toute autre dimension dont vous souhaitez effectuer le suivi. Toutes ces facettes ont des exigences distinctes, mais doivent toutes tenir dans le même accès.

Dans les versions précédentes d’Adobe Analytics, cet exploit a été accompli à l’aide de la variable `products`. Il s’agissait d’une chaîne concaténée séparée par des points-virgules (`;`) pour séparer les facettes d’un produit, tandis que des virgules (`,`) délimitaient les produits. C’était la seule variable avec une prise en charge limitée des « tableaux d’objets ». Les variables à plusieurs valeurs, telles que les variables de liste, peuvent prendre en charge l’équivalent de tableaux, mais elles ne peuvent pas prendre en charge les « tableaux d’objets ». Customer Journey Analytics développe ce concept en prenant en charge des hiérarchies arbitrairement profondes au sein d’une seule ligne de données, une fonctionnalité indisponible dans les versions précédentes d’Adobe Analytics.

## Exemple d’événement identique

L’événement suivant est un objet JSON qui représente un achat d’une machine à laver et d’un sèche-linge par un client.

```json
{
  "ID": "1", 
  "product": [
    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
  ], 
  "timestamp": 1534219229
}
```

Lors de la création d’une vue de données, les dimensions et mesures suivantes sont disponibles (en fonction du schéma) :

* **Dimensions :**
   * ID
   * produit : SKU
   * produit : nom
   * produit : id_commande
   * produit : garantie : couverture
   * produit : garantie : durée
   * produit : garantie : nom
   * produit : garantie : type
* **Mesures :**
   * produit : commandes
   * produit : unités
   * produit : chiffre d’affaires
   * produit : garantie
   * produit : garantie : chiffre d’affaires

### Exemples d’événements identiques (comportement de création de rapports)

En utilisant uniquement l’événement ci-dessus, les tableaux suivants présentent les rapports Workspace avec certaines combinaisons de dimensions et de mesures.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

Customer Journey Analytics examine de manière sélective la dimension et les mesures de l’objet en fonction du tableau.

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
+      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
+      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
+      "name": "LG Dryer 2000", 
+      "orders": 1, 
+      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Si vous souhaitez obtenir un rapport sur le seul chiffre d’affaires lié à la garantie, votre projet ressemblera à ce qui suit :

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

Customer Journey Analytics examine les parties suivantes de l’événement pour générer le rapport :

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
+          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
+          "revenue": 200
+        }, 
+        {
+          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
+          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
+  ], 
+  "timestamp": 1534219229
+}
```

Le sèche-linge n’étant pas couvert par une garantie, il n’est pas inclus dans le tableau.

Puisque vous pouvez combiner n’importe quelle dimension avec n’importe quelle mesure, le tableau suivant indique comment les données pourraient comporter des éléments de dimension non spécifiés :

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Il existe une commande de produit sans qu’un nom de garantie lui soit associé, de sorte que l’élément de dimension attribue à « Non spécifié ». La même situation s’applique également à la commande de garantie du produit :

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
          "coverage": "full coverage", 
          "length": "2 year", 
+          "name": "LG 2000 standard", 
+          "orders": 1, 
          "revenue": 200
+        }, 
+        {
          "coverage": "extended", 
          "length": "1 year", 
+          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
+      "orders": 1, 
      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Notez les commandes auxquelles aucun nom n’est associé. Il s’agit des commandes attribuées à l’élément de dimension « Non spécifié ».

### Combinaison de mesures

Customer Journey Analytics ne combine pas nativement des mesures dotées du même nom si elles se trouvent à différents niveaux d’objet.

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

Vous pouvez toutefois créer une mesure calculée qui combine les mesures de votre choix :

Mesure calculée « Chiffre d‘affaires total » : `[product : revenue] + [product : warranty : revenue]`

L’application de cette mesure calculée affiche les résultats souhaités :

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |



## Limites

Des limitations s’appliquent aux tableaux dans les données utilisées par Customer Journey Analytics et modélisées dans le cadre d’un schéma dans Experience Platform. Consultez les sections [Limites du modèle de données](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails#data-model-limits) et [Limites de taille des données](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails#data-size-limits) dans le [Mécanismes de sécurisation par défaut pour les données et la segmentation du profil client en temps réel](https://experienceleague.adobe.com/fr/docs/experience-platform/profile/guardrails).

