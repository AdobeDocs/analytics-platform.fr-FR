---
title: Inclure plusieurs dimensions dans un tableau à structure libre
description: Découvrez comment inclure plusieurs dimensions dans un tableau à structure libre
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: bff352181392c19b6c4fe70893a016179fb77f06
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 2%

---

# Inclure plusieurs dimensions dans un tableau à structure libre

{{release-limited-testing}}

Vous pouvez inclure jusqu’à 5 colonnes de dimension dans un tableau à structure libre, ce qui vous permet d’afficher plusieurs éléments de dimension côte à côte. Chaque ligne d’éléments de dimension agit comme un seul élément concaténé.

Vous pouvez trier les colonnes des dimensions (ainsi que les colonnes des mesures) pour une analyse plus complète et personnalisée.

## Plusieurs colonnes et répartitions de dimension

Analysis Workspace propose les méthodes suivantes pour ajouter plusieurs dimensions dans un tableau à structure libre :

* Inclure plusieurs colonnes de dimension (comme décrit dans cet article)

* [Ajouter des répartitions](/help/components/dimensions/t-breakdown-fa.md)

Ces deux méthodes vous permettent d’analyser les dimensions par rapport à d’autres dimensions. Cependant, il existe des différences importantes, et les deux méthodes peuvent être utilisées dans le même tableau pour une analyse encore plus approfondie.

Plusieurs colonnes de dimension vous permettent d’effectuer les opérations suivantes :

* Mettre en corrélation des lignes de données sur plusieurs dimensions et mesures.

* Afficher les données uniquement lorsqu’elles s’appliquent à chaque colonne de dimension du tableau. Pour ce faire, utilisez le filtre de colonne pour désélectionner le paramètre **[!UICONTROL Inclure « Aucune valeur »]** sur chaque colonne de dimension.

  Pour plus d’informations, voir [Filtrer et trier des tableaux](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

* Triez les données en fonction de plusieurs colonnes de dimensions et de mesures.

  Pour plus d’informations, voir [Filtrer et trier des tableaux](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

Les répartitions vous permettent de :

* Afficher les éléments de dimension pour un seul élément

* Afficher les principaux éléments de dimension pour un seul

## Ajouter des colonnes de dimension

Vous pouvez ajouter des colonnes de dimension une par une ou en bloc.

1. Dans Analysis Workspace, créez un tableau à structure libre.

   Pour plus d’informations, voir [Ajouter des visualisations à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) dans [Présentation des visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Ajoutez des dimensions au tableau à structure libre. Vous pouvez ajouter des dimensions une par une ou vous pouvez ajouter plusieurs dimensions à la fois.

   * Faites glisser les dimensions une par une dans le tableau à structure libre. Placez des colonnes de dimension supplémentaires à gauche ou à droite des colonnes de dimension existantes dans le tableau. Une ligne verticale bleue **[!UICONTROL Ajouter]** indique l’emplacement de création de la colonne.

     ![Faire glisser des dimensions individuelles](assets/dimensions-add-individually.png)

   * Sélectionnez jusqu’à 5 dimensions dans le menu des composants et faites-les glisser dans le tableau à structure libre. Les dimensions sont ajoutées au tableau de gauche à droite dans l’ordre dans lequel vous les sélectionnez.

     Pour sélectionner plusieurs dimensions, maintenez la touche ***Commande*** (sous Mac) ou la touche ***Ctrl*** enfoncée (sous Windows).

     ![Faire glisser plusieurs dimensions](assets/dimensions-add-multiple.png)

## Filtrer des tableaux

Pour plus d’informations sur le filtrage des tableaux, voir [Filtrer les tableaux](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#filter-tables) dans [Filtrer et trier les tableaux](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Trier des tableaux {#sort-tables}

<!--At GA, move this section into the "Filter and sort tables" article and replace the current "Sort tables" section. Change the "Filter tables" section above to "Filter and sort tables" and link to the other article. Also add row to Guardrails article. -->

Vous pouvez trier les données d’un tableau à structure libre selon n’importe quelle colonne d’Analysis Workspace qui est une dimension ou une mesure.

Par défaut, les dimensions sont triées par ordre croissant et les mesures sont triées par ordre décroissant.

### Trier les tableaux par colonne

Lorsque vous triez les données d’une seule colonne comme décrit dans cette section, tout [tri avancé](#sort-tables-by-multiple-columns-advanced-sorting) appliqué au tableau est supprimé.

Pour trier les données des tableaux selon une seule colonne :

1. Placez le pointeur de la souris sur l’en-tête de la colonne à trier, puis sélectionnez l’icône **Trier** ![Trier](/help/assets/icons/SortOrderDown.svg) lorsqu’elle s’affiche.

   ![Menu déroulant Tri](assets/sort-dropdown-menu.png)

1. Sélectionnez **[!UICONTROL Croissant]** ou **[!UICONTROL Décroissant]**.

   L’icône de tri reste visible lorsque le tri est appliqué à la colonne. Une flèche indique le mode de tri des données (![Tri](/help/assets/icons/SortOrderUp.svg) pour l’ordre croissant ou ![Tri](/help/assets/icons/SortOrderDown.svg) pour l’ordre décroissant).

### Trier des tableaux sur plusieurs colonnes (tri avancé)

{{release-limited-testing-section}}

#### Appliquer le tri à plusieurs colonnes

Pour trier les données des tableaux en fonction de plusieurs colonnes :

1. Placez le pointeur de la souris sur l’en-tête d’une colonne à trier, puis sélectionnez l’icône **Trier** ![Trier](/help/assets/icons/SortOrderDown.svg) lorsqu’elle s’affiche.

   ![Menu déroulant Tri](assets/sort-dropdown-menu.png)

1. Sélectionnez **[!UICONTROL Tri avancé]**.

   ![&#x200B; Boîte de dialogue Tri avancé &#x200B;](assets/sort-advanced-dialog.png)

1. Dans la boîte de dialogue Tri avancé , effectuez l’une des opérations suivantes :

   * Ajoutez les colonnes qui ne sont pas encore triées en sélectionnant le bouton **[!UICONTROL Ajouter une colonne de tri]**.

   * Supprimez les colonnes que vous ne souhaitez plus trier en sélectionnant l’icône **Supprimer** ![Supprimer](/help/assets/icons/Close.svg).

   * Faire glisser les colonnes plus haut ou plus bas dans la liste pour ajuster la priorité de tri.

     Pour plus d’informations, voir [Priorité de tri](#sort-priority).

   * Modifiez la valeur de tri en sélectionnant **[!UICONTROL Croissant]** ou **[!UICONTROL Décroissant]** dans le menu déroulant.

   * Sélectionnez une autre colonne en sélectionnant le menu déroulant Nom de la colonne .

1. Sélectionnez **[!UICONTROL Appliquer]**.

L’icône de tri reste visible lorsque le tri est appliqué à une colonne. Une flèche indique le mode de tri des données (![Tri](/help/assets/icons/SortOrderUp.svg) pour l’ordre croissant ou ![Tri](/help/assets/icons/SortOrderDown.svg) pour l’ordre décroissant).

![exemple multi-tri](assets/dimensions-multiple-sort.png)

#### Priorité de tri

Lorsque vous triez des données pour plusieurs colonnes, les données sont triées en fonction de la priorité que vous attribuez à chaque colonne. La numérotation de priorité s’affiche en regard de l’icône de tri ![icône de priorité de tri](assets/sort-priority-icon.png).

La colonne avec la priorité principale détermine l’ordre principal, la colonne avec la priorité secondaire détermine l’ordre lorsque des lignes ont la même valeur dans la colonne principale, la colonne avec la priorité tertiaire détermine l’ordre lorsque des lignes ont la même valeur dans les colonnes principale et secondaire, etc.

Prenons l’exemple d’un tableau avec les colonnes suivantes :

* Jour du mois (dimension)

* Heure de la journée (dimension)

* Événements (mesure)

Vous pouvez attribuer une priorité de tri à chaque colonne, comme suit :

| Nom de la colonne (composant) | Type de composant | Priorité de tri |
|---------|----------|---------|
| Jour du mois | Dimension | 1 |
| Heure de la journée | Dimension | 2 |
| Événements | Mesure | 3 |

En attribuant une priorité de tri à chaque colonne, vous pouvez contrôler exactement l’affichage des données dans le tableau. Dans cet exemple, les informations sont d’abord triées par Jour du mois, puis par Heure de la journée et enfin par Événements.

![exemple multi-tri](assets/dimensions-multiple-sort.png)

## Ajouter des répartitions à un tableau avec plusieurs colonnes de dimension

Lorsque vous ajoutez une répartition à un tableau qui comporte plusieurs colonnes de dimensions, la répartition s’étend sur tous les éléments de dimension de la ligne où elle est ajoutée.

Vous pouvez ajouter une répartition comme décrit dans la section [Répartir les dimensions](/help/components/dimensions/t-breakdown-fa.md).

## Dimensions non prises en charge {#unsupported}

Les combinaisons de dimensions suivantes ne sont pas prises en charge. Analysis Workspace les interdit ou affiche un message d’erreur une fois ajoutées :

* Dimensions multiples provenant de champs référençant différents [tableaux d’objets](/help/use-cases/object-arrays.md) utilisés ensemble dans le même tableau à structure libre.

  Plusieurs dimensions sont autorisées ensemble dans le même tableau à structure libre si elles référencent le même tableau d’objets.