---
title: Panneau d’attribution
description: Utilisation et interprétation du panneau d’attribution dans Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 94%

---

# Panneau d’attribution

Le panneau [!UICONTROL Attribution] vous permet de créer facilement une analyse comparant différents modèles d’attribution. Il s’agit d’une fonctionnalité d’[Attribution IQ](../attribution/overview.md) qui vous permet d’utiliser et de comparer des modèles d’attribution dans un espace de travail dédié.

## Création d’un panneau d’attribution

1. Cliquez sur l’icône du panneau à gauche.
1. Faites glisser le panneau [!UICONTROL Attribution] dans votre projet Analysis Workspace.

   ![Nouveau panneau d’attribution](assets/Attribution_Panel_1.png)

1. Ajoutez une mesure que vous souhaitez attribuer et ajoutez toute dimension à laquelle vous souhaitez l’attribuer. Par exemple, les canaux marketing ou les dimensions personnalisées, telles que les promotions internes.

   ![Sélection d’une dimension et d’une mesure](assets/attribution_panel2.png)

1. Sélectionnez les [modèles d’attribution et l’intervalle de recherche en amont](../attribution/models.md) que vous souhaitez comparer.

1. Le panneau d’attribution renvoie un riche ensemble de données et des visualisations qui comparent l’attribution de la dimension et de la mesure sélectionnées.

   ![Visualisations d’attribution](assets/attr_panel_vizs.png)

## Visualisations d’attribution

* **Mesure totale** : nombre total de conversions survenues pendant le créneau de rapport. Il s’agit des conversions qui sont attribuées pour la dimension que vous avez sélectionnée.
* **Barres de comparaison d’attribution** : compare visuellement les conversions attribuées à chacun des éléments de dimension de la dimension sélectionnée. Chaque couleur de barre représente un modèle d’attribution distinct.
* **Tableau de comparaison d’attribution** : affiche, sous forme de tableau, les mêmes données que le graphique à barres. La sélection de différentes colonnes ou lignes dans ce tableau permet de filtrer le graphique à barres ainsi que plusieurs autres visualisations du panneau. Ce tableau fonctionne de la même manière que tout autre tableau à structure libre de Workspace, ce qui vous permet d’ajouter des composants tels que des mesures, des filtres ou des ventilations.
* **Diagramme de chevauchement** : diagramme de Venn présentant les trois principaux éléments de dimension et la fréquence à laquelle ils participent conjointement à une conversion. Par exemple, la taille du chevauchement des bulles indique la fréquence des conversions lorsqu’un visiteur a été exposé aux deux éléments de dimension. La sélection d’autres lignes dans le tableau à structure libre adjacent met à jour la visualisation pour refléter votre sélection.
* **Détails sur les performances** : vous permet de comparer visuellement jusqu’à trois modèles d’attribution à l’aide d’un graphique de dispersion.
* **Performance de tendance** : affiche la tendance des conversions attribuées pour le principal élément de dimension. La sélection d’autres lignes dans le tableau à structure libre adjacent met à jour la visualisation pour refléter votre sélection.
* **Flux** : vous permet de voir avec quels canaux les visiteurs interagissent le plus souvent lors de leur parcours, et dans quel ordre.
