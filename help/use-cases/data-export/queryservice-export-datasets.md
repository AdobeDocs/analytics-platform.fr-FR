---
title: Experience Platform Query Service (Data Distiller) et exportation de jeux de données
description: Décrit comment utiliser Query Service (Data Distiller) et l’exportation de jeux de données pour exporter des données.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 19018e31bb2a46e88a27643fe10c388b40de243e
workflow-type: tm+mt
source-wordcount: '2475'
ht-degree: 10%

---

# Query Service (Data Distiller) et exportation de jeux de données

Cet article décrit comment la combinaison de l’exportation de jeux de données et Experience Platform Query Service (Data Distiller) peut être utilisée pour mettre en oeuvre les éléments suivants : [cas d’utilisation d’exportation de données](overview.md):

- Validation des données
- Lac de données, Data Warehouse des outils de BI
- Préparation à l’apprentissage intelligent et automatique artificiel.


Adobe Analytics peut mettre en oeuvre ces cas d’utilisation à l’aide de ses [Flux de données](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) . Les flux de données sont un moyen puissant d’extraire des données brutes d’Adobe Analytics. Cet article décrit comment obtenir un type similaire de données brutes d’Experience Platform afin que vous puissiez mettre en oeuvre les cas d’utilisation mentionnés ci-dessus. Le cas échéant, les fonctionnalités décrites dans cet article sont comparées aux flux de données Adobe Analytics afin de clarifier les différences de données et de processus.

## Introduction

L’exportation de données à l’aide de Query Service (Data Distiller) et de l’exportation de jeux de données se compose des éléments suivants :

- définition d’un **requête planifiée** qui génère les données de votre flux de données en tant que jeu de données de sortie ![jeu de données de sortie](../assets/output-dataset.svg), en utilisant **Query Service**.
- définition d’un **export du jeu de données planifié** qui exporte le jeu de données de sortie vers une destination de stockage dans le cloud, en utilisant **Exportation des jeux de données**.

![Flux de données](../assets/queryservice-export-datasets.svg)


## Conditions préalables

Veillez à respecter toutes les conditions requises ci-après avant d’utiliser les fonctionnalités décrites dans ce cas d’utilisation :

- Mise en oeuvre opérationnelle qui collecte des données dans le lac de données des Experience Platform.
- Accès au module complémentaire Data Distiller pour vous assurer que vous êtes autorisé à exécuter des requêtes par lots. Voir [Package Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/packaging) pour plus d’informations.
- Accès à la fonctionnalité Exporter les jeux de données , disponible lorsque vous avez acheté le package Real-Time CDP Prime ou Ultimate, Adobe Journey Optimizer ou Customer Journey Analytics. Voir [Exportation des jeux de données vers des destinations de stockage dans le cloud](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) pour plus d’informations.
- Une ou plusieurs destinations configurées (par exemple : Amazon S3, Google Cloud Storage) vers lesquelles vous pouvez exporter les données brutes de votre flux de données.


## Query Service

Experience Platform Query Service vous permet d’interroger et de joindre n’importe quel jeu de données dans le lac de données Experience Platform comme s’il s’agissait d’une table de base de données. Vous pouvez ensuite capturer les résultats sous la forme d’un nouveau jeu de données en vue d’une utilisation ultérieure dans les rapports ou pour l’exportation.

Vous pouvez utiliser Query Service [interface utilisateur](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/overview), un [client connecté via le protocole PostgresQL](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview), ou [API RESTful](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) pour créer et planifier des requêtes qui collectent les données de votre flux de données.

### Créer une requête

Vous pouvez utiliser toutes les fonctionnalités de SQL ANSI standard pour les instructions SELECT et d’autres commandes limitées afin de créer et d’exécuter des requêtes qui génèrent les données de votre flux de données. Voir [Syntaxe SQL](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/syntax) pour plus d’informations. Au-delà de cette syntaxe SQL, Adobe prend en charge :

- prédéfinie [Fonctions définies par Adobe (ADF)](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) qui aident à effectuer des tâches commerciales courantes sur les données d’événement stockées dans le lac de données Experience Platform, y compris des fonctions pour [Sessionization](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing) et [Attribution](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview),
- plusieurs composants intégrés [Fonctions Spark SQL](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions),
- [Commandes de métadonnées PostgreSQL](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/metadata),
- [instructions préparées](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/prepared-statements).

#### Colonnes de flux de données

Les champs XDM que vous pouvez utiliser dans votre requête dépendent de la définition de schéma sur laquelle vos jeux de données sont basés. Assurez-vous de bien comprendre le schéma sous-jacent au jeu de données. Pour plus d’informations, voir [Guide de l’interface utilisateur des jeux de données](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide).

Pour vous aider à définir le mappage entre les colonnes de flux de données et les champs XDM, voir [Mappage des champs Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). Voir aussi [Présentation de l’interface utilisateur des schémas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/overview#defining-xdm-fields) pour plus d’informations sur la gestion des ressources XDM, notamment les schémas, les classes, les groupes de champs et les types de données.

Par exemple, si vous souhaitez utiliser *nom de page* dans votre flux de données :

- Dans l’interface utilisateur du flux de données Adobe Analytics, vous pouvez sélectionner **[!UICONTROL pagename]** comme colonne à ajouter à votre définition de flux de données.
- Dans Query Service, vous incluez `web.webPageDetails.name` de la `sample_event_dataset_for_website_global_v1_1` jeu de données (basé sur la variable **Exemple de schéma d’événement pour le site web (Global v1.1)** schéma d’événement d’expérience) dans votre requête. Voir [Groupe de champs de schéma Détails web](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/web-details) pour plus d’informations.


#### Identités

Dans Experience Platform, différentes identités sont disponibles. Lors de la création de vos requêtes, vérifiez que vous interrogez correctement les identités.


Souvent, les identités se trouvent dans un groupe de champs distinct. Dans un ECID d’implémentation (`ecid`) peut être défini comme faisant partie d’un groupe de champs avec un `core` , qui fait elle-même partie d’un objet `identification` (par exemple : `_sampleorg.identification.core.ecid`). Les ECID peuvent être organisés différemment dans vos schémas.

Vous pouvez également utiliser `identityMap` pour rechercher des identités. La variable `identityMap` est de type `Map` et utilise une [structure de données imbriquées](#nested-data-structure).

Voir [Définition des champs d’identité dans l’interface utilisateur](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) pour plus d’informations sur la définition des champs d’identité dans Experience Platform.

Voir [Identifiants de Principal dans les données Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data) pour comprendre comment les identités Adobe Analytics sont mappées aux identités Experience Platform lors de l’utilisation du connecteur source Analytics. Ce mappage peut servir de guide pour la configuration de vos identités, même si vous n’utilisez pas le connecteur source Analytics.


#### Données et identification au niveau de l’accès

En fonction de l’implémentation, les données au niveau de l’accès traditionnellement collectées dans Adobe Analytics sont désormais stockées en tant que données d’événement horodatées dans Experience Platform. Le tableau suivant est extrait de [Mappage des champs Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields) et montre des exemples de mappage de colonnes de flux de données Adobe Analytics spécifiques au niveau de l’accès avec les champs XDM correspondants dans vos requêtes. Le tableau présente également des exemples d’identification des accès, des visites et des visiteurs à l’aide de champs XDM.

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

Les flux de données Adobe Analytics utilisent le concept de colonnes avec un `post_` qui sont des colonnes contenant des données après traitement. Pour plus d’informations, consultez la [FAQ sur les flux de données](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/df-faq#post).

Les données collectées dans les jeux de données par le biais de l’Edge Network Experience Platform (SDK Web, SDK Mobile, API de serveur) n’ont aucun concept de `post_` des champs. Par conséquent, `post_` préfixé et *non*-`post_` les colonnes de flux de données prédéfinies sont mappées aux mêmes champs XDM. Par exemple, les deux `page_url` et `post_page_url` les colonnes des flux de données sont mappées sur le même `web.webPageDetails.URL` Champ XDM.

Voir [Comparaison du traitement des données dans Adobe Analytics et Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons) pour un aperçu de la différence de traitement des données.

La variable `post_` lorsqu’elles sont collectées dans le lac de données Experience Platform, le type de colonne préfixe de données nécessite toutefois des transformations avancées avant de pouvoir être utilisé avec succès dans un cas d’utilisation de flux de données. L’exécution de ces transformations avancées dans vos requêtes implique l’utilisation de la fonction [Fonctions définies par Adobe](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) pour la session, l’attribution et le dédoublonnage. Voir [Exemples](#examples) sur l’utilisation de ces fonctions.

#### Recherches

Pour rechercher des données d’autres jeux de données, vous utilisez la fonctionnalité SQL standard (`WHERE` clause, `INNER JOIN`, `OUTER JOIN`, etc.).

#### Calculs

Pour effectuer des calculs sur les champs (colonnes), utilisez les fonctions SQL standard (par exemple `COUNT(*)`), ou la variable [opérateurs mathématiques et statistiques et fonctions](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#math) fait partie de Spark SQL. En outre, [fonctions de fenêtre](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions#window-functions) prennent en charge la mise à jour des agrégations et le renvoi d’éléments uniques pour chaque ligne d’un sous-ensemble ordonné. Voir [Exemples](#examples) sur l’utilisation de ces fonctions.

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

Vous pouvez utiliser la variable [`explode()` ou d’autres fonctions de tableau](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#arrays) de Spark SQL pour accéder aux données dans une structure de données imbriquée, par exemple :

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Vous pouvez également faire référence à des éléments individuels à l’aide de la notation par points. Par exemple :

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Voir [Utiliser les structures de données imbriquées dans Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/nested-data-structures) pour plus d’informations.


#### Exemples

Pour les requêtes :

- qui utilisent les données des jeux de données du lac de données Experience Platform,
- exploite les fonctionnalités supplémentaires des fonctions définies par l’Adobe et/ou de Spark SQL, et
- qui produirait des résultats similaires à un flux de données Adobe Analytics équivalent,

voir :

- [navigateur abandonné](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/abandoned-browse)
- [analyse d’attribution](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/attribution-analysis)
- [filtrage de robots](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/bot-filtering)
- et autres [cas d’utilisation pris en charge dans le guide Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/overview).


### Planification de la requête

Vous planifiez la requête pour vous assurer qu’elle est exécutée et que les résultats sont générés selon l’intervalle de votre choix.

#### Utilisation de Query Editor

Vous pouvez planifier une requête à l’aide de Query Editor. Lors de la planification de la requête, vous définissez un jeu de données de sortie. Voir [Planifications de requête](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/query-schedules) pour plus d’informations.


#### Utilisation de l’API Query Service

Vous pouvez également utiliser les API RESTful pour définir une requête et un planning pour la requête. Voir [Guide de l’API Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) pour plus d’informations.
Assurez-vous de définir le jeu de données de sortie dans le cadre de l’option `ctasParameters` lors de la création de la requête ([Créer une requête](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) ou lors de la création du planning d’une requête ([Création d’une requête planifiée](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Exportation de jeux de données

Une fois que vous avez créé et planifié votre requête, et vérifié les résultats, vous pouvez exporter les jeux de données bruts vers des destinations de stockage dans le cloud. Cette exportation est conforme à la terminologie des destinations Experience Platform appelée destinations d’exportation de jeux de données. Voir [Exportation des jeux de données vers des destinations de stockage dans le cloud](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) pour une vue d’ensemble.

Les destinations de stockage dans le cloud suivantes sont prises en charge :

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Zone d’atterrissage des données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp)


### Interface utilisateur Experience Platform

Vous pouvez exporter et planifier l’exportation de vos jeux de données de sortie via l’interface utilisateur Experience Platform. Cette section décrit les étapes à suivre.

#### Sélectionner la destination

Lorsque vous avez déterminé la destination de stockage dans le cloud vers laquelle vous souhaitez exporter le jeu de données de sortie, [sélectionner la destination ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Lorsque vous n’avez pas encore configuré de destination pour votre espace de stockage préféré dans le cloud, vous devez [créer une connexion de destination ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Lors de la configuration d’une destination, vous pouvez

- définir le type de fichier (JSON ou Parquet),
- si le fichier obtenu doit être compressé ou non, et
- si un fichier de manifeste doit être inclus ou non.


#### Sélectionner le jeu de données

Lorsque vous avez sélectionné la destination, dans la **[!UICONTROL Sélectionner des jeux de données]** vous devez sélectionner votre jeu de données de sortie dans la liste des jeux de données. Si vous avez créé plusieurs requêtes planifiées et que vous souhaitez que les jeux de données de sortie soient envoyés vers la même destination de stockage dans le cloud, vous pouvez sélectionner les jeux de données de sortie correspondants. Voir [Sélectionner vos jeux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) pour plus d’informations.

#### Planifier l’exportation des jeux de données

Enfin, vous souhaitez planifier l’exportation de votre jeu de données dans le cadre du **[!UICONTROL Planification]** étape . Au cours de cette étape, vous pouvez définir le planning et indiquer si l’exportation du jeu de données de sortie doit être incrémentielle ou non. Voir [Planification de l’exportation des jeux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) pour plus d’informations.


#### Étapes finales

[Réviser](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) votre sélection, et lorsque cela est correct, commencez à exporter votre jeu de données de sortie vers la destination de stockage dans le cloud.

Vous devez [verify](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) une exportation de données réussie. Lors de l’exportation de jeux de données, Experience Platform en crée un ou plusieurs `.json` ou `.parquet` dans l’emplacement de stockage défini dans votre destination. Attendez-vous à ce que les nouveaux fichiers soient déposés dans votre emplacement de stockage en fonction du planning d’exportation que vous configurez. Experience Platform crée une structure de dossiers dans l’emplacement de stockage que vous avez spécifié comme faisant partie de la destination sélectionnée, où il dépose les fichiers exportés. Un nouveau dossier est créé pour chaque heure d’exportation, selon le modèle suivant : `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Le nom de fichier par défaut est généré de manière aléatoire pour garantir que les noms de fichier exportés soient uniques.

### API de service de flux

Vous pouvez également exporter et planifier l’exportation des jeux de données de sortie à l’aide d’API. Les étapes à suivre sont décrites dans la section [Exportation de jeux de données à l’aide de l’API Flow Service](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### Prise en main

Pour exporter des jeux de données, assurez-vous que vous disposez de la variable [autorisations requises](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). Vérifiez également que la destination vers laquelle vous souhaitez envoyer votre jeu de données de sortie prend en charge l’exportation de jeux de données. Vous devez alors [rassembler les valeurs des en-têtes requis et facultatifs ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) que vous utilisez dans les appels API. Vous devez également [identifier les spécifications de connexion et les identifiants de spécification de flux de la destination ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) vous envisagez d’exporter des jeux de données vers .

#### Récupération des jeux de données éligibles

Vous pouvez [récupérer une liste de jeux de données éligibles ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) pour l’exportation et vérifiez si votre jeu de données de sortie fait partie de cette liste à l’aide de la variable [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Création d’une connexion source

Ensuite, vous devez [créer une connexion source ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) pour le jeu de données de sortie, à l’aide de son identifiant unique, que vous souhaitez exporter vers la destination de stockage dans le cloud. Vous utilisez la variable [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Authentification à la destination (créer une connexion de base)

Vous devez maintenant [créer une connexion de base ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) pour vous authentifier et stocker en toute sécurité les informations d’identification dans votre destination de stockage dans le cloud à l’aide de la variable [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Fournir des paramètres d’exportation

Ensuite, vous devez [créer une connexion cible supplémentaire qui stocke les paramètres d’exportation ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) pour votre jeu de données de sortie en utilisant, une fois de plus, la variable [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Ces paramètres d’exportation incluent l’emplacement, le format de fichier, la compression, etc.

#### Configuration du flux de données

Enfin, vous [Configuration du flux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) pour vous assurer que votre jeu de données de sortie est exporté vers votre destination de stockage dans le cloud à l’aide de la variable [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. Au cours de cette étape, vous pouvez définir le planning de l&#39;export, à l&#39;aide du `scheduleParams` .

#### Validation du flux de données

À [vérifier les exécutions réussies de votre flux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), utilisez le [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, spécifiant l’identifiant de flux de données comme paramètre de requête. Cet identifiant de flux de données est un identifiant renvoyé lors de la configuration du flux de données.

[Vérifier](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) une exportation de données réussie. Lors de l’exportation de jeux de données, Experience Platform en crée un ou plusieurs `.json` ou `.parquet` dans l’emplacement de stockage défini dans votre destination. Attendez-vous à ce que les nouveaux fichiers soient déposés dans votre emplacement de stockage en fonction du planning d’exportation que vous configurez. Experience Platform crée une structure de dossiers dans l’emplacement de stockage que vous avez spécifié comme faisant partie de la destination sélectionnée, où il dépose les fichiers exportés. Un nouveau dossier est créé pour chaque heure d’exportation, selon le modèle suivant : `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Le nom de fichier par défaut est généré de manière aléatoire pour garantir que les noms de fichier exportés soient uniques.

## Conclusion

En résumé, l’émulation de la fonctionnalité de flux de données Adobe Analytics implique la configuration de requêtes planifiées à l’aide de Query Service et l’utilisation des résultats de ces requêtes dans les exportations planifiées de jeux de données.

>[!IMPORTANT]
>
>Deux planificateurs sont impliqués dans ce cas pratique. Pour garantir le bon fonctionnement de la fonctionnalité de flux de données émulé, assurez-vous que les plannings configurés dans Query Service et dans les exportations de données n’interfèrent pas.