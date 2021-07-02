---
title: Options d’ingestion des données pour Customer Journey Analytics
description: Comprendre les différentes manières d’ingérer des données dans Customer Journey Analytics
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: ht
source-wordcount: '940'
ht-degree: 100%

---

# Options d’ingestion des données pour Customer Journey Analytics

Plusieurs options s’offrent à vous pour l’ingestion de données dans Customer Journey Analytics. Certaines de ces options supposent que vous voulez déplacer les données Adobe Analytics classique, d’autres supposent que vous ingérez les données directement à partir d’Adobe Experience Platform. Cette référence fournit les étapes générales à suivre, avec des liens vers des informations plus détaillées.

## Ingérer des données à partir d’Adobe Analytics classique

Ce workflow utilise le connecteur Adobe Analytics et varie selon que vous utilisez DTM ou Launch comme gestionnaire de balises.

### Avec la Dynamic Tag Management (DTM)

1. [Créez une couche de données](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=fr), si ce n’est déjà fait. Une couche de données désigne une structure d’objets JavaScript sur votre site qui contient toutes les valeurs de variable utilisées dans votre mise en œuvre. Il permet un meilleur contrôle et une maintenance plus facile dans votre mise en œuvre.
1. Utilisez [DTM](https://experienceleague.adobe.com/docs/analytics/implementation/other/dtm/dtm-implementation-overview.html) pour implémenter du code sur votre site pour la collecte de données, si ce n’est déjà fait. La Dynamic Tag Management procure une couche de données unique qui pousse les données à partir de plusieurs sources.
1. Créez un [Connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) dans Adobe Experience Platform. Ce connecteur source ingèrera vos données Analytics dans Experience Platform dans un framework standardisé appelé [Système de modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr).
1. Utilisez [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=fr) pour créer une ou plusieurs connexions et vues de données qui informeront votre reporting cross-canal.

### Avec Launch

1. [Créez une couche de données](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=fr), si ce n’est déjà fait. Une couche de données désigne une structure d’objets JavaScript sur votre site qui contient toutes les valeurs de variable utilisées dans votre mise en œuvre. Il permet un meilleur contrôle et une maintenance plus facile dans votre mise en œuvre.
1. Utilisez [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=fr) pour implémenter du code sur votre site pour la collecte de données, si ce n’est déjà fait. Launch est une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Launch propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site..
1. Créez un [Connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) dans Adobe Experience Platform. Ce connecteur source ingèrera vos données Analytics dans Experience Platform dans un framework standardisé appelé [Système de modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr).
1. Utilisez [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=fr) pour créer une ou plusieurs connexions et vues de données qui informeront votre reporting cross-canal.

## Ingestion des données via le SDK web Adobe Experience Platform et le réseau Edge

[Le SDK Web d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) est une bibliothèque JavaScript côté client qui permet aux clients d’Adobe Experience Cloud d’interagir avec les différents services d’Experience Cloud à travers Adobe Experience Platform Edge Network.

1. [Configurez l’extension du SDK Web AEP dans Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=fr#configure-the-aep-web-sdk-extension) pour envoyer des données à Adobe Experience Cloud à partir de propriétés web via Adobe Experience Platform Edge Network.
1. Utilisez [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=fr) pour créer une ou plusieurs connexions et vues de données qui informeront votre reporting cross-canal.

## Ingestion des données par lots et en flux continu

Adobe Experience Platform rassemble des données provenant de plusieurs sources afin d’aider les professionnels du marketing à mieux comprendre le comportement de leurs clients. Adobe Experience Platform Data Ingestion représente les diverses méthodes que Platform emploie pour ingérer des données à partir de ces sources, ainsi que la manière dont ces données sont conservées dans le lac de données pour être utilisées par les services de Platform en aval.

### Ingestion par lots

1. Configurez l’[ingestion par lots](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=fr#batch) pour permettre l’ingestion des données dans Adobe Experience Platform en fichiers par lots. Les données en cours d’ingestion peuvent être les données du profil d’un fichier plat dans un système CRM (par exemple un fichier parquet) ou des données conformes à un schéma connu dans le registre Experience Data Model (XDM).
1. Utilisez [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=fr) pour créer une ou plusieurs connexions et vues de données qui informeront votre reporting cross-canal.

### Ingestion par flux

1. Configurez l’[ingestion en flux continu](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=fr#streaming) pour envoyer des données depuis des périphériques côté client et serveur vers Experience Platform en temps réel.
1. Utilisez [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=fr) pour créer une ou plusieurs connexions et vues de données qui informeront votre reporting cross-canal.

## Intégration des données Google Analytics à analyser dans Customer Journey Analytics

Consultez ce tutoriel sur la façon d’[analyser les données Google Analytics à l’aide de Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=fr#objectives) pour obtenir des instructions détaillées.

## Utilisez l’API d’insertion de données en bloc pour obtenir des données dans Analytics, puis lancez l’ingestion via le connecteur source d’Adobe dans Experience Platform.

1. [Utilisez l’API d’insertion de données en bloc](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) pour envoyer des données de collecte côté serveur à Adobe Analytics. Elle vous permet d’envoyer des fichiers au format CSV contenant des données d’événement.
1. [Créez un connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) pour importer ces données client dans Adobe Experience Platform.
1. Utilisez [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=fr) pour créer une ou plusieurs connexions et vues de données qui informeront votre reporting cross-canal.
