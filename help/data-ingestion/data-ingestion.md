---
title: Présentation de l’ingestion des données
description: Comprendre les différentes manières d’ingérer des données dans Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 70%

---

# Présentation de l’ingestion des données

Vous disposez de plusieurs options lors de l’ingestion de données dans Customer Journey Analytics. Certaines de ces options supposent que vous voulez déplacer les données Adobe Analytics classiques, d’autres supposent que vous utilisez des données ingérées dans Adobe Experience Platform.

>[!IMPORTANT]
>
>Dans tous les scénarios, les données que vous souhaitez _utiliser_ dans Customer Journey Analytics sont en réalité _ingérées_ dans Adobe Experience Platform.


Consultez l’architecture de Customer Journey Analytics de haut niveau présentée précédemment dans la [Présentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr) :

![Architecture du Customer Journey Analytics décrite dans cette section](./assets/cja-architecture.png)

Le jeu de données dans l’architecture ci-dessus peut provenir de diverses sources :

- Données par lot

- Données de flux

- Données provenant d’un déploiement d’Adobe Analytics actuel

- données issues du suivi de votre site web/application mobile à l’aide du SDK Web/mobile Adobe Experience Platform,

- données issues du suivi d’une application de bureau, d’un jeu de console, d’un décodeur ou d’un périphérique IoT à l’aide de l’API Adobe Experience Platform Edge Network Server, ou

- Données provenant d’un fournisseur de données tiers pour lequel Adobe fournit un connecteur source

De plus, il est possible de disposer de plusieurs de ces jeux de données.

Cette section de la documentation fournit des guides de démarrage rapide pour divers scénarios.

## Ingérer et utiliser des données à partir d’Adobe Analytics classique

Adobe Analytics est déjà déployé et vous souhaitez ingérer ces données dans Adobe Experience Platform, les utiliser, les combiner et les analyser avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Consultez [Ingérer et utiliser des données à partir d’Adobe Analytics classique](./analytics.md) pour plus d’informations.


## Ingérer et utiliser des données via le réseau Edge

### Utilisation du SDK Web de Adobe Experience Platform

Vous souhaitez analyser votre site web à l’aide de la technologie d’Adobe, éventuellement migrer à partir d’une autre solution ou commencer à suivre le comportement de votre personne. Vous souhaitez suivre les bonnes pratiques d’Adobe en matière d’implémentation, qui consistent à utiliser les SDK Adobe Experience Platform et le réseau Edge, pour ingérer les données. Vous pouvez ensuite utiliser, combiner et analyser les données ingérées avec les données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Voir [Ingérer et utiliser des données via le SDK Web de Adobe Experience Platform](./aepwebsdk.md) pour plus d’informations.

### Utilisation du SDK Mobile Adobe Experience Platform

Vous souhaitez analyser votre application mobile à l’aide de la technologie d’Adobe, en effectuant potentiellement la migration à partir d’une autre solution ou en commençant à suivre de A à Z le comportement d’une personne dans l’application. Vous souhaitez suivre les bonnes pratiques d’Adobe en matière d’implémentation, qui consistent à utiliser les SDK Adobe Experience Platform et le réseau Edge, pour ingérer les données. Vous pouvez ensuite utiliser, combiner et analyser les données ingérées avec les données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Voir [Ingestion et utilisation de données via le SDK Adobe Experience Platform Mobile](./aepmobilesdk.md) pour plus d’informations.

### Utilisation de l’API Adobe Experience Platform Edge Network Server

Vous souhaitez analyser votre application de bureau, le jeu tel qu’il est joué sur une console de jeu, l’utilisation d’une application de diffusion vidéo en continu sur un décodeur ou votre appareil IoT avec technologie d’Adobe. Migration potentielle à partir d’une autre solution ou commencez à suivre de A à Z le comportement d’une personne sur ces périphériques. Vous souhaitez suivre les bonnes pratiques d’Adobe en matière d’implémentation, qui utilisent les API Adobe Experience Platform Edge Network Server et Edge Network, pour ingérer les données. Vous pouvez ensuite utiliser, combiner et analyser les données ingérées avec les données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Voir [Ingestion et utilisation de données via l’API Adobe Experience Platform Edge Network Server](./serverapi.md) pour plus d’informations.

## Ingérer et utiliser les données par lot

Vous disposez des données par lot appropriées qui fournissent des détails pouvant vous aider à mieux comprendre le comportement des clients et à analyser les interactions des clients. Les fichiers plats au format CSV, JSON ou Parquet d’un système CRM, d’une application de fidélité ou d’une autre solution pour laquelle Adobe ne fournit pas actuellement de connecteur source sont des exemples de ces données par lot. L’ingestion de ces données par lot dans Adobe Experience Platform vous permet de les utiliser, de les combiner et de les analyser avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Consultez [Ingérer et utiliser les données par lot](./batch.md) pour plus d’informations.

## Ingérer et utiliser des données de flux

Vous disposez d’une source de données appropriée, telle qu’un système CRM, un système ERP ou toute autre source, qui fournit des détails pouvant vous aider à mieux comprendre le comportement des clients et à analyser les interactions des clients. Cette source de données peut communiquer via HTTP ou une infrastructure cloud public de diffusion en continu, mais pour laquelle Adobe ne fournit pas actuellement de connecteur source. L’ingestion de ces données de flux dans Adobe Experience Platform en temps réel vous permet de les utiliser, de les combiner et de les analyser avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Consultez [Ingérer et utiliser des données de flux](./streaming.md) pour plus d’informations.

## Ingérer et utiliser des données à l’aide des connecteurs source

Vous disposez de données provenant d’une source prise en charge par un connecteur source. Les connecteurs source sont des configurations qui vous permettent d’ingérer des données à partir d’une application Adobe, d’une application propriétaire ou d’une application tierce dans Adobe Experience Platform. Consultez [Présentation des connecteurs source](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=fr) pour obtenir une vue d’ensemble des connecteurs source disponibles. Grâce au connecteur source, vous pouvez facilement ingérer des données de la source dans Adobe Experience Platform, puis les utiliser, les combiner et les analyser avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Consultez [Ingérer et utiliser des données à l’aide des connecteurs source](./sources.md) pour plus d’informations.
