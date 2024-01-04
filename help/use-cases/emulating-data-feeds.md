---
title: Émuler la fonctionnalité de flux de données
description: Découvrez comment émuler des flux de données Adobe Analytics avec des données dans Experience Platform.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '2556'
ht-degree: 17%

---

# Émuler la fonctionnalité de flux de données

Les flux de données Adobe Analytics sont un moyen puissant d’extraire des données brutes d’Adobe Analytics. Ce cas d’utilisation décrit comment obtenir du Experience Platform un type similaire de données brutes, de sorte que vous puissiez utiliser les données dans d’autres plateformes, des outils en dehors de l’Adobe et à la discrétion de votre entreprise.

## Introduction

L’émulation d’un flux de données Adobe Analytics implique :

* définition d’un **requête planifiée** qui génère les données de votre flux de données en tant que jeu de données de sortie ![jeu de données de sortie](assets/output-dataset.svg), en utilisant **Query Service**.
* définition d’un **export du jeu de données planifié** qui exporte le jeu de données de sortie vers une destination de stockage dans le cloud, en utilisant **Exportation des jeux de données**.

![Flux de données](assets/data-feed.svg)


## Conditions préalables

Veillez à respecter toutes les conditions requises ci-après avant d’utiliser les fonctionnalités décrites dans ce cas d’utilisation :

* Mise en oeuvre opérationnelle qui collecte des données dans le lac de données des Experience Platform.
* Accédez au module complémentaire Data Distiller pour vous assurer que vous êtes autorisé à exécuter des requêtes par lots. Voir [Package Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) pour plus d’informations.
* Accès à la fonctionnalité Exporter les jeux de données , disponible lorsque vous avez acheté le package Real-Time CDP Prime ou Ultimate, Adobe Journey Optimizer ou Customer Journey Analytics. Voir [Exportation des jeux de données vers des destinations de stockage dans le cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=fr) pour plus d’informations.
* Une ou plusieurs destinations (par exemple : Amazon S3, Google Cloud Storage) configurées pour vous permettre d’exporter les données brutes de votre flux de données.


## Query Service

Experience Platform Query Service vous permet d’interroger et de joindre n’importe quel jeu de données dans un lac de données Experience Platform comme s’il s’agissait d’une table de base de données. Vous pouvez ensuite capturer les résultats sous la forme d’un nouveau jeu de données en vue d’une utilisation ultérieure dans les rapports ou pour l’exportation.

Vous utilisez Query Service [interface utilisateur](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en), un [client connecté via le protocole PostgresQL](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=fr), ou [API RESTful](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) pour créer et planifier des requêtes qui collectent les données de votre flux de données.

### Créer une requête

Vous pouvez utiliser toutes les fonctionnalités de SQL ANSI standard pour les instructions SELECT et d’autres commandes limitées afin de créer et d’exécuter des requêtes qui génèrent les données de votre flux de données. Voir [Syntaxe SQL](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) pour plus d’informations. Au-delà de cette syntaxe SQL, Adobe prend en charge :

* prédéfinie [Fonctions définies par Adobe (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) qui aident à effectuer des tâches commerciales courantes sur les données d’événement stockées dans le lac de données Experience Platform, y compris des fonctions pour [Sessionization](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=fr) et [Attribution](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=fr),
* plusieurs composants intégrés [Fonctions Spark SQL](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en),
* [Commandes de métadonnées PostgreSQL](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en),
* [instructions préparées](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### Identités

Dans Experience Platform, différentes identités sont disponibles. Lors de la création de vos requêtes, vérifiez que vous interrogez correctement les identités.

Souvent, les identités se trouvent dans un groupe de champs distinct. Dans un ECID d’implémentation (`ecid`) peut être défini comme faisant partie d’un groupe de champs avec un `core` , qui fait elle-même partie d’un objet `identification` . (par exemple : `_sampleorg.identification.core.ecid`). Les ECID peuvent être organisés différemment dans vos schémas.

Vous pouvez également utiliser `identityMap` pour rechercher des identités. Cet objet est de type `Map` et utilise une [structure de données imbriquées](#nested-data-structure).


#### Colonnes de flux de données

Les champs XDM que vous pouvez utiliser dans votre requête dépendent de la définition de schéma sur laquelle vos jeux de données sont basés. Assurez-vous de bien comprendre le schéma sous-jacent au jeu de données.

Pour faciliter le mappage entre les colonnes de flux de données et les champs XDM, vous devez envisager d’inclure la variable [Modèle ExperienceEvent Adobe Analytics](https://github.com/adobe/xdm/blob/master/extensions/adobe/experience/analytics/experienceevent-all.schema.json) groupe de champs dans votre schéma d’événement d’expérience. Voir [Bonnes pratiques relatives à la modélisation des données](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=en) et plus spécifiquement [Adobe de groupes de champs de schéma d’application](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=en#adobe-application-schema-field-groups).

Par exemple, si vous souhaitez utiliser *nom de page* dans votre flux de données :

* Dans l’interface utilisateur du flux de données Adobe Analytics, vous pouvez sélectionner **[!UICONTROL pagename]** comme colonne à ajouter à votre définition de flux de données.
* Dans Query Service, vous incluez `web.webPageDetails.name` de la `sample_event_dataset_for_website_global_v1_1` jeu de données (basé sur la variable **Exemple de schéma d’événement pour le site web (Global v1.1)** schéma d’événement d’expérience) dans votre requête. Voir [Groupe de champs de schéma Détails web](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) pour plus d’informations.

Pour comprendre le mappage entre les anciennes colonnes de flux de données Adobe Analytics et les champs XDM dans votre jeu de données d’événement d’expérience et votre schéma sous-jacent, voir [Mappage des champs Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=fr) et la variable [Groupe de champs de l’extension complète Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) pour plus d’informations.

En outre, la [collecte automatique des informations par le SDK Web Experience Platform (prêt à l’emploi)](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) peut être utile pour identifier les colonnes de votre requête.

#### Données et identification au niveau de l’accès

En fonction de l’implémentation, les données au niveau de l’accès traditionnellement collectées dans Adobe Analytics sont désormais stockées en tant que données d’événement horodatées dans Experience Platform. Le tableau suivant est extrait de [Mappage des champs Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en#generated-mapping-fields) et montre des exemples de mappage des colonnes de flux de données Adobe Analytics spécifiques au niveau de l’accès avec les champs XDM correspondants dans vos requêtes. Le tableau présente également des exemples d’identification des accès, des visites et des visiteurs à l’aide de champs XDM.

| Colonne de flux de données | Champ XDM | Type | Description |
|---|---|---|---|
| hitid_high + hitid_low | _id | string | Identifiant unique permettant d’identifier un accès. |
| hitid_low | _id | string | Utilisé conjointement avec hitid_high pour identifier de manière unique un accès. |
| hitid_high | _id | string | Utilisé conjointement avec hitid_high pour identifier de manière unique un accès. |
| hit_time_gmt | receivedTimestamp | string | Horodatage de l’accès, selon l’heure Unix. |
| first_hit_time_gmt | _experience.analytics.endUser.firstTimestamp | string | Horodatage du tout premier accès du visiteur en heure Unix. |
| cust_hit_time_gmt | timestamp | string | Utilisé uniquement dans les jeux de données horodatés. Il s’agit de l’horodatage envoyé avec l’accès, selon l’heure Unix. |
| visid_high + visid_low | identityMap | objet | Identifiant unique d’une visite. |
| visid_high + visid_low | endUserIDs._experience.aaid.id | string | Identifiant unique d’une visite. |
| visid_high | endUserIDs._experience.aaid.primary | booléen | Utilisé conjointement avec visid_low pour identifier de manière unique une visite. |
| visid_high | endUserIDs._experience.aaid.namespace.code | string | Utilisé conjointement avec visid_low pour identifier de manière unique une visite. |
| visid_low | identityMap | objet | Utilisé conjointement avec visid_high pour identifier de manière unique une visite. |
| cust_visid | identityMap | objet | Identifiant visiteur du client |
| cust_visid | endUserIDs._experience.aacustomid.id | objet | Identifiant visiteur du client. |
| cust_visid | endUserIDs._experience.aacustomid.primary | booléen | Code d’espace de noms de l’identifiant visiteur du client. |
| cust_visid | endUserIDs._experience.aacustomid.namespace.code | string | Utilisé conjointement avec visid_low pour identifier de manière unique l’identifiant visiteur du client. |
| geo\_* | placeContext.geo.* | chaîne, nombre | Données de géolocalisation, telles que pays, région, ville et autres |
| visit_page_num | _experience.analytics.session.depth | number | Variable utilisée dans la dimension Détail des accès. Cette valeur augmente de 1 pour chaque accès généré par l’utilisateur et est réinitialisée après chaque visite. |
| event_list | commerce.achats, commerce.productViews, commerce.productListOpens, commerce.checkouts, commerce.productListAdds, commerce.productListRemovals, commerce.productListViews, \_experience.analytics.event101to200.*, ..., \_experience.analytics.event901_1000.\* | string | Événements de commerce standard et personnalisés déclenchés lors de l’accès. |
| page_event | web.webInteraction.type | string | Le type d’accès qui est envoyé dans la demande d’image (accès standard, lien de téléchargement, lien de sortie ou lien personnalisé sur lequel le visiteur a cliqué). |
| page_event | web.webInteraction.linkClicks.value | number | Le type d’accès qui est envoyé dans la demande d’image (accès standard, lien de téléchargement, lien de sortie ou lien personnalisé sur lequel le visiteur a cliqué). |
| page_event_var_1 | web.webInteraction.URL | string | Variable utilisée uniquement dans les demandes d’image de suivi de liens. Cette variable contient l’URL du lien de téléchargement, de sortie ou personnalisé sur lequel a cliqué l’utilisateur. |
| page_event_var_2 | web.webInteraction.name | string | Variable utilisée uniquement dans les demandes d’image de suivi de liens. Répertorie le nom personnalisé du lien, s’il est spécifié. |
| first_hit_ref_type | _experience.analytics.endUser.firstWeb.webReferrer.type | string | Identifiant numérique, représentant le type de référent du tout premier référent du visiteur. |
| first_hit_time_gmt | _experience.analytics.endUser.firstTimestamp | entier | Horodatage du tout premier accès du visiteur en heure Unix. |
| paid_search | search.isPaid | booléen | Indicateur défini si l’accès correspond à la détection des référencements payants. |
| ref_type | web.webReferrertype | string | Identifiant numérique représentant le type de référence pour l’accès. |

#### Colonnes de publication

Les flux de données Adobe Analytics utilisent le concept de colonnes avec un `post_` qui sont des colonnes contenant des données après traitement. Pour plus d’informations, consultez la [FAQ sur les flux de données](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html?lang=en#post).

Les données collectées dans les jeux de données par le biais du réseau Edge Experience Platform (SDK web, SDK mobile, API serveur) n’ont aucun concept de `post_` , ce qui explique pourquoi `post_` préfixé et *non* `post_` préfixe des colonnes de flux de données dans le mappage des champs Analytics sur les mêmes champs XDM. Par exemple, les deux `page_url` et `post_page_url` les colonnes des flux de données sont mappées sur le même `web.webPageDetails.URL` Champ XDM.

Voir [Comparaison du traitement des données dans Adobe Analytics et Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html?lang=fr) pour un aperçu de la différence de traitement des données.

La variable `post_` lorsqu’elles sont collectées dans le lac de données Experience Platform, le type de colonne préfixe de données nécessite toutefois des transformations avancées avant de pouvoir être utilisé avec succès dans un cas d’utilisation de flux de données. L’exécution de ces transformations avancées dans vos requêtes implique l’utilisation de la fonction [Fonctions définies par Adobe](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) pour la session, l’attribution et le dédoublonnage. Voir [Exemples](#examples) sur l’utilisation de ces fonctions.

#### Recherches

Pour rechercher des données d’autres jeux de données, vous utilisez la fonctionnalité SQL standard (`WHERE` clause, `INNER JOIN`, `OUTER JOIN`, etc.).

#### Calculs

Pour effectuer des calculs sur les champs (colonnes), utilisez les fonctions SQL standard (par exemple `COUNT(*)` ou le [opérateurs mathématiques et statistiques et fonctions](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) fait partie de Spark SQL. En outre, [fonctions de fenêtre](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en#window-functions) prennent en charge la mise à jour des agrégations et le renvoi d’éléments uniques pour chaque ligne d’un sous-ensemble ordonné. Voir [Exemples](#examples) sur l’utilisation de ces fonctions.

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

Vous pouvez utiliser la variable [`explode()` ou d’autres fonctions de tableau](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) de Spark SQL pour accéder aux données dans une structure de données imbriquée, par exemple :

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Vous pouvez également faire référence à des éléments individuels à l’aide de la notation par points. Par exemple :

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Voir [Utiliser les structures de données imbriquées dans Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en) pour plus d’informations.


#### Exemples

Par exemple, les requêtes qui utilisent des données de jeux de données dans le lac de données Experience Platform exploitent les fonctionnalités supplémentaires des fonctions définies par l’Adobe et/ou de Spark SQL, et qui produiraient des résultats similaires à un flux de données Adobe Analytics équivalent, voir

* [navigateur abandonné](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en),
* [analyse d’attribution](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en),
* [filtrage de robots](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en),
* et d’autres exemples d’utilisation dans le guide Query Service.


### Planification de la requête

Vous planifiez la requête pour vous assurer qu’elle est exécutée et que les résultats sont générés selon l’intervalle de votre choix.

#### Utilisation de Query Editor

Vous pouvez planifier une requête à l’aide de Query Editor. Lors de la planification de la requête, vous définissez un jeu de données de sortie. Voir [Planifications de requête](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) pour plus d’informations.


#### Utilisation de l’API Query Service

Vous pouvez également utiliser les API RESTful pour définir une requête et un planning pour la requête. Voir [Guide de l’API Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) pour plus d’informations.
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

