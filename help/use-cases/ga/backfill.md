---
title: Ingestion de données historiques Google Analytics dans Adobe Experience Platform
description: Explique comment utiliser Customer Journey Analytics (CJA) pour ingérer vos données Google Analytics dans Adobe Experience Platform.
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: f65f13d696ad2045f58ccb5c9ef7fed45eb9d68c
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 9%

---


# Ingestion de données historiques Google Analytics dans Adobe Experience Platform

Cette page se concentre sur la manière d’ingérer vos données historiques Google Analytics dans Adobe Experience Platform en tant que jeu de données, ce qui vous permet de référencer ce jeu de données dans une vue de données dans Customer Journey Analytics. Vous pouvez associer les étapes de cette page à [Configuration d’une mise en oeuvre de Google Analytics en direct](streaming.md), qui génère un jeu de données récurrent. Combinez ce jeu de données historique avec le jeu de données de votre mise en oeuvre actuelle afin d’obtenir une vue transparente des données en Customer Journey Analytics avec les données actives et renvoyées.

## Conditions préalables

Pour accomplir ces tâches, vous devez disposer des autorisations et des droits d’accès suivants :

* Un accès à Adobe Experience Platform
* Accès aux Google Analytics (GA Standard ou GA 360)
* [Accès administrateur](/help/getting-started/cja-access-control.md) à Customer Journey Analytics

## Configuration d’une exportation BigQuery

La structure de données dans les propriétés Analytics universelles est différente de la structure de données dans les propriétés Google Analytics 4. Configurez une exportation BigQuery en fonction du type de propriété à partir duquel vous souhaitez exporter des données :

* [Configuration d’une exportation BigQuery pour une propriété Universal Analytics](https://support.google.com/analytics/answer/3416092)
* [Configuration d’une exportation BigQuery pour une propriété Google Analytics 4](https://support.google.com/analytics/answer/9823238)

### Autres configurations requises pour les propriétés Analytics universelles

>[!NOTE]
>
>Cette section s’applique uniquement aux propriétés Universal Analytics. Si vous exportez à partir d’une propriété GA4, vous pouvez passer à [Exportation de données vers Google Cloud Platform](#export-gcp).

Les propriétés Analytics universelles stockent chaque enregistrement dans leurs données sous la forme d’une session d’utilisateur plutôt que d’événements individuels. Une requête SQL pour transformer les données Analytics universelles en un format compatible avec Adobe Experience Platform est requise. Appliquez la variable `UNNEST` vers la fonction `hits` dans le schéma GA, et enregistrez-le en tant que table BigQuery.

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

## Exportation de données vers Google Cloud Platform {#export-gcp}

Dans Google Cloud Platform, accédez à **Exporter > Exporter vers GCS**. Une fois que les données se trouvent dans le stockage cloud Google, elles sont prêtes à être extraites dans Adobe Experience Platform.

## Importation des données de Google Cloud Storage dans Experience Platform

1. Dans Adobe Experience Platform, sélectionnez **[!UICONTROL Sources]** sur la gauche.
1. Sous le catalogue, recherchez **[!UICONTROL Stockage dans le cloud Google]** . Cliquez sur **[!UICONTROL Ajouter des données]**.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>Si vous prévoyez d’importer des données de Google Analytics de diffusion en continu historiques et en direct, veillez à utiliser le même schéma pour les deux jeux de données. Vous pouvez fusionner les jeux de données dans un CJA à l’aide d’une [Jeu de données combiné](/help/connections/combined-dataset.md).

Vous pouvez mapper les données d’événement GA dans un jeu de données existant que vous avez créé précédemment ou créer un jeu de données, à l’aide du schéma XDM de votre choix. Une fois que vous avez sélectionné le schéma, Experience Platform applique le machine learning pour pré-mapper automatiquement chacun des champs des données Google Analytics à votre [schéma XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr#ui).

![Schéma map](../assets/schema-map.png)

Une fois que vous avez terminé de mapper les champs dans votre schéma XDM, vous pouvez planifier cet import de manière récurrente et appliquer la validation des erreurs pendant le processus d’ingestion. Cette validation permet de s’assurer qu’il n’y a aucun problème avec les données que vous avez importées.

## Champs XDM obligatoires

Certains champs XDM de Platform nécessitent le format correct pour que les données soient correctement traitées.

* **`timestamp`**: Créez un champ calculé spécial dans l’interface utilisateur du schéma Experience Platform. Cliquez sur **[!UICONTROL Ajouter un champ calculé]** et encapsulez la variable `timestamp` chaîne dans une `date` function:

   `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

   Enregistrez le champ calculé dans la structure de données de l’horodatage du schéma :

   ![Horodatage](../assets/timestamp.png)

* **`_id`**: Ce champ doit comporter une valeur : CJA ne se soucie pas de la valeur. Vous pouvez ajouter un &quot;1&quot; au champ :

   ![ID](../assets/_id.png)

## Étapes suivantes

* Si vous souhaitez diffuser des données en cours dans Adobe Experience Platform, reportez-vous à la section [Configuration de la diffusion en continu pour les données Google Analytics](streaming.md).
* Si vous souhaitez commencer à créer des rapports sur les données renvoyées, reportez-vous à la section [Création d’une connexion](/help/connections/create-connection.md).
