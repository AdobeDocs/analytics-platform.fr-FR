---
title: Configuration d’une visualisation de matrice dans Analysis Workspace
description: Découvrez comment configurer la visualisation de la matrice dans Customer Journey Analytics Analysis Workspace, y compris ses composants, les options d’affichage et les paramètres.
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 4%
---

# Configuration d’une visualisation de matrice

La visualisation Matrice est une grille de valeurs qui montre comment les éléments de dimension de deux dimensions se chevauchent ou se corrélent. Chaque cellule affiche l’intersection de l’élément de dimension de la ligne avec celui de l’élément de dimension de la colonne.

![Visualisation de la matrice](assets/matrix-overview.png)

## Présentation de la matrice

Voir [Présentation de la matrice](/help/analysis-workspace/visualizations/matrix/matrix.md) pour en savoir plus sur la visualisation de la matrice, notamment :

* Principales fonctionnalités

* Informations potentielles

* Différences entre les visualisations Matrice, Tableau à structure libre, Venn et Dispersion

## Création d’une visualisation de matrice

1. Ajoutez un panneau vierge à votre projet, sélectionnez l’icône [!UICONTROL **Visualisations**] dans le rail de gauche, puis faites glisser la visualisation [!UICONTROL **Matrice**] dans le panneau. <!-- FOLLOW-UP: add the Matrix icon before the name when it's available in help/assets/icons. -->

   Ou

   Ajoutez une visualisation de la matrice de l’une des manières décrites dans la section [Ajouter des visualisations à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) de la [Vue d’ensemble des visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

   <!-- add screenshot of the Matrix configuration fields -->

1. Spécifiez les informations suivantes pour configurer la visualisation de la matrice :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Dimension de ligne**] | Dimension dont les éléments apparaissent sous forme de lignes dans la matrice. |
   | [!UICONTROL **Dimension de colonne**] | Dimension dont les éléments apparaissent sous forme de colonnes dans la matrice. <p>Si vous sélectionnez la même dimension pour les dimensions de ligne et de colonne, la visualisation de la matrice compare les éléments de dimension les uns aux autres. Par exemple, si les deux dimensions sont _Type d’appareil_, chaque cellule affiche le chevauchement ou la corrélation entre deux types d’appareils, tels que _Téléphone mobile_ et _Tablette_. Les valeurs au-dessus et au-dessous de la diagonale se reflètent.</p> |
   | [!UICONTROL **Mesure**] | Mesure affichée par chaque cellule pour la combinaison de son élément de dimension de ligne et de son élément de dimension de colonne. |
   | [!UICONTROL **Conteneur**] | Conteneur qui détermine l’étendue du chevauchement entre les éléments de dimension de ligne et les éléments de dimension de colonne. (Si les noms de vos conteneurs diffèrent des noms par défaut affichés ci-dessous, cela signifie qu’ils ont été personnalisés dans votre vue de données.)<ul><li>**Personne :** (par défaut) Un élément de dimension de ligne et un élément de dimension de colonne se chevauchent lorsqu’ils se produisent pour la même personne, sur un nombre quelconque de sessions.</li><li>**Session :** un élément de dimension de ligne et un élément de dimension de colonne se chevauchent lorsqu’ils se produisent dans la même session.</li><li>**Événement :** un élément de dimension de ligne et un élément de dimension de colonne se chevauchent lorsqu’ils se produisent sur le même événement.</li></ul><!-- SME CHECK: confirm how each container defines overlap. --> |

1. (Facultatif) Modifiez l’un des paramètres suivants :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Limite de lignes**] | Nombre maximal de lignes affichées par la visualisation de la matrice. La valeur par défaut est 10. <!-- SME CHECK: Which items are shown (top items by the metric?)? Does the limit also apply to columns? What's the maximum? --> |
   | [!UICONTROL **Palette de chevauchement**] | Échelle de couleur des cellules lorsque la matrice affiche [décomptes de chevauchement](#view-overlap-count-or-correlation-strength). |
   | [!UICONTROL **Palette de corrélation**] | Échelle de couleur des cellules lorsque la matrice affiche [force de corrélation](#view-overlap-count-or-correlation-strength). Les corrélations négatives et positives utilisent des couleurs différentes. |
   | [!UICONTROL **Granularité de la corrélation**] | Granularité temporelle utilisée pour calculer [l’intensité de corrélation](#view-overlap-count-or-correlation-strength), par exemple **[!UICONTROL Jour]**. Cette valeur est définie automatiquement en fonction de la période du panneau. Vous ne pouvez pas le changer. <p>Les granularités suivantes sont sélectionnées en fonction de la période du panneau :</p><ul><li>[!UICONTROL **Heure**] : choisie pour des périodes de 7 jours ou moins</li><li>[!UICONTROL **Jour**] : sélectionné pour les périodes de plus de 7 jours et de 3 mois maximum</li><li>[!UICONTROL **Semaine**] : choisie pour les périodes de plus de 3 mois, jusqu’à 1 an</li><li>[!UICONTROL **Mois**] : sélectionné pour les périodes de plus d’un an</li></ul><!-- SME CHECK: The granularities and date range thresholds in this list are a best guess. Confirm which granularities are used for which date ranges. --> |
   | [!UICONTROL **Valeurs de cellule diagonale**] | Affichage de la visualisation de la matrice dans les cellules où se rencontre un élément de dimension. Ce paramètre n’est disponible que lorsque la dimension de ligne et la dimension de colonne sont identiques.<ul><li>**[!UICONTROL Afficher] :** affiche la valeur.</li><li>**[!UICONTROL Dash]:** affiche un tiret au lieu de la valeur.</li><li>**[!UICONTROL Vide]:** laisse la cellule vide.</li></ul> |

1. Sélectionnez la [!UICONTROL **Version**].

   <!-- add screenshot -->

1. Continuez avec la section suivante, [Afficher le nombre de chevauchements ou l&#39;intensité de la corrélation](#view-overlap-count-or-correlation-strength).

## Afficher le nombre de chevauchements ou l&#39;intensité de corrélation

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_matrix_overlap_correlation"
>title="Nombre de chevauchements par rapport à l’intensité de corrélation"
>abstract="<p>**Le nombre de chevauchements** est la valeur de la mesure sélectionnée où un élément de dimension de ligne et un élément de dimension de colonne se chevauchent.</p><p>**L’intensité de la corrélation** est une corrélation linéaire, de -1 à +1, de la proximité de la mesure pour les deux éléments de dimension qui se déplacent ensemble au fil du temps. Une valeur de +1 signifie qu&#39;ils s&#39;élèvent et tombent ensemble, 0 signifie qu&#39;il n&#39;y a aucune relation, et -1 signifie qu&#39;ils se déplacent dans des directions opposées. La force de corrélation est calculée séparément du chevauchement, de sorte que les éléments de dimension avec peu de chevauchement peuvent toujours avoir une forte corrélation.</p>"

<!-- markdownlint-enable MD034 -->

Vous pouvez activer/désactiver la visualisation de la matrice pour afficher le nombre de chevauchements ou la force de corrélation. Le nombre de chevauchements s’affiche par défaut.

1. Dans Analysis Workspace, ouvrez une visualisation Matrice ou [créez-en une](#build-a-matrix-visualization).

1. Dans le coin supérieur gauche de la visualisation Matrice, sélectionnez l’une des options suivantes :

   * [!UICONTROL **Nombre de chevauchements**] : indique le niveau de chevauchement existant pour chaque élément de dimension de ligne avec chaque élément de dimension de colonne. Chaque cellule affiche la valeur de la mesure sélectionnée pour les personnes, les sessions ou les événements (selon le conteneur) où les deux éléments de dimension se produisent.

   * [!UICONTROL **Intensité de la corrélation**] : indique la proximité de la mesure sélectionnée pour chaque élément de dimension de ligne et chaque élément de dimension de colonne se déplace ensemble sur la période du panneau, sous la forme d’une corrélation linéaire de -1 à +1. Une valeur de +1 signifie que les deux éléments de dimension montent et descendent toujours ensemble, 0 signifie qu’il n’y a aucune relation, et -1 signifie qu’ils se déplacent toujours dans des directions opposées. La force de corrélation est calculée séparément du chevauchement, de sorte que les éléments de dimension avec peu de chevauchement peuvent toujours avoir une forte corrélation. La corrélation est calculée à la granularité temporelle indiquée dans le paramètre [!UICONTROL **Granularité de la corrélation**]. <!-- SME CHECK: Confirm that the linear correlation is Pearson. -->

   Une légende dans le coin supérieur droit de la visualisation Matrice affiche l’échelle de couleur de la vue actuelle : faible à élevée pour le nombre de chevauchements ou négative (-1) à positive (+1) pour l’intensité de la corrélation.

## Afficher les informations

<!-- FOLLOW-UP: Draft based on a prototype screenshot. Add a screenshot of the insight card. -->

Une carte insight au bas de la visualisation Matrice décrit les modèles notables dans les données de la matrice.

<!-- SME CHECK: How are insights generated (AI)? What does the label on the card (such as ABSOLUTE) mean, and what other labels are there? Do the insights differ between the Overlap count and Correlation strength views? Are they updated when you change the settings or the panel date range? Can you hide the card? Are any permissions, entitlements, or AI settings required? -->

Pour afficher des informations :

1. Dans une visualisation de la matrice, affichez la carte insight au bas de la visualisation.

1. Utilisez les flèches de la carte insight pour parcourir les informations disponibles.

## Modifier les paramètres de la matrice

Après avoir créé une visualisation de la matrice, vous pouvez modifier ses paramètres, tels que les dimensions, la mesure ou le conteneur.

Pour modifier les paramètres de la matrice :

1. Dans une visualisation de matrice, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) en regard du sous-titre en haut de la visualisation. Le sous-titre résume les paramètres actuels, tels que la mesure et les dimensions.

1. Modifiez l’un des paramètres décrits dans [Créer une visualisation de matrice](#build-a-matrix-visualization).

1. Sélectionnez la [!UICONTROL **Version**].

<!-- SME CHECK: Confirm that the Edit icon reopens the build settings. Does the Matrix keep the Overlap count or Correlation strength view after you rebuild it? -->

## Afficher les données de tendance

Vous pouvez afficher les données de tendance d’une cellule dans une [visualisation en ligne](/help/analysis-workspace/visualizations/line.md). La visualisation en ligne montre comment la mesure sélectionnée change au cours de la période du panneau. Les lignes affichées varient selon que la matrice affiche [le nombre de chevauchements ou la force de corrélation](#view-overlap-count-or-correlation-strength).

Pour afficher les données de tendance :

1. Dans une visualisation de la matrice, cliquez avec le bouton droit sur la cellule pour laquelle vous souhaitez afficher les données de tendance.

1. Sélectionnez [!UICONTROL **Tendance**].

   Une visualisation en ligne est ajoutée au panneau, au-dessus de la visualisation Matrice :

   * [!UICONTROL **Nombre de chevauchements**] : une seule ligne affiche la mesure sélectionnée, filtrée par l’élément de dimension de ligne et l’élément de dimension de colonne.

   * [!UICONTROL **Force de la corrélation**] : deux lignes affichent la mesure sélectionnée, l’une pour l’élément de dimension de ligne et l’autre pour l’élément de dimension de colonne. Comparez les lignes pour voir à quel point les deux éléments de dimension suivent la tendance.

   <!-- SME CHECK: Does the overlap count filter use the Matrix container? Is the time granularity the panel default or the Correlation granularity? Can you select multiple cells? Is the option available for diagonal cells? -->

## Afficher le chevauchement dans une visualisation de Venn

Vous pouvez afficher le chevauchement entre l’élément de dimension de ligne et l’élément de dimension de colonne pour une cellule dans une [visualisation de Venn](/help/analysis-workspace/visualizations/venn.md).

Pour plus d’informations sur l’utilisation d’une visualisation Matrice ou d’une visualisation Venn, consultez [Choix entre les visualisations Matrice, Tableau à structure libre, Venn ou Nuage de points](/help/analysis-workspace/visualizations/matrix/matrix.md#choose-between-matrix-freeform-table-venn-or-scatter-visualizations) dans la [Présentation de la matrice](/help/analysis-workspace/visualizations/matrix/matrix.md).

Pour afficher le chevauchement dans une visualisation de Venn :

1. Dans une visualisation de la matrice, cliquez avec le bouton droit sur la cellule dont vous souhaitez afficher le chevauchement.

1. Sélectionnez [!UICONTROL **Afficher à Venn**].

   Une visualisation de Venn est ajoutée au panneau. Un cercle représente l’élément de dimension de ligne et l’autre cercle représente l’élément de dimension de colonne. La visualisation de Venn utilise la même mesure que la visualisation Matrice. <!-- SME CHECK: Where is the Venn visualization added? Are segments created for each dimension item, and do they use the Matrix container? Is the option available for diagonal cells and in the Correlation strength view? -->

## Appliquer une répartition

Vous pouvez ventiler les données d’une cellule par une autre dimension pour voir quels éléments de dimension contribuent à la valeur de la cellule.

Pour appliquer une répartition :

1. Dans une visualisation Matrice, cliquez avec le bouton droit sur la cellule à laquelle vous souhaitez appliquer une répartition.

1. Sélectionnez [!UICONTROL **Répartition**].

1. Sélectionnez la dimension à utiliser pour la répartition.

   Les principaux éléments de dimension de la dimension de répartition s’affichent dans un nouveau tableau à structure libre. <!-- SME CHECK: Where is the table added? Does the breakdown use the Matrix metric and container? Can you select multiple cells? Is the option available for diagonal cells and in the Correlation strength view? -->


