---
title: Panneau d’attribution
description: Utilisation et interprétation du panneau d’attribution dans Analysis Workspace.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 94%

---


# Panneau d’attribution

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

Le panneau d’attribution permet de créer aisément une analyse comparant différents modèles d’attribution. Il s’agit d’une fonctionnalité d’[Attribution IQ](../attribution/overview.md) qui vous permet d’utiliser et de comparer des modèles d’attribution dans un espace de travail dédié.

## Création d’un panneau d’attribution

1. Cliquez sur l’icône du panneau à gauche.
1. Faites glisser le panneau d’attribution dans votre projet Analysis Workspace.

   ![Nouveau panneau d’attribution](assets/Attribution_Panel_1.png)

1. Ajoutez une mesure que vous souhaitez attribuer et ajoutez toute dimension à laquelle vous souhaitez l’attribuer. Par exemple, les canaux marketing ou les dimensions personnalisées, telles que les promotions internes.

   ![Sélection d’une dimension et d’une mesure](assets/attribution_panel2.png)

1. Sélectionnez les [modèles d’attribution et l’intervalle de recherche en amont](../attribution/models.md) que vous souhaitez comparer.

1. Le panneau d’attribution renvoie un riche ensemble de données et des visualisations qui comparent l’attribution de la dimension et de la mesure sélectionnées.

   ![Visualisations d’attribution](assets/attr_panel_vizs.png)

## Visualisations d’attribution

* **Mesure totale** : nombre total de conversions survenues pendant le créneau de rapport. Il s’agit des conversions qui sont attribuées pour la dimension que vous avez sélectionnée.
* **Graphique à barres de comparaison d’attribution des mesures** : compare visuellement les conversions attribuées à chacun des éléments de dimension de la dimension sélectionnée. Chaque couleur de barre représente un modèle d’attribution distinct.
* **Tableau à structure libre d’attribution des mesures** : affiche, sous forme de tableau, les mêmes données que le graphique à barres. La sélection de différentes colonnes ou lignes dans ce tableau permet de filtrer le graphique à barres ainsi que plusieurs autres visualisations du panneau. Ce tableau se comporte de la même manière que tout autre tableau à structure libre de Workspace. Il vous permet d’ajouter des composants tels que des mesures, des segments ou des ventilations.
* **Diagramme de chevauchement des dimensions** : diagramme de Venn présentant les trois principaux éléments de dimension et la fréquence à laquelle ils participent conjointement à une conversion. Par exemple, la taille du chevauchement des bulles indique la fréquence des conversions lorsqu’un visiteur a été exposé aux deux éléments de dimension. La sélection d’autres lignes dans le tableau à structure libre adjacent met à jour la visualisation pour refléter votre sélection.
* **Points de contact marketing par parcours** : histogramme indiquant le nombre de points de contact d’un visiteur dans l’intervalle de recherche en amont. Ceci est utile pour voir l’impact de l’attribution multi-touch pour votre jeu de données. Si presque tous les visiteurs n’ont qu’un seul point de contact, il est probable que différents modèles d’attribution affichent des données similaires.
* **Détails sur les performances des canaux de marketing** : vous permet de comparer visuellement jusqu’à trois modèles d’attribution à l’aide d’un graphique de dispersion.
* **Flux de canal marketing** : vous permet de voir avec quels canaux les visiteurs interagissent le plus souvent, et dans quel ordre au cours de leur parcours.
