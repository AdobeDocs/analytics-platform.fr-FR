---
title: Bonnes pratiques d’attribution
description: Découvrez les bonnes pratiques pour décider du modèle d’attribution à utiliser.
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: 1b6e1d432bfe4b0574b8ee68bcfa940941f3c36f
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 66%

---

# Bonnes pratiques en matière dʼattribution

Le choix du modèle dʼattribution approprié pour votre organisation dépend de plusieurs critères. Cet article explore une méthodologie ainsi que quelques bonnes pratiques générales :

* [Analyse exploratoire](#exploratory-analysis)
* [Attributions basées sur des règles](#rule-base-attribution)
* [Utiliser l’attribution algorithmique](#use-algorithmic-attribution)

## Analyse exploratoire

>[!NOTE]
>Cette analyse doit avoir lieu avant de choisir un modèle dʼattribution.

Cette phase consiste dʼabord à comprendre le comportement des clients et à définir des mesures de conversion. Selon les mesures de conversion, des outils tels que les [Flux de données](https://experienceleague.adobe.com/fr/docs/analytics/export/analytics-data-feed/data-feed-overview) (pour les données brutes) ou Analysis Workspace facilitent votre compréhension des questions suivantes :

* Le nombre de clientes et clients qui touchent différents canaux marketing avant la conversion.
* La proportion ou répartition de ces comportements.

Par exemple, si 50 % des clients empruntent 3 canaux avant la conversion, y a-t-il une interaction entre ces 3 canaux ?
Vous pouvez ensuite effectuer une analyse des entonnoirs supérieur et inférieur afin dʼaméliorer votre compréhension.

### Analyse de lʼentonnoir supérieur

Les analyses en entonnoir supérieur étudient les canaux utilisés pour faire connaître la marque ou le produit. Par exemple, lʼobjectif de la plupart des publicités télévisées est de faire connaître la marque. Vous pouvez utiliser le modèle d’attribution [&#x200B; Décroissance temporelle &#x200B;](/help/analysis-workspace/attribution/models.md), car les gens finiront par oublier votre publicité TV au fil du temps.

### Analyse de lʼentonnoir inférieur

Dans l’analyse en entonnoir inférieur, le postulat est que les personnes connaissent déjà votre marque et que vous souhaitez qu’elles effectuent une conversion. Utilisez des e-mails, des notifications push ou des annonces Facebook.

## Attribution basée sur des règles

Cette étape a pour but de valider vos hypothèses.

**Exemple 1**

Supposons que votre hypothèse soit la suivante : « *Mon canal Première touche a plus d’impact sur la conversion que mon canal Dernière touche.* »

Dans ce cas, vous utiliserez alors le [modèle d’attribution en forme de J inversé](/help/analysis-workspace/attribution/models.md) pour tester cette hypothèse. Ce modèle accorde 60 % du crédit au premier point de contact.

**Exemple 2**

Supposons que votre hypothèse soit la suivante : *« Dans un secteur spécifique (comme l’industrie du voyage), la fenêtre d’attribution est de 60 ou 90 jours, et non de 30 jours, car les clients font beaucoup de recherches avant d’acheter un produit* ».

Dans ce cas, vous pouvez modifier votre [intervalle de recherche en amont](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/models) à 90 jours.

## Utiliser l’attribution algorithmique

Si vous ne disposez pas encore d’un modèle d’attribution qui fournit des réponses satisfaisantes à toutes vos questions, vous pouvez utiliser l’[attribution algorithmique](/help/analysis-workspace/attribution/algorithmic.md). Comme il est très difficile de valider un grand nombre d’hypothèses et de combinaisons possibles, l’attribution algorithmique utilise des algorithmes intégrés pour répartir le crédit entre les éléments de dimension.

## Autres considérations

* Il se peut que vous deviez faire appel aux services dʼun spécialiste des données au lieu de vous fier uniquement à Analysis Workspace.
* Vous pouvez vous fier aux données brutes, comme dans les flux de données Adobe.
* Pensez à utiliser [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview), par exemple, si vous souhaitez tenir compte des données de vos impressions.
