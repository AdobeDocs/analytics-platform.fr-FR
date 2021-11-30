---
title: Ingestion de données Google Analytics dans Adobe Experience Platform
description: 'Décrit comment tirer parti de Customer Journey Analytics (CJA) pour ingérer vos données Google Analytics dans Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 100%

---


# Ingestion de données Google Analytics dans Adobe Experience Platform

Ce cas d’utilisation se concentre sur la manière d’ingérer vos données Google Analytics sous forme de jeu de données dans Adobe Experience Platform. Nous expliquons comment ingérer à la fois des données historiques et actives. Une fois cette opération terminée, vous pouvez combiner les deux jeux de données dans Customer Journey Analytics, ceci afin d’obtenir une vue entre appareils du parcours de votre utilisateur.

Les jeux de données d’Experience Platform sont constitués de deux éléments : un schéma et les enregistrements en cours dans le jeu de données. Le schéma (que nous appelons modèle de données d’expérience ou XDM en version abrégée) est semblable aux colonnes du jeu de données et est semblable au plan directeur ou aux règles qui décrivent les données elles-mêmes. Au sein de Platform, Adobe fournit deux types de schémas :

* Les schémas prêts à l’emploi auxquels vous pouvez mapper vos données Google Analytics de façon automatique (appelés schéma d’événement d’expérience).
* Les schémas personnalisés que vous pouvez créer et mapper facilement aux données Google Analytics.

L’un des plus puissants aspects du modèle de données d’Adobe est qu’il vous permet de normaliser toutes vos données d’interaction client en un schéma commun, ce qui facilite considérablement le regroupement des données dans CJA.

## Conditions préalables

Pour accomplir ces tâches, vous devez disposer des autorisations et des droits d’accès suivants :

* Un accès à Adobe Experience Platform
* Accès à Universal Google Analytics (version Google Analytics 360) ou à Google Analytics 4 (version gratuite ou version Google Analytics 360)
* Accès à Customer Journey Analytics et à ses [autorisations d’administrateur](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr#admin-access-permissions).

La façon dont vous importez les données Google Analytics dans Adobe Experience Platform dépend de la version de Google Analytics que vous utilisez :

| Si vous utilisez... | Vous avez également besoin de cette licence… | Et de faire ceci… |
| --- | --- | --- |
| **Universal Analytics** | Google Analytics 360 | Suivez les étapes 1 à 3 décrites dans les instructions ci-dessous. |
| **Google Analytics 4** | Version GA gratuite ou Google Analytics 360 | Suivez les étapes 1 et 3 décrites dans les instructions ci-dessous. Pas besoin de passer par l’étape 2. |

## Ingestion de données historiques (de renvoi)

### 1. Connexion de vos données Google Analytics à BigQuery

Pour plus d’informations, reportez-vous à [ces instructions](https://support.google.com/analytics/answer/3416092?hl=fr). Veuillez noter que ces instructions sont basées sur Universal Google Analytics.

### 2. Transformation de sessions Google Analytics en événements dans BigQuery et exportation vers Google Cloud Storage

>[!IMPORTANT]
>
>Cette étape s’applique uniquement aux clients d’Universal Analytics.

Les données GA stockent chaque enregistrement dans leurs données sous la forme d’une session d’utilisateur plutôt que d’événements individuels. Vous devez créer une requête SQL pour transformer les données Universal Analytics en un format compatible avec Experience Platform. Vous appliquez la fonction « unnest » au champ « hits » dans le schéma GA. Voici l’exemple SQL que vous pouvez utiliser :

```
SELECT
   *,
   timestamp_seconds(`visitStartTime` + hit.time) AS `timestamp` 
FROM
   (
      SELECT
         fullVisitorId,
         visitNumber,
         visitId,
         visitStartTime,
         trafficSource,
         socialEngagementType,
         channelGrouping,
         device,
         geoNetwork,
         hit 
      FROM
         `your_bq_table_2021_04_*`,
         UNNEST(hits) AS hit 
   )
```

Une fois la requête terminée, enregistrez les résultats complets dans un tableau BigQuery.

Reportez-vous à [ces instructions](https://support.google.com/analytics/answer/7029846?hl=fr&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql), qui incluent des instructions sur la requête SQL.

La vidéo suivante détaille également la prochaine étape, qui consiste à exporter les événements Google Analytics vers Google Cloud Storage au format JSON. Il vous suffit de cliquer sur **Exporter > Exporter vers GCS**. Alors, les données sont prêtes à être extraites dans Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Importation des données de Google Cloud Storage dans Experience Platform et mappage au schéma XDM

Dans Experience Platform, sélectionnez **[!UICONTROL Sources]** et recherchez l’option **[!UICONTROL Google Cloud Storage]**. À partir de là, il vous suffit de trouver le jeu de données que vous avez enregistré depuis BigQuery.

N’oubliez pas ce qui suit :

* Assurez-vous de sélectionner le format JSON.
* Vous pouvez sélectionner un jeu de données existant ou en créer un nouveau (recommandé).
* Assurez-vous de sélectionner le même schéma pour les données Google Analytics historiques et les données Google Analytics en flux continu actives, même si elles se trouvent dans des jeux de données distincts. Vous pouvez ensuite fusionner les jeux de données dans une [connexion CJA](/help/connections/combined-dataset.md).

Pour obtenir des instructions détaillées, regardez cette vidéo :

>[!VIDEO](https://video.tv.adobe.com/v/332676)

Vous pouvez mapper les données d’événement GA dans un jeu de données existant créé précédemment, ou créer un jeu de données en utilisant le schéma XDM de votre choix. Une fois que vous avez sélectionné le schéma, Experience Platform applique le machine learning pour pré-mapper automatiquement chacun des champs des données Google Analytics à votre [schéma XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr#ui).

![](assets/schema-map.png)

Les mappages sont très faciles à modifier. Vous pouvez même créer des champs dérivés ou calculés à partir des données Google Analytics. Une fois que vous avez terminé de mapper les champs dans votre schéma XDM, vous pouvez planifier cette importation de manière récurrente et appliquer une validation d’erreur pendant le processus d’ingestion. Cela permet de s’assurer qu’il n’y a aucun problème avec les données que vous avez importées.

**Champ calculé « Date et heure »**

Pour le champ de schéma `timestamp` dans les données Google Analytics, vous devez créer un champ calculé spécial dans l’interface utilisateur du schéma Experience Platform. Cliquez sur **[!UICONTROL Ajouter champ calculé]** et renvoyez la chaîne `timestamp` dans une fonction `date`, comme dans l’exemple suivant :

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

Vous devez ensuite enregistrer ce champ calculé dans la structure des données de date et heure du schéma :

![](assets/timestamp.png)

**Champ calculé « _id »**

Le champ de schéma `_id` doit comporter une valeur. CJA ne se soucie pas de cette valeur. Vous pouvez simplement ajouter un « 1 » au champ suivant :

![](assets/_id.png)

## Ingestion de données Google Analytics en flux continu actives

Vous pouvez également capturer des événements de flux continu actifs depuis Google Tag Manager directement vers Adobe Experience Platform.

### 1. Ajout de variables personnalisées

Après vous être connecté au compte Google Tag Manager, vous devez ajouter certaines variables constantes personnalisées liées à Adobe. Vous disposez probablement déjà de variables dans Google Tag Manager qui sont envoyées à Google Analytics, telles que l’e-mail du client, le nom du client, la langue et l’état de connexion du client. Vous devez définir 5 nouvelles variables personnalisées :

* ID d’organisation Adobe Experience Cloud
* Point d’entrée DCS en flux continu
* ID de jeu de données Experience Platform
* Référence du schéma
* Date et heure de page

L’obtention de ces valeurs permet de s’assurer que toutes les données Google Analytics sont envoyées au jeu de données adéquat et qu’elles disposent du schéma approprié. Si votre organisation Experience Cloud ou l’une des autres variables mentionnées ci-dessus vous est inconnue, contactez votre gestionnaire de compte Adobe afin de retrouver cet élément.

Une fois que vous avez défini ces variables personnalisées, nous pouvons configurer un déclencheur. Celui-ci permettra d’envoyer toutes les données que vous envoyez déjà à Google Analytics vers Experience Platform également.

### 2. Configuration d’un déclencheur dans Google Tag Manager

Dans cet exemple, le déclencheur « Création de compte » a été défini, où `pageUrl equals account-creation`. En ajoutant des informations à ce déclencheur, vous pouvez vous assurer que lorsque l’utilisateur s’authentifie avec succès et que la page de création de compte se charge, les données sont envoyées à Google Analytics et à AEP.

Vous pouvez également vous reporter aux informations sur l’[ingestion de données et Google Tag Manager](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=fr#module9).

Pour obtenir des instructions détaillées, regardez cette vidéo :

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## Création d’une connexion vers le jeu de données Google Analytics dans CJA

Une fois qu’Adobe Experience Platform a commencé à recevoir les données Google Analytics actives et que vous avez renvoyé les données Google Analytics historiques depuis BigQuery, vous voilà prêt à utiliser CJA afin de [créer votre première connexion](/help/connections/create-connection.md). Cette connexion regroupe les données GA avec toutes les autres données client à l’aide d’un « ID client » commun.

## Étapes suivantes

* Créez une [vue de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=fr#cja-dataviews) basée sur la connexion contenant les données Google Analytics.

* Effectuez une [analyse époustouflante dans Workspace](/help/use-cases/ga-to-cja-reporting.md).