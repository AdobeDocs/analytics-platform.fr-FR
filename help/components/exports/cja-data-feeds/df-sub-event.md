---
title: Présentation des sous-événements et des tableaux d’objets dans les flux de données
description: Découvrez comment les flux de données Customer Journey Analytics exportent des sous-événements à partir de tableaux de schéma, en préservant la hiérarchie au lieu de l’aplatir comme le fait Workspace.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: a4fdb1f8d49b42b6de21881e0c8392995124c1ea
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 2%
---
# Sous-événements dans les flux de données

{{release-limited-testing}}

[Sous-événements](/help/components/segments/sub-event.md) dans Customer Journey Analytics vous permet d’analyser les données d’événement à un niveau plus granulaire que le niveau d’événement.

Utilisez les informations suivantes pour comprendre comment utiliser les sous-événements dans vos flux de données Customer Journey Analytics.

## Comprendre les sous-événements

### Sous-événements dans le schéma XDM

Dans le schéma XDM, chaque élément d’un tableau (un tableau de chaîne ou un tableau d’objet) est un sous-événement.

Pour afficher un événement avec des sous-événements dans le schéma XDM d’Adobe Experience Platform, sélectionnez [!UICONTROL **Schémas**], puis développez un événement contenant des sous-événements.

Dans l’exemple suivant, `Product list items` est un tableau d’objets contenant divers sous-événements.

![Schéma XDM contenant un tableau d’objets et des sous-événements](assets/df-sub-event-schema.png)

### Exemple de sous-événement : Produits dans un événement d’achat

Un client achète deux produits en une seule commande : une perceuse sans fil et deux packs de batteries de perceuse. Votre implémentation envoie un seul événement d’achat qui inclut les deux produits dans le tableau d’objets `productListItems` :

```json
{
  "eventType": "commerce.purchases",
  "timestamp": "2026-09-16T14:32:07.512Z",
  "commerce": {
    "purchases": { "value": 1 }
  },
  "productListItems": [
    { "SKU": "CD-2000", "name": "Cordless Drill", "quantity": 1, "priceTotal": 129.99 },
    { "SKU": "BP-2000", "name": "Drill Battery Pack", "quantity": 2, "priceTotal": 39.98 }
  ]
}
```

Cet événement contient deux sous-événements, un pour chaque objet du tableau `productListItems`. Le tableau suivant indique les champs qui appartiennent à l&#39;événement et ceux qui appartiennent à ses sous-événements.

| Niveau | Champs | Description des champs |
| --- | --- | --- |
| **Événement** | `eventType`, `timestamp`, `commerce.purchases.value` | L’achat dans son ensemble. Chaque champ comporte une valeur pour l’événement. La mesure **Commandes** compte `1` pour cet événement, quel que soit le nombre de produits qu’il contient. |
| **Sous-événement** | `SKU`, `name`, `quantity`, `priceTotal` dans chaque objet `productListItems` | Un produit individuel dans l’achat. Chaque champ comporte une valeur par produit. Par exemple, `quantity` est `1` pour la perceuse sans fil et `2` pour le bloc-batterie de perceuse. |

{style="table-layout:auto"}

>[!NOTE]
>
>Les sous-événements incluent uniquement les données envoyées avec l’événement. Customer Journey Analytics ne reconstruit pas le contenu du panier à partir d’événements précédents, tels que des ajouts au panier ou des passages en caisse. Pour que les produits apparaissent en tant que sous-événements d’un événement d’achat, votre implémentation doit les inclure dans les `productListItems` de cet événement d’achat.

## Ajout de données de sous-événement à un flux de données

Lorsque vous tentez d’ajouter une colonne qui est un sous-événement lors de la création d’un flux de données, une boîte de dialogue s’affiche, vous invitant à ajouter l’un des sous-événements pairs. Dans la sortie du flux de données, tous ces événements apparaissent dans une seule colonne.

## Afficher les données de sous-événement dans la sortie du flux de données

### Différences de sous-événements entre Analysis Workspace et les flux de données

Les sous-événements sont représentés différemment entre Analysis Workspace et les flux de données dans Customer Journey Analytics.

| Emplacement | Représentation des sous-événements |
| --- | --- |
| **Analysis Workspace (dans Customer Journey Analytics)** | Sélectionnable en tant que composants individuels, séparés de toute hiérarchie visible. |
| **Flux de données (dans Customer Journey Analytics)** | Représentés sous la forme d’un groupe, avec leur hiérarchie intacte. |

### Différences de sous-événements entre Adobe Analytics et Customer Journey Analytics

Les données de sous-événement (comme plusieurs détails de produit dans un seul événement d’achat) apparaissent différemment dans les flux de données Customer Journey Analytics et dans les flux de données Adobe Analytics. Le tableau suivant compare la manière dont chaque produit représente les données de sous-événement.

| Product | Affichage des données de sous-événements dans les flux de données | Exemple : liste de produits |
| --- | --- | --- |
| **Adobe Analytics** | Aplati en une chaîne délimitée dans une seule colonne. | Une liste de produits contient plusieurs produits regroupés dans une seule chaîne :<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Les sous-événements conservent la hiérarchie définie dans votre schéma XDM. Bien que regroupés dans la même colonne, ils affichent leur hiérarchie relationnelle par rapport à l’événement parent et aux sous-événements frères. | Une liste de produits conserve sa hiérarchie définie dans le schéma XDM sous la forme d’un tableau :<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### Différences par rapport à Adobe Analytics

### Différence de sortie entre les flux de données Adobe Analytics et Customer Journey Analytics

Les données de sous-événement (comme plusieurs détails de produit dans un seul événement d’achat) apparaissent différemment dans les flux de données Customer Journey Analytics et dans les flux de données Adobe Analytics. Le tableau suivant compare la manière dont chaque produit représente les données de sous-événement.

| Product | Affichage des données de sous-événements dans les flux de données | Exemple : liste de produits |
| --- | --- | --- |
| **Adobe Analytics** | Aplati en une chaîne délimitée dans une seule colonne. | Une liste de produits contient plusieurs produits regroupés dans une seule chaîne :<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Les sous-événements conservent la hiérarchie définie dans votre schéma XDM. Bien que regroupés dans la même colonne, ils affichent leur hiérarchie relationnelle par rapport à l’événement parent et aux sous-événements frères. | Une liste de produits conserve sa hiérarchie définie dans le schéma XDM sous la forme d’un tableau :<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Différence des sous-événements entre la sortie Analysis Workspace et les flux de données

Les sous-événements sont représentés différemment entre Analysis Workspace et les flux de données dans Customer Journey Analytics.

| Emplacement | Représentation des sous-événements |
| --- | --- |
| **Analysis Workspace** | Sélectionnable en tant que composants individuels, séparés de toute hiérarchie visible. |
| **Flux de données** | Représentés sous la forme d’un groupe, avec leur hiérarchie intacte. |


## Afficher les données de sous-événement dans la sortie du flux de données

Les données de sous-événement (comme plusieurs détails de produit dans un seul événement d’achat) apparaissent différemment dans les flux de données Customer Journey Analytics et dans les flux de données Adobe Analytics. Le tableau suivant compare la manière dont chaque produit représente les données de sous-événement.

| Product | Affichage des données de sous-événements dans les flux de données | Exemple : liste de produits |
| --- | --- | --- |
| **Adobe Analytics** | Aplati en une chaîne délimitée dans une seule colonne. | Une liste de produits contient plusieurs produits regroupés dans une seule chaîne :<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Les sous-événements conservent la hiérarchie définie dans votre schéma XDM. Bien que regroupés dans la même colonne, ils affichent leur hiérarchie relationnelle par rapport à l’événement parent et aux sous-événements frères. | Une liste de produits conserve sa hiérarchie définie dans le schéma XDM sous la forme d’un tableau :<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Requête sur les données de sous-événement dans la sortie du flux de données

Comme les données de sous-événement [apparaissent différemment dans les flux de données Customer Journey Analytics](#view-sub-event-data-in-data-feed-output), les requêtes que vous utilisez pour ces flux diffèrent de celles que vous utilisez pour les flux de données Adobe Analytics.

Les exemples suivants montrent comment rechercher des événements qui incluent un produit spécifique. Les exemples utilisent la syntaxe BigQuery Google. D’autres entrepôts de données, tels que Snowflake et Databricks, prennent en charge la même approche avec des différences de syntaxe mineures.

+++ Requête sur les données de produit dans les flux de données Customer Journey Analytics

Dans les flux de données Customer Journey Analytics, les deux mêmes produits apparaissent sous la forme d’un tableau d’objets dans la colonne `product_list_items`. Aucune analyse du délimiteur n’est requise :

```json
{
  "row_id": "01K3F2M9-...-4821",
  "timestamp_utc": "2026-09-16T14:32:07.512000Z",
  "product_list_items": [
    { "category": "Power Tools", "product": "Cordless Drill", "quantity": 1, "revenue": 129.99,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} },
    { "category": "Power Tools", "product": "Drill Battery Pack", "quantity": 2, "revenue": 39.98,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} }
  ]
}
```

Le mode d’écriture de la requête varie selon que vous souhaitez une ligne par événement ou une ligne par produit correspondant.

**Renvoie une ligne par événement**

Pour filtrer les événements sans modifier le nombre de lignes, utilisez `UNNEST` dans une sous-requête `EXISTS` :

```sql
SELECT row_id, timestamp_utc, product_list_items
FROM `project.dataset.cja_data_feed` AS f
WHERE EXISTS (
  SELECT 1
  FROM UNNEST(f.product_list_items) AS item
  WHERE item.product = 'Cordless Drill'
);
```

Cette requête renvoie une ligne pour chaque événement correspondant, avec le tableau `product_list_items` complet intact, quel que soit le nombre de produits dans le tableau qui correspondent.

**Renvoie une ligne par produit correspondant**

Pour renvoyer une ligne pour chaque produit correspondant, déplacez-`UNNEST` dans la clause de `FROM` externe :

```sql
SELECT f.row_id, f.timestamp_utc, item.product, item.quantity, item.revenue
FROM `project.dataset.cja_data_feed` AS f,
     UNNEST(f.product_list_items) AS item
WHERE item.product = 'Cordless Drill';
```

Un événement avec plusieurs produits correspondants s’affiche sur plusieurs lignes et les colonnes de l’événement, telles que `row_id`, se répètent sur chaque ligne. N’utilisez cette approche que lorsque vous avez besoin de détails au niveau du produit. Pour comptabiliser les événements dans les résultats, utilisez `COUNT(DISTINCT row_id)` au lieu de comptabiliser les lignes.

Cette approche s’applique à tout champ de tableau de votre schéma XDM, et pas seulement aux produits.

+++

+++ Requête sur les données de produit dans les flux de données Adobe Analytics

Dans les flux de données Adobe Analytics, un événement avec deux produits achetés ensemble s’affiche sous la forme d’une chaîne délimitée unique dans la colonne `product_list` :

```text
Power Tools;Cordless Drill;1;129.99;event1=1;eVar10=DrillBundle,Power Tools;Drill Battery Pack;2;39.98;event1=1;eVar10=DrillBundle
```

Pour rechercher des événements qui incluent une exploration sans fil, vous analysez cette chaîne avec une expression régulière :

```sql
SELECT hitid_high, hitid_low, post_evar10
FROM aa_hit_data
WHERE REGEXP_CONTAINS(product_list, r'(^|,)[^;]*;Cordless Drill;')
```

+++






