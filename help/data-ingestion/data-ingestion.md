---
title: Présentation de l’ingestion des données
description: Comprendre les différentes manières d’ingérer des données dans Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: ec56bc657961b2e4e8318ab14cd676288398462f
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 85%

---

# Vue d’ensemble de l’ingestion de données

Plusieurs options s’offrent à vous lors de l’ingestion de données dans Customer Journey Analytics. Certaines de ces options supposent que vous voulez déplacer les données Adobe Analytics classiques, d’autres supposent que vous utilisez des données ingérées dans Adobe Experience Platform.

>[!IMPORTANT]
>
>Dans tous les scénarios, les données que vous souhaitez _utiliser_ dans Customer Journey Analytics sont en réalité _ingérées_ dans Adobe Experience Platform.


L’architecture de haut niveau de Customer Journey Analytics est présentée ici :

![Architecture de Customer Journey Analytics](/help/getting-started/assets/cja-overview.svg)

Cette architecture illustre la manière dont Customer Parcours Analytics vous permet d’effectuer les opérations suivantes :

* Combinez plusieurs jeux de données ![Données](/help/assets/icons/Data.svg) dans une [connexion](/help/connections/overview.md).
* Définissez et configurez des dimensions ![Dimensions](/help/assets/icons/Dimensions.svg) et des mesures ![Événement](/help/assets/icons/Event.svg) dans une [vue de données](/help/data-views/data-views.md) en fonction des champs disponibles à partir des jeux de données que vous avez définis dans votre connexion.
* Créez des rapports ![ViewTable](/help/assets/icons/ViewTable.svg) et des visualisations (ligne ![Ligne](/help/assets/icons/GraphTrend.svg) et zone ![Zone](/help/assets/icons/GraphAreaStacked.svg)) dans les [projets](/help/analysis-workspace/home.md) en fonction des dimensions et des mesures de vos vues de données.

Les jeux de données de l’architecture peuvent provenir de diverses sources :

* Données par lot

* Données de flux

* Données provenant d’un déploiement d’Adobe Analytics actuel

* Données provenant du suivi de votre site web/application mobile à l’aide du SDK Web/mobile Adobe Experience Platform

* Données provenant du suivi d’une application de bureau, d’un jeu de console, d’un décodeur ou d’un appareil IoT à l’aide de l’API Adobe Experience Platform Edge Network Server, ou

* Données provenant d’un fournisseur de données tiers pour lequel Adobe fournit un connecteur source

De plus, il est possible de disposer de plusieurs de ces jeux de données.

Cette section de la documentation fournit des guides de démarrage rapide pour divers scénarios.

## Hiérarchisation et latence de l’ingestion

Vous pouvez désormais ingérer vos données d’événement dans Customer Journey Analytics dans les 90 minutes (SLT), qu’elles aient été créées il y a 24 heures, 48 heures ou 7 jours.

Notez que cette fonctionnalité diffère en fonction du package SKU acheté par votre entreprise :

* Ingestion de priorité de base : données datant de 24 heures dans un traitement SLT de 90 minutes (disponible pour **CJA Foundation** et **CJA Select**).

* Ingestion de priorité intermédiaire : données datant de 72 heures dans un traitement SLT de 90 minutes (disponible pour **CJA Prime**).

* Ingestion de priorité avancée : données datant d’une semaine dans un traitement SLT de 90 minutes (disponible pour **CJA Ultimate**).

## Ingérer et utiliser des données à partir d’Adobe Analytics classique

Adobe Analytics est déjà déployé et vous souhaitez ingérer ces données dans Adobe Experience Platform, les utiliser, les combiner et les analyser avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Consultez [Ingérer et utiliser des données à partir d’Adobe Analytics classique](./analytics.md) pour plus d’informations.


## Ingérer et utiliser des données via Edge Network

### Avec le SDK Web Adobe Experience Platform

Vous souhaitez analyser le site web à l’aide de la technologie Adobe, éventuellement effectuer une migration à partir d’une autre solution ou commencer à suivre le comportement des visiteurs et visiteuses. Vous souhaitez suivre les bonnes pratiques d’Adobe en matière d’implémentation, qui consistent à utiliser les SDK Adobe Experience Platform et le réseau Edge, pour ingérer les données. Vous pouvez ensuite utiliser, combiner et analyser les données ingérées avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Pour plus d’informations, consultez [Ingérer et utiliser des données via le SDK Web Adobe Experience Platform](./aepwebsdk.md).

### Avec le SDK mobile Adobe Experience Platform

Vous souhaitez analyser votre application mobile avec la technologie Adobe, éventuellement effectuer une migration à partir d’une autre solution ou commencer à suivre le comportement des visiteurs et visiteuses dans l’application à partir de zéro. Vous souhaitez suivre les bonnes pratiques d’Adobe en matière d’implémentation, qui consistent à utiliser les SDK Adobe Experience Platform et le réseau Edge, pour ingérer les données. Vous pouvez ensuite utiliser, combiner et analyser les données ingérées avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Pour plus d’informations, consultez [Ingérer et utiliser des données via le SDK mobile Adobe Experience Platform](./aepmobilesdk.md).

### Avec l’API Adobe Experience Platform Edge Network Server

Vous souhaitez analyser votre application de bureau, le jeu joué sur une console de jeu, l’utilisation d’une application de streaming vidéo sur un décodeur ou votre appareil IoT avec la technologie Adobe. Vous souhaitez éventuellement effectuer une migration à partir d’une autre solution ou commencer à suivre le comportement des visiteurs et visiteuses sur ces appareils à partir de zéro. Vous souhaitez suivre les bonnes pratiques d’Adobe en matière d’implémentation, qui consistent à utiliser les API Adobe Experience Platform Edge Network Server et Edge Network, pour ingérer les données. Vous pouvez ensuite utiliser, combiner et analyser les données ingérées avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Pour plus d’informations, consultez [Ingérer et utiliser des données via l’API Adobe Experience Platform Edge Network Server](./serverapi.md).

## Ingérer et utiliser les données par lot

Vous disposez des données par lot appropriées qui fournissent des détails pouvant vous aider à mieux comprendre le comportement des clients et à analyser les interactions des clients. Les fichiers plats au format CSV, JSON ou Parquet d’un système CRM, d’une application de fidélité ou d’une autre solution pour laquelle Adobe ne fournit pas actuellement de connecteur source sont des exemples de ces données par lot. L’ingestion de ces données par lot dans Adobe Experience Platform vous permet de les utiliser, de les combiner et de les analyser avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Consultez [Ingérer et utiliser les données par lot](./batch.md) pour plus d’informations.

## Ingérer et utiliser des données de flux

Vous disposez d’une source de données appropriée, telle qu’un système CRM, un système ERP ou toute autre source, qui fournit des détails pouvant vous aider à mieux comprendre le comportement des clients et à analyser les interactions des clients. Cette source de données peut communiquer via HTTP ou une infrastructure cloud public de diffusion en continu, mais pour laquelle Adobe ne fournit pas actuellement de connecteur source. L’ingestion de ces données de flux dans Adobe Experience Platform en temps réel vous permet de les utiliser, de les combiner et de les analyser avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Consultez [Ingérer et utiliser des données de flux](./streaming.md) pour plus d’informations.

## Ingérer et utiliser des données à l’aide des connecteurs source

Vous disposez de données provenant d’une source prise en charge par un connecteur source. Les connecteurs source sont des configurations qui vous permettent d’ingérer des données à partir d’une application Adobe, d’une application propriétaire ou d’une application tierce dans Adobe Experience Platform. Consultez [Présentation des connecteurs source](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=fr) pour obtenir une vue d’ensemble des connecteurs source disponibles. Grâce au connecteur source, vous pouvez facilement ingérer des données de la source dans Adobe Experience Platform, puis les utiliser, les combiner et les analyser avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Consultez [Ingérer et utiliser des données à l’aide des connecteurs source](./sources.md) pour plus d’informations.

## Ingérer et utiliser des données ad hoc

Vous disposez de données ad hoc qui ne nécessitent qu’un seul jeu de données dans Experience Platform et ne nécessitent pas la configuration d’un schéma de modèle de données d’expérience (XDM). Ce scénario est appelé schéma ad hoc. Les schémas ad hoc sont utilisés dans divers workflows d’ingestion de données pour Experience Platform, notamment dans l’ingestion de fichiers CSV et dans la création de certains types de connexions sources.

Voir [ Ingérer et utiliser des données ad hoc](./adhoc.md)

>[!MORELIKETHIS]
>
>Blog : [en savoir plus sur le traitement et l’ingestion des données dans Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-closer-look-at-data-processing-amp-ingestion-in-adobe-customer/ba-p/665091)

