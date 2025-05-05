---
title: Experience Platform Query Service (Data Distiller) et exportation de jeux de données
description: Décrit comment utiliser Query Service (Data Distiller) et l’exportation de jeux de données pour exporter des données.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 14a90758-91eb-4610-8802-1edfdb8b9689
source-git-commit: 3568aad27001b322da77f5d1fb762db5ba6d433d
workflow-type: tm+mt
source-wordcount: '2642'
ht-degree: 9%

---

# Query Service (Data Distiller) et exportation de jeux de données

Cet article décrit comment la combinaison de l’exportation de jeux de données et Experience Platform Query Service (Data Distiller) peut être utilisée pour mettre en oeuvre les [cas d’utilisation de l’exportation de données](overview.md) suivants :

- Validation des données
- Lac de données, Data Warehouse des outils de BI
- Préparation à l’apprentissage intelligent et automatique artificiel.


Adobe Analytics peut mettre en oeuvre ces cas d’utilisation à l’aide de sa fonctionnalité [ Flux de données](https://experienceleague.adobe.com/fr/docs/analytics/export/analytics-data-feed/data-feed-overview). Les flux de données sont un moyen puissant d’extraire des données brutes d’Adobe Analytics. Cet article décrit comment obtenir un type similaire de données brutes d’Experience Platform afin que vous puissiez mettre en oeuvre les cas d’utilisation mentionnés ci-dessus. Le cas échéant, les fonctionnalités décrites dans cet article sont comparées aux flux de données Adobe Analytics afin de clarifier les différences de données et de processus.

## Introduction

L’exportation de données à l’aide de Query Service (Data Distiller) et de l’exportation de jeux de données se compose des éléments suivants :

- définition d’une **requête planifiée** qui génère les données de votre flux de données en tant que jeu de données de sortie ![jeu de données de sortie](../assets/output-dataset.svg), à l’aide de **Query Service**.
- définition d’un **export de jeu de données planifié** qui exporte le jeu de données de sortie vers une destination de stockage dans le cloud, à l’aide de **l’export de jeu de données**.

![Flux de données](../assets/queryservice-export-datasets.svg)


## Conditions préalables

Veillez à respecter toutes les conditions requises ci-après avant d’utiliser les fonctionnalités décrites dans ce cas d’utilisation :

- Mise en oeuvre opérationnelle qui collecte des données dans le lac de données des Experience Platform.
- Accès au module complémentaire Data Distiller pour vous assurer que vous êtes autorisé à exécuter des requêtes par lots. Pour plus d’informations, voir [Query Service packaging](https://experienceleague.adobe.com/fr/docs/experience-platform/query/packaging) .
- Accès à la fonctionnalité Exporter les jeux de données , disponible lorsque vous avez acheté le package Real-Time CDP Prime ou Ultimate, Adobe Journey Optimizer ou Customer Journey Analytics. Pour plus d’informations, voir [Exportation de jeux de données vers des destinations de stockage dans le cloud](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/ui/activate/export-datasets) .
- Une ou plusieurs destinations configurées (par exemple : Amazon S3, Google Cloud Storage) vers lesquelles vous pouvez exporter les données brutes de votre flux de données.


## Query Service

Experience Platform Query Service vous permet d’interroger et de joindre n’importe quel jeu de données dans le lac de données Experience Platform comme s’il s’agissait d’une table de base de données. Vous pouvez ensuite capturer les résultats sous la forme d’un nouveau jeu de données en vue d’une utilisation ultérieure dans les rapports ou pour l’exportation.

Vous pouvez utiliser l’ [ interface utilisateur ](https://experienceleague.adobe.com/fr/docs/experience-platform/query/ui/overview) de Query Service, un [ client connecté via le protocole PostgresQL](https://experienceleague.adobe.com/fr/docs/experience-platform/query/clients/overview) ou les [API RESTful](https://experienceleague.adobe.com/fr/docs/experience-platform/query/api/getting-started) pour créer et planifier des requêtes qui collectent les données pour votre flux de données.

### Créer une requête

Vous pouvez utiliser toutes les fonctionnalités de SQL ANSI standard pour les instructions SELECT et d’autres commandes limitées afin de créer et d’exécuter des requêtes qui génèrent les données de votre flux de données. Voir [Syntaxe SQL](https://experienceleague.adobe.com/fr/docs/experience-platform/query/sql/syntax) pour plus d’informations. Au-delà de cette syntaxe SQL, Adobe prend en charge :

- [Fonctions prédéfinies par Adobe (ADF)](https://experienceleague.adobe.com/fr/docs/experience-platform/query/sql/adobe-defined-functions) qui permettent d’effectuer des tâches commerciales courantes sur les données d’événement stockées dans le lac de données Experience Platform, y compris des fonctions pour [Session](https://experienceleague.adobe.com/fr/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing) et [Attribution](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/attribution/overview),
- plusieurs fonctions [Spark SQL ](https://experienceleague.adobe.com/fr/docs/experience-platform/query/sql/spark-sql-functions) intégrées,
- [Commandes de métadonnées PostgreSQL](https://experienceleague.adobe.com/fr/docs/experience-platform/query/sql/metadata),
- [instructions préparées](https://experienceleague.adobe.com/fr/docs/experience-platform/query/sql/prepared-statements).

#### Colonnes de flux de données

Les champs XDM que vous pouvez utiliser dans votre requête dépendent de la définition de schéma sur laquelle vos jeux de données sont basés. Assurez-vous de bien comprendre le schéma sous-jacent au jeu de données. Voir pour plus d’informations le [guide de l’interface utilisateur des jeux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/catalog/datasets/user-guide).

Pour vous aider à définir le mappage entre les colonnes de flux de données et les champs XDM, voir [Mapping des champs Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). Pour plus d’informations sur la gestion des ressources XDM, notamment les schémas, les classes, les groupes de champs et les types de données, consultez également la [présentation de l’interface utilisateur des schémas](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/overview#defining-xdm-fields).

Par exemple, si vous souhaitez utiliser *nom de page* dans votre flux de données :

- Dans l’interface utilisateur du flux de données Adobe Analytics, sélectionnez **[!UICONTROL pagename]** comme colonne à ajouter à la définition du flux de données.
- Dans Query Service, vous incluez `web.webPageDetails.name` du jeu de données `sample_event_dataset_for_website_global_v1_1` (basé sur le schéma d’événement **Sample Event Schema for Website (Global v1.1)** schéma d’événement d’expérience) dans votre requête. Pour plus d’informations, consultez le [groupe de champs de schéma Détails web](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/field-groups/event/web-details) .


#### Identités

Dans Experience Platform, différentes identités sont disponibles. Lors de la création de vos requêtes, vérifiez que vous interrogez correctement les identités.


Souvent, les identités se trouvent dans un groupe de champs distinct. Dans une implémentation, un ECID (`ecid`) peut être défini comme faisant partie d’un groupe de champs avec un objet `core`, qui fait lui-même partie d’un objet `identification` (par exemple : `_sampleorg.identification.core.ecid`). Les ECID peuvent être organisés différemment dans vos schémas.

Vous pouvez également utiliser `identityMap` pour rechercher des identités. `identityMap` est de type `Map` et utilise une [structure de données imbriquée](#nested-data-structure).

Voir [Définition des champs d’identité dans l’interface utilisateur](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/identity) pour plus d’informations sur la définition des champs d’identité dans Experience Platform.

Reportez-vous à la section [Identifiants de Principal dans les données Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data) pour comprendre comment les identités Adobe Analytics sont mappées aux identités Experience Platform lors de l’utilisation du connecteur source Analytics. Ce mappage peut servir de guide pour la configuration de vos identités, même si vous n’utilisez pas le connecteur source Analytics.


#### Données et identification au niveau de l’accès

En fonction de l’implémentation, les données au niveau de l’accès traditionnellement collectées dans Adobe Analytics sont désormais stockées en tant que données d’événement horodatées dans Experience Platform. Le tableau suivant est extrait à partir du [mappage de champs Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields) et montre des exemples de mappage de colonnes de flux de données Adobe Analytics spécifiques au niveau de l’accès avec les champs XDM correspondants dans vos requêtes. Le tableau présente également des exemples d’identification des accès, des visites et des visiteurs à l’aide de champs XDM.

| Colonne de flux de données | Champ XDM | Type | Description |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | string | Identifiant unique permettant d’identifier un accès. |
| `hitid_low` | `_id` | string | Utilisé avec `hitid_high` pour identifier un accès de manière unique. |
| `hitid_high` | `_id` | string | Utilisé avec `hitid_high` pour identifier un accès de manière unique. |
| `hit_time_gmt` | `receivedTimestamp` | string | Horodatage de l’accès, basé sur l’heure UNIX®. |
| `cust_hit_time_gmt` | `timestamp` | string | Cet horodatage n’est utilisé que dans les jeux de données horodatés. Cet horodatage est envoyé avec l’accès, selon l’heure UNIX®. |
| `visid_high` + `visid_low` | `identityMap` | objet | Identifiant unique d’une visite. |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | string | Identifiant unique d’une visite. |
| `visid_high` | `endUserIDs._experience.aaid.primary` | booléen | Utilisé avec `visid_low` pour identifier une visite de manière unique. |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | string | Utilisé avec `visid_low` pour identifier une visite de manière unique. |
| `visid_low` | `identityMap` | objet | Utilisé avec `visid_high` pour identifier une visite de manière unique. |
| `cust_visid` | `identityMap` | objet | Identifiant visiteur du client. |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | objet | Identifiant visiteur du client. |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | booléen | Code d’espace de noms de l’identifiant visiteur du client. |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | string | Utilisé avec `visid_low` pour identifier de manière unique l’identifiant visiteur du client. |
| `geo\_*` | `placeContext.geo.* ` | chaîne, nombre | Données de géolocalisation, telles que pays, région, ville et autres |
| `event_list` | `commerce.purchases`, `commerce.productViews`, `commerce.productListOpens`, `commerce.checkouts`, `commerce.productListAdds`, `commerce.productListRemovals`, `commerce.productListViews`, `_experience.analytics.event101to200.*`, ..., `_experience.analytics.event901_1000.*` | string | Événements de commerce standard et personnalisés déclenchés lors de l’accès. |
| `page_event` | `web.webInteraction.type` | string | Le type d’accès qui est envoyé dans la demande d’image (accès standard, lien de téléchargement, lien de sortie ou lien personnalisé sur lequel le visiteur a cliqué). |
| `page_event` | `web.webInteraction.linkClicks.value` | number | Le type d’accès qui est envoyé dans la demande d’image (accès standard, lien de téléchargement, lien de sortie ou lien personnalisé sur lequel le visiteur a cliqué). |
| `page_event_var_1` | `web.webInteraction.URL` | string | Variable utilisée uniquement dans les demandes d’image de suivi de liens. Cette variable contient l’URL du lien de téléchargement, de sortie ou personnalisé sur lequel a cliqué l’utilisateur. |
| `page_event_var_2` | `web.webInteraction.name` | string | Variable utilisée uniquement dans les demandes d’image de suivi de liens. Répertorie le nom personnalisé du lien, s’il est spécifié. |
| `paid_search` | `search.isPaid` | booléen | Indicateur défini si l’accès correspond à la détection des référencements payants. |
| `ref_type` | `web.webReferrertype` | string | Identifiant numérique représentant le type de référence pour l’accès. |

#### Colonnes de publication

Les flux de données Adobe Analytics utilisent le concept de colonnes avec un préfixe `post_`, qui sont des colonnes contenant des données après traitement. Pour plus d’informations, consultez la [FAQ sur les flux de données](https://experienceleague.adobe.com/fr/docs/analytics/export/analytics-data-feed/df-faq#post).

Les données collectées dans les jeux de données par le biais de l’Edge Network Experience Platform (SDK Web, SDK Mobile, API de serveur) n’ont aucun concept de champs `post_`. Par conséquent, les colonnes de flux de données `post_` préfixes et *non*-`post_` préfixes sont mappées aux mêmes champs XDM. Par exemple, les colonnes de flux de données `page_url` et `post_page_url` correspondent au même champ XDM `web.webPageDetails.URL`.

Voir [Comparer le traitement des données dans Adobe Analytics et Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons) pour un aperçu de la différence de traitement des données.

Le type de colonne de préfixe `post_` des données, lorsqu’il est collecté dans un lac de données Experience Platform, nécessite toutefois des transformations avancées avant qu’elles ne puissent être utilisées avec succès dans un cas d’utilisation de flux de données. L’exécution de ces transformations avancées dans vos requêtes implique l’utilisation de [fonctions définies par Adobe](https://experienceleague.adobe.com/fr/docs/experience-platform/query/sql/adobe-defined-functions) pour la sessionisation, l’attribution et la déduplication. Voir [Exemples](#examples) sur l&#39;utilisation de ces fonctions.

#### Recherches

Pour rechercher des données d’autres jeux de données, vous utilisez la fonctionnalité SQL standard (`WHERE` clause, `INNER JOIN`, `OUTER JOIN`, etc.).

#### Calculs

Pour effectuer des calculs sur les champs (colonnes), utilisez les fonctions SQL standard (par exemple `COUNT(*)`) ou la partie [ maths et statistiques et fonctions](https://experienceleague.adobe.com/fr/docs/experience-platform/query/sql/spark-sql-functions#math) de Spark SQL. En outre, les [fonctions de fenêtre](https://experienceleague.adobe.com/fr/docs/experience-platform/query/sql/adobe-defined-functions#window-functions) prennent en charge la mise à jour des agrégations et le renvoi d’éléments uniques pour chaque ligne d’un sous-ensemble ordonné. Voir [Exemples](#examples) sur l&#39;utilisation de ces fonctions.

#### Structure des données imbriquées

Les schémas sur lesquels les jeux de données sont basés contiennent souvent des types de données complexes, y compris des structures de données imbriquées. `identityMap` précédemment mentionné est un exemple de structure de données imbriquées. Voir ci-dessous un exemple de données `identityMap`.

```json
{
   "identityMap":{
      "FPID":[
         {
            "id":"55613368189701342632255821452918751312",
            "authenticatedState":"ambiguous"
         }
      ],
      "CRM":[
         {
            "id":"2394509340-30453470347",
            "authenticatedState":"authenticated"
         }
      ]
   }
}
```

Vous pouvez utiliser les [`explode()` ou d’autres fonctions de tableau ](https://experienceleague.adobe.com/fr/docs/experience-platform/query/sql/spark-sql-functions#arrays) de Spark SQL pour accéder aux données dans une structure de données imbriquée, par exemple :

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Vous pouvez également faire référence à des éléments individuels à l’aide de la notation par points. Par exemple :

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Voir [Utiliser les structures de données imbriquées dans Query Service](https://experienceleague.adobe.com/fr/docs/experience-platform/query/key-concepts/nested-data-structures) pour plus d’informations.


#### Exemples

Pour les requêtes :

- qui utilisent les données des jeux de données du lac de données Experience Platform,
- exploite les fonctionnalités supplémentaires des fonctions définies par l’Adobe et/ou de Spark SQL, et
- qui produirait des résultats similaires à un flux de données Adobe Analytics équivalent,

voir :

- [abandon du navigateur](https://experienceleague.adobe.com/fr/docs/experience-platform/query/use-cases/abandoned-browse)
- [analyse d’attribution](https://experienceleague.adobe.com/fr/docs/experience-platform/query/use-cases/attribution-analysis)
- [filtrage de robots](https://experienceleague.adobe.com/fr/docs/experience-platform/query/use-cases/bot-filtering)
- et d’autres [cas d’utilisation pris en charge dans le guide Query Service](https://experienceleague.adobe.com/fr/docs/experience-platform/query/use-cases/overview).

Vous trouverez ci-dessous un exemple d’application correcte de l’attribution entre les sessions qui illustre comment

- utiliser les 90 derniers jours comme recherche en amont,
- appliquer des fonctions de fenêtre telles que la sessionisation et/ou l’attribution ; et
- restreignez la sortie en fonction de `ingest_time`.

+++
Détails

  Pour cela, vous devez...

   - Utilisez une table d’état de traitement, `checkpoint_log`, pour effectuer le suivi de l’heure actuelle par rapport à l’heure de la dernière ingestion. Pour plus d’informations, voir [ce guide](https://experienceleague.adobe.com/fr/docs/experience-platform/query/key-concepts/incremental-load) .
   - Désactivez les colonnes système de dépôt, afin que vous puissiez utiliser `_acp_system_metadata.ingestTime`.
   - Utilisez un `SELECT` interne pour saisir les champs que vous souhaitez utiliser et limiter les événements à votre période de recherche arrière pour les calculs de session et/ou d’attribution. Par exemple, 90 jours.
   - Utilisez un niveau suivant `SELECT` pour appliquer vos fonctions de session et/ou de fenêtre d’attribution et d’autres calculs.
   - Utilisez `INSERT INTO` dans votre tableau de sortie pour limiter la recherche en amont aux événements arrivés depuis votre dernière heure de traitement. Pour ce faire, effectuez un filtrage sur `_acp_system_metadata.ingestTime ` par rapport à la dernière heure stockée dans votre table d’état de traitement.

  **Exemple de fonctions de fenêtre de sessionisation**

  ```sql
  $$ BEGIN
     -- Disable dropping system columns
     set drop_system_columns=false; 
  
     -- Initialize variables
     SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
     -- Get the last processed batch ingestion time
     SET @from_batch_ingestion_time = SELECT coalesce(last_batch_ingestion_time, 'HEAD') 
        FROM checkpoint_log a 
        JOIN (
              SELECT MAX(process_timestamp) AS process_timestamp 
              FROM checkpoint_log
              WHERE process_name = 'data_feed' 
              AND process_status = 'SUCCESSFUL'
        ) b
        ON a.process_timestamp = b.process_timestamp;
  
     -- Get the last batch ingestion time
     SET @to_batch_ingestion_time = SELECT MAX(_acp_system_metadata.ingestTime) 
        FROM events_dataset;
  
     -- Sessionize the data and insert into data_feed.
     INSERT INTO data_feed
     SELECT *
     FROM (
        SELECT
              userIdentity,
              timestamp,
              SESS_TIMEOUT(timestamp, 60 * 30) OVER (
                 PARTITION BY userIdentity
                 ORDER BY timestamp
                 ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
              ) AS session_data,
              page_name,
              ingest_time
        FROM (
              SELECT
                 userIdentity,
                 timestamp,
                 web.webPageDetails.name AS page_name,
                 _acp_system_metadata.ingestTime AS ingest_time
              FROM events_dataset
              WHERE timestamp >= current_date - 90
        ) AS a
        ORDER BY userIdentity, timestamp ASC
     ) AS b
     WHERE b.ingest_time >= @from_batch_ingestion_time;
  
     -- Update the checkpoint_log table
     INSERT INTO checkpoint_log
     SELECT
        'data_feed' process_name,
        'SUCCESSFUL' process_status,
        cast(@to_batch_ingestion_time AS string) last_batch_ingestion_time,
        cast(@last_updated_timestamp AS TIMESTAMP) process_timestamp
  END
  $$;
  ```

  **Exemple de fonctions de fenêtre d’attribution**

  ```sql
  $$ BEGIN
   SET drop_system_columns=false;
  
  -- Initialize variables
   SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
  -- Get the last processed batch ingestion time 1718755872325
   SET @from_batch_ingestion_time =
       SELECT coalesce(last_snapshot_id, 'HEAD')
       FROM checkpoint_log a
       JOIN (
           SELECT MAX(process_timestamp) AS process_timestamp
           FROM checkpoint_log
           WHERE process_name = 'data_feed'
           AND process_status = 'SUCCESSFUL'
       ) b
       ON a.process_timestamp = b.process_timestamp;
  
   -- Get the last batch ingestion time 1718758687865
   SET @to_batch_ingestion_time =
       SELECT MAX(_acp_system_metadata.ingestTime)
       FROM demo_data_trey_mcintyre_midvalues;
  
   -- Sessionize the data and insert into new_sessionized_data
   INSERT INTO new_sessionized_data
   SELECT *
   FROM (
       SELECT
           _id,
           timestamp,
           struct(User_Identity,
           cast(SESS_TIMEOUT(timestamp, 60 * 30) OVER (
               PARTITION BY User_Identity
               ORDER BY timestamp
               ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
           ) as string) AS SessionData,
           to_timestamp(from_unixtime(ingest_time/1000, 'yyyy-MM-dd HH:mm:ss')) AS IngestTime,      
           PageName,
           first_url,
           first_channel_type
             ) as _demosystem5
       FROM (
           SELECT
               _id,
               ENDUSERIDS._EXPERIENCE.MCID.ID as User_Identity,
               timestamp,
               web.webPageDetails.name AS PageName,
              attribution_first_touch(timestamp, '', web.webReferrer.url) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_url,
              attribution_first_touch(timestamp, '',channel.typeAtSource) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_channel_type,
               _acp_system_metadata.ingestTime AS ingest_time
           FROM demo_data_trey_mcintyre_midvalues
           WHERE timestamp >= current_date - 90
       )
       ORDER BY User_Identity, timestamp ASC    
   )
   WHERE _demosystem5.IngestTime >= to_timestamp(from_unixtime(@from_batch_ingestion_time/1000, 'yyyy-MM-dd HH:mm:ss'));
  
  -- Update the checkpoint_log table
  INSERT INTO checkpoint_log
  SELECT
     'data_feed' as process_name,
     'SUCCESSFUL' as process_status,
     cast(@to_batch_ingestion_time AS string) as last_snapshot_id,
     cast(@last_updated_timestamp AS timestamp) as process_timestamp;
  
  END
  $$;
  ```

+++


### Planification de la requête

Vous planifiez la requête pour vous assurer qu’elle est exécutée et que les résultats sont générés selon l’intervalle de votre choix.

#### Utilisation de Query Editor

Vous pouvez planifier une requête à l’aide de Query Editor. Lors de la planification de la requête, vous définissez un jeu de données de sortie. Pour plus d’informations, voir [Planifications de requête](https://experienceleague.adobe.com/fr/docs/experience-platform/query/ui/query-schedules) .


#### Utilisation de l’API Query Service

Vous pouvez également utiliser les API RESTful pour définir une requête et un planning pour la requête. Pour plus d’informations, consultez le [guide de l’API Query Service](https://experienceleague.adobe.com/fr/docs/experience-platform/query/api/getting-started) .
Assurez-vous de définir le jeu de données de sortie dans le cadre de la propriété facultative `ctasParameters` lors de la création de la requête ([Créer une requête](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) ou lors de la création du planning d’une requête ([Créer une requête planifiée](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Exporter les jeux de données

Une fois que vous avez créé et planifié votre requête, et vérifié les résultats, vous pouvez exporter les jeux de données bruts vers des destinations de stockage dans le cloud. Cette exportation est conforme à la terminologie des destinations Experience Platform appelée destinations d’exportation de jeux de données. Voir [Exportation de jeux de données vers des destinations de stockage dans le cloud](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/ui/activate/export-datasets) pour obtenir un aperçu.

Les destinations de stockage dans le cloud suivantes sont prises en charge :

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Zone d’atterrissage des données](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3)
- [Azure Blob](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob)
- [SFTP](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/catalog/cloud-storage/sftp)


### Interface utilisateur Experience Platform

Vous pouvez exporter et planifier l’exportation de vos jeux de données de sortie via l’interface utilisateur Experience Platform. Cette section décrit les étapes à suivre.

#### Sélectionner la destination

Lorsque vous avez déterminé la destination de stockage dans le cloud vers laquelle vous souhaitez exporter le jeu de données de sortie, [sélectionnez la destination](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Lorsque vous n&#39;avez pas encore configuré de destination pour l&#39;espace de stockage de votre choix dans le cloud, vous devez [créer une nouvelle connexion de destination](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/ui/connect-destination).

Lors de la configuration d’une destination, vous pouvez

- définir le type de fichier (JSON ou Parquet),
- si le fichier obtenu doit être compressé ou non, et
- si un fichier de manifeste doit être inclus ou non.


#### Sélectionner le jeu de données

Lorsque vous avez sélectionné la destination, à l’étape suivante **[!UICONTROL Sélectionner les jeux de données]** , vous devez sélectionner votre jeu de données de sortie dans la liste des jeux de données. Si vous avez créé plusieurs requêtes planifiées et que vous souhaitez que les jeux de données de sortie soient envoyés vers la même destination de stockage dans le cloud, vous pouvez sélectionner les jeux de données de sortie correspondants. Voir [Sélectionner vos jeux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) pour plus d’informations.

#### Planifier l’exportation des jeux de données

Enfin, vous souhaitez planifier l’exportation de votre jeu de données dans le cadre de l’étape **[!UICONTROL Planification]** . Au cours de cette étape, vous pouvez définir le planning et indiquer si l’exportation du jeu de données de sortie doit être incrémentielle ou non. Pour plus d’informations, voir [Planification de l’exportation des jeux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) .


#### Étapes finales

[Vérifiez](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/ui/activate/export-datasets#review) votre sélection et, lorsque cela est correct, commencez à exporter votre jeu de données de sortie vers la destination de stockage dans le cloud.

Vous devez [vérifier](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/ui/activate/export-datasets#verify) que l’exportation des données a réussi. Lors de l’exportation de jeux de données, Experience Platform crée un ou plusieurs fichiers `.json` ou `.parquet` à l’emplacement de stockage défini dans votre destination. Attendez-vous à ce que les nouveaux fichiers soient déposés dans votre emplacement de stockage en fonction du planning d’exportation que vous configurez. Experience Platform crée une structure de dossiers dans l’emplacement de stockage que vous avez spécifié comme faisant partie de la destination sélectionnée, où il dépose les fichiers exportés. Un nouveau dossier est créé pour chaque heure d’exportation, selon le modèle : `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Le nom de fichier par défaut est généré de manière aléatoire pour garantir que les noms de fichier exportés soient uniques.

### API de service de flux

Vous pouvez également exporter et planifier l’exportation des jeux de données de sortie à l’aide d’API. Les étapes impliquées sont documentées dans [Export des jeux de données à l’aide de l’API Flow Service](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/api/export-datasets).

#### Commencer

Pour exporter des jeux de données, assurez-vous de disposer des [autorisations requises](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/api/export-datasets#permissions). Vérifiez également que la destination vers laquelle vous souhaitez envoyer votre jeu de données de sortie prend en charge l’exportation de jeux de données. Vous devez ensuite [ rassembler les valeurs des en-têtes requis et facultatifs](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) que vous utilisez dans les appels API. Vous devez également [identifier les spécifications de connexion et les identifiants de spécification de flux de la destination](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) vers laquelle vous envisagez d’exporter des jeux de données.

#### Récupération des jeux de données éligibles

Vous pouvez [récupérer une liste de jeux de données éligibles](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) pour l’exportation et vérifier si votre jeu de données de sortie fait partie de cette liste à l’aide de l’API [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets).


#### Création d’une connexion source

Ensuite, vous devez [créer une connexion source](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/api/export-datasets#create-source-connection) pour le jeu de données de sortie, à l’aide de son identifiant unique, que vous souhaitez exporter vers la destination de stockage dans le cloud. Vous utilisez l’API [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection).

#### Authentification à la destination (créer une connexion de base)

Vous devez maintenant [créer une connexion de base](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/api/export-datasets#create-base-connection) pour vous authentifier et stocker en toute sécurité les informations d’identification vers votre destination de stockage dans le cloud à l’aide de l’API [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection).


#### Fournir des paramètres d’exportation

Ensuite, vous devez [ créer une connexion cible supplémentaire qui stocke les paramètres d’exportation](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/api/export-datasets#create-target-connection) pour votre jeu de données de sortie à l’aide, une fois de plus, de l’API [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection). Ces paramètres d’exportation incluent l’emplacement, le format de fichier, la compression, etc.

#### Configuration du flux de données

Enfin, vous [ configurez le flux de données ](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/api/export-datasets#create-dataflow) pour vous assurer que votre jeu de données de sortie est exporté vers votre destination de stockage dans le cloud à l’aide de l’API [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow). Au cours de cette étape, vous pouvez définir la planification de l’exportation à l’aide du paramètre `scheduleParams` .

#### Validation du flux de données

Pour [vérifier les exécutions réussies de votre flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), utilisez l’API [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns), en spécifiant l’identifiant du flux de données comme paramètre de requête. Cet identifiant de flux de données est un identifiant renvoyé lors de la configuration du flux de données.

[Vérifiez](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/ui/activate/export-datasets#verify) qu’une exportation de données a réussi. Lors de l’exportation de jeux de données, Experience Platform crée un ou plusieurs fichiers `.json` ou `.parquet` à l’emplacement de stockage défini dans votre destination. Attendez-vous à ce que les nouveaux fichiers soient déposés dans votre emplacement de stockage en fonction du planning d’exportation que vous configurez. Experience Platform crée une structure de dossiers dans l’emplacement de stockage que vous avez spécifié comme faisant partie de la destination sélectionnée, où il dépose les fichiers exportés. Un nouveau dossier est créé pour chaque heure d’exportation, selon le modèle : `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Le nom de fichier par défaut est généré de manière aléatoire pour garantir que les noms de fichier exportés soient uniques.

## Conclusion

En résumé, l’émulation de la fonctionnalité de flux de données Adobe Analytics implique la configuration de requêtes planifiées à l’aide de Query Service et l’utilisation des résultats de ces requêtes dans les exportations planifiées de jeux de données.

>[!IMPORTANT]
>
>Deux planificateurs sont impliqués dans ce cas pratique. Pour garantir le bon fonctionnement de la fonctionnalité de flux de données émulé, assurez-vous que les plannings configurés dans Query Service et dans les exportations de données n’interfèrent pas.
