---
title: Présentation des sous-événements et des tableaux d’objets dans les flux de données
description: Découvrez comment les flux de données Customer Journey Analytics exportent des sous-événements à partir de tableaux de schéma, en préservant la hiérarchie au lieu de l’aplatir comme le fait Workspace.
hide: true
feature: Components
source-git-commit: afc1b55eb54b5f3342800489d0a7f63508ee8b10
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%
---
# Sous-événements dans les flux de données

{{release-limited-testing}}

Dans le schéma XDM, tout ce qui est un tableau (chaîne ou objet) est un sous-événement. Dans Customer Journey Analytics, les sous-événements sont représentés dans les exportations de flux de données avec leur hiérarchie.

Dans Adobe Analytics, les sous-événements sont représentés sous la forme d’une seule colonne.

Utilisez les informations suivantes pour comprendre comment utiliser les sous-événements dans vos flux de données Customer Journey Analytics.

## Sous-événements dans le schéma XDM, Workspace et les flux de données

Vous définissez des sous-événements dans le schéma XDM, sous la forme de tableaux de chaînes ou de tableaux d’objets.

Ces sous-événements sont représentés différemment selon que vous les affichez dans Analysis Workspace ou dans les flux de données.

| Emplacement | Représentation des sous-événements |
| --- | --- |
| **Analysis Workspace** | Les objets individuels d’un tableau d’objets peuvent être sélectionnés en tant que composants individuels, séparés de toute hiérarchie visible. |
| **Flux de données** | Les objets d’un tableau d’objets sont représentés sous la forme d’un groupe, avec leur hiérarchie intacte. |

## Ajout de données de sous-événement à un flux de données

Lorsque vous tentez d’ajouter une colonne qui est un sous-événement lors de la création d’un flux de données, une boîte de dialogue s’affiche et vous permet d’ajouter tous les sous-événements pairs. Tous ces événements s’affichent dans une seule colonne de la sortie du flux de données.

## Afficher les données de sous-événement dans la sortie du flux de données

Les données de sous-événement (comme plusieurs produits dans un seul événement) apparaissent différemment dans les flux de données Customer Journey Analytics et dans les flux de données Adobe Analytics. Le tableau suivant compare la manière dont chaque produit représente les données de sous-événement.

| Product | Affichage des données de sous-événements dans les flux de données | Exemple : liste de produits |
| --- | --- | --- |
| **Adobe Analytics** | Aplati en une chaîne délimitée dans une seule colonne. | Une liste de produits contient plusieurs produits regroupés dans une seule chaîne :<p>`;LG Washing Machine 2000;1;1600,;LG Dryer 2000;1;500` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Les sous-événements conservent la hiérarchie définie dans votre schéma XDM. Ils restent regroupés dans la même colonne, avec leur événement parent et les sous-événements frères. | Une liste de produits conserve sa hiérarchie définie dans le schéma XDM sous la forme d’un tableau :<p>`[{"name":"LG Washing Machine 2000","units":1,"revenue":1600},{"name":"LG Dryer 2000","units":1,"revenue":500}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Requête sur les données de sous-événement dans la sortie du flux de données

Comme les données de sous-événement [apparaissent différemment dans les flux de données Customer Journey Analytics](#customer-journey-analytics-vs-adobe-analytics), les requêtes que vous utilisez pour ces flux diffèrent de celles que vous utilisez pour les flux de données Adobe Analytics.

Les exemples suivants montrent comment rechercher des événements qui incluent un produit spécifique. Les exemples utilisent la syntaxe BigQuery Google. D’autres entrepôts de données, tels que Snowflake et Databricks, prennent en charge la même approche avec des différences de syntaxe mineures.

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






