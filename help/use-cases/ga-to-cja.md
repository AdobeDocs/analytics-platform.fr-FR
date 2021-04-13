---
title: Comment obtenir des données Google Analytics dans Adobe Experience Platform pour analyse en Customer Journey Analytics (CJA)
description: 'Explique comment tirer parti du Customer Journey Analytics (CJA) pour intégrer vos Google Analytics et vos données de base de feu dans Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 793b2ce4ec8a487f6c4290fe2eff00879fcca13d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 3%

---


# Envoi de données Google Analytics dans Adobe Experience Platform

Ce cas d’utilisation se concentre sur la manière d’assimiler vos données Google Analytics en tant que jeu de données dans Adobe Experience Platform. (Ceci s’applique aux données historiques et actives.) Une fois cette opération effectuée, vous pouvez combiner les deux jeux de données pour obtenir une vue sur plusieurs périphériques du parcours de votre utilisateur.

Les jeux de données de l&#39;Experience Platform sont composés de deux éléments : un schéma et les enregistrements réels dans le jeu de données. Le schéma (nous l’appelons le modèle de données d’expérience ou XDM pour faire court) est semblable aux colonnes du jeu de données et est semblable au modèle ou aux règles qui décrivent les données elles-mêmes. Au sein de la plate-forme, Adobe fournit deux types de schémas :

* Schémas prêts à l’emploi auxquels vous pouvez associer automatiquement vos données Google Analytics (appelés schéma de Événement d’expérience)
* Schémas personnalisés que vous pouvez créer et associer facilement aux données Google Analytics

L’un des aspects les plus puissants du modèle de données d’Adobe est qu’il vous permet de normaliser toutes vos données d’interaction avec la clientèle en un seul schéma commun, ce qui facilite considérablement la mise en jonction des données dans CJA.

## Conditions préalables

Pour accomplir ces tâches, vous devez disposer des autorisations et des droits d’accès suivants :

* Un accès à Adobe Experience Platform
* Accès aux Google Analytics universels (version Google Analytics 360) ou aux Google Analytics 4 (version gratuite ou version Google Analytics 360)
* Accès au Customer Journey Analytics et à ses [autorisations d’administrateur](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr-FR#admin-access-permissions).

La manière d&#39;importer les données Google Analytics dans Adobe Experience Platform dépend de la version de Google Analytics que vous utilisez :

| Si vous utilisez... | Vous avez aussi besoin de cette licence... | Et fais ça... |
| --- | --- | --- |
| **Google Analytics universel** | Google Analytics 360 | Exécutez les étapes 1 à 5 des instructions ci-dessous |
| **Google Analytics 4** | Version GA gratuite ou Google Analytics 360 | Exécutez les étapes 1 et 3 à 5 des instructions ci-dessous. Pas besoin de passer à l&#39;étape 2. |

## 1. Connectez vos données Google Analytics à BigQuery.

Notez que les instructions suivantes sont basées sur le Google Analytics universel.

Reportez-vous à [ces instructions](https://support.google.com/analytics/answer/3416092?hl=en).

## 2. Transformez les sessions Google Analytics en événements dans BigQuery

>[!IMPORTANT]
>
>Cette étape s’applique uniquement aux clients d’Universal Analytics.

Les données GA stockent chaque enregistrement dans leurs données sous la forme d’une session d’utilisateur plutôt que de événements individuels. La transformation des données rend les données compatibles avec Adobe Experience Platform.

Reportez-vous à [ces instructions](https://support.google.com/analytics/answer/3437618?hl=en).

Vous devez créer une requête SQL pour transformer les données Universal Analytics en un format compatible Experience Platform. Vue de cette vidéo pour obtenir des instructions :

>[!VIDEO](https://video.tv.adobe.com/v/332634)

## 3. Exportez des événements Google Analytics au format JSON dans l’Enregistrement Google Cloud et enregistrez-les dans un compartiment.

Reportez-vous à [ces instructions](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

## 4. Intégrer les données de l’Enregistrement Google Cloud dans l’Experience Platform

Vue de cette vidéo pour obtenir des instructions :

>[!VIDEO](https://video.tv.adobe.com/v/332641)

## 5. Importez des événements GCS dans Adobe Experience Platform et faites correspondre les données au schéma XDM.

Schéma d&#39;exportation BigQuery (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
