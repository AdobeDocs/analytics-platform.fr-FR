---
title: Migrer des données à partir de Google Analytics
description: Découvrez le workflow global permettant de transférer les données de Google Analytics vers Adobe Experience Platform et d’afficher des rapports dans Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
source-git-commit: 8262539078c57e32bc3195ef669325fa4889bea0
workflow-type: tm+mt
source-wordcount: '303'
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
