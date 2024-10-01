---
title: Panneau d’attribution
description: Utilisation et interprétation du panneau d’attribution dans Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 40%

---

# Panneau d’attribution {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_attribution_button"
>title="Attribution"
>abstract="Comparer et visualiser rapidement de nombreux modèles d’attribution en utilisant n’importe quelle dimension ou mesure de conversion"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panneau Attribution IQ"

>[!CONTEXTUALHELP]
>id="cja_workspace_attribution_panel"
>title="Panneau d’attribution"
>abstract="Comparez et visualisez rapidement de nombreux modèles d’attribution en utilisant n’importe quelle dimension ou mesure de conversion.<br/><br/>**Paramètres **<br/>**Canal**<br/> Dimension à attribuer. Il peut s’agir de canaux marketing, de campagnes ou de toute autre dimension.<br/>**Modèles**<br/> Le modèle détermine la manière dont le crédit est attribué aux points de contact.<br/>**Intervalle de recherche en amont**<br/> Ce paramètre détermine la fenêtre d’attribution de données qui s’applique à chaque conversion."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panneau Attribution IQ"

<!-- markdownlint-enable MD034 -->


Le panneau **[!UICONTROL Attribution]** vous permet de créer facilement une analyse comparant différents modèles d’attribution. Le panneau vous fournit un espace de travail dédié pour utiliser et comparer des modèles d’attribution.

Customer Journey Analytics améliore l’attribution en vous permettant de :

* Définir l’attribution au-delà des médias payants : n’importe quelle dimension, mesure, canal ou événement peut être appliquée aux modèles (par exemple, la recherche interne), et pas seulement aux campagnes marketing.
* Utilisez la comparaison illimitée de modèles d’attribution : comparez dynamiquement autant de modèles que vous le souhaitez.
* Éviter les modifications de mise en oeuvre : grâce au traitement de la période de rapport et aux sessions contextuelles, le contexte du parcours client peut être intégré et appliqué au moment de l’exécution.
* construire la session qui correspond le mieux à votre scénario d’attribution ;
* Ventiler l’attribution par filtres : comparez facilement les performances de vos canaux marketing sur n’importe quel filtre important (par exemple, Nouveaux clients par rapport aux clients réguliers, Produit X par rapport au Produit Y, Niveau de fidélité ou CLV).
* inspecter le croisement des canaux et l’analyse multi-touch : utilisation des histogrammes et diagrammes de Venn ainsi que des résultats de l’attribution des tendances ;
* analyser visuellement des séquences marketing importantes : explorez les chemins d’accès qui ont mené à la conversion sur le plan visuel par le biais de visualisations à plusieurs nœuds de flux et d’abandons ;
* créer des mesures calculées : utilisez n’importe quel nombre de méthodes d’attribution.

## Sélectionnez l’option  

Pour utiliser un panneau **[!UICONTROL Attribution]** :

1. Créez un panneau **[!UICONTROL Attribution]**. Pour plus d’informations sur la création d’un panneau, voir [Création d’un panneau](panels.md#create-a-panel).

1. Spécifiez la [entrée](#panel-input) pour le panneau.

1. Observez la [sortie](#panel-output) pour le panneau.

### Entrée de panneau

Vous pouvez configurer le panneau Attribution à l’aide des paramètres d’entrée suivants :

1. Ajoutez une **[!UICONTROL mesure de succès]** et une dimension du **[!UICONTROL canal]** sur lequel vous souhaitez attribuer. Par exemple, les canaux marketing ou les dimensions personnalisées, telles que les promotions internes.

   ![Fenêtre du panneau Attribution présentant plusieurs dimensions et mesures sélectionnées.](assets/attribution-panel.png)

1. Sélectionnez un ou plusieurs [modèles d’attribution](#attribution-models) à partir de **[!UICONTROL modèles inclus]** et un [intervalle de recherche en amont](#lookback-window) à partir de la **[!UICONTROL fenêtre de recherche en amont]** que vous souhaitez utiliser pour la comparaison.

1. Sélectionnez **[!UICONTROL Créer]** pour créer les visualisations dans le panneau.

### Sortie de panneau

Le panneau **[!UICONTROL Attribution]** renvoie un vaste ensemble de données et de visualisations qui comparent l’attribution pour la dimension et la mesure sélectionnées.

![Visualisations du panneau Attribution qui comparent les mesures et dimensions sélectionnées.](assets/attr_panel_vizs.png)

### Visualisations d’attribution

Les visualisations suivantes font partie de la sortie du panneau.

* **Mesure totale** : nombre total de conversions survenues au cours de la période du rapport et qui sont attribuées à la dimension que vous avez sélectionnée.
* **Barres de comparaison d’attribution** : compare visuellement les conversions attribuées à chacun des éléments de dimension de la dimension sélectionnée. Chaque couleur de barre représente un modèle d’attribution distinct.
* **Tableau de comparaison d’attribution** : affiche, sous forme de tableau, les mêmes données que le graphique à barres. La sélection de différentes colonnes ou lignes dans ce tableau permet de filtrer le graphique à barres ainsi que plusieurs autres visualisations du panneau. Ce tableau fonctionne de la même manière que tout autre tableau à structure libre de Workspace. Il vous permet d’ajouter des composants tels que des mesures, des filtres ou des ventilations.
* **Diagramme de chevauchement** : visualisation de Venn présentant les trois principaux éléments de dimension et la fréquence à laquelle ils participent conjointement à une conversion. Par exemple, la taille du chevauchement des bulles indique la fréquence des conversions lorsqu’une personne a été exposée aux deux éléments de dimension. La sélection d’autres lignes dans le tableau à structure libre adjacent met à jour la visualisation pour refléter votre sélection.
* **Détails sur les performances** : visualisation de dispersion permettant de comparer visuellement jusqu’à trois modèles d’attribution.
* **Performance de tendance** : affiche la tendance des conversions attribuées pour le principal élément de dimension. La sélection d’autres lignes dans le tableau à structure libre adjacent met à jour la visualisation pour refléter votre sélection.
* **Flux** : vous permet de voir avec quels canaux les visiteurs interagissent le plus souvent, et dans quel ordre sur le parcours d’une personne.

## Modèles d’attribution

{{attribution-models-details}}

## Intervalle de recherche en amont

{{attribution-lookback-window}}

>[!MORELIKETHIS]
>
> [Créer un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
