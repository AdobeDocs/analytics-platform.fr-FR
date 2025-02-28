---
title: Panneau d’attribution
description: Utilisation et interprétation du panneau d’attribution dans Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
source-git-commit: 1709bb2e262759376b0b0bb78444253968f9dac4
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 38%

---

# Panneau d’attribution {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_attribution_button"
>title="Attribution"
>abstract="Comparez et visualisez rapidement un certain nombre de modèles d’attribution à l’aide de la mesure de succès, du canal et de l’intervalle de recherche en amont."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panneau Attribution IQ"

>[!CONTEXTUALHELP]
>id="workspace_attribution_panel"
>title="Panneau d’attribution"
>abstract="Comparez et visualisez rapidement un nombre illimité de modèles d’attribution pour une mesure de succès. Sélectionnez le canal (dimension), les modèles à inclure et l’intervalle de recherche en amont."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panneau Attribution IQ"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Cet article présente le panneau Attribution dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Voir [Panneau d’attribution](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/attribution) pour la version_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de cet article._

>[!ENDSHADEBOX]

Le panneau **[!UICONTROL Attribution]** vous permet de créer facilement une analyse comparant différents modèles d’attribution. Le panneau vous fournit un espace de travail dédié à l’utilisation et à la comparaison des modèles d’attribution.

Customer Journey Analytics améliore l’attribution en vous permettant de :

* Définissez l’attribution au-delà des médias achetés : toute dimension, mesure, canal ou événement peut être appliqué aux modèles (par exemple, la recherche interne), et pas seulement aux campagnes marketing.
* Utiliser la comparaison de modèles d’attribution illimitée : comparez dynamiquement autant de modèles que vous le souhaitez.
* Évitez les modifications d’implémentation : grâce au traitement de la période de rapport et aux sessions contextuelles, le contexte du parcours client peut être intégré et appliqué au moment de l’exécution.
* construire la session qui correspond le mieux à votre scénario d’attribution ;
* Ventilez l’attribution par filtres : comparez facilement les performances de vos canaux marketing sur n’importe quel filtre important (par exemple, les nouveaux clients par rapport aux clients réguliers, le produit X par rapport au produit Y, le niveau de fidélité ou la valeur vie client (CLV)).
* inspecter le croisement des canaux et l’analyse multi-touch : utilisation des histogrammes et diagrammes de Venn ainsi que des résultats de l’attribution des tendances ;
* analyser visuellement des séquences marketing importantes : explorez les chemins d’accès qui ont mené à la conversion sur le plan visuel par le biais de visualisations à plusieurs nœuds de flux et d’abandons ;
* créer des mesures calculées : utilisez n’importe quel nombre de méthodes d’attribution.

## Utilisation

Pour utiliser un panneau **[!UICONTROL Attribution]** :

1. Créez un panneau **[!UICONTROL Attribution]**. Pour plus d’informations sur la création d’un panneau, consultez [Créer un panneau](panels.md#create-a-panel).

1. Spécifiez l’[entrée](#panel-input) du panneau.

1. Observez la [sortie](#panel-output) du panneau.

### Entrée du panneau

Vous pouvez configurer le panneau Attribution à l’aide des paramètres d’entrée suivants :

1. Ajoutez une **[!UICONTROL mesure de succès]** et une dimension du **[!UICONTROL canal]** à laquelle vous souhaitez affecter des attributs. Par exemple, les canaux marketing ou les dimensions personnalisées, telles que les promotions internes.

   ![Fenêtre du panneau Attribution présentant plusieurs dimensions et mesures sélectionnées.](assets/attribution-panel.png)

1. Sélectionnez un ou plusieurs [modèles d’attribution](#attribution-models) parmi **[!UICONTROL Modèles inclus]** et un [intervalle de recherche en amont](#lookback-window) parmi les **[!UICONTROL intervalles de recherche en amont]** que vous souhaitez utiliser à des fins de comparaison.

1. Sélectionnez **[!UICONTROL Créer]** pour créer les visualisations dans le panneau.

### Sortie du panneau

Le panneau **[!UICONTROL Attribution]** renvoie un riche ensemble de données et de visualisations qui comparent l’attribution pour la dimension et la mesure sélectionnées.

![Visualisations du panneau Attribution qui comparent les mesures et dimensions sélectionnées.](assets/attr_panel_vizs.png)

### Visualisations d’attribution

Les visualisations suivantes font partie de la sortie du panneau.

* **Mesure totale** : nombre total de conversions qui se sont produites au cours de la période de création des rapports et qui sont attribuées à la dimension que vous avez sélectionnée.
* **Barres de comparaison d’attribution** : compare visuellement les conversions attribuées à chacun des éléments de dimension de la dimension sélectionnée. Chaque couleur de barre représente un modèle d’attribution distinct.
* **Tableau de comparaison d’attribution** : affiche, sous forme de tableau, les mêmes données que le graphique à barres. La sélection de différentes colonnes ou lignes dans ce tableau permet de filtrer le graphique à barres ainsi que plusieurs autres visualisations du panneau. Ce tableau fonctionne de la même manière que tout autre tableau à structure libre de Workspace. Il vous permet d’ajouter des composants tels que des mesures, des filtres ou des répartitions.
* **Diagramme de chevauchement** : visualisation de Venn présentant les trois principaux éléments de dimension et la fréquence à laquelle ils participent conjointement à une conversion. Par exemple, la taille du chevauchement des bulles indique la fréquence des conversions lorsqu’une personne a été exposée aux deux éléments de dimension. La sélection d’autres lignes dans le tableau à structure libre adjacent met à jour la visualisation pour refléter votre sélection.
* **Détails sur les performances** : visualisation en nuage de points pour comparer visuellement jusqu’à trois modèles d’attribution.
* **Performance de tendance** : affiche la tendance des conversions attribuées pour le principal élément de dimension. La sélection d’autres lignes dans le tableau à structure libre adjacent met à jour la visualisation pour refléter votre sélection.
* **Flux** : vous permet de voir avec quels canaux les personnes interagissent le plus souvent lors de leur parcours, et dans quel ordre.

## Modèles d’attribution

{{attribution-models-details}}

## Intervalle de recherche en amont

{{attribution-lookback-window}}

>[!MORELIKETHIS]
>
> [Créer un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
