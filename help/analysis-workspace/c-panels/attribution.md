---
title: Panneau Attribution
description: Utilisation et interprétation du panneau d’attribution dans l’Analysis Workspace.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 14%

---


# Panneau Attribution

>[!NOTE]
>
>Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

Le panneau d’attribution permet de créer aisément une analyse comparant différents modèles d’attribution. Il s’agit d’une fonctionnalité du QI [](../attribution/overview.md) d’attribution qui vous permet d’utiliser et de comparer des modèles d’attribution dans un espace de travail dédié.

## Création d’un panneau d’attribution

1. Cliquez sur l’icône du panneau située à gauche.
1. Faites glisser le panneau d’attribution dans votre projet Analysis Workspace.

   ![Nouveau panneau d’attribution](assets/Attribution_Panel_1.png)

1. Ajoutez une mesure que vous souhaitez attribuer et ajoutez toute dimension à attribuer. Par exemple, les Canaux marketing ou les dimensions personnalisées, telles que les promotions internes.

   ![Sélectionner une dimension et une mesure](assets/attribution_panel2.png)

1. Sélectionnez les modèles [d’attribution et la fenêtre](../attribution/models.md) de recherche en amont que vous souhaitez comparer.

1. Le panneau Attribution renvoie un riche ensemble de données et de visualisations qui comparent l’attribution pour la dimension et la mesure sélectionnées.

   ![Visualisations d’attribution](assets/attr_panel_vizs.png)

## Visualisations d’attribution

* **Mesure** totale : Nombre total de conversions survenues au cours de la période du rapports. Il s’agit des conversions qui sont attribuées pour la dimension que vous avez sélectionnée.
* **Graphique**&#x200B;à barres de comparaison d&#39;attribution des mesures : compare visuellement les conversions attribuées à chacun des éléments de dimension de la dimension sélectionnée. Chaque couleur de barre représente un modèle d’attribution distinct.
* **Tableau**&#x200B;à structure libre Attribution de mesure : Affiche les mêmes données que le graphique à barres, représenté sous la forme d’un tableau. La sélection de différentes colonnes ou lignes dans ce tableau filtres le graphique à barres ainsi que plusieurs autres visualisations du panneau. Ce tableau se comporte de la même manière que tout autre tableau à structure libre de Workspace. Il vous permet d’ajouter des composants tels que des mesures, des segments ou des ventilations.
* **Diagramme** de chevauchement des dimensions : Diagramme de Venn présentant les trois principales valeurs de dimension et la fréquence à laquelle elles participent conjointement à une conversion. Par exemple, la taille du chevauchement des bulles indique la fréquence des conversions lorsqu’un visiteur a été exposé aux deux valeurs de dimension. La sélection d’autres lignes dans le tableau à structure libre adjacent met à jour la visualisation pour refléter votre sélection.
* **Points de contact marketing par parcours**: Histogramme indiquant le nombre de points de contact qu’un visiteur a eus dans la fenêtre de recherche en amont. Ceci est utile pour voir l’impact de l’attribution multi-touch pour votre jeu de données. Si presque tous les visiteurs n’ont qu’un seul point de contact, différents modèles d’attribution présentent probablement des données similaires.
* **Détails** des performances du Canal marketing : Permet de comparer visuellement jusqu’à trois modèles d’attribution à l’aide d’un graphique de dispersion.
* **Flux** de Canal marketing : Vous permet de déterminer les canaux qui interagissent le plus souvent et dans quel ordre d’un visiteur à l’autre.
