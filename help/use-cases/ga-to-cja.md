---
title: Configuration du rapports Google Analytics dans le Customer Journey Analytics
description: null
translation-type: tm+mt
source-git-commit: c07d32eef579432bf92f94cbbe4e99188b2de74c
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 3%

---


# Configuration du rapports Google Analytics dans le Customer Journey Analytics

configuration de Google Cloud Enregistrement Connector,

configurer Google Tag Manager

Schéma d&#39;exportation BigQuery (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)

1. Conversion de sessions GA en événements dans les grandes Requêtes
1. Exportation de événements Google Analytics vers l’Enregistrement Google Cloud
1. Importer des événements GCS dans Adobe Experience Platform et mapper sur un schéma XDM

## Conditions préalables

* Un accès à Adobe Experience Platform
* Accès aux Google Analytics universels (version Google Analytics 360) ou aux Google Analytics 4 (version gratuite ou version Google Analytics 360)
* Accès au Customer Journey Analytics

## 1. Connectez les données Google Analytics à Adobe Experience Platform.

La manière d&#39;importer les données Google Analytics dans Adobe Experience Platform dépend de la version de Google Analytics que vous utilisez :

| Si vous utilisez... | Vous avez aussi besoin de cette licence... | Et fais ça... |
| --- | --- | --- |
| **Google Analytics universel** | Google Analytics 360 | Exécutez les étapes 1 à x des instructions ci-dessous |
| **Google Analytics 4** | Version GA gratuite ou Google Analytics 360 | Il n’est pas nécessaire de suivre l’étape x dans les instructions ci-dessous. |

Les instructions suivantes sont basées sur le Google Analytics universel.

1. Connectez vos données Google Analytics à BigQuery et
Reportez-vous à [ces instructions](https://support.google.com/analytics/answer/3416092?hl=en).
1. (Utilisateurs d’Analytics universels uniquement) Transformez les sessions de Google Analytics en événements dans BigQuery. Cela rend les données compatibles avec Adobe Experience Platform. Reportez-vous à [ces instructions](https://support.google.com/analytics/answer/3437618?hl=en).

   Détails : Dans BigQuery, vos données GA s’affichent sous forme de tableau :

   ![](assets/ga-bigquery.png)
Vous devez créer une requête SQL pour transformer les données Universal Analytics en un format compatible Experience Platform.
   * Vue de cette vidéo pour obtenir des instructions.

1. Exportez des événements Google Analytics au format JSON dans l’Enregistrement Google Cloud et enregistrez-les dans un compartiment.
Reportez-vous à [ces instructions](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).
1. Apportez les données de l’Enregistrement Google Cloud dans l’Experience Platform. (obtenez la vidéo de la diapositive 10 de Trevor.)

