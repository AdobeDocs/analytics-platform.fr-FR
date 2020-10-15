---
title: Prise en main de Customer Journey Analytics
description: Comprendre les conditions préalables et le workflow requis pour implémenter Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 8067bb355934f8f6f1d54776f44abfd853aee231
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 100%

---


# Prise en main de Customer Journey Analytics

Pour implémenter Customer Journey Analytics, vous devez suivre ce processus. Certaines tâches initiales sont effectuées dans Adobe Experience Platform et d’autres dans Customer Journey Analytics.

## Conditions préalables

Customer Journey Analytics est disponible pour les clients qui

* sont des clients Adobe Analytics [Select, Prime ou Ultimate](https://www.adobe.com/fr/analytics/compare-adobe-analytics-packages.html), et
* sont configurés pour [Adobe Experience Platform](https://www.adobe.com/fr/experience-platform.html), et
* qui ont acheté le SKU Customer Journey Analytics.

## Processus

| Tâche | Détails |
|---|---|
| **Étape 1 : Ingestion de vos données dans Adobe Experience Platform** | Cette étape, effectuée dans Adobe Experience Platform, implique plusieurs sous-étapes :<ul><li>**Étape 1a : préparez votre schéma de données** : utilisez [Adobe Experience Data Model (XDM)](https://docs.adobe.com/content/help/fr-FR/experience-platform/xdm/home.translate.html) pour normaliser les données d’expérience client et [définir des schémas](https://docs.adobe.com/content/help/fr-FR/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md) pour la gestion de l’expérience client.</li><li>**Étape 1b : créez un jeu de données basé sur le schéma** : les données dans la plateforme sont composées de jeux de données, tels que les jeux de données de messagerie électronique, les jeux de données CRM, les jeux de données Points de vente, le jeu de données Adobe Analytics, etc. Chaque jeu de données se compose d’un schéma et de lots de données. Vous pouvez créer un jeu de données [dans Experience Platform](https://docs.adobe.com/content/help/fr-FR/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).</li><li>**Étape 1c : ingérez des données dans Experience Platform** : utilisez l’Adobe Analytics Platform Connector prêt à l’emploi pour importer les données traditionnelles d’Adobe Analytics dans Platform. Vous pouvez créer une connexion source par suite de rapports. Voir [Création d’une connexion source avec Adobe Analytics](https://docs.adobe.com/content/help/fr-FR/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) dans la documentation d’Adobe Experience Platform. Une fois la connexion créée, un schéma et un jeu de données cibles sont automatiquement créés pour contenir les données entrantes. En outre, un remplissage de données se produit et ingère jusqu’à 13 mois de données historiques. Une fois l’ingestion initiale terminée, vous pouvez poursuivre l’`Step 2` pour créer une connexion entre ce jeu de données Analytics et les Customer Journey Analytics. Vous pouvez également ingérer d’autres types de données par [importation par lot](https://docs.adobe.com/content/help/fr-FR/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md), par [assimilation en flux continu](https://docs.adobe.com/content/help/fr-FR/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) ou par [d’autres connecteurs source](https://docs.adobe.com/content/help/fr-FR/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md).</li></ul> |
| **Étape 2 : Création de connexions entre les jeux de données Platform et Customer Journey Analytics** | Une connexion vous permet d’intégrer des jeux de données d’Adobe Experience Platform dans Workspace. Pour générer des rapports sur des jeux de données Experience Platform, vous devez d’abord établir une connexion entre les jeux de données dans Experience Platform et Workspace.<br>Voir [Création d’une connexion](/help/connections/create-connection.md). |
| **Étape 3 : Création de vues de données** | Une vue de données est une vue « filtrée » des données. Vous pouvez créer différentes vues de données pour la même connexion, avec des paramètres différents pour le délai d’expiration de la visite, l’attribution, etc. Vous pouvez créer plusieurs vues de données pour un seul jeu de données.<br>Voir [Création d’une vue de données](/help/data-views/create-dataview.md). |
| **Étape 4 : Création de rapports sur vos données cross-canal dans Workspace** | Après avoir créé des connexions et des vues de données, analysez les données que vous avez introduites en utilisant la puissance et la flexibilité d’Analysis Workspace.<br>Voir [Exécution d’une analyse de base](/help/analysis-workspace/perform-basic-analysis.md) et [Exécution d’une analyse avancée](/help/analysis-workspace/perform-adv-analysis.md). |
