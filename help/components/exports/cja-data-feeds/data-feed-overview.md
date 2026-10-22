---
description: Découvrez comment utiliser les flux de données pour exporter des données brutes au niveau de l’événement depuis Customer Journey Analytics, consulter les conditions préalables et rechercher les articles dont vous avez besoin pour commencer.
keywords: flux de clics;flux de données;flux des données;Flux de données
title: Présentation des flux de données Customer Journey Analytics
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 34959e37a7040bcd861a506968895ad6f051b686
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 1%
---
# Présentation des flux de données

{{release-limited-testing}}

Les flux de données exportent des données brutes au niveau de l’événement de Customer Journey Analytics vers une destination cloud. Vous pouvez utiliser ces données sur d’autres plateformes en dehors d’Adobe, telles qu’un entrepôt de données.

Les flux de données sont créés à partir des composants dans une vue de données. Chaque dimension et mesure que vous incluez devient une colonne dans le flux de données et les paramètres de vue de données tels que la persistance, les champs dérivés et les segments sont appliqués aux données. Les fichiers sont livrés au format Parquet.

Vous pouvez créer les types de flux de données suivants :

* **Flux en direct** : exportez les données actuelles et futures toutes les heures ou quotidiennement. Chaque diffusion est envoyée après la fin de l’heure ou de la journée et le délai de traitement est dépassé.

* **Flux de renvoi** : exportez les données historiques d’une période passée.

Pour une comparaison des flux de données par rapport à d’autres méthodes d’exportation Customer Journey Analytics, telles que l’exportation de table complète, voir [Comparaison des produits Analytics](/help/getting-started/analytics-product-comparison.md).

## Conditions préalables

Assurez-vous de respecter toutes les exigences suivantes avant d’utiliser les flux de données :

* Les données sont ingérées dans Customer Journey Analytics et une connexion et une [vue de données](/help/data-views/create-dataview.md) sont configurées. <!-- For more information, see Data ingestion overview - add link -->

* Votre compte est un administrateur de produit Customer Journey Analytics ou appartient à un profil de produit avec l’autorisation [!UICONTROL **Flux de données**] (dans la catégorie [!UICONTROL **Outils de vues de données**]) pour la vue de données que vous souhaitez utiliser. Pour plus d’informations, voir [Contrôle d’accès](/help/technotes/access-control.md). <!--Add a Data Feeds row to the Data View Tools permissions table in access-control.md.-->

* Un compte et un emplacement d’exportation cloud sont configurés pour [!DNL Amazon S3], [!DNL Google Cloud Platform], [!DNL Azure RBAC] ou [!DNL Azure SAS]. Pour plus d’informations, consultez [Configuration des comptes d’exportation cloud](/help/components/exports/cloud-export-accounts.md) et [Configuration des emplacements d’exportation cloud](/help/components/exports/cloud-export-locations.md).

>[!TIP]
>
>Comme les modifications apportées aux composants d’une vue de données affectent chaque flux de données qui l’utilise, pensez à créer une vue de données utilisée uniquement pour les flux de données.
>
>* **Avantage** : réduit le risque que les modifications apportées aux rapports Analysis Workspace modifient de manière inattendue la sortie du flux de données.
>
>* **Inconvénient** : vous devez conserver la vue de données supplémentaire avec vos autres vues de données.

## Commencer

Consultez les articles suivants pour planifier, migrer et créer vos flux de données.

### Planification des flux de données

* [Comparer des flux de données dans Customer Journey Analytics et Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md) : découvrez les différences de fonctionnalités et de concepts si vous avez utilisé des flux de données Adobe Analytics par le passé.

* [Comprendre les écarts de données entre les flux de données et Analysis Workspace](/help/components/exports/cja-data-feeds/df-comparison-workspace.md) : découvrez pourquoi la sortie des flux de données peut ne pas correspondre aux rapports dans Analysis Workspace.

* [Disponibilité des composants dans les flux de données](/help/components/exports/cja-data-feeds/df-components.md) : découvrez les dimensions et mesures requises, non prises en charge ou restreintes dans les flux de données.

### Migration des flux de données d’Adobe Analytics

1. [Préparer le mappage des colonnes de flux de données](/help/components/exports/cja-data-feeds/df-column-mapping-prep.md) : découvrez les facteurs qui affectent la manière dont les colonnes Adobe Analytics sont mappées à Customer Journey Analytics.

1. [Mapper les colonnes de flux de données Adobe Analytics à Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md) : recherchez l’équivalent Customer Journey Analytics de chaque colonne Adobe Analytics que vous souhaitez conserver.

### Création et configuration des flux de données

* [Créer un flux de données](/help/components/exports/cja-data-feeds/create-feed.md) : sélectionnez les composants, configurez le planning et configurez la diffusion.

* [Segmentation dans les flux de données](/help/components/exports/cja-data-feeds/df-segmentation.md) : appliquez des segments pour filtrer les données d’un flux de données.

* [Appliquer des transformations de données](/help/components/exports/cja-data-feeds/df-data-transformations.md) : transformez des données à l’aide de paramètres de composant, de champs dérivés ou de SQL.

* [Composants de sous-événement dans les flux de données](/help/components/exports/cja-data-feeds/df-sub-event.md) : découvrez comment les composants des tableaux et des mappages sont exportés et comment les interroger.

