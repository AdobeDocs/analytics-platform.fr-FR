---
title: Configuration des solutions natives Data Warehouse
description: Découvrez comment configurer des solutions natives d’entrepôt de données pour Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
source-git-commit: b585187f112c2081a8e51bd84d9f95e75ceebdc3
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Configuration des solutions natives Data Warehouse

{{release-limited-testing}}

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

Pour plus d’informations, consultez le guide sur les instructions de langage de définition de données dans [ [!DNL GoogleSQL]](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list).

Lisez la documentation suivante pour savoir comment activer la capture de données de modification pour votre connexion source [!DNL Google BigQuery] :

* [Créer une connexion  [!DNL Google BigQuery]  base](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/bigquery).
* [Créer une connexion source pour une base de données](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Snowflake]

Activez le **suivi des modifications** dans vos tables [!DNL Snowflake] pour utiliser la capture de données de modification dans vos connexions source.

Dans [!DNL Snowflake], activez le suivi des modifications à l’aide de l’`ALTER TABLE` et définissez `CHANGE_TRACKING` sur `TRUE`.

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

Pour plus d’informations, consultez le guide [[!DNL Snowflake]  sur l’utilisation de la clause de modification ](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes).

Lisez la documentation suivante pour savoir comment activer la capture de données de modification pour votre connexion source [!DNL Snowflake] :

* [Créer une connexion  [!DNL Snowflake]  base](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/snowflake).
* [Créer une connexion source pour une base de données](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).


>[!MORELIKETHIS]
>
>Guide de démarrage rapide de [Data Mirror : mise en miroir et utilisation de données basées sur des modèles](model-based.md)
>
