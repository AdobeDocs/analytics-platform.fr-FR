---
title: Configuration des solutions natives Data Warehouse
description: Découvrez comment configurer des solutions natives d’entrepôt de données pour Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
autotag-review: '2026-05-19T08:56:46.637Z'
TQID: 'https://experienceleague.adobe.com/A3GkkNVAO9qpbOqCrZnf6PNJfRuwMaodJVOOuSRg0w8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 441
ht-degree: 0%

---

# Configuration des solutions natives Data Warehouse

Pour prendre en charge Experience Platform Data Mirror for Customer Journey Analytics, les données que vous souhaitez utiliser à partir des trois solutions natives d’entrepôt de données prises en charge ([[!DNL Azure Databricks]](#azure-databricks), [[!DNL Google BigQuery]](#google-bigquery), [[!DNL Snowflake]](#snowflake)) doivent être activées pour la capture de données de modification.


## [!DNL Azure Databricks]

Activez **modifier le flux de données** dans vos tableaux de [!DNL Azure Databricks] pour utiliser la capture de données de modification dans votre connexion source.

Utilisez les commandes suivantes pour activer la modification du flux de données sur vos tableaux :

**Nouveau tableau**

Pour appliquer le flux de données de modification à un nouveau tableau, vous devez définir la propriété de tableau `delta.enableChangeDataFeed` sur `TRUE` dans la commande `CREATE TABLE`.

```sql
CREATE TABLE student (id INT, name STRING, age INT) TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**Table existante**

Pour appliquer le flux de données de modification à un tableau existant, vous devez définir la propriété de tableau `delta.enableChangeDataFeed` sur `TRUE` dans la commande `ALTER TABLE`.

```sql
ALTER TABLE myDeltaTable SET TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**Toutes les nouvelles tables**

Pour appliquer le flux de données de modification à tous les nouveaux tableaux, vous devez définir vos propriétés par défaut sur `TRUE`.

```sql
set spark.databricks.delta.properties.defaults.enableChangeDataFeed = true;
```

Pour plus d’informations, consultez le guide [[!DNL Azure Databricks]  sur l’activation du flux de données de modification](https://docs.databricks.com/aws/en/delta/delta-change-data-feed#enable-change-data-feed).

Lisez la documentation suivante pour savoir comment activer la capture de données de modification pour votre connexion source [!DNL Azure Databricks] :

* [Créer une connexion  [!DNL Azure Databricks]  base](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/databricks).
* [Créer une connexion source pour une base de données](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Google BigQuery]

Pour utiliser la capture de données de modification dans votre connexion source [!DNL Google BigQuery], accédez à la page [!DNL Google BigQuery] dans la console [!DNL Google Cloud] et définissez `enable_change_history` sur `TRUE`. Cette propriété active l&#39;historique des modifications de votre tableau de données.

Pour plus d’informations, consultez le guide sur les instructions de langage de définition de données dans  [!DNL GoogleSQL][&#128279;](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list).

Lisez la documentation suivante pour savoir comment activer la capture de données de modification pour votre connexion source [!DNL Google BigQuery] :

* [Créer une connexion  [!DNL Google BigQuery]  base](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/bigquery).
* [Créer une connexion source pour une base de données](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Snowflake]

Activez le **suivi des modifications** dans vos tables [!DNL Snowflake] pour utiliser la capture de données de modification dans vos connexions source.

Dans [!DNL Snowflake], activez le suivi des modifications à l’aide de l’`ALTER TABLE` et définissez `CHANGE_TRACKING` sur `TRUE`.

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

Pour plus d’informations, consultez le guide [[!DNL Snowflake]  sur l’utilisation de la clause de modification &#x200B;](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes).

Lisez la documentation suivante pour savoir comment activer la capture de données de modification pour votre connexion source [!DNL Snowflake] :

* [Créer une connexion  [!DNL Snowflake]  base](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/snowflake).
* [Créer une connexion source pour une base de données](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).


>[!MORELIKETHIS]
>
>Guide de démarrage rapide de [Data Mirror : mise en miroir et utilisation des données relationnelles](relational.md)
>
