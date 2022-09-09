---
title: Configuration des données de Google Analytics en flux continu dans Adobe Experience Platform
description: Découvrez comment configurer votre mise en oeuvre pour envoyer une couche de données Google dans Adobe Experience Platform
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 2%

---

# Configuration des données de Google Analytics en flux continu dans Adobe Experience Platform

Cette page se concentre sur la manière d’ingérer vos données de Google Analytics actives dans Adobe Experience Platform, ce qui vous permet de référencer ce jeu de données dans une vue de données dans Customer Journey Analytics. Vous pouvez associer les étapes de cette page à [Ingestion de données historiques Google Analytics dans Adobe Experience Platform](backfill.md), qui génère un jeu de données contenant des données historiques. Combinez un jeu de données de diffusion en continu avec un jeu de données de renvoi pour obtenir une vue transparente des données présentes et antérieures dans Customer Journey Analytics.

La configuration de la collecte de données implique les étapes suivantes :

1. Mise en oeuvre [Balises pour Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr). Voir [Guide de démarrage rapide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) pour qu’une mise en oeuvre de base soit opérationnelle.
1. Installez le [Extension de la couche de données Google](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). Cette extension sert de alternative à l’installation de l’extension SDK Web, orientée spécifiquement vers une couche de données Google.
1. [Création d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) dans la collecte de données Adobe Experience Platform. Configurez le flux de données pour envoyer des données à Adobe Experience Platform. Vous devez actuellement mapper chaque objet de couche de données Google à un champ XDM applicable ici. Adobe prévoit de simplifier ce workflow de mappage à l’avenir.

Une fois que vous avez implémenté et publié les balises souhaitées sur votre site, vous pouvez passer à la [Création d’une connexion](/help/connections/create-connection.md), puis [Création d’une vue de données](/help/data-views/create-dataview.md).
