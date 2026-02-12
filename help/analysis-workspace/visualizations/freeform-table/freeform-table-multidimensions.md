---
title: Inclure plusieurs dimensions dans un tableau à structure libre
description: Découvrez comment inclure plusieurs dimensions dans un tableau à structure libre
feature: Visualizations
role: User
exl-id: 66ebb4fc-feb2-4fa7-a107-37508cca4748
source-git-commit: 14718476695dcf121c94ba4cb8b2c39e5874342d
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 2%

---

# Inclure plusieurs colonnes de dimensions dans un tableau à structure libre

{{release-limited-testing}}

Vous pouvez inclure jusqu’à 5 colonnes de dimension dans un tableau à structure libre, ce qui vous permet d’afficher plusieurs éléments de dimension côte à côte. Chaque ligne d’éléments de dimension se comporte comme un seul élément de dimension concaténé.

Vous pouvez appliquer des filtres, un tri, des répartitions, etc. aux tableaux à structure libre à plusieurs colonnes de dimensions afin de créer une analyse plus approfondie et plus personnalisée.

## Éléments de dimension concaténés

Lorsque vous [ajoutez plusieurs colonnes de dimension à un tableau à structure libre](#add-multiple-dimension-columns), chaque ligne d’éléments de dimension se comporte comme un seul élément de dimension concaténé. Cette fonctionnalité vous permet d’afficher les données de mesure pour des combinaisons spécifiques de dimensions.

Prenons l’exemple d’un tableau à structure libre dont les colonnes de dimension sont _Ville_, _Type d’appareil_ et _Jour du mois_ et la mesure est _Événements_. Les 3 éléments de dimension de la première ligne de ce tableau deviennent un seul élément de dimension concaténé montrant qu&#39;il y a eu 2 056 événements qui ont eu lieu à Mumbai à partir de téléphones portables le 30ème jour du mois.

| Dimension : Ville | Dimension : type d’appareil | Dimension : Jour du mois | Mesure : Événements |
|---------|----------|---------|---------|
| Bombay | Téléphone portable | 30 | 2 056 |
| New York | Tablette | 31 | 1 761 |
| Bangalore | Bureau | 1 | 1 666 |
| Delhi | Téléphone portable | 14 | 1 396 |

Voici comment apparaît ce tableau dans Analysis Workspace :

![Exemple multidimension](assets/multi-dim-example.png)

## Ajouter plusieurs colonnes de dimension

Vous pouvez ajouter plusieurs colonnes de dimension une par une ou en bloc.

1. Dans Analysis Workspace, créez un tableau à structure libre.

   Pour plus d’informations, voir [Ajouter des visualisations à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) dans [Présentation des visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Ajoutez des dimensions au tableau à structure libre. Vous pouvez ajouter des dimensions une par une ou vous pouvez ajouter plusieurs dimensions à la fois.

   * Faites glisser les dimensions une par une dans le tableau à structure libre. Placez des colonnes de dimension supplémentaires à gauche ou à droite des colonnes de dimension existantes dans le tableau. Une ligne verticale bleue **[!UICONTROL Ajouter]** indique l’emplacement de création de la colonne.

     ![Faire glisser des dimensions individuelles](assets/dimensions-add-individually.png)

   * Sélectionnez jusqu’à 5 dimensions dans le menu des composants et faites-les glisser dans le tableau à structure libre. Les dimensions sont ajoutées au tableau de gauche à droite dans l’ordre dans lequel vous les sélectionnez.

     Pour sélectionner plusieurs dimensions, maintenez la touche ***Commande*** (sous Mac) ou la touche ***Ctrl*** enfoncée (sous Windows).

     ![Faire glisser plusieurs dimensions](assets/dimensions-add-multiple.png)

1. Affichez chaque ligne du tableau en tant qu’élément de dimension unique. Pour plus d’informations, voir [Éléments de dimension concaténés](#concatenated-dimension-items).

## Filtrer et trier des tableaux

Vous pouvez appliquer un filtrage et un tri aux colonnes d’un tableau à structure libre. Vous pouvez trier les données d’un tableau à structure libre selon n’importe quelle colonne, qu’il s’agisse de dimensions ou de mesures. Vous pouvez même trier par plusieurs colonnes en même temps.

Pour plus d’informations, voir [Filtrer et trier les tableaux à structure libre](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Plusieurs colonnes et répartitions de dimension

Analysis Workspace propose les méthodes suivantes pour ajouter plusieurs dimensions dans un tableau à structure libre :

* Inclure plusieurs colonnes de dimension (comme décrit dans cet article)

* [Ajouter des répartitions](/help/components/dimensions/t-breakdown-fa.md)

Ces deux méthodes vous permettent d’analyser les dimensions par rapport à d’autres dimensions. Cependant, il existe des différences importantes, et les deux méthodes peuvent être utilisées dans le même tableau pour une analyse encore plus approfondie.

### Différences entre les colonnes et les répartitions de dimension

Plusieurs colonnes de dimension vous permettent d’effectuer les opérations suivantes :

* Concaténer des éléments de dimension dans des lignes de données distinctes sur plusieurs dimensions.

* Incluez les éléments de dimension dans des lignes concaténées uniquement lorsque les éléments de dimension s’appliquent à chaque colonne de dimension du tableau. Pour ce faire, utilisez le filtre de colonne pour désélectionner le paramètre **[!UICONTROL Inclure « Aucune valeur »]** sur chaque colonne de dimension.

  Pour plus d’informations, voir [Tri des tableaux sur plusieurs colonnes (tri avancé)](#sort-tables-by-multiple-columns-advanced-sorting).

* Triez les données en fonction de plusieurs colonnes de dimensions et de mesures pour afficher davantage de données personnalisées.

  Pour plus d’informations, voir [Tri des tableaux en fonction de plusieurs colonnes (tri avancé)](#sort-tables-by-multiple-columns-advanced-sorting)

Les répartitions vous permettent de :

* Ventilez un élément de dimension dans le tableau à structure libre par une dimension secondaire. Vous pouvez afficher jusqu’à 400 éléments de dimension pour la dimension secondaire.

### Ajouter des répartitions à un tableau avec plusieurs colonnes de dimension

Lorsque vous ajoutez une répartition à un tableau qui comporte plusieurs colonnes de dimension, la répartition s’applique à l’élément de dimension concaténé (sur toutes les colonnes de dimension) sur la ligne où vous l’ajoutez.

![exemple de répartition multitri](assets/dimensions-multiple-sort-breakdown.png)

De plus, vous pouvez ajouter plusieurs colonnes de dimension dans une répartition. Chaque ligne d’éléments de dimension dans la répartition se comporte également comme un seul élément de dimension concaténé.

<!-- Add a screenshot of a breakdown with multiple cllumns, then add this sentence: "For example, you can break down the first dimension item in this table by a new concatenated dimension item that shows..." -->

Pour plus d’informations sur l’ajout d’une répartition, voir [Répartition des dimensions](/help/components/dimensions/t-breakdown-fa.md).

## Créer un segment basé sur un élément de dimension qui s’étend sur plusieurs colonnes de dimension

Lorsque vous créez un segment basé sur un élément de dimension qui s’étend sur plusieurs colonnes de dimension, chaque élément de dimension est inclus dans la définition de segment, avec les opérateurs Et qui les rejoignent.

Pour plus d’informations sur la création d’un segment, voir [Créer des segments](/help/components/segments/seg-create.md).

## Dimensions et fonctionnalités non prises en charge {#unsupported}

Les combinaisons et fonctions de dimensions suivantes ne sont pas prises en charge lors de l’utilisation de plusieurs colonnes de dimensions. Analysis Workspace interdit leur utilisation ou affiche un message d’erreur :

* Dimensions multiples provenant de champs référençant différents [tableaux d’objets](/help/use-cases/object-arrays.md) utilisés ensemble dans le même tableau à structure libre.

  Plusieurs dimensions sont autorisées ensemble dans le même tableau à structure libre si elles référencent le même tableau d’objets.

* [Éléments de dimension statiques](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md#static-dimension-items).
