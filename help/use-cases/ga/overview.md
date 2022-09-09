---
title: Migration des données des Google Analytics vers Customer Journey Analytics
description: Découvrez le processus global de déplacement des données des Google Analytics vers Adobe Experience Platform et d’affichage des rapports dans Customer Journey Analytics.
source-git-commit: 7c195453490499cc42e7d5b2f2d111e2654f918c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Migration des données des Google Analytics vers Customer Journey Analytics

Si vous découvrez Customer Journey Analytics, il est possible que votre entreprise dispose de données existantes sur une autre plateforme Analytics, comme des Google Analytics. Vous pouvez suivre ces étapes principales pour déplacer ces données dans Adobe Experience Platform, ce qui vous permet d’afficher les rapports dans Customer Journey Analytics.

Les workflows sont fournis pour les données historiques et la collecte de données actives. Vous pouvez suivre l’un de ces workflows ou les deux, en fonction des besoins de données de votre entreprise.

## Importation des données historiques des Google Analytics dans Adobe Experience Platform

L’ingestion de données historiques (de renvoi) implique l’exportation de données à partir de Google et l’importation de ces données dans Adobe Experience Platform. Voir [Ingestion de données Google Analytics dans Adobe Experience Platform](backfill.md).

Une fois les données historiques importées dans Platform, vous pouvez effectuer l’une des opérations suivantes : [Configuration de la diffusion en continu des données actives](streaming.md)ou commencer immédiatement à créer des rapports sur les données renvoyées dans CJA par [Créer une connexion](/help/connections/create-connection.md).

## Configuration d’une mise en oeuvre de Google Analytics existante pour Adobe Experience Platform {#configure}

L’ingestion de données actives (par flux) implique l’envoi de données à Adobe Experience Edge, qui les transfère ensuite à Adobe Experience Platform. Voir [Configuration des données de Google Analytics en continu dans Adobe Experience Platform](streaming.md).

## Configuration d’une connexion et d’une vue des données dans CJA

Une fois que vous avez ingéré des données historiques et/ou configuré la collecte de données sur Adobe Experience Platform, vous pouvez [Création d’une connexion](/help/connections/create-connection.md) pour permettre à Customer Journey Analytics de référencer ces données.

Utilisez la connexion pour créer une ou plusieurs [Vues des données](/help/data-views/create-dataview.md) à utiliser dans Analysis Workspace.

## Création de rapports

Après avoir configuré les dimensions et les mesures dans une vue de données, vous pouvez commencer à utiliser Analysis Workspace pour générer les rapports de votre choix. Voir [Rapport sur les données de Google Analytics dans Customer Journey Analytics](report.md).
