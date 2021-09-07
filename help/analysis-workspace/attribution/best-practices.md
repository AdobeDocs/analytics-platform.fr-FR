---
title: Bonnes pratiques d’attribution
description: Quelles sont les bonnes pratiques permettant de choisir un modèle d’attribution ?
source-git-commit: 0e0d77425edeceb3ede6d2d7ca81846b30179607
workflow-type: ht
source-wordcount: '393'
ht-degree: 100%

---


# Bonnes pratiques d’attribution

Le choix du modèle d’attribution approprié pour votre organisation dépend de plusieurs considérations. Cet article explore une méthodologie ainsi que quelques bonnes pratiques générales.

## Étape 1 : Analyse exploratoire

>[!NOTE]
>Cette analyse doit avoir lieu avant que vous ne choisissiez un modèle d’attribution.

Cette phase consiste initialement à comprendre le comportement des clients et à définir des mesures de conversion. En fonction des mesures de conversion, des outils tels qu’Analysis Workspace et l’extraction de sources de données à partir de plusieurs canaux (comme les données d’impression) peuvent faciliter votre compréhension des éléments suivants :

* Combien de clients touchent différents canaux marketing avant la conversion ?
* La proportion/distribution de ces comportements.

Par exemple, si 50 % des clients touchent 3 canaux avant la conversion, y a-t-il une interaction entre ces 3 canaux ?
Vous pouvez ensuite effectuer une analyse des entonnoirs supérieur et inférieur afin d’améliorer votre compréhension.

### Analyse de l’entonnoir supérieur

L’analyse de l’entonnoir supérieur analyse les canaux utilisés pour créer une sensibilisation à la marque ou au produit. Par exemple, la plupart des publicités TV ont pour objectif d’accroître la notoriété de la marque. Vous pouvez utiliser le [modèle d’attribution « Décroissance temporelle »](/help/analysis-workspace/attribution/models.md), car les gens finiront par oublier votre publicité TV au fil du temps.

### Analyse de l’entonnoir inférieur

Dans cette analyse, on suppose que les gens connaissent déjà votre marque et que vous souhaitez que cela entraîne une conversion. Utilisez des e-mails, des notifications Push ou des publicités Facebook.

## Étape 2 : Attribution basée sur les règles

Cette étape a pour but de valider vos hypothèses.

**Exemple 1**

Supposons que votre hypothèse soit « Mon canal Première touche a plus d’impact sur la conversion que mon canal Dernière touche ». Utilisez alors le [modèle d’attribution « En forme de J inversé »](/help/analysis-workspace/attribution/models.md) pour tester cette hypothèse. Ce modèle accorde 60 % du crédit au premier point de contact.

**Exemple 2**

Votre hypothèse peut être la suivante : « Dans notre secteur (par exemple, celui du tourisme), la fenêtre d’attribution est de 60 ou 90 jours et non de 30 jours, car les clients font beaucoup de recherches avant d’acheter un produit ». Remplacez alors l’[intervalle de recherche en amont](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=fr#lookback-windows) par 90 jours.

## Étape 3 : Utiliser l’attribution algorithmique

Étant donné qu’il est très difficile de valider un grand nombre d’hypothèses et de combinaisons possibles, vous pouvez utiliser l’ [attribution algorithmique](/help/analysis-workspace/attribution/algorithmic.md) pour laisser ce travail aux algorithmes intégrés. Si vous avez déjà trouvé le modèle d’attribution idéal, celui qui répond à toutes vos questions et correspond parfaitement à vos besoins, il n’est évidemment pas nécessaire de suivre cette étape.

## Autres considérations

* Il est possible que vous deviez recourir aux services d’un spécialiste des données et non vous reposer uniquement sur Analysis Workspace.
