---
title: Émuler la fonctionnalité de flux de données
description: Découvrez comment émuler des flux de données Adobe Analytics avec des données dans Experience Platform.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: d6e10a00bf9afb2788f99800e09a7e80fd31e489
workflow-type: tm+mt
source-wordcount: '2107'
ht-degree: 4%

---

# Émuler la fonctionnalité de flux de données

Les flux de données Adobe Analytics sont un moyen puissant d’extraire des données brutes d’Adobe Analytics. Ce cas d’utilisation décrit comment obtenir un type similaire de données brutes d’Experience Platform, à utiliser sur d’autres plateformes en dehors de l’Adobe et à la discrétion de votre entreprise.

## Conditions préalables

Veillez à respecter toutes les conditions requises ci-après avant d’utiliser les fonctionnalités décrites dans ce cas d’utilisation :

* Mise en oeuvre opérationnelle qui envoie des données en ligne et hors ligne dans le lac de données des Experience Platform.
* Accès à Query Service, mis en package dans le cadre d’applications basées sur une plateforme ou du module complémentaire Data Distiller. Voir [Package Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) pour plus d’informations.
* Accès à la fonctionnalité Exporter les jeux de données , disponible pour les clients qui ont acheté le package Real-Time CDP Prime ou Ultimate, Adobe Journey Optimizer ou Customer Journey Analytics. Voir [Exportation des jeux de données vers des destinations de stockage dans le cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=fr) pour plus d’informations.
* Une ou plusieurs destinations (par exemple : Amazon S3, Google Cloud Storage) configurées pour vous permettre d’exporter les données brutes de votre flux de données.

## Introduction

L’émulation d’un flux de données Adobe Analytics implique :

* définition d’un **requête planifiée** qui génère les données de votre flux de données en tant que jeu de données de sortie, en utilisant **Query Service**.
* définition d’un **export du jeu de données planifié** qui exporte le jeu de données de sortie vers une destination de stockage dans le cloud, en utilisant **Exportation des jeux de données**.


![Flux de données](assets/data-feed.svg)


## Query Service

Experience Platform Query Service vous permet d’interroger et de joindre n’importe quel jeu de données dans le lac de données Experience Platform comme s’il s’agissait d’une table de base de données. Vous pouvez ensuite capturer les résultats sous la forme d’un nouveau jeu de données en vue d’une utilisation ultérieure dans les rapports ou pour l’exportation.

Vous utilisez Query Service [interface utilisateur](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en), un [client connecté via le protocole PostgresSQL](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=fr), ou [API RESTful](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) pour créer et planifier des requêtes qui collectent les données de votre flux de données.

### Créer une requête

Vous pouvez utiliser toutes les fonctionnalités de SQL ANSI standard pour les instructions SELECT et d’autres commandes limitées afin de créer et d’exécuter les requêtes qui génèrent les données pour votre flux de données. Voir [Syntaxe SQL](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) pour plus d’informations. Au-delà de cette syntaxe SQL, Adobe prend en charge :

* prédéfinie [Fonctions définies par Adobe (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) qui aident à effectuer des tâches commerciales courantes sur les données d’événement stockées dans le lac de données Experience Platform, y compris des fonctions pour [Sessionization](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=fr) et [Attribution](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=fr),
* plusieurs composants intégrés [Fonctions Spark SQL](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en),
* [Commandes de métadonnées PostgreSQL](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en),
* [instructions préparées](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### Exemples

Vous trouverez ci-dessous quelques exemples de requêtes qui collectent des données pour vos flux de données. Ces exemples utilisent `demo_system_event_dataset_for_website_global_v1_1` comme exemple de jeu de données d’événement d’expérience contenant les données collectées auprès des clients interagissant avec le site web.

+++Les cinq premiers produits

*Quels sont les cinq premiers produits consultés sur le site web ?*

```sql
select productListItems.name, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType = 'commerce.productViews'
group  by productListItems.name
order  by 2 desc
limit 5;
```

+++

+++Entonnoir d’interaction du produit

*Quelles sont les différentes interactions entre les produits sur le site web ?*

```sql
select eventType, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType is not null
and    eventType <> ''
group  by eventType;
```

+++

+++Que font les gens

*Que font les visiteurs sur le site avant d’atteindre la page &quot;Annuler le service&quot; comme troisième page d’une session ?*

Cette requête utilise les fonctions définies par l’Adobe `SESS_TIMEOUT` et `NEXT`.

* Le `SESS_TIMEOUT()` reproduit les regroupements de visites découverts dans Adobe Analytics. Il réalise un regroupement en fonction du temps similaire, mais avec des paramètres personnalisables.
* `NEXT()` et `PREVIOUS()` vous aide à comprendre comment les clients naviguent sur votre site.

```sql
SELECT
  webPage,
  webPage_2,
  webPage_3,
  webPage_4,
  count(*) journeys
FROM
  (
      SELECT
        webPage,
        NEXT(webPage, 1, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_2,
        NEXT(webPage, 2, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_3,
        NEXT(webPage, 3, true)
           OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_4,
        session.depth AS SessionPageDepth
      FROM (
            select a._sampleorg.identification.core.ecid as ecid,
                   a.timestamp,
                   web.webPageDetails.name as webPage,
                    SESS_TIMEOUT(timestamp, 60 * 30)
                       OVER (PARTITION BY a._sampleorg.identification.core.ecid
                             ORDER BY timestamp
                             ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)
                  AS session
            from   demo_system_event_dataset_for_website_global_v1_1 a
            where  a._sampleorg.identification.core.ecid in (
                select b._sampleorg.identification.core.ecid
                from   demo_system_event_dataset_for_website_global_v1_1 b
                where  b.web.webPageDetails.name = 'Cancel Service'
            )
        )
)
WHERE SessionPageDepth=1
and   webpage_3 = 'Cancel Service'
GROUP BY webPage, webPage_2, webPage_3, webPage_4
ORDER BY journeys DESC
LIMIT 10;
```

+++

+++Durée

*Combien de temps reste-t-il avant qu’un visiteur appelle le centre d’appel après avoir visité la page &quot;Annuler le service&quot; ?*

Pour répondre à ce type de requête, vous utilisez le `TIME_BETWEEN_NEXT_MATCH()` Fonction définie par Adobe. L’intervalle entre les fonctions de correspondance précédente ou suivante fournit une nouvelle dimension, qui mesure le temps qui s’est écoulé depuis un incident particulier.

```sql
select * from (
       select _sampleorg.identification.core.ecid as ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
where r.webPage = 'Cancel Service'
limit 15;
```

+++

+++Quel est le résultat ?

*Quel est le résultat des clients qui appellent le centre d’appel ?*

Pour cette requête, la variable `demo_system_event_dataset_for_website_global_v1_1` le jeu de données est associé à un exemple `demo_system_event_dataset_for_call_center_global_v1_1` jeu de données contenant les interactions avec le centre d’appels.

```sql
select distinct r.*,
       c._sampleorg.interactionDetails.core.callCenterAgent.callFeeling,
       c._sampleorg.interactionDetails.core.callCenterAgent.callTopic,
       c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled
from (
       select _sampleorg.identification.core.ecid ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
, demo_system_event_dataset_for_call_center_global_v1_1 c
where r.ecid = c._sampleorg.identification.core.ecid
and r.webPage = 'Cancel Service'
and c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled IN (true,false)
and c._sampleorg.interactionDetails.core.callCenterAgent.callTopic IN ('contract', 'invoice','complaint','wifi')
limit 15;
```

+++

+++Engagement des canaux marketing (données Adobe Analytics)

*Quel est l’engagement sur les canaux marketing pour le trafic web italien ?*

Cet exemple utilise le jeu de données créé automatiquement par le connecteur source Adobe Analytics, par exemple `demo_data_sample_org_midvalues`.

```sql
select 
    channel.typeAtSource, count(*) 
from 
    demo_data_sample_org_midvalues 
where 
    (channel.typeAtSource IS NOT NULL
and
    web.webPageDetails.URL LIKE '%/it/it/%')
group by 
    channel.typeAtSource
order by 2 desc;
```

+++

Pour obtenir des exemples de requêtes (avancées) supplémentaires, voir [navigateur abandonné](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en), [analyse d’attribution](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en), [filtrage de robots](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en), ainsi que d’autres exemples dans le guide de Query Service.


#### Identités

Dans Experience Platform, différentes identités sont disponibles. Vérifiez que vous interrogez correctement les identités. Dans les exemples ci-dessus, ECID est défini comme faisant partie d’un objet principal, qui fait lui-même partie d’un objet d’identification, tous deux ajoutés au schéma à l’aide d’un groupe de champs Experience Event Core (par exemple : `_sampleorg.identification.core.ecid`). Les ECID peuvent être organisés différemment dans vos schémas.

Vous pouvez également utiliser `identityMap` pour rechercher des identités. Cet objet est de type `Map` et utilise une [structure de données imbriquées](#nested-data-structure).

Pour les données ingérées à l’aide du connecteur source Adobe Analytics, plusieurs identités peuvent être disponibles. L’identifiant principal dépend de l’existence d’un ECID ou d’un AAID. Voir [Identifiants de Principal dans les données Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#how-the-analytics-source-treats-identities) et [AAID, ECID, AACUSTOMID et connecteur source Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=fr) pour plus d’informations

#### Colonnes de flux de données

Les champs (colonnes) que vous pouvez utiliser dans votre requête dépendent de la définition de schéma sur laquelle vos jeux de données sont basés. Assurez-vous de bien comprendre le schéma sous-jacent au jeu de données.

Par exemple, dans certains des [exemple de requêtes](#examples) vous avez demandé pour *nom de page*.

* Dans l’interface utilisateur du flux de données Adobe Analytics, vous pouvez sélectionner **[!UICONTROL pagename]** comme colonne à ajouter à votre définition de flux de données.
* Dans Query Service, vous incluez `web.webPageDetails.name` de la `demo_system_event_dataset_for_website_global_v1_1` jeu de données (basé sur la variable **Système de démonstration - Schéma d’événement pour le site web (Global v1.1)** schéma d’événement d’expérience) dans votre requête. Voir [Groupe de champs de schéma Détails web](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) pour plus d’informations.

Pour comprendre le mappage entre les anciennes colonnes de données Adobe Analytics et les champs XDM dans votre jeu de données d’événement d’expérience et votre schéma sous-jacent, voir [Mappage des champs Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=fr) et la variable [Groupe de champs de l’extension complète Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) pour plus d’informations.

De plus, les informations automatiquement collectées par le SDK Web Experience Platform (prêt à l’emploi) peuvent également être utiles pour identifier les colonnes de votre requête. Voir [Informations collectées automatiquement](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) pour plus d’informations.


#### Recherches

Pour rechercher des données d’autres jeux de données, vous utilisez la fonctionnalité SQL standard (clause WHERE, INNER JOIN, OUTER JOIN, etc.). Voir [Quel est le résultat ?](#examples) dans les exemples.

#### Calculs

Pour effectuer des calculs sur les champs (colonnes), utilisez simplement les fonctions SQL standard (par exemple : `COUNT(*)` dans le [Entonnoir d’interaction du produit](#examples) dans les exemples) ou le [opérateurs mathématiques et statistiques et fonctions](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) fait partie de Spark SQL.

#### Structure des données imbriquées

Les schémas sur lesquels les jeux de données sont basés contiennent souvent des types de données complexes, y compris des structures de données imbriquées. Précédemment mentionné `identityMap` est un exemple de structure de données imbriquées. Voir ci-dessous un exemple `identityMap` data.

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

Vous pouvez utiliser la variable [`explode()` ou d’autres fonctions de tableau](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) de Spark SQL pour accéder aux données dans une structure de données imbriquée.

Par exemple :

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Vous pouvez également faire référence à des éléments individuels à l’aide de la notation par points. Par exemple :

```sql
select identityMap,ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Voir [Utiliser les structures de données imbriquées dans Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en) pour plus d’informations.

### Planification de la requête

Vous planifiez la requête pour vous assurer qu’elle est exécutée et que les résultats sont générés selon l’intervalle de votre choix. Lors de la planification de la requête, vous définissez un jeu de données de sortie.

#### Utilisation de Query Editor

Vous pouvez planifier une requête à l’aide de Query Editor. Lors de la définition d’un planning pour une requête, vous pouvez définir le jeu de données de sortie. Voir [Planifications de requête](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) pour plus d’informations.


#### Utilisation de l’API Query Service

Vous pouvez également utiliser les API RESTful pour définir une requête et un planning pour la requête. Voir [Guide de l’API Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en_) pour plus d’informations.
Assurez-vous de définir le jeu de données de sortie dans le cadre de l’option `ctasParameters` lors de la création de la requête ([Créer une requête](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) ou lors de la création du planning d’une requête ([Création d’une requête planifiée](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Exportation des jeux de données

Une fois que vous avez créé et planifié votre requête, et vérifié les résultats des jeux de données de sortie correspondant à vos besoins, vous pouvez exporter les jeux de données bruts vers des destinations de stockage dans le cloud. Cette exportation est conforme à la terminologie des destinations Experience Platform appelée destinations d’exportation de jeux de données. Voir [Exportation des jeux de données vers des destinations de stockage dans le cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=fr) pour une vue d’ensemble.

Les destinations de stockage dans le cloud suivantes sont prises en charge :

* [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=en)
* [Zone d’atterrissage des données](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en)
* [Google Cloud Storage](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=en)
* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=en#changelog)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=en#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=en#changelog)


### Interface utilisateur Experience Platform

Vous pouvez exporter et planifier l’exportation de vos jeux de données de sortie via l’interface utilisateur Experience Platform. Cette section décrit les étapes à suivre.

#### Sélectionner la destination

Lorsque vous avez déterminé vers quelle destination de stockage dans le cloud vous souhaitez exporter le jeu de données de sortie, [sélectionner la destination ;](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-destination). Lorsque vous n’avez pas encore configuré de destination pour votre espace de stockage préféré dans le cloud, vous devez [créer une connexion de destination ;](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=fr).

Dans le cadre de la configuration d’une destination, vous pouvez définir le type de fichier (JSON ou Parquet), si le fichier obtenu doit être compressé ou non et si un fichier manifeste doit être inclus ou non.


#### Sélectionner le jeu de données

Lorsque vous avez sélectionné la destination, dans la **[!UICONTROL Sélectionner des jeux de données]** vous devez sélectionner votre jeu de données de sortie dans la liste des jeux de données. Si vous avez créé plusieurs requêtes planifiées et que vous souhaitez que les jeux de données de sortie soient envoyés vers la même destination de stockage dans le cloud, vous pouvez sélectionner les jeux de données de sortie correspondants. Voir [Sélectionner vos jeux de données](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-datasets) pour plus d’informations.

#### Planifier l’exportation des jeux de données

Enfin, vous souhaitez planifier l’exportation de votre jeu de données dans le cadre du **[!UICONTROL Planification]** étape . Au cours de cette étape, vous pouvez définir le planning et indiquer si l’exportation du jeu de données de sortie doit être incrémentielle ou non. Voir [Planification de l’exportation des jeux de données](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#scheduling) pour plus d’informations.


#### Étapes finales

[Réviser](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#review) votre sélection et, le cas échéant, commencez à exporter votre jeu de données de sortie vers la destination de stockage dans le cloud.

Vous devez [verify](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) une exportation de données réussie. Lors de l’exportation de jeux de données, Experience Platform en crée un ou plusieurs `.json` ou `.parquet` dans l’emplacement de stockage défini dans votre destination. Attendez-vous à ce que les nouveaux fichiers soient déposés dans votre emplacement de stockage en fonction du planning d’exportation que vous configurez. Experience Platform crée une structure de dossiers dans l’emplacement de stockage que vous avez spécifié comme faisant partie de la destination sélectionnée, où il dépose les fichiers exportés. Un nouveau dossier est créé pour chaque heure d’exportation, selon le modèle suivant : `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Le nom de fichier par défaut est généré de manière aléatoire pour garantir que les noms de fichier exportés soient uniques.

### API de service de flux

Vous pouvez également exporter et planifier l’exportation des jeux de données de sortie à l’aide d’API. Les étapes à suivre sont décrites dans la section [Exportation de jeux de données à l’aide de l’API Flow Service](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### Prise en main

Assurez-vous que vous disposez de la variable [autorisations requises](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions) pour exporter des jeux de données et que la destination vers laquelle vous souhaitez envoyer votre jeu de données de sortie prend en charge l’exportation de jeux de données. Vous devez alors [rassembler les valeurs des en-têtes requis et facultatifs ;](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) vous utilisez dans les appels API, ainsi que [identifier les spécifications de connexion et les identifiants de spécification de flux de la destination ;](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) vous envisagez d’exporter des jeux de données vers .

#### Récupération des jeux de données éligibles

Vous pouvez [récupérer une liste de jeux de données éligibles ;](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#retrieve-list-of-available-datasets) pour l’exportation et vérifiez si votre jeu de données de sortie fait partie de cette liste à l’aide de la variable [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Création d’une connexion source

Ensuite, vous devez [créer une connexion source ;](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-source-connection) pour le jeu de données de sortie, à l’aide de son identifiant unique, que vous souhaitez exporter vers la destination de stockage dans le cloud. Vous utilisez la variable [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Authentification à la destination (créer une connexion de base)

Vous devez maintenant [créer une connexion de base ;](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-base-connection) pour vous authentifier correctement et stocker en toute sécurité les informations d’identification dans votre destination de stockage dans le cloud à l’aide de la variable [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Fournir des paramètres d’exportation

Ensuite, vous devez [créer une connexion cible supplémentaire qui stocke les paramètres d&#39;export ;](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-target-connection) pour votre jeu de données de sortie en utilisant, une fois de plus, la variable [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Ces paramètres d’exportation incluent l’emplacement, le format de fichier, la compression, etc.

#### Configuration du flux de données

Enfin, vous [Configuration du flux de données](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-dataflow) pour vous assurer que votre jeu de données de sortie est exporté vers votre destination de stockage dans le cloud à l’aide de la variable [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. Au cours de cette étape, vous pouvez définir le planning de l&#39;export, à l&#39;aide du `scheduleParams` .

#### Validation du flux de données

À [vérifier les exécutions réussies de votre flux de données](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#get-dataflow-runs), utilisez le [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, spécifiant l’identifiant de flux de données comme paramètre de requête. Cet identifiant de flux de données est un identifiant renvoyé lors de la configuration du flux de données.

[Vérifier](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) une exportation de données réussie. Lors de l’exportation de jeux de données, Experience Platform en crée un ou plusieurs `.json` ou `.parquet` dans l’emplacement de stockage défini dans votre destination. Attendez-vous à ce que les nouveaux fichiers soient déposés dans votre emplacement de stockage en fonction du planning d’exportation que vous configurez. Experience Platform crée une structure de dossiers dans l’emplacement de stockage que vous avez spécifié comme faisant partie de la destination sélectionnée, où il dépose les fichiers exportés. Un nouveau dossier est créé pour chaque heure d’exportation, selon le modèle suivant : `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Le nom de fichier par défaut est généré de manière aléatoire pour garantir que les noms de fichier exportés soient uniques.

## Conclusion

En résumé, l’émulation de la fonctionnalité de flux de données Adobe Analytics implique la configuration de requêtes planifiées à l’aide de Query Service et l’utilisation des résultats de ces requêtes dans les exportations planifiées de jeux de données.

>[!IMPORTANT]
>
>Deux planificateurs sont impliqués dans ce cas pratique. Pour garantir le bon fonctionnement de la fonctionnalité de flux de données émulé, assurez-vous que les plannings configurés dans Query Service et dans les exportations de données n’interfèrent pas.






