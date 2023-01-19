---
title: Présentation de Data Ingestion
description: Comprendre les différentes manières d’ingérer des données dans Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
source-git-commit: 3331f41590509ef38cb67802335414ca3de5ff94
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 4%

---

# Présentation de Data Ingestion

Plusieurs options s’offrent à vous lors de l’ingestion de données dans Customer Journey Analytics. Certains supposent que vous souhaitez déplacer les données Adobe Analytics traditionnelles, d’autres supposent que vous utilisez des données ingérées dans Adobe Experience Platform.

>[!IMPORTANT]
>
>Dans tous les scénarios, les données que vous souhaitez _use_ en Customer Journey Analytics _ingéré_ dans Adobe Experience Platform.


Voir l’architecture de Customer Journey Analytics de haut niveau présentée dans la section [Présentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr):

![Customer Journey Analytics](./assets/cja-architecture.png)

Le jeu de données dans l’architecture ci-dessus peut provenir de diverses sources :

- données de lot,

- données de diffusion en continu,

- données provenant d’un déploiement Adobe Analytics actuel,

- données issues du suivi de votre site web/application mobile à l’aide du SDK Web/mobile Adobe Experience Platform, ou

- données provenant d’un fournisseur de données tiers pour lequel Adobe fournit un connecteur source.

Et vous pouvez avoir beaucoup de ces jeux de données.

Cette section de la documentation fournit des guides de démarrage rapide pour divers scénarios.

## Ingestion et utilisation de données à partir d’Adobe Analytics traditionnel

Adobe Analytics est déjà déployé et vous souhaitez ingérer ces données dans Adobe Experience Platform et les utiliser, les combiner et les analyser avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Voir [Ingestion et utilisation de données à partir d’Adobe Analytics traditionnel](./analytics.md) pour plus d’informations.

## Ingérer et utiliser des données via le SDK web Adobe Experience Platform et le réseau Edge

Vous souhaitez analyser votre site web à l’aide de la technologie d’Adobe, éventuellement migrer à partir d’une autre solution ou commencer à suivre le comportement de votre visiteur. Vous souhaitez suivre les bonnes pratiques d’Adobe en matière d’implémentation, qui utilisent les SDK Adobe Experience Platform et le réseau Edge, pour ingérer les données. Vous pouvez ensuite utiliser, combiner et analyser les données ingérées avec les données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Voir [Ingérer et utiliser des données via le SDK web Adobe Experience Platform et le réseau Edge](./aepwebsdk.md) pour plus d’informations.

## Ingestion et utilisation de données par lots

Vous disposez de données de lot pertinentes qui fournissent des détails qui peuvent vous aider à mieux comprendre le comportement des clients et à analyser les interactions des clients. Les fichiers plats au format CSV, JSON ou Parquet d’un système CRM, d’une application de fidélité ou d’une autre solution pour laquelle Adobe ne fournit pas de connecteur source sont des exemples de ces données par lots. L’ingestion de ces données par lots dans Adobe Experience Platform vous permet de les utiliser, de les combiner et de les analyser avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Voir [Ingestion et utilisation de données par lots](./batch.md) pour plus d’informations.

## Ingestion et utilisation de données de diffusion en continu

Vous disposez d’une source de données appropriée, telle qu’un système CRM, un système ERP ou toute autre source, qui fournit des détails qui peuvent vous aider à mieux comprendre le comportement des clients et à analyser les interactions des clients. Cette source de données peut communiquer sur une infrastructure de diffusion en continu de cloud HTTP ou public, mais pour laquelle Adobe ne fournit actuellement pas de connecteur source. L’ingestion de ces données en flux continu dans Adobe Experience Platform en temps réel vous permet de les utiliser, de les combiner et de les analyser avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Voir [Ingestion et utilisation de données de diffusion en continu](./streaming.md) pour plus d’informations.

## Ingestion et utilisation de données à l’aide des connecteurs source

Vous disposez de données provenant d’une source prise en charge par un connecteur source. Les connecteurs source sont des configurations configurables qui vous permettent d’ingérer des données à partir d’une application d’Adobe, d’une application propriétaire ou d’une application tierce dans Adobe Experience Platform. Voir [Présentation des connecteurs source](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=fr) pour une présentation des connecteurs source disponibles. Grâce au connecteur source, vous pouvez facilement ingérer des données de la source dans Adobe Experience Platform, puis les utiliser, les combiner et les analyser avec des données provenant d’autres canaux et sources de données dans Customer Journey Analytics.

Voir [Ingestion et utilisation de données à l’aide des connecteurs source](./sources.md) pour plus d’informations.
