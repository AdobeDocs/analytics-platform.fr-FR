---
title: Prise en main de Customer Journey Analytics
description: Comprendre les conditions préalables et le workflow requis pour implémenter Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 2204bb6ff66a3eb26caeebab7208797866342e12
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 82%

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
| --- | --- |
| **Étape 1 : Si vous effectuez une migration d’Adobe Analytics vers CJA, consultez le guide de migration.** | [Guide de migration d’Adobe Analytics vers Customer Journey Analytics](/help/getting-started/aa-to-cja.md) |
| **Étape 2 : Ingestion de vos données dans Adobe Experience Platform** | Cette étape, effectuée dans Adobe Experience Platform, implique plusieurs sous-étapes :<ul><li>**Étape 2a : préparez votre schéma de données** : utilisez [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) pour normaliser les données d’expérience client et [définir des schémas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en) pour la gestion de l’expérience client.</li><li>**Étape 2b : créez un jeu de données basé sur le schéma** : les données dans la plateforme sont composées de jeux de données, tels que les jeux de données de messagerie électronique, les jeux de données CRM, les jeux de données Points de vente, le jeu de données Adobe Analytics, etc. Chaque jeu de données se compose d’un schéma et de lots de données. Vous pouvez [création d’un jeu de données dans Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html).</li><li>**Étape 2c : Ingestion de données dans Experience Platform**: Vous disposez ici de plusieurs options. Afficher la variable [cas d’utilisation de l’ingestion de données](/help/use-cases/data-ingestion.md) pour plus d’informations. |
| **Étape 2 : Création de connexions entre les jeux de données Platform et Customer Journey Analytics** | Une connexion vous permet d’intégrer des jeux de données d’Adobe Experience Platform dans Espace de travail. Pour générer des rapports sur des jeux de données Experience Platform, vous devez d’abord établir une connexion entre les jeux de données dans Experience Platform et Espace de travail.<br>Voir [Création d’une connexion](/help/connections/create-connection.md). |
| **Étape 3 : Création de vues de données** | Une vue de données est une vue « filtrée » des données. Vous pouvez créer différentes vues de données pour la même connexion, avec des paramètres différents pour le délai d’expiration de la visite, l’attribution, etc. Vous pouvez créer plusieurs vues de données pour un seul jeu de données.<br>Voir [Création d’une vue de données](/help/data-views/create-dataview.md). |
| **Étape 4 : Création de rapports sur vos données cross-canal dans Espace de travail** | Après avoir créé des connexions et des vues de données, analysez les données que vous avez introduites en utilisant la puissance et la flexibilité d’Analysis Workspace.<br>Voir [Exécution d’une analyse de base](/help/analysis-workspace/perform-basic-analysis.md) et [Exécution d’une analyse avancée](/help/analysis-workspace/perform-adv-analysis.md). |
