---
title: Options d’ingestion des données pour Customer Journey Analytics
description: Comprendre les différentes manières d’ingérer des données dans Customer Journey Analytics
translation-type: tm+mt
source-git-commit: ab1ea4c75c4c28f196c6793a819ce4dbe656d52c
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 70%

---


# Options d’ingestion des données pour Customer Journey Analytics

Plusieurs options s’offrent à vous pour l’ingestion de données dans Customer Journey Analytics. Certaines de ces options supposent que vous voulez déplacer les données Adobe Analytics classique, d’autres supposent que vous ingérez les données directement à partir d’Adobe Experience Platform. Cette référence fournit les étapes générales à suivre, avec des liens vers des informations plus détaillées.

## Ingérer des données à partir d’Adobe Analytics classique

Ce workflow utilise le connecteur Adobe Analytics et varie selon que vous utilisez DTM ou Launch comme gestionnaire de balises.

### Avec la Dynamic Tag Management (DTM)

1. [Créez une couche de données](https://docs.adobe.com/content/help/fr-FR/analytics/implementation/prepare/data-layer.html), si ce n’est déjà fait. Une couche de données désigne une structure d’objets JavaScript sur votre site qui contient toutes les valeurs de variable utilisées dans votre mise en œuvre. Il permet un meilleur contrôle et une maintenance plus facile dans votre mise en œuvre.
1. Utilisez [DTM](https://docs.adobe.com/content/help/fr-FR/analytics/implementation/other/dtm/dtm-implementation-overview.html) pour implémenter du code sur votre site pour la collecte de données, si ce n’est déjà fait. La Dynamic Tag Management procure une couche de données unique qui pousse les données à partir de plusieurs sources.
1. Créez un [Connecteur source Adobe Analytics](https://docs.adobe.com/content/help/fr-FR/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) dans Adobe Experience Platform. Ce connecteur source ingèrera vos données Analytics dans Experience Platform dans un framework standardisé appelé [Système de modèle de données d’expérience (XDM)](https://docs.adobe.com/content/help/fr-FR/experience-platform/xdm/home.html).
1. Utilisez [Customer Journey Analytics](https://docs.adobe.com/content/help/fr-FR/analytics-platform/using/cja-overview/cja-getting-started.html) pour créer une ou plusieurs connexions et vues de données qui informeront votre reporting cross-canal.

### Avec Launch

1. [Créez une couche de données](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), si ce n’est déjà fait. Une couche de données désigne une structure d’objets JavaScript sur votre site qui contient toutes les valeurs de variable utilisées dans votre mise en œuvre. Il permet un meilleur contrôle et une maintenance plus facile dans votre mise en œuvre.
1. Utilisez [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/fr-FR/analytics/implementation/launch/overview.html) pour implémenter du code sur votre site pour la collecte de données, si ce n’est déjà fait. Launch est une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Launch propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site..
1. Créez un [Connecteur source Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) dans Adobe Experience Platform. Ce connecteur source ingèrera vos données Analytics dans Experience Platform dans un framework standardisé appelé [Système de modèle de données d’expérience (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Utilisez [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) pour créer une ou plusieurs connexions et vues de données qui informeront votre reporting cross-canal.

## Envoi de données via le Adobe Experience Platform Web SDK et le réseau Edge

[Adobe Experience Platform Web ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) SDK est une bibliothèque JavaScript côté client qui permet aux clients de Adobe Experience Cloud d’interagir avec les différents services de l’Experience Cloud via le réseau Adobe Experience Platform Edge. Vous pouvez configurer cette assimilation avec ou sans lancement.

### Sans lancement

Ce lien ne fonctionne pas : https://docs.adobe.com/content/help/en/experience-platform/edge/get-started/quick-start-without-launch.html. Est-ce encore possible sans Lancement ?

### Avec lancement

1. [Configurez l’](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension) extension AEP Web SDK pour envoyer des données à Adobe Experience Cloud à partir de propriétés web, via Adobe Experience Platform Edge Network.
1. Utilisez [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) pour créer une ou plusieurs connexions et vues de données qui informeront votre reporting cross-canal.

## Envoi de données avec assimilation par lot et assimilation en flux continu

Adobe Experience Platform rassemble des données provenant de plusieurs sources afin d’aider les professionnels du marketing à mieux comprendre le comportement de leurs clients. Adobe Experience Platform Data Ingestion représente les diverses méthodes que Platform emploie pour ingérer des données à partir de ces sources, ainsi que la manière dont ces données sont conservées dans le lac de données pour être utilisées par les services de Platform en aval.

### Ingestion par lots

1. Configurez [Ingestion par lots](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en#batch) pour que vous puissiez assimiler des données à Adobe Experience Platform sous forme de fichiers de commandes. Les données en cours d’ingestion peuvent être les données du profil d’un fichier plat dans un système CRM (par exemple un fichier parquet) ou des données conformes à un schéma connu dans le registre Experience Data Model (XDM).
1. Utilisez [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) pour créer une ou plusieurs connexions et vues de données qui informeront votre reporting cross-canal.

### Ingestion par flux

1. Configurez [l&#39;assimilation en flux continu](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en#streaming) pour envoyer en temps réel des données des périphériques client et serveur à l&#39;Experience Platform.
1. Utilisez [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) pour créer une ou plusieurs connexions et vues de données qui informeront votre reporting cross-canal.

## Insérez les données Google Analytics à analyser en Customer Journey Analytics

Consultez ce didacticiel sur la façon d&#39;[analyser les données Google Analytics à l&#39;aide de Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=en#objectives) pour obtenir des instructions détaillées.

## Utilisez l’API d’insertion de données en bloc pour obtenir des données dans Analytics, puis assimilez-les par le biais du connecteur de source d’Adobe dans l’Experience Platform.

1. [Utilisez l&#39;](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) API d&#39;insertion de données en bloc pour envoyer des données de collecte côté serveur à Adobe Analytics. Il vous permet d’envoyer des fichiers au format CSV contenant des données de événement.
1. [Créez un ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) connecteur source Adobe Analytics pour importer ces données grand public dans Adobe Experience Platform.
1. Utilisez [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) pour créer une ou plusieurs connexions et vues de données qui informeront votre reporting cross-canal.