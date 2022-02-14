---
title: Migration d’Adobe Analytics vers Customer Journey Analytics
description: Étapes de migration d’Adobe Analytics vers Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 2a330a430b48eb753d269e1165e95b61cb5fb483
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 6%

---

# Préparation à la migration d’Adobe Analytics vers Customer Journey Analytics

Avant de migrer vos données d’Adobe Analytics vers Customer Journey Analytics, prenez connaissance des points suivants afin de préparer vos données et de prendre conscience des différences critiques entre les deux technologies.

## Préparation de vos données

La préparation de vos données Adobe Analytics pour un passage en Customer Journey Analytics transparent est essentielle à l’intégrité des données et à la cohérence des rapports.

### 1. Collecter les identités

Le composant le plus important pour comprendre un parcours client est peut-être de savoir qui est le client à chaque étape. Pour Customer Journey Analytics, disposer d’un identifiant qui existe sur tous vos canaux et des données correspondantes permet de regrouper plusieurs sources dans CJA.
Il peut s’agir d’un ID de client, d’un ID de compte ou d’un ID de courrier électronique. Quelle que soit l’identité (et il peut y avoir plusieurs), veillez à tenir compte des points suivants pour chaque ID :

* L’ID existe ou peut être ajouté à toutes les sources de données que vous souhaitez importer dans CJA.
* L’identifiant est renseigné sur chaque ligne de données.
* L’ID ne contient pas de PII. Appliquez le hachage à tout ce qui peut être sensible.
* L’ID utilise le même format pour toutes les sources (même longueur, même méthode de hachage, etc.)

Dans des jeux de données tels qu’Adobe Analytics, une identité peut ne pas exister sur chaque ligne de données, mais une identité secondaire le fait. Dans ce cas, l’analyse cross-channel (anciennement appelée &quot;assemblage basé sur les champs&quot;) peut être utilisée pour combler l’écart entre les lignes lorsqu’un client n’est identifié que par son ECID et lorsqu’une identité est collectée (par exemple, lorsqu’un client s’authentifie). [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=fr)

### 2. Aligner les variables

La migration la plus simple des données Adobe Analytics vers Customer Journey Analytics consiste à ingérer une suite de rapports globale dans Experience Platform à l’aide de la variable [Connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr). Ce connecteur mappe directement vos variables Adobe Analytics à un schéma et à un jeu de données XDM dans AEP, qui peuvent à leur tour être facilement connectés à CJA.

Une suite de rapports globale complète peut ne pas toujours être faisable pour une mise en oeuvre. Si vous prévoyez d’importer plusieurs suites de rapports dans Customer Journey Analytics, vous devrez planifier l’alignement des variables entre ces suites de rapports.

Par exemple, l’eVar 1 de la suite de rapports 1 peut pointer vers [!UICONTROL Page]. Dans la suite de rapports 2, l’eVar 1 peut pointer vers [!UICONTROL Campagne interne]. Lorsqu’elles sont introduites dans CJA, ces variables se combinent dans une seule dimension eVar1, ce qui peut entraîner des rapports potentiellement déroutants et inexacts.

Si vous avez évité de passer à une suite de rapports globale en raison de problèmes liés à [!UICONTROL Valeurs uniques dépassées] ou [!UICONTROL Faible trafic], sachez que CJA n’a pas de [limites de cardinalité sur une dimension](/help/components/dimensions/high-cardinality.md). Cela permet à n’importe quelle valeur unique d’apparaître et d’être comptabilisée.

### 3. (Reconfigurer vos canaux marketing)

Les paramètres traditionnels du canal marketing Adobe Analytics ne s’exécutent pas de la même manière dans CJA. C&#39;est pour deux raisons :

* le niveau de traitement des données Adobe Analytics ingérées dans Adobe Experience Platform, et

* La nature du Customer Journey Analytics dans la génération de rapports

Adobe publié [mise à jour des bonnes pratiques relatives à l’implémentation des canaux marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=en). Ces recommandations mises à jour vous aident à tirer le meilleur parti des fonctionnalités déjà présentes dans Adobe Analytics avec Attribution IQ. Ils vous configureront également pour la réussite lors de la transition vers Customer Journey Analytics.

### 4. Choix de l’utilisation du connecteur source Analytics par rapport aux SDK Experience Platform

As [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) la collecte de données évolue. Il est probable que vous migriez vers l’une des [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=en) ou [SDK Adobe Experience Platform Mobile](https://experienceleague.adobe.com/docs/mobile.html?lang=en) avec Adobe Experience Platform Edge Network. Bien qu’une mise en oeuvre standard des SDK envoie des données dans Adobe Analytics, une nouvelle opportunité s’affiche pour envoyer des données directement à Adobe Experience Platform. Il peut ensuite être ingéré dans Customer Journey Analytics, tout en conservant les données envoyées à Adobe Analytics.

Cette méthode développe considérablement les possibilités de collecte de données : Il n’existe plus de limitation du nombre de champs ou de nécessité de mapper des éléments de données à des props, des eVars et des événements tels que dans Analytics. Vous pouvez utiliser un nombre illimité d’éléments de schéma de différents types et les représenter de plusieurs manières à l’aide de CJA. [Vues des données](/help/data-views/data-views.md). La vitesse de disponibilité des données augmente lorsque les données sont envoyées directement à Adobe Experience Platform, car le temps de traitement des données par le biais d’Adobe Analytics est supprimé.

**Avantages de l’utilisation des SDK Experience Platform**

* Schéma flexible pour définir les champs dont vous avez besoin
* Ne pas dépendre de la nomenclature Adobe Analytics (prop, eVar, événement, etc.)
* Aucune limite de caractères pour les variables (100 caractères pour les props)
* Disponibilité plus rapide des données dans Adobe Experience Platform

**Refus d’utilisation des SDK Experience Platform**

Les composants Adobe Analytics suivants ne sont pas pris en charge :

* Canaux marketing
* Filtrage des robots
* Recherche de géo, de domaine et de périphérique
* Analytics for Target (A4T)

## Préparation aux différences critiques

### Comprendre le traitement de la période de rapport

La création de rapports dans Adobe Analytics repose sur une quantité importante de prétraitement des données pour générer des résultats tels que la persistance que vous voyez dans les eVars. Customer Journey Analytics exécute ces calculs au moment de l’exécution du rapport.

Le traitement de la période de rapport permet d’appliquer des paramètres rétroactifs et de créer plusieurs versions de persistance des variables sans avoir à modifier la manière dont les données sous-jacentes sont collectées.

Ce changement se traduira par des différences dans la manière dont les données sont consignées, en particulier pour les variables qui peuvent avoir une longue période d’expiration. Vous pouvez commencer par évaluer la manière dont le traitement de la période de rapport peut avoir un impact sur la création de rapports à l’aide d’une [suite de rapports virtuelle](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html).

### Identification des segments critiques et des mesures calculées

Les segments Adobe Analytics (appelés filtres dans CJA) et les mesures calculées ne sont pas compatibles avec Customer Journey Analytics. Dans de nombreux cas, ces composants peuvent être reconstruits dans CJA à l’aide des nouveaux schémas et des nouvelles données disponibles.

Pour que la transition soit aussi fluide que possible pour les utilisateurs lorsqu’ils passent d’un système à l’autre, prévoyez

1. Identification des composants les plus critiques.

1. documenter leurs définitions, et

1. Identification des champs qui seront requis dans les données pour les répliquer dans CJA en tant que [Filtres](/help/components/filters/filters-overview.md) et [Mesures calculées](/help/components/calc-metrics/calc-metr-overview.md).

Voici quelques vidéos pour vous guider :

* [Déplacement des segments Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=en)

* [Déplacement de vos mesures calculées d’Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en)
