---
title: Options d'assimilation des données pour le Customer Journey Analytics
description: Comprendre les différentes manières d'assimiler des données dans un Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 32dd6194ab2777652c3fb7df5fadd42395a0697d
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 31%

---


# Options d&#39;assimilation des données pour le Customer Journey Analytics

Plusieurs options s’offrent à vous pour l’assimilation de données dans le Customer Journey Analytics. Certains supposent que vous voulez déplacer les données Adobe Analytics traditionnelles, d&#39;autres supposent que vous ingérez les données directement à partir de Adobe Experience Platform. Cette référence fournit les étapes de haut niveau à suivre.

## Envoi de données à partir de l’Adobe Analytics traditionnel

Ce processus utilise le connecteur de données Adobe Analytics et varie selon que vous utilisez la gestion dynamique des balises ou le lancement comme gestionnaire de balises.

### Via la gestion dynamique des balises (DTM)

1. [Créer une couche de données](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), si vous ne l&#39;avez pas déjà fait. Une couche de données désigne une structure d’objets JavaScript sur votre site qui contient toutes les valeurs de variable utilisées dans votre mise en œuvre. Il permet un meilleur contrôle et une maintenance plus facile dans votre mise en œuvre.
1. Utiliser [DTM](https://docs.adobe.com/content/help/fr-FR/analytics/implementation/other/dtm/dtm-implementation-overview.html) pour implémenter du code sur votre site pour la collecte de données, si ce n’est déjà fait. Dynamic Tag Management procure une couche de données unique qui pousse les données à partir de plusieurs sources.
1. Créez une [Connecteur source Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) à Adobe Experience Platform. Ce connecteur source va intégrer vos données Analytics dans un Experience Platform dans une structure standardisée appelée [Système de modèle de données d’expérience (XDM)](https://docs.adobe.com/content/help/fr-FR/experience-platform/xdm/home.html).
1. Utiliser [Customer Journey Analytics](https://docs.adobe.com/content/help/fr-FR/analytics-platform/using/cja-overview/cja-getting-started.html) pour créer une ou plusieurs connexions et vues de données qui informeront votre rapports inter-canaux.

### Via Launch

1. [Créer une couche de données](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), si vous ne l&#39;avez pas déjà fait. Une couche de données désigne une structure d’objets JavaScript sur votre site qui contient toutes les valeurs de variable utilisées dans votre mise en œuvre. Il permet un meilleur contrôle et une maintenance plus facile dans votre mise en œuvre.
1. Utiliser [adobe experience platform launch](https://docs.adobe.com/content/help/en/analytics/implementation/launch/overview.html) pour implémenter du code sur votre site pour la collecte de données, si ce n’est déjà fait. Launch est une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Lancez des intégrations d’offres à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site..
1. Créez une [Connecteur source Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) à Adobe Experience Platform. Ce connecteur source va intégrer vos données Analytics dans un Experience Platform dans une structure standardisée appelée [Système de modèle de données d’expérience (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Utiliser [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) pour créer une ou plusieurs connexions et vues de données qui informeront votre rapports inter-canaux.

## Envoi de données à partir du SDK Web AEP

À déterminer

### Via Experience Edge

À déterminer

### Via Launch

À déterminer

## assimilation par lots et assimilation en flux continu

À déterminer

## Envoi de données Google Analytics

À déterminer

## Envoi de données via l&#39;API d&#39;importation en masse

À déterminer