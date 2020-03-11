---
title: Prise en main d’Analytics de parcours du client
description: Prise En Main De L’Analyse De Voyage Du Client.
translation-type: tm+mt
source-git-commit: 12ab54b09caea3b7bb5fbc345ba5e396c198a36c

---


# Prise en main d’Analytics de parcours du client

Pour mettre en oeuvre Customer Journey Analytics, vous devez suivre ce processus. Certains  initiaux sont effectués dans Adobe Experience Platform et d’autres dans Customer Journey Analytics.

| Tâche | Où effectué | Détails |
|---|---|---|
| **Étape 1 : Obtenir vos données dans Adobe Experience Platform** | Adobe Experience Platform |  |
| **Étape 2 : Préparation de votre de données** | Adobe Experience Platform | Utilisez [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) pour normaliser les données d’expérience client et définir des  de pour la gestion de l’expérience client. |
| **Étape 3 : Création d’un jeu de données basé sur le** | Adobe Experience Platform | Les données de la plate-forme sont constituées d’ensembles de données, tels que les jeux de données de courrier électronique, les jeux de données CRM, les jeux de données POS, le jeu de données Adobe Analytics, etc. Chaque jeu de données se compose d’un  et de lots de données. Vous pouvez créer un jeu de données [dans la plateforme](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)d’expérience.<br>Bien que le  des jeux de données pouvant être importés dans les analyses de parcours du client soit flexible, il doit être conforme à certaines règles de base. Il est préférable de s’assurer que vos données répondent à ces exigences avant de les télécharger dans Platform. (Notez que le inclut des mesures et des dimensions.)<br>Il existe trois types de données compatibles avec les analyses de parcours du client :<ul><li>**Données** : Données qui représentent des  dans le temps (par exemple, visites Web, interactions, transactions, données POS, données de , données d’impression, etc.). Il s’agit généralement de données de parcours de navigation, avec un ID de client ou un ID de cookie, ainsi qu’un horodatage. Avec les données de , nous vous permettons d&#39;utiliser n&#39;importe quel ID.</li><li>**Données** de recherche : Ces données sont utilisées pour rechercher des valeurs ou des clés trouvées dans vos données de  ou de. Vous pouvez, par exemple, télécharger des données de recherche qui mappent des ID numériques dans vos données de  aux noms de produits.</li><li>**Données** : Données appliquées à vos, utilisateurs ou clients dans les données  du. Vous permet, par exemple, de transférer des données CRM sur vos clients.</li></ul> |
| **Etape 3 : création de connexions entre les jeux de données de plateformes et les analyses de parcours du client** | Analytics du parcours client | Voir [Création d’une connexion](/help/connections/create-connection.md). |
| **Étape 4 : Création d’un de données** | Analytics du parcours client | See [Create a data view](/help/data-views/create-dataview.md). |
| **Étape 5 : Rapport sur vos données  inter-dans Workspace** | Analytics du parcours client | Voir [Exécution d’un](/help/projects/perform-basic-analysis.md)  de base et [Exécution d’un](/help/projects/perform-adv-analysis.md)de  avancé. |

## Conditions préalables

Les analyses de parcours du client sont disponibles pour les clients qui

* Adobe Analytics [Select, Prime ou Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) clients et
* sont configurés pour [Adobe Experience Platform](https://www.adobe.com/experience-platform.html)et
* Avoir acheté le SKU Analyse de parcours du client

## Préparation de votre de données 

[Création d’un  à l’aide de l’éditeur de  de](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## Étape 1 : Obtenir vos données dans Adobe Experience Platform

Avant de pouvoir exploiter les données de la plateforme d’expérience dans CJA, vous devez assimiler ces données dans la plateforme. Il existe plusieurs façons de procéder :

* Si vous souhaitez importer vos données Adobe Analytics existantes, utilisez Adobe Analytics Platform Connector.
* Pour importer d’autres données, utilisez des fichiers au format .csv ou Parquet pour


## Étape 1 a : Intégrer vos données Analytics existantes dans Adobe Experience Platform

Utilisez Adobe Analytics Platform Connector pour importer des données Analytics traditionnelles dans la plate-forme. Vous pouvez créer une connexion source par suite de rapports. Voir [Création d’une connexion source avec Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) dans la documentation d’Adobe Experience Platform.

Une fois la connexion créée, un  et un jeu de données sont automatiquement créés pour contenir les données entrantes. De plus, le renvoi des données se produit et ingère jusqu’à 13 mois de données historiques. Une fois l’assimilation initiale terminée, vous pouvez passer à l’étape x pour créer une connexion entre ce jeu de données Analytics et les analyses de parcours du client.

## Étape 1 b: Création d’un 




