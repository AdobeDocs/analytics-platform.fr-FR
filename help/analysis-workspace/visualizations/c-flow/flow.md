---
description: Découvrez la fonction Flux qui présente les parcours des clients sur vos sites web et dans vos applications.
title: Flux - Aperçu
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: 3abe8fd0e43d9ab8810e7166cbdb463bc9244223
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 53%

---

# Flux {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_flow_button"
>title="Flux"
>abstract="Créez une visualisation pour afficher le flux de personnes d’un point de contrôle à un autre."

>[!CONTEXTUALHELP]
>id="cja_workspace_flow_panel"
>title="Flux"
>abstract="Analysez le flux des visites ou des visiteurs et visiteuses d’un point de contact à l’autre.<br/><br/>**Paramètres **<br/>**Commence par** : ajoutez une dimension, un élément de dimension ou une mesure pour afficher les principaux points de contact après l’occurrence du composant sélectionné.<br/>**Contient** : ajoutez une dimension ou un élément de dimension pour afficher les principaux points de contact avant et après l’occurrence du composant sélectionné.<br/>**Se termine par** : ajoutez une dimension, un élément de dimension ou une mesure pour afficher les principaux points de contact avant l’occurrence du composant sélectionné.<br/>**Dimension de cheminement** : ajoutez une dimension à utiliser comme chemin d’accès ou de sortie du composant sélectionné."

<!-- markdownlint-enable MD034 -->



La visualisation ![GraphPath](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flux]** affiche les chemins des clients sur vos sites web et dans vos applications.

Avec la visualisation, vous pouvez :

* Visualisez le parcours client sur votre site web ou dans votre application.
* Analysez où se rendent les clients avant et après les points de contrôle spécifiés, tels qu’une entrée, une dimension spécifique ou une sortie.
* Créer des filtres en désignant un point spécifique dans un parcours donné

+++ Affichez une démonstration vidéo de la visualisation Flux.

>[!VIDEO](https://video.tv.adobe.com/v/346063/?quality=12)

{{videoaa}}

+++

## Flux interdimensionnels

Vous pouvez afficher le [flux entre plusieurs dimensions](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md). Vous pouvez, par exemple, combiner dans un seul diagramme des pages et des services ou rayons. Dans ce cas, votre flux peut aller de la page d’accueil à la page Hommes, puis au rayon Chaussures.

Chaque colonne peut présenter une dimension distincte. Faites glisser une dimension et ajoutez-la au diagramme en la déposant dans une zone de dépôt.

>[!MORELIKETHIS]
>
>[Configurez une visualisation de flux](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
>

## Visualisations Flux, Abandons ou Zone de travail de Parcours

La visualisation Flux présente des similitudes avec la [visualisation Abandons](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) et la [ visualisation Canevas de Parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md), mais présente des différences importantes.

### Comprendre les différences

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Quand utiliser le flux

Les visualisations du flux sont mieux adaptées aux éléments suivants :

* Analyses exploratoires ad hoc pour le prochain point de contact immédiat sur le chemin. (Utilisez le canevas de Parcours pour les parcours avec une séquence de pages prédéfinie ou ceux qui utilisent un chemin éventuel.)

* Parcours non linéaires avec plusieurs points d’entrée et chemins. (Utilisez un canevas de Parcours pour les parcours avec une séquence de pages prédéfinie.)

Utilisez [le tableau ci-dessus](#understand-the-differences) pour comprendre les différences entre le flux, les abandons et le canevas de Parcours.
