---
title: Options d’ingestion des données pour Customer Journey Analytics
description: Comprendre les différentes manières d’ingérer des données dans Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 4ea06ca1f13255c570ccc9f69cb328d57bf975b2
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 97%

---


# Options d’ingestion des données pour Customer Journey Analytics

Plusieurs options s’offrent à vous pour l’ingestion de données dans Customer Journey Analytics. Certaines de ces options supposent que vous voulez déplacer les données Adobe Analytics classique, d’autres supposent que vous ingérez les données directement à partir d’Adobe Experience Platform. Cette référence fournit des étapes de haut niveau à suivre, avec des liens vers des informations plus détaillées.

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
