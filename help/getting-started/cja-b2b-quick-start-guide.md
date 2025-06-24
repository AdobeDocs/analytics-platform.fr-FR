---
title: Guide de démarrage rapide B2B de Customer Journey Analytics
description: Guide de démarrage rapide pour B2B Edition de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Guide de démarrage rapide de B2B Edition

Pour implémenter Customer Journey Analytics B2B Edition, assurez-vous d’abord de bien comprendre les concepts et fonctionnalités spécifiques au B2B. En outre, vous devez connaître le workflow traditionnel d’implémentation de Customer Journey Analytics.

Ce document se concentre sur le workflow spécifique à l’implémentation de Customer Journey Analytics.

## Conditions préalables

Pour mettre en œuvre Customer Journey Analytics B2B Edition, les conditions préalables suivantes doivent être remplies

* Vous disposez [ du contrôle d’accès et des autorisations](/help/technotes/access-control.md) nécessaires pour effectuer des tâches d’administration dans Customer Journey Analytics.
* Vous avez acheté le package de module complémentaire Customer Journey Analytics B2B Edition.


## Processus

| Tâche | Détails |
| --- | --- |
| **Étape 1 : obtenir des données B2B dans Experience Platform** | Cette étape, effectuée dans Experience Platform, implique plusieurs sous-étapes :<ul><li>**Étape 1a : préparer votre schéma de données** : utilisez le [Modèle de données d’expérience (XDM) Adobe](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/home) pour normaliser les données B2B et [définir des schémas](https://experienceleague.adobe.com/fr/docs/experience-platform/rtcdp/schemas/b2b) pour vos données B2B.</li><li>**Étape 1b : créer un jeu de données basé sur le schéma** : les données dans Platform se composent de jeux de données, tels que des données de compte, des données d’opportunité, des données de groupe d’achat, des données de campagne, des données de liste marketing, des jeux de données d’e-mail, des jeux de données CRM, des jeux de données de point de vente, etc. Chaque jeu de données se compose d’un schéma et de lots de données. Vous pouvez [créer un jeu de données dans Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=fr).</li><li>**Étape 1c : ingérer des données dans Experience Platform** : vous disposez de [plusieurs options](https://experienceleague.adobe.com/fr/docs/experience-platform/ingestion/home).</li></ul> |
| **Étape 2 : Création de connexions entre les jeux de données Platform et Customer Journey Analytics** | Une connexion vous permet d’intégrer des jeux de données d’Adobe Experience Platform dans Espace de travail. Pour générer des rapports sur des jeux de données Experience Platform, vous devez d’abord établir une connexion entre les jeux de données dans Experience Platform et Workspace. Vous disposez d’options supplémentaires lorsque vous configurez une connexion avec B2B Edition. <br>Voir [Créer ou modifier une connexion](/help/connections/create-connection.md). |
| **Étape 3 : Création de vues de données** | Une vue de données est une vue *filtrée* des données. Vous pouvez créer différentes vues de données pour la même connexion, avec des paramètres différents pour le délai d’expiration de la visite, l’attribution, etc. Vous pouvez créer plusieurs vues de données pour un seul jeu de données. Vous disposez d’options supplémentaires lorsque vous configurez une vue de données avec B2B Edition.<br>Voir [Création d’une vue de données](/help/data-views/create-dataview.md). |
| **Étape 4 : Création de rapports sur vos données cross-canal dans Espace de travail** | Après avoir créé des connexions et des vues de données, analysez les données B2B que vous avez introduites en utilisant la puissance et la flexibilité d’Analysis Workspace.<br>Voir [Exécution d’une analyse de base](/help/analysis-workspace/perform-basic-analysis.md) et [Exécution d’une analyse avancée](/help/analysis-workspace/perform-adv-analysis.md). |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->