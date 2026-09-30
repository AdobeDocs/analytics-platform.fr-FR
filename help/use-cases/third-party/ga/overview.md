---
title: Migrer des données à partir de Google Analytics
description: Découvrez le workflow global permettant de transférer les données de Google Analytics vers Adobe Experience Platform et d’afficher des rapports dans Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
TQID: 'https://experienceleague.adobe.com/C9rt1pyuM6ykLUlXCHc0ITwGeGcuLw6qisXnJxwX4uU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
    internal-label: Use cases
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 70%
---
# Migrer des données à partir de Google Analytics

>[!BEGINSHADEBOX]

Ce guide couvre la migration des données pour les administrateurs. Si vous êtes un analyste cherchant à trouver vos rapports GA4 dans Customer Journey Analytics, voir [Transition de Google Analytics 4 vers Customer Journey Analytics](/help/getting-started/ga-to-cja/home.md) et [rapports GA4 dans Customer Journey Analytics](/help/getting-started/ga-to-cja/reports.md).

>[!ENDSHADEBOX]

Si vous utilisez Customer Journey Analytics pour la première fois, il est possible que votre organisation dispose de données existantes sur une autre plateforme Analytics, telle que Google Analytics. Vous pouvez effectuer la procédure suivante pour migrer ces données vers Adobe Experience Platform et ainsi afficher des rapports dans Customer Journey Analytics.

Les données historiques et la collecte de données actuelles font l’objet de workflows distincts. Vous pouvez suivre l’un de ces workflows ou les deux, en fonction des besoins en matière de données de votre organisation.

## Migrer des données historiques de Google Analytics vers la plateforme Adobe Experience Platform

L’ingestion de données historiques (de renvoi) consiste à exporter des données depuis Google, puis à les importer dans la plateforme Adobe Experience Platform. Consultez la section [Ingérer des données Google Analytics dans Adobe Experience Platform](backfill.md).

Une fois les données historiques importées dans Platform, vous pouvez choisir de [Configurer les données actuelles de diffusion en continu](streaming.md) ou commencer immédiatement à créer des rapports sur les données renvoyées dans Customer Journey Analytics en [Créant une connexion](/help/connections/create-connection.md).

## Configurer une mise en œuvre Google Analytics existante pour Adobe Experience Platform {#configure}

L’ingestion de données actuelles (de diffusion en continu) consiste en l’envoi de données à Adobe Experience Platform Edge Network, qui les transfère ensuite à Adobe Experience Platform. Consultez la section [Configurer les données Google Analytics de diffusion en continu dans Adobe Experience Platform](streaming.md).

## Configurer une connexion et une vue de données dans Customer Journey Analytics

Une fois l’ingestion de données historiques et/ou la configuration de la collecte de données vers Adobe Experience Platform terminée, vous pouvez [créer une connexion](/help/connections/create-connection.md) pour permettre à Customer Journey Analytics de référencer ces données.

Utilisez la connexion pour créer une ou plusieurs [vues de données](/help/data-views/create-dataview.md) que vous utiliserez dans Analysis Workspace.

## Créer des rapports

Une fois les dimensions et les mesures configurées dans une vue de données, vous pouvez commencer à utiliser Analysis Workspace pour générer les rapports souhaités. Consultez la section [Créer des rapports sur les données Google Analytics dans Customer Journey Analytics](report.md).
