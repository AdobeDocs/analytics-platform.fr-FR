---
title: Configurer des données de Google Analytics en streaming
description: Découvrez comment configurer votre implémentation afin d’envoyer une couche de données Google dans Adobe Experience Platform.
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
source-git-commit: 8262539078c57e32bc3195ef669325fa4889bea0
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 89%

---

# Configurer des données de Google Analytics en streaming

Cette page se concentre sur la manière d’ingérer vos données dynamiques Google Analytics dans Adobe Experience Platform, ce qui vous permet de référencer ce jeu de données dans une vue de données de Customer Journey Analytics. Vous pouvez associer les étapes de cette page à [l’ingestion de données historiques Google Analytics dans Adobe Experience Platform](backfill.md), qui génère un jeu de données contenant des données historiques. Combinez un jeu de données en flux continu avec un jeu de données de renvoi pour obtenir une vue transparente des données antérieures et présentes dans Customer Journey Analytics.

La configuration de la collecte de données implique les étapes suivantes :

1. Implémentez les [Balises pour Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr). Voir [Guide de démarrage rapide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) pour qu’une implémentation de base soit opérationnelle.
1. Installez l‘[Extension de la couche de données Google](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). Cette extension sert d’alternative à l’installation de l’extension du SDK Web, orientée spécifiquement vers une couche de données Google.
1. [Créez un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) dans la collecte de données Adobe Experience Platform. Configurez le flux de données pour envoyer des données à Adobe Experience Platform. Vous devez actuellement mapper chaque objet de la couche de données Google à un champ XDM applicable ici. Adobe prévoit de simplifier ce workflow de mappage à l’avenir.

Une fois que vous avez implémenté et publié les balises souhaitées sur votre site, vous pouvez passer à [créer une connexion](/help/connections/create-connection.md), puis [créer une vue de données](/help/data-views/create-dataview.md).
