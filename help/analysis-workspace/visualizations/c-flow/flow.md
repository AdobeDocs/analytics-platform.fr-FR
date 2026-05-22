---
description: Découvrez comment utiliser la visualisation des flux dans Analysis Workspace.
title: Flux - Aperçu
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
autotag-review: '2026-05-19T08:39:33.544Z'
TQID: 'https://experienceleague.adobe.com/X0VLZhluDR9Q-ax7TcTOHEcn4r0V5yu64spZlfc4fwU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 349
ht-degree: 86%

---

# Flux - Aperçu {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="Flux"
>abstract="Créez une visualisation pour afficher le flux de personnes d’un point de contrôle à un autre."

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="Flux"
>abstract="Analysez le flux des visites ou des visiteurs et visiteuses d’un point de contact à l’autre. Spécifiez un composant (mesure, dimension ou élément) par lequel commencer et terminer. Vous pouvez éventuellement définir des paramètres avancés pour configurer plus en détail la visualisation."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Cet article présente la visualisation de flux dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Voir [Flux](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow) pour la version_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de cet article._

>[!ENDSHADEBOX]


La visualisation ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flux]** présente les parcours des clientes et clients sur vos sites web et dans vos applications.

Avec cette visualisation, vous pouvez réaliser les actions suivantes :

* Visualisez le parcours des clientes e t clients dans votre site web ou votre application.
* Analysez où se rendent les clientes et clients avant et après les points de contrôle spécifiés, tels qu’une entrée, une dimension spécifique ou une sortie.
* Créez des segments en désignant un point spécifique dans un chemin donné.


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Créer une visualisation Flux](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization){target="_blank"} pour une vidéo de démonstration.

{{videoaa}}

>[!ENDSHADEBOX]


## Flux interdimensionnels

Vous pouvez afficher le [flux entre plusieurs dimensions](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md). Vous pouvez, par exemple, combiner dans un seul diagramme des pages et des services ou rayons. Dans ce cas, votre flux peut aller de la page d’accueil à la page Hommes, puis au rayon Chaussures.

Chaque colonne peut présenter une dimension distincte. Faites glisser une dimension et ajoutez-la au diagramme en la déposant dans une zone de dépôt.

>[!MORELIKETHIS]
>
>[Configurez une visualisation Flux](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
>

## Choisissez entre les visualisations Flux, Abandons ou Zone de travail de parcours.

La visualisation Flux présente des similitudes avec la [visualisation Abandons](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) et la [visualisation Zone de travail de parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md), mais comporte des différences importantes.

### Comprendre les différences

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Quand utiliser la visualisation Flux

Les visualisations Flux sont particulièrement adaptées aux éléments suivants :

* Analyse exploratoire et ad hoc pour le prochain point de contact immédiat sur le chemin. (Utilisez la zone de travail de parcours pour les parcours avec une séquence prédéfinie de pages ou ceux qui utilisent un chemin d’accès définitif.)

* Parcours non linéaires avec plusieurs points d’entrée et chemins. (Utilisez la zone de travail de parcours pour les parcours avec une séquence prédéfinie de pages.)

Utilisez [le tableau ci-dessus](#understand-the-differences) pour comprendre les différences entre les visualisations Flux, Abandons et Zone de travail de parcours.
