---
title: Guide de démarrage rapide de Customer Journey Analytics
description: Découvrez les conditions préalables et le workflow requis pour implémenter Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 100%

---

# Guide de démarrage rapide

Pour implémenter Customer Journey Analytics, vous devez suivre ce processus. Certaines tâches initiales sont effectuées dans Adobe Experience Platform et d’autres dans Customer Journey Analytics.

## Conditions préalables

Customer Journey Analytics est disponible pour les clients qui

* sont configurés pour [Adobe Experience Platform](https://www.adobe.com/fr/experience-platform.html), et
* qui ont acheté le SKU Customer Journey Analytics.

## Processus

| Tâche | Détails |
| --- | --- |
| **Étape 1 : (si vous effectuer une mise à niveau d’Adobe Analytics vers Customer Journey Analytics) : choix d’un chemin de mise à niveau et envoi des données vers Adobe Experience Platform** | Plusieurs chemins sont disponibles lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics. Chaque chemin de mise à niveau possible a ses propres avantages et inconvénients. Ainsi, un chemin approprié pour une organisation peut ne pas avoir de sens pour une autre. <p>Pour commencer la mise à niveau d’Adobe Analytics vers Customer Journey Analytics, effectuez l’une des opérations suivantes :</p><ul><li>Suivez le chemin de mise à niveau recommandé par Adobe. Pour plus d’informations, voir [Chemin recommandé lors de la mise à niveau à partir d’Adobe Analytics vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</li><li>Découvrez tous les chemins de mise à niveau disponibles et choisissez le chemin qui convient le mieux à votre entreprise. Pour plus d’informations, voir [Commencer avec la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md).</li></ul> |
| **Étape 2 : intégrer d’autres données à Adobe Experience Platform**. | Cette étape, effectuée dans Adobe Experience Platform, implique plusieurs sous-étapes :<ul><li>**Étape 2a : préparez votre schéma de données** : utilisez [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) pour normaliser les données d’expérience client et [définir des schémas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=fr) pour la gestion de l’expérience client.</li><li>**Étape 2b : créez un jeu de données basé sur le schéma** : les données de Platform sont composées de jeux de données, tels que les jeux de données d’e-mail, les jeux de données CRM, les jeux de données Points de vente, le jeu de données Adobe Analytics, etc. Chaque jeu de données se compose d’un schéma et de lots de données. Vous pouvez [créer un jeu de données dans Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=fr).</li><li>**Étape 2c : ingérer des données dans Experience Platform** : vous disposez de plusieurs options.</li></ul> |
| **Étape 3 : Création de connexions entre les jeux de données Platform et Customer Journey Analytics** | Une connexion vous permet d’intégrer des jeux de données d’Adobe Experience Platform dans Espace de travail. Pour générer des rapports sur des jeux de données Experience Platform, vous devez d’abord établir une connexion entre les jeux de données dans Experience Platform et Espace de travail.<br>Voir [Créer ou modifier une connexion](/help/connections/create-connection.md). |
| **Étape 4 : Création de vues de données** | Une vue de données est une vue « filtrée » des données. Vous pouvez créer différentes vues de données pour la même connexion, avec des paramètres différents pour le délai d’expiration de la visite, l’attribution, etc. Vous pouvez créer plusieurs vues de données pour un seul jeu de données.<br>Voir [Création d’une vue de données](/help/data-views/create-dataview.md). |
| **Étape 5 : Transfert de l’utilisation de l’API de création de rapports**</br> S’applique uniquement lors de la migration depuis Adobe Analytics. | L’API de création de rapports de Customer Journey Analytics est au même format, mais utilise un point d’entrée différent. Transférez l’utilisation de l’API de création de rapports d’Adobe Analytics vers l’API de création de rapports du Customer Journey Analytics. |
| **Étape 6 : Prise en compte des flux de données et des cas pratiques de l’entrepôt de données**</br> S’applique uniquement lors de la migration depuis Adobe Analytics. | Déterminez comment utiliser les options d’export disponibles dans Customer Journey Analytics afin de mieux répliquer les flux de données et les fonctionnalités d’entrepôt de données que vous utilisiez dans Adobe Analytics. <!-- link to docs Rob is creating --> |
| **Étape 7 : Migration de projets et de composants**</br> S’applique uniquement lors de la migration depuis Adobe Analytics. | La zone Migration de composants d’Adobe Analytics permet de migrer vos projets et les composants associés d’Adobe Analytics vers Customer Journey Analytics.<p>Le processus de migration comprend :</p><ul><li>La recréation de projets Adobe Analytics dans Customer Journey Analytics.</li><li>Le mappage des dimensions et des mesures des suites de rapports Adobe Analytics à des dimensions et des mesures dans les vues de données de Customer Journey Analytics.</li></ul><p>Avant de commencer la migration, commencez par [préparer la migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=fr).</p><p>Après avoir effectué toutes les préparations nécessaires, vous pouvez [migrer des composants et des projets d’Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=fr).</p> |
| **Étape 8 : Planification de l’intégration des utilisateurs et utilisatrices** | Comme dans Adobe Analytics, Analysis Workspace est le principal outil de Customer Journey Analytics destiné aux utilisateurs et utilisatrices. Cependant, il existe des différences clés à connaître lors de l’utilisation d’Analysis Workspace dans Customer Journey Analytics.<p>Donnez à vos utilisateurs et utilisatrices suffisamment de temps (3 à 6 mois) pour se familiariser avec les différences clés d’Analysis Workspace dans Customer Journey Analytics.</p><p>Pour plus d’informations sur certaines différences clés entre Adobe Analytics et Customer Journey Analytics, voir le [Guide de l’utilisateur pour les utilisateurs et utilisatrices d’Adobe Analytics](/help/getting-started/aa-to-cja-user.md).</p> |
| **Étape 9 : Création de rapports sur vos données cross-canal dans Workspace** | Après avoir créé des connexions et des vues de données, analysez les données que vous avez introduites en utilisant la puissance et la flexibilité d’Analysis Workspace.<br>Voir [Exécution d’une analyse de base](/help/analysis-workspace/perform-basic-analysis.md) et [Exécution d’une analyse avancée](/help/analysis-workspace/perform-adv-analysis.md). |

## Guides de démarrage rapide

La section [Ingestion des données](../data-ingestion/data-ingestion.md) fournit des guides de démarrage rapide sur le workflow ci-dessus. Ces guides de démarrage rapide expliquent comment ingérer des données provenant de diverses sources (y compris Adobe Analytics) dans Adobe Experience Platform, puis les utiliser dans Customer Journey Analytics.
