---
description: Découvrez comment utiliser la visualisation des abandons dans Analysis Workspace.
title: Présentation des abandons
feature: Visualizations
exl-id: c4338821-64ac-4345-828a-15af18a95ea6
role: User
autotag-review: '2026-05-19T08:41:54.033Z'
TQID: 'https://experienceleague.adobe.com/sitlejANJcDN2u-baGg2iz2SaOyZJe8jbyXjgBbasss'
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
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 87%
---
# Abandon - Aperçu {#fallout-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_fallout_button"
>title="Abandons"
>abstract="Crée une visualisation pour voir comment les personnes accèdent avec succès aux points de contrôle souhaités."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Cet article présente la visualisation des abandons dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Voir [Abandon](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow) pour la version_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** de cet article._

>[!ENDSHADEBOX]

Une visualisation ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Abandons]** indique où les personnes sont sorties (ont abandonné) une séquence prédéfinie de pages et où ils ont poursuivi leur visite à travers ces pages (diminution).


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Créer un rapport de visualisation Abandons](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/fallout-visualization){target="_blank"} pour une vidéo de démonstration.

{{videoaa}}

>[!ENDSHADEBOX]


Les visualisations d’abandon vous permettent d’effectuer les opérations suivantes :

* Comparer en vis-à-vis deux segments du même rapport
* Glisser-déposer (et réorganiser) les étapes du funnel (points de contact).
* Combinez et associez des valeurs issues de différentes dimensions et mesures.
* Créer un rapport sur les abandons multidimensionnel.
* Déterminez où se rendent les clientes et clients immédiatement après un abandon.

La visualisation Abandons présente les taux de conversion et d’abandon entre chaque étape ou point de contact d’une séquence.

Vous pouvez, par exemple, effectuer le suivi des points d’abandon d’une personne au cours d’un processus d’achat. Il vous suffit de sélectionner un point de contact de départ et un autre de conclusion, puis d’ajouter des points de contact intermédiaires afin de créer un chemin de navigation sur le site web. Vous pouvez également effectuer un suivi sur les abandons multidimensionnels.

## Choisir entre les visualisations Abandon, Flux et Canevas de parcours

La visualisation Abandons présente des similitudes avec la [visualisation Flux](/help/analysis-workspace/visualizations/c-flow/flow.md) et la [visualisation Zone de travail de parcours &#x200B;](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).

### Comprendre les différences

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Quand utiliser la visualisation Abandon

Les visualisations Abandons et [Zone de travail de parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) sont utiles pour analyser les éléments suivants :

* Taux de conversion par le biais de processus particuliers sur votre site (tels qu’un processus d’achat ou d’enregistrement).
* Flux de trafic généraux et de portée plus large : de toutes les personnes qui ont visité la page d’accueil, ce flux indique le nombre de personnes qui ont effectué une recherche. Et ensuite combien d’entre elles ont finalement regardé un article spécifique.
* Corrélations entre les événements de votre site. Les corrélations indiquent le pourcentage de personnes qui, après avoir consulté votre politique de confidentialité, ont acheté un produit.

Les visualisations Abandon sont particulièrement adaptées aux éléments suivants :

* L’analyse des abandons portant sur des parcours comportant une séquence prédéfinie de pages, avec un point d’entrée et un chemin uniques. (Utilisez le canevas de parcours pour les parcours comportant plusieurs points d’entrée et chemins.)

* Parcours pour lesquels vous devez effectuer une comparaison en vis-à-vis de deux segments différents du même rapport.

Utilisez [le tableau ci-dessus](#understand-the-differences) pour comprendre les différences entre les visualisations Zone de travail de parcours, Abandons et Flux.

>[!MORELIKETHIS]
>
>[Configuration d’une visualisation d’abandon](configuring-fallout.md)



