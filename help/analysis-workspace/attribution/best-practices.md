---
title: Bonnes pratiques d’attribution
description: Quelles sont les bonnes pratiques pour décider d’un modèle d’attribution ?
source-git-commit: 3839639858edbd019ef467ca5fb1791f48864100
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 2%

---


# Bonnes pratiques d’attribution

Le choix du modèle d’attribution approprié pour votre organisation dépend de plusieurs considérations. Le présent article explore une méthodologie et quelques bonnes pratiques générales.

## Étape 1 : Analyse exploratoire

>[!NOTE]
>Cette analyse doit avoir lieu avant de choisir un modèle d’attribution.

Cette phase consiste initialement à comprendre le comportement des clients et à définir des mesures de conversion. Sur la base des mesures de conversion, des outils tels que [Flux de données](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) (pour les données brutes) ou Analysis Workspace facilitent votre compréhension des

* Combien de clients touchent différents canaux marketing avant la conversion ?
* La proportion/distribution de ces comportements.

Par exemple, si 50 % des clients touchent 3 canaux avant la conversion, y a-t-il une interaction entre ces 3 canaux ?
Vous pouvez ensuite effectuer une analyse des entonnoirs supérieur et inférieur afin d’améliorer votre compréhension.

### Analyse de l’entonnoir supérieur

L’analyse de l’entonnoir supérieur analyse les canaux utilisés pour créer une notoriété de la marque ou du produit. Par exemple, l’objectif de la plupart des publicités télévisées est la sensibilisation à la marque. Vous pouvez utiliser le modèle d’attribution [ &quot;Décroissance temporelle&quot;](/help/analysis-workspace/attribution/models.md), car les visiteurs oublieront votre publicité télévisée au fil du temps.

### Analyse de l’entonnoir inférieur

Dans cette analyse, on suppose que les gens connaissent déjà votre marque et que vous voulez qu’elle soit convertie. Utilisez des notifications par e-mail ou push ou des publicités Facebook.

## Étape 2 : Attribution d’après les règles

Cette étape a pour but de valider vos hypothèses.

**Exemple 1**

Supposons que votre hypothèse soit &quot;Mon canal Première touche a plus d’impact sur la conversion que mon canal Dernière touche. Vous utiliserez ensuite le modèle d’attribution [ &quot;En forme de J inversé&quot;](/help/analysis-workspace/attribution/models.md) pour tester cette hypothèse. Ce modèle accorde 60 % du crédit au point de première touche.

**Exemple 2**

Votre hypothèse peut être la suivante : &quot;Dans notre secteur (tel que celui des voyages), la période d’attribution est de 60 ou 90 jours, et non de 30 jours, car les clients font beaucoup de recherches avant d’acheter un produit. Vous remplacerez ensuite la [période de recherche arrière](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#lookback-windows) par 90 jours.

## Étape 3 : Utilisation de l’attribution algorithmique

Comme il est très difficile de valider un grand nombre d’hypothèses et de combinaisons possibles, vous pouvez utiliser [l’attribution algorithmique](/help/analysis-workspace/attribution/algorithmic.md) pour laisser ce travail aux algorithmes intégrés. Si vous avez déjà trouvé le modèle d’attribution parfait qui répond à toutes vos questions et est idéal, alors vous n’avez évidemment pas besoin de passer à cette étape.

## Autres considérations

* Vous devrez peut-être utiliser les services d’un spécialiste des données au lieu de vous fier uniquement à Analysis Workspace.
* Vous pouvez vous fier aux données brutes, comme dans les flux de données Adobe.
* Pensez à utiliser [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr), par exemple, si vous souhaitez prendre en compte vos données Impressions.

