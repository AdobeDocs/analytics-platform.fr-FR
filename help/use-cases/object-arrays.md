---
title: Utilisation de la méthode CJA avec des tableaux d’objets
description: Comprenez comment la CJA crée des rapports sur les hiérarchies de données.
translation-type: tm+mt
source-git-commit: b7cd74f3fe2f0222e78452f58a7c387f6e0c86d2
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---


# Utilisation de la méthode CJA avec des tableaux d’objets

Certains schémas de plateforme peuvent avoir des tableaux d’objets. Un des exemples les plus courants est celui du panier, qui contient plusieurs produits. Chaque produit a un nom, un SKU, une catégorie, un prix, une quantité et toute autre dimension dont vous souhaitez effectuer le suivi. Toutes ces facettes ont des exigences distinctes, mais doivent toutes tenir dans le même accès.

Dans les versions précédentes d’Adobe Analytics, cet exploit a été accompli à l’aide de la `products` variable. Il s’agissait d’une chaîne concaténée séparée par des points-virgules (`;`) pour séparer les facettes d’un produit, tandis que des virgules (`,`) délimitaient les produits. C&#39;était la seule variable avec une prise en charge limitée des &quot;tableaux d&#39;objets&quot;. Les variables à plusieurs valeurs, telles que les variables de liste, peuvent prendre en charge l’équivalent de tableaux, mais elles ne peuvent pas prendre en charge les &quot;tableaux d’objets&quot;. CJA développe ce concept en prenant en charge des hiérarchies arbitrairement profondes dans une seule ligne de données, une fonctionnalité qui n&#39;est pas disponible dans aucune version précédente d&#39;Adobe Analytics.

## Exemple de même accès

L’accès suivant est un objet JSON qui représente l’achat d’un client à partir d’une machine à laver et d’un sèche-linge.

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

Lors de la création d’une vue de données, les dimensions et mesures suivantes sont disponibles (en fonction du schéma) :

* **Dimensions:**
   * ID
   * product : SKU
   * product : name
   * product : order_id
   * product : garantie : couverture
   * produit : garantie : length
   * product : garantie : name
   * product : garantie : type
* **Mesures:**
   * product : commandes
   * product : unités
   * product : recette
   * product : garantie
   * product : garantie : recette

### Exemples d’accès identiques (comportement du rapports)

En utilisant uniquement l’accès ci-dessus, les tableaux suivants montrent les rapports Workspace avec certaines combinaisons de dimensions et de mesures.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJA examine de manière sélective la dimension et les mesures de l’objet en fonction du tableau.

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

Si vous souhaitez obtenir un rapport sur les seules recettes de garantie, votre projet ressemblera à ce qui suit :

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

CJA examine ces parties de l’accès pour générer le rapport :

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

Le séchoir n&#39;étant pas couvert par une garantie, il n&#39;est pas inclus dans le tableau.

Puisque vous pouvez combiner n’importe quelle dimension avec n’importe quelle mesure, le tableau suivant indique comment les données pourraient comporter des valeurs de dimension non spécifiées :

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Il existe une commande de produit sans qu&#39;un nom de garantie lui soit lié, de sorte que la valeur de dimension attribue à &quot;Non spécifié&quot;. La même situation s&#39;applique également à la commande de garantie du produit :

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
