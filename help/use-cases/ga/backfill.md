---
title: Ingérer les données historiques Google Analytics dans Adobe Experience Platform
description: Décrit comment tirer parti de Customer Journey Analytics (CJA) pour ingérer vos données Google Analytics dans Adobe Experience Platform.
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: eceea9ef96701f66cceed5bcb50f92588df6e507
workflow-type: ht
source-wordcount: '620'
ht-degree: 100%

---


# Ingérer les données historiques Google Analytics dans Adobe Experience Platform

Cette page explique comment ingérer vos données historiques Google Analytics dans Adobe Experience Platform sous la forme de jeu de données, ce qui vous permet de référencer ce jeu au sein d’une vue de données dans Customer Journey Analytics. Vous pouvez associer les étapes de cette page à [Configurer une implémentation de Google Analytics en direct](streaming.md), ce qui génère un jeu de données récurrent. Combinez ce jeu de données historique avec le jeu de données de votre implémentation actuelle afin d’obtenir une vue transparente des données de Customer Journey Analytics avec les données actives et renvoyées.

## Conditions préalables

Pour accomplir ces tâches, vous devez disposer des autorisations et des droits d’accès suivants :

* Un accès à Adobe Experience Platform
* Accès à Google Analytics (GA Standard ou GA 360)
* [Accès administrateur](/help/admin/cja-access-control.md) à Customer Journey Analytics.

## Configurer une exportation BigQuery

La structure de données dans les propriétés Universal Analytics est différente de celle dans les propriétés Google Analytics 4. Configurez une exportation BigQuery en fonction du type de propriété à partir duquel vous souhaitez exporter des données :

* [Configurer une exportation BigQuery pour une propriété Universal Analytics](https://support.google.com/analytics/answer/3416092)
* [Configurer une exportation BigQuery pour une propriété Google Analytics 4](https://support.google.com/analytics/answer/9823238)

### Autres configurations requises pour les propriétés Universal Analytics

>[!NOTE]
>
>Cette section s’applique uniquement aux propriétés Universal Analytics. Si vous exportez à partir d’une propriété GA4, vous pouvez passer à [Exporter les données vers Google Cloud Platform](#export-gcp).

Les propriétés Universal Analytics stockent chaque enregistrement dans leurs données sous la forme d’une session d’utilisateur au lieu d’événements individuels. Afin de transformer les données Universal Analytics en un format compatible avec Adobe Experience Platform, une requête SQL est requise. Appliquez la fonction `UNNEST` au champ `hits` dans le schéma GA, et enregistrez-le en tant que table BigQuery.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

```sql
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
         `example_bq_table_*`,
         UNNEST(hits) AS hit 
   )
```

## Exporter des données vers Google Cloud Platform {#export-gcp}

Dans Google Cloud Platform, accédez à **Exporter > Exporter vers GCS**. Une fois que les données se trouvent dans Google Cloud Storage, elles sont prêtes à être extraites dans Adobe Experience Platform.

## Importer les données de Google Cloud Storage dans Experience Platform

1. Dans Adobe Experience Platform, sélectionnez **[!UICONTROL Sources]** sur la gauche.
1. Sous le catalogue, recherchez l’option **[!UICONTROL Google Cloud Storage]**. Cliquez sur **[!UICONTROL Ajouter des données]**.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>Si vous prévoyez d’importer à la fois des données Google Analytics historiques et en flux continu, veillez à utiliser le même schéma pour les deux jeux de données. Vous pouvez fusionner les jeux de données dans un CJA à l’aide d’un [jeu de données combiné](/help/connections/combined-dataset.md).

Vous pouvez mapper les données d’événement GA dans un jeu de données existant créé précédemment, ou créer un jeu de données en utilisant le schéma XDM de votre choix. Une fois que vous avez sélectionné le schéma, Experience Platform applique le machine learning pour pré-mapper automatiquement chacun des champs des données Google Analytics à votre [schéma XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr#ui).

![Mappage du schéma](../assets/schema-map.png)

Une fois que vous avez terminé de mapper les champs dans votre schéma XDM, vous pouvez planifier cette importation de manière récurrente et appliquer une validation d’erreur pendant le processus d’ingestion. Cette validation permet de s’assurer qu’il n’y a aucun problème avec les données que vous avez importées.

## Champs XDM obligatoires

Certains champs XDM de Platform nécessitent le bon format pour que les données soient correctement traitées.

* **`timestamp`** : Créez un champ calculé spécial dans l’interface utilisateur du schéma Experience Platform. Cliquez sur **[!UICONTROL Ajouter champ calculé]** et enroulez la chaîne `timestamp` dans une fonction `date` :

   `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

   Enregistrez le champ calculé dans la structure de données d’horodatage du schéma :

   ![Horodatage](../assets/timestamp.png)

* **`_id`** : Le champ doit comporter une valeur. CJA ne se soucie pas de cette valeur. Vous pouvez ajouter un « 1 » au champ :

   ![ID](../assets/_id.png)

## Étapes suivantes

* Si vous souhaitez diffuser des données actuelles dans Adobe Experience Platform, reportez-vous à la section [Configurer la diffusion en continu pour les données Google Analytics](streaming.md).
* Si vous souhaitez commencer à créer des rapports sur les données renvoyées, reportez-vous à la section [Créer une connexion](/help/connections/create-connection.md).
