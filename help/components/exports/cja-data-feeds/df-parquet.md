---
title: Utiliser des fichiers Parquet à partir des flux de données Customer Journey Analytics
description: Découvrez pourquoi les flux de données Customer Journey Analytics diffusent des fichiers Parquet, comment le fichier Parquet se compare aux fichiers CSV, TSV et JSON, et comment interroger ou charger les fichiers.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: f77f416ad958b28a8489d7a6eb13100ba699236e
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%
---
# Utiliser des fichiers Parquet dans les flux de données

{{release-limited-testing}}

Les flux de données Customer Journey Analytics diffusent des fichiers au format Parquet. La plupart des entrepôts de données modernes peuvent lire les fichiers Parquet directement, de sorte que vous n&#39;avez généralement pas besoin de convertir les fichiers avant de les utiliser.

Utilisez les informations suivantes pour comprendre pourquoi les flux de données utilisent Parquet, comment Parquet se compare à d’autres formats de fichiers et comment interroger ou charger des fichiers Parquet dans votre entrepôt de données.

## Avantages de l’utilisation de Parquet pour les flux de données

Parquet est mieux adapté à la sortie de flux de données que CSV, TSV ou JSON pour les raisons suivantes :

* **Flux étendus** : les flux de données peuvent comporter des centaines de colonnes. Parquet permet à une requête de lire uniquement les colonnes dont elle a besoin.

* **Champs imbriqués** : le parquet représente les champs imbriqués, tels qu’une liste de produits, de manière native. Les formats CSV et TSV ne peuvent les représenter qu’en les codant en chaînes. Pour plus d’informations, voir [Composants de sous-événement dans les flux de données](/help/components/exports/cja-data-feeds/df-sub-event.md).

* **Schéma intégré** : chaque fichier Parquet stocke son propre schéma, y compris les noms de colonne, les types de données et les structures imbriquées. Comme le schéma se trouve dans le fichier , votre entrepôt de données peut créer des tables directement à partir des fichiers . Vous n’avez pas besoin de fournir un fichier d’en-tête distinct ou une définition de schéma, et l’entrepôt de données n’a pas besoin d’en déduire des types de données.

* **Exportations importantes** : Le parquet réduit généralement les coûts de stockage et de transfert. Cela évite également l’analyse de texte lorsque vous chargez les données.

## Comparaison de Parquet aux formats CSV, TSV et JSON

CSV, TSV et JSON sont des formats de fichiers courants basés sur du texte :

* **CSV et TSV** : chaque ligne de données est une ligne de texte brut, avec des valeurs séparées par des virgules (CSV) ou des tabulations (TSV). Les flux de données Adobe Analytics diffusent des fichiers TSV. Pour connaître les autres différences entre les flux de données dans Customer Journey Analytics et Adobe Analytics, voir [Comparer les flux de données dans Customer Journey Analytics et Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

* **JSON** : chaque enregistrement est stocké en tant que texte avec des champs nommés et peut inclure des tableaux et des objets imbriqués.

Le tableau suivant présente les différences entre Parquet, CSV, TSV et JSON :

| Caractéristique | Parquet | CSV ou TSV | JSON |
| --- | --- | --- | --- |
| **Vitesse des requêtes** | Vite. Une requête lit uniquement les colonnes dont elle a besoin. | Plus lentement. Des lignes entières doivent être lues et analysées. | Plus lentement. Des lignes entières doivent être lues et analysées. |
| **Types des données** | Saisi. Le schéma est incorporé dans le fichier . | Non typé. Toutes les valeurs sont au format texte et les types sont déduits lors du chargement des données. | Lentement tapé. |
| **Données imbriquées** | Les tableaux et les objets sont pris en charge de manière native. | Non pris en charge. Les tableaux et les objets doivent être aplatis ou codés en tant que chaînes. | Les tableaux et les objets sont pris en charge de manière native. |
| **Lisibilité** | Nécessite un outil tel que votre entrepôt de données, DuckDB ou Python. | S’ouvre dans un éditeur de texte ou une feuille de calcul. | S’ouvre dans un éditeur de texte. |

## Requête ou chargement de fichiers Parquet

Les fichiers de flux de données sont diffusés au format Parquet à l’emplacement d’espace de stockage que vous avez sélectionné lors de la [création du flux de données](/help/components/exports/cja-data-feeds/create-feed.md).

Plutôt que de télécharger les fichiers, vous connectez généralement votre entrepôt de données à l’emplacement de stockage . Vous pouvez ensuite utiliser les fichiers Parquet de l’une des manières suivantes :

### Interroger les fichiers en place

Définissez une table externe qui pointe vers les fichiers de votre espace de stockage dans le cloud. L’entrepôt de données lit les fichiers lorsque vous exécutez une requête.

* **** : tables externes ou requêtes sur une étape externe
* **Bricks de données** : tables externes sur Amazon S3, Azure Data Lake Storage (ADLS) ou Google Cloud Storage
* **BigQuery** : tables externes sur Google Cloud Storage
* **Amazon Redshift** : spectre Redshift sur Amazon S3

### Charger les fichiers dans les tables managées

Le chargement de fichiers dans des tables gérées est un choix courant pour les charges de travail récurrentes. Par exemple :

* **Snowflake** : `COPY INTO`
* **BigQuery** : chargement de tâches
* **Briques de données** : `COPY INTO` ou chargeur automatique

## Convertir les données Parquet en CSV ou JSON

Si vos processus en aval nécessitent des fichiers CSV ou JSON, la plupart des entrepôts de données et des outils peuvent exporter des données Parquet vers l’un ou l’autre format après leur chargement. Par exemple, dans Snowflake, vous pouvez décharger les résultats de la requête au format CSV ou JSON avec des `COPY INTO`.
