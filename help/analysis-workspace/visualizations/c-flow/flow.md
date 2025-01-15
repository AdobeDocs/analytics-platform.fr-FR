---
description: Découvrez la fonctionnalité Flux qui présente les parcours des clients sur vos sites web et dans vos applications.
title: Flux - Aperçu
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: bf5853a1d23d6e648024016a64dc67d09da3fbb4
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 50%

---

# Flux {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="Flux"
>abstract="Créez une visualisation pour afficher le flux de personnes d’un point de contrôle à un autre."

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="Flux"
>abstract="Analysez le flux des visites ou des visiteurs et visiteuses d’un point de contact à l’autre.<br/><br/>**Paramètres **<br/>**Commence par** : ajoutez une dimension, un élément de dimension ou une mesure pour afficher les principaux points de contact après l’occurrence du composant sélectionné.<br/>**Contient** : ajoutez une dimension ou un élément de dimension pour afficher les principaux points de contact avant et après l’occurrence du composant sélectionné.<br/>**Se termine par** : ajoutez une dimension, un élément de dimension ou une mesure pour afficher les principaux points de contact avant l’occurrence du composant sélectionné.<br/>**Dimension de cheminement** : ajoutez une dimension à utiliser comme chemin d’accès ou de sortie du composant sélectionné."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*Cet article présente la visualisation Flux dans le Customer Journey Analytics ****.<br/>Voir [Flux](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow) pour la version **Adobe Analytics**de cet article.*

>[!ENDSHADEBOX]


La visualisation ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flow]** présente les parcours des clients sur vos sites web et vos applications.

Avec la visualisation, vous pouvez :

* Visualisez le parcours client sur votre site web ou votre application.
* Analysez où les clients se rendent avant et après les points de contrôle spécifiés, tels qu’une entrée, une dimension spécifique ou une sortie.
* Créer des filtres en désignant un point spécifique dans un parcours donné

+++ Regardez une vidéo de démonstration de la visualisation Flux .

>[!VIDEO](https://video.tv.adobe.com/v/346063/?quality=12)

{{videoaa}}

+++

## Flux interdimensionnels

Vous pouvez afficher le [flux entre plusieurs dimensions](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md). Vous pouvez, par exemple, combiner dans un seul diagramme des pages et des services ou rayons. Dans ce cas, votre flux peut aller de la page d’accueil à la page Hommes, puis au rayon Chaussures.

Chaque colonne peut présenter une dimension distincte. Faites glisser une dimension et ajoutez-la au diagramme en la déposant dans une zone de dépôt.

>[!MORELIKETHIS]
>
>[Configurer une visualisation de flux](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
>

## Choisissez entre les visualisations de la zone de travail Flux, Abandons ou Parcours .

La visualisation Flux présente des similitudes avec la visualisation [Abandons](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) et la visualisation de la zone de travail de Parcours [](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md), mais avec des différences importantes.

### Comprendre les différences

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Quand utiliser le flux

Les visualisations de flux sont particulièrement adaptées aux éléments suivants :

* Analyse exploratoire et ad hoc pour le prochain point de contact immédiat sur le chemin. (Utilisez la zone de travail des Parcours pour les parcours avec une séquence prédéfinie de pages ou ceux qui utilisent un chemin d’accès éventuel.)

* Parcours non linéaires avec plusieurs points d’entrée et tracés. (Utilisez la zone de travail des Parcours pour les parcours avec une séquence prédéfinie de pages.)

Utilisez [le tableau ci-dessus](#understand-the-differences) pour comprendre les différences entre la zone de travail Flux, Abandon et Parcours.
