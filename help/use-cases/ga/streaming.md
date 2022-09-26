---
title: Configurer les données en flux continu de Google Analytics dans Adobe Experience Platform
description: Découvrez comment configurer votre implémentation afin d’envoyer une couche de données Google dans Adobe Experience Platform.
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: ht
source-wordcount: '259'
ht-degree: 100%

---

# Configurer les données en flux continu de Google Analytics dans Adobe Experience Platform

Cette page se concentre sur la manière d’ingérer vos données dynamiques Google Analytics dans Adobe Experience Platform, ce qui vous permet de référencer ce jeu de données dans une vue de données de Customer Journey Analytics. Vous pouvez associer les étapes de cette page à [l’ingestion de données historiques Google Analytics dans Adobe Experience Platform](backfill.md), qui génère un jeu de données contenant des données historiques. Combinez un jeu de données en flux continu avec un jeu de données de renvoi pour obtenir une vue transparente des données antérieures et présentes dans Customer Journey Analytics.

La configuration de la collecte de données implique les étapes suivantes :

1. Implémentez les [Balises pour Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr). Voir [Guide de démarrage rapide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) pour qu’une implémentation de base soit opérationnelle.
1. Installez l‘[Extension de la couche de données Google](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). Cette extension sert d’alternative à l’installation de l’extension du SDK Web, orientée spécifiquement vers une couche de données Google.
1. [Créez un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) dans la collecte de données Adobe Experience Platform. Configurez le flux de données pour envoyer des données à Adobe Experience Platform. Vous devez actuellement mapper chaque objet de la couche de données Google à un champ XDM applicable ici. Adobe prévoit de simplifier ce workflow de mappage à l’avenir.

Une fois que vous avez implémenté et publié les balises souhaitées sur votre site, vous pouvez passer à la [Création d’une connexion](/help/connections/create-connection.md), puis à la [Création d’une vue de données](/help/data-views/create-dataview.md).
