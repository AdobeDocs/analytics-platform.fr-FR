---
title: Guide de démarrage rapide B2B de Customer Journey Analytics
description: Guide de démarrage rapide pour le B2B edition de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: d7ee16c64761440989f2850d72b8159799bb8479
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 22%

---

# Guide de démarrage rapide de B2B edition

{{draft-b2b}}

Pour mettre en œuvre Customer Journey Analytics B2B edition, assurez-vous d’abord de bien comprendre les concepts et fonctionnalités spécifiques au B2B. En outre, vous devez connaître le workflow traditionnel d’implémentation de Customer Journey Analytics.

Ce document se concentre sur le workflow spécifique à l’implémentation de Customer Journey Analytics.

## Conditions préalables

Pour mettre en œuvre Customer Journey Analytics B2B edition, les conditions préalables suivantes doivent être remplies

* Vous disposez des [contrôle d’accès et autorisations](/help/technotes/access-control.md) nécessaires pour effectuer des tâches d’administration dans Customer Journey Analytics.
* Vous avez acheté le package de module complémentaire Customer Journey Analytics B2B edition.


## Processus

| Tâche | Détails |
| --- | --- |
| **Étape 1 : obtenir des données B2B dans Experience Platform** | Cette étape, effectuée dans Experience Platform, implique plusieurs sous-étapes :<ul><li>**Étape 1a : préparez votre schéma de données** : utilisez [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) pour normaliser les données B2B et [définir des schémas](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b) pour vos données B2B.</li><li>**Étape 1b : créez un jeu de données basé sur le schéma** : les données dans Platform se composent de jeux de données, tels que des données de compte, des données d’opportunité, des données de groupe d’achats, des données de campagne, des données de liste marketing, des jeux de données d’e-mail, des jeux de données CRM, des jeux de données POS, etc. Chaque jeu de données se compose d’un schéma et de lots de données. Vous pouvez [créer un jeu de données dans Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=fr).</li><li>**Étape 1c : ingestion de données dans Experience Platform** : vous disposez de [plusieurs options](https://experienceleague.adobe.com/fr/docs/experience-platform/ingestion/home).</li></ul> |
| **Étape 2 : Création de connexions entre les jeux de données Platform et Customer Journey Analytics** | Une connexion vous permet d’intégrer des jeux de données d’Adobe Experience Platform dans Espace de travail. Pour générer des rapports sur des jeux de données Experience Platform, vous devez d’abord établir une connexion entre les jeux de données dans Experience Platform et Workspace. Vous disposez d’options supplémentaires lorsque vous configurez une connexion avec le B2B edition. <br>Voir [Créer ou modifier une connexion](/help/connections/create-connection.md). |
| **Étape 3 : Création de vues de données** | Une vue de données est une vue *filtrée* des données. Vous pouvez créer différentes vues de données pour la même connexion, avec différents paramètres pour le délai de visite, l’attribution, etc. Vous pouvez créer plusieurs vues de données pour un seul jeu de données. Vous disposez d’options supplémentaires lorsque vous configurez une vue de données avec le B2B edition.<br>Voir [Création d’une vue de données](/help/data-views/create-dataview.md). |
| **Étape 4 : Création de rapports sur vos données cross-canal dans Espace de travail** | Après avoir créé des connexions et des vues de données, analysez les données B2B que vous avez introduites à l’aide de la puissance et de la flexibilité d’Analysis Workspace.<br>Voir [Exécution d’une analyse de base](/help/analysis-workspace/perform-basic-analysis.md) et [Exécution d’une analyse avancée](/help/analysis-workspace/perform-adv-analysis.md). |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->