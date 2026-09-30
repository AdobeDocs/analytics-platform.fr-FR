---
title: Configurer des données de Google Analytics en streaming
description: Découvrez comment configurer votre implémentation afin d’envoyer une couche de données Google dans Adobe Experience Platform.
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T09:49:39.181Z'
TQID: 'https://experienceleague.adobe.com/xav7bGdbGLjYXm70GJBSxnDMfNDZpYp5qij1IqkaZSY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
    internal-label: Analytics integration
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
    internal-label: Use cases
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 90%
---
# Configurer des données de Google Analytics en streaming

Cette page se concentre sur la manière d’ingérer vos données dynamiques Google Analytics dans Adobe Experience Platform, ce qui vous permet de référencer ce jeu de données dans une vue de données de Customer Journey Analytics. Vous pouvez associer les étapes de cette page à [l’ingestion de données historiques Google Analytics dans Adobe Experience Platform](backfill.md), qui génère un jeu de données contenant des données historiques. Combinez un jeu de données en flux continu avec un jeu de données de renvoi pour obtenir une vue transparente des données antérieures et présentes dans Customer Journey Analytics.

La configuration de la collecte de données implique les étapes suivantes :

1. Implémentez les [Balises pour Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr). Voir [Guide de démarrage rapide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) pour qu’une implémentation de base soit opérationnelle.
1. Installez l‘[Extension de la couche de données Google](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). Cette extension sert d’alternative à l’installation de l’extension du SDK Web, orientée spécifiquement vers une couche de données Google.
1. [Créez un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) dans la collecte de données Adobe Experience Platform. Configurez le train de données pour envoyer des données à Adobe Experience Platform. Vous devez actuellement mapper chaque objet de la couche de données Google à un champ XDM applicable ici. Adobe prévoit de simplifier ce workflow de mappage à l’avenir.

Une fois que vous avez implémenté et publié les balises souhaitées sur votre site, vous pouvez passer à [créer une connexion](/help/connections/create-connection.md), puis [créer une vue de données](/help/data-views/create-dataview.md).
