---
title: Migrer des données à partir de Google Analytics
description: Découvrez le workflow global permettant de transférer les données de Google Analytics vers Adobe Experience Platform et d’afficher des rapports dans Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
TQID: https://experienceleague.adobe.com/C9rt1pyuM6ykLUlXCHc0ITwGeGcuLw6qisXnJxwX4uU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 303
ht-degree: 79%

---

# Migrer des données à partir de Google Analytics

Si vous utilisez Customer Journey Analytics pour la première fois, il est possible que votre organisation dispose de données existantes sur une autre plateforme Analytics, telle que Google Analytics. Vous pouvez effectuer la procédure suivante pour migrer ces données vers Adobe Experience Platform et ainsi afficher des rapports dans Customer Journey Analytics.

Les données historiques et la collecte de données actuelles font l’objet de workflows distincts. Vous pouvez suivre l’un de ces workflows ou les deux, en fonction des besoins en matière de données de votre organisation.

## Migrer des données historiques de Google Analytics vers Adobe Experience Platform

L’ingestion de données historiques (renvoi) consiste en l’exportation de données provenant de Google et l’importation de celles-ci dans Adobe Experience Platform. Consultez la section [Ingérer des données Google Analytics dans Adobe Experience Platform](backfill.md).

Une fois les données historiques importées dans Platform, vous pouvez choisir de [Configurer les données actuelles de diffusion en continu](streaming.md) ou commencer immédiatement à créer des rapports sur les données renvoyées dans Customer Journey Analytics en [Créant une connexion](/help/connections/create-connection.md).

## Configurer une implémentation Google Analytics existante pour Adobe Experience Platform {#configure}

L’ingestion de données actuelles (de diffusion en continu) consiste en l’envoi de données à Adobe Experience Platform Edge Network, qui les transfère ensuite à Adobe Experience Platform. Consultez la section [Configurer les données Google Analytics de diffusion en continu dans Adobe Experience Platform](streaming.md).

## Configurer une connexion et une vue de données dans Customer Journey Analytics

Une fois l’ingestion de données historiques et/ou la configuration de la collecte de données vers Adobe Experience Platform terminée, vous pouvez [créer une connexion](/help/connections/create-connection.md) pour permettre à Customer Journey Analytics de référencer ces données.

Utilisez la connexion pour créer une ou plusieurs [vues de données](/help/data-views/create-dataview.md) que vous utiliserez dans Analysis Workspace.

## Créer des rapports

Une fois les dimensions et les mesures configurées dans une vue de données, vous pouvez commencer à utiliser Analysis Workspace pour générer les rapports souhaités. Consultez la section [Créer des rapports sur les données Google Analytics dans Customer Journey Analytics](report.md).
