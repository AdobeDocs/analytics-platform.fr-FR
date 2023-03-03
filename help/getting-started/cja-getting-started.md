---
title: Prise en main de Customer Journey Analytics
description: Comprendre les conditions préalables et le workflow requis pour implémenter Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: ab4b65a8948d650615cdf9b99718cbc50499e9f5
workflow-type: ht
source-wordcount: '415'
ht-degree: 100%

---

# Prise en main de Customer Journey Analytics

Pour implémenter Customer Journey Analytics, vous devez suivre ce processus. Certaines tâches initiales sont effectuées dans Adobe Experience Platform et d’autres dans Customer Journey Analytics.

## Conditions préalables

Customer Journey Analytics est disponible pour les clients qui

* sont configurés pour [Adobe Experience Platform](https://www.adobe.com/fr/experience-platform.html), et
* qui ont acheté le SKU Customer Journey Analytics.

## Processus

| Tâche | Détails |
| --- | --- |
| **Étape 1 : si vous effectuez une migration d’Adobe Analytics vers CJA, découvrez ce que vous devez faire.** | Voir [Utilisation des données de suite de rapports Adobe Analytics dans Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md) et [Ingérer et utiliser des données à partir de la version standard d’Adobe Analytics](../data-ingestion/analytics.md). |
| **Étape 2 : intégrer d’autres données à Adobe Experience Platform**. | Cette étape, effectuée dans Adobe Experience Platform, implique plusieurs sous-étapes :<ul><li>**Étape 2a : préparez votre schéma de données** : utilisez [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) pour normaliser les données d’expérience client et [définir des schémas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=fr) pour la gestion de l’expérience client.</li><li>**Étape 2b : créez un jeu de données basé sur le schéma** : les données dans la plateforme sont composées de jeux de données, tels que les jeux de données de messagerie électronique, les jeux de données CRM, les jeux de données Points de vente, le jeu de données Adobe Analytics, etc. Chaque jeu de données se compose d’un schéma et de lots de données. Vous pouvez [créer un jeu de données dans Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=fr).</li><li>**Étape 2c : ingérer des données dans Experience Platform** : vous disposez de plusieurs options.</li></ul> |
| **Étape 3 : Création de connexions entre les jeux de données Platform et Customer Journey Analytics** | Une connexion vous permet d’intégrer des jeux de données d’Adobe Experience Platform dans Espace de travail. Pour générer des rapports sur des jeux de données Experience Platform, vous devez d’abord établir une connexion entre les jeux de données dans Experience Platform et Espace de travail.<br>Voir [Création d’une connexion](/help/connections/create-connection.md). |
| **Étape 4 : Création de vues de données** | Une vue de données est une vue « filtrée » des données. Vous pouvez créer différentes vues de données pour la même connexion, avec des paramètres différents pour le délai d’expiration de la visite, l’attribution, etc. Vous pouvez créer plusieurs vues de données pour un seul jeu de données.<br>Voir [Création d’une vue de données](/help/data-views/create-dataview.md). |
| **Étape 5 : Création de rapports sur vos données cross-canal dans Espace de travail** | Après avoir créé des connexions et des vues de données, analysez les données que vous avez introduites en utilisant la puissance et la flexibilité d’Analysis Workspace.<br>Voir [Exécution d’une analyse de base](/help/analysis-workspace/perform-basic-analysis.md) et [Exécution d’une analyse avancée](/help/analysis-workspace/perform-adv-analysis.md). |

## Guides de démarrage rapide

La section [Ingestion des données](../data-ingestion/data-ingestion.md) fournit des guides de démarrage rapide sur le workflow ci-dessus. Ces guides de démarrage rapide expliquent comment ingérer des données provenant de diverses sources (y compris Adobe Analytics) dans Adobe Experience Platform, puis les utiliser dans Customer Journey Analytics.
