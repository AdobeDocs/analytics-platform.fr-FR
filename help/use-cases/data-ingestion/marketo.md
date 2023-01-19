---
title: Ingestion de données Marketo Engage dans AEP et création de rapports dans CJA
description: Découvrez comment importer des données Marketo Engage dans CJA
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

---

# Ingestion de données Marketo Engage dans AEP et création de rapports dans CJA

Vous pouvez utiliser les nouveaux jeux de données Marketo Engage disponibles dans Adobe Experience Platform (AEP) pour fournir des solutions d’analyse et de création de rapports utiles aux spécialistes du marketing B2B. Créez ensuite un rapport sur ces jeux de données dans Customer Journey Analytics (CJA).

## Étape 1 : Mapper les champs de données source Marketo à leurs cibles XDM

Mappez les objets [Personnes](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=fr#persons) et [Activités](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=fr#activities) à leurs champs cibles de schéma XDM respectifs.

## Étape 2 : Ingérer des données Marketo dans AEP

Utilisez le [connecteur Marketo Engage](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=fr) pour importer les données de Marketo dans Experience Platform et les tenir à jour à l’aide des applications connectées à Platform.

## Étape 3 : Configurer une connexion à ce jeu de données dans CJA

Pour générer des rapports sur des jeux de données Experience Platform, vous devez d’abord établir une connexion entre les jeux de données dans Experience Platform et CJA. Pour plus d’informations, consultez [Création d’une connexion](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr).

## Étape 4 : Créer une ou plusieurs vues de données

Une [vue de données](/help/data-views/data-views.md) est un conteneur spécifique à Customer Journey Analytics qui vous permet de déterminer comment interpréter les données d’une connexion. Elle spécifie toutes les dimensions et mesures disponibles dans Analysis Workspace, soit dans le cas qui nous intéresse, les mesures et dimensions spécifiques à Marketo. Elle spécifie également les colonnes à partir desquelles ces dimensions et mesures obtiennent leurs données. Les vues de données sont définies en vue de la création de comptes rendus des performances dans Analysis Workspace.

## Étape 5 : Rapport dans Analysis Workspace

Voici un cas pratique que vous pouvez explorer : Combien de visites de pages web par prospect avions-nous d’avril à juin 2020 ?

1. Ouvrez [Analytics Workspace](/help/analysis-workspace/home.md) et créez un projet.
Les clients disposant de la plateforme de données clients B2B/B2P peuvent réaliser une analyse de type B2C dans CJA. Les objets B2B ne sont pas encore disponibles.

1. Créez un [filtre](/help/components/filters/create-filters.md) pour les pages vues web comme suit - Type d’événement = web.webpagedetails.pageViews :

   ![](../assets/marketo-filter.png)

1. Dans le tableau à structure libre, extrayez le filtre que vous avez créé - Pages vues web, puis extrayez la période Mois. Vous obtenez ainsi les visites des pages web par prospect chaque mois :

   ![](../assets/marketo-freeform.png)

1. Vous pouvez également extraire les dimensions suivantes : Clé de personne ou adresse e-mail professionnelle. Vous obtenez ainsi les visites des pages web par prospect :

   ![](../assets/marketo-freeform2.png)
