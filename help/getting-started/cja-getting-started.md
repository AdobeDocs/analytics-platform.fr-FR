---
title: Prise en main d’Analyses de parcours client
description: Prise en main de l’analyse du parcours client.
translation-type: tm+mt
source-git-commit: e30bbae59e11bbf93668ffe072508727f6efdd51
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 10%

---


# Prise en main d’Analyses de parcours client

Pour mettre en oeuvre Customer Journey Analytics, vous devez suivre ce processus. Certaines tâches initiales sont effectuées dans Adobe Experience Platform et d’autres dans Customer Journey Analytics.

## Conditions préalables

Les analyses de parcours du client sont disponibles pour les clients qui

* Les clients Adobe Analytics [Select, Prime ou Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) sont-ils et
* sont configurés pour la plate-forme [d’](https://www.adobe.com/fr/experience-platform.html)Adobe Experience, et
* Vous avez acheté le SKU Analyse de parcours du client

## Processus

| Tâche | Détails |
|---|---|---|
| **Étape 1 : Obtention de vos données dans Adobe Experience Platform** | Cette étape, effectuée dans Adobe Experience Platform, implique plusieurs sous-étapes :<br>**Etape 1a : Préparez votre schéma **de données : Utilisez[Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html)pour normaliser les données d’expérience client et[définir des schémas](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)pour la gestion de l’expérience client.<br>**Étape 1b : Créez un jeu de données basé sur le schéma**: Les données de la plate-forme se composent de jeux de données, tels que des jeux de données de messagerie électronique, de jeux de données CRM, de jeux de données POS, de jeux de données Adobe Analytics, etc. Chaque jeu de données se compose d’un schéma et de lots de données. Vous pouvez créer un jeu de données [dans la plate-forme](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)d’expérience.<br>**Étape 1c : Envoi de données dans la plate-forme **d’expérience : Utilisez Adobe Analytics Platform Connector prêt à l’emploi pour importer les données Adobe Analytics traditionnelles dans la plate-forme. Vous pouvez créer une connexion source par suite de rapports. Voir[Création d’une connexion source avec Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)dans la documentation d’Adobe Experience Platform. Une fois la connexion créée, un schéma de cible et un jeu de données sont automatiquement créés pour contenir les données entrantes. En outre, le renvoi des données se produit et ingère jusqu&#39;à 13 mois de données historiques. Une fois l’assimilation initiale terminée, vous pouvez continuer`Step 2`à créer une connexion entre ce jeu de données Analytics et les analyses de parcours du client.<br>Vous pouvez également assimiler d’autres types de données par assimilation[](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md)par lot, par assimilation[en](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)flux continu ou par l’intermédiaire d’[autres connecteurs](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)source. |
| **Étape 2 : Créer des connexions entre les jeux de données de plateformes et les analyses de parcours client** | Une connexion vous permet d’intégrer des jeux de données d’Adobe Experience Platform dans Workspace. Pour générer des rapports sur les jeux de données de la plate-forme d’expérience, vous devez d’abord établir une connexion entre les jeux de données de la plate-forme d’expérience et de l’espace de travail.<br>Voir [Création d’une connexion](/help/connections/create-connection.md). |
| **Étape 3 : Création de vues de données** | Une vue de données est une vue &quot;filtrée&quot; des données. Vous pouvez créer différentes vues de données pour la même connexion, avec des paramètres différents pour le délai d’expiration de la visite, l’attribution, etc. Vous pouvez créer plusieurs vues de données pour un seul jeu de données.<br>Voir [Création d’une vue](/help/data-views/create-dataview.md)de données. |
| **Étape 4 : Création de rapports sur vos données entre canaux dans Workspace** | Après avoir créé des connexions et des vues de données, analysez les données que vous avez introduites en utilisant la puissance et la flexibilité de Analyse Workspace.<br>Voir [Exécution d’une analyse](/help/projects/perform-basic-analysis.md) de base et [Exécution d’une analyse](/help/projects/perform-adv-analysis.md)avancée. |
