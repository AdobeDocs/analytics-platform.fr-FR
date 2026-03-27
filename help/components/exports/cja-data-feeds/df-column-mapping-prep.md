---
description: Découvrez comment vous préparer à mapper les colonnes de flux de données d’Adobe Analytics à Customer Journey Analytics.
keywords: flux de clics;flux de données;flux des données;Flux de données
title: Préparation du mappage des colonnes de flux de données d’Adobe Analytics vers Customer Journey Analytics
feature: Components
hide: true
hidefromtoc: true
exl-id: d0a9e697-1e48-4cfb-8613-2f932bf5015b
source-git-commit: 9403a4c6d0e0389de19aa4627d9d952f0c31f1a2
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 2%

---

# Préparer le mappage des colonnes de flux de données d’Adobe Analytics vers Customer Journey Analytics

Customer Journey Analytics offre une architecture plus flexible qu’Adobe Analytics pour déterminer les colonnes qui peuvent être incluses dans un flux de données. La plupart des entreprises doivent s’attendre à exporter des colonnes de flux de données de Customer Journey Analytics différentes de celles exportées à partir d’Adobe Analytics. Ces différences sont dues aux facteurs suivants :

* **[Architecture du schéma](#schema-architecture)** : les colonnes de flux de données d’Adobe Analytics sont dérivées des variables Analytics, tandis que les colonnes de flux de données de Customer Journey Analytics sont dérivées du schéma de la vue de données.

* **[Traitement des données](#data-processing)** : il existe des différences fondamentales de traitement des données entre Adobe Analytics et Customer Journey Analytics, en particulier l’existence de colonnes pré- et post-traitées pour de nombreuses colonnes d’Adobe Analytics.

* **[Colonnes inutilisées](#unused-columns)** : Adobe Analytics contient plus de 1 100 colonnes de flux de données. La plupart des organisations n’utilisent pas les données de toutes les colonnes exportées.

* **[Colonnes cross-canal](#cross-channel-columns)** : Customer Journey Analytics prend en charge les données cross-canal (telles que les données de centre d’appels), qui ne sont pas disponibles dans Adobe Analytics.

Avant de commencer à mapper les colonnes de flux de données Adobe Analytics aux colonnes de flux de données Customer Journey Analytics, consultez les sections ci-dessous pour mieux comprendre ces facteurs clés qui affectent le mappage.

Après avoir consulté ces informations, suivez les instructions de mappage pour chaque colonne de flux de données Adobe Analytics que vous prévoyez de conserver dans Customer Journey Analytics, comme décrit dans la section [Référence des colonnes de données](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

## Architecture des schémas

Customer Journey Analytics offre une architecture plus flexible qu’Adobe Analytics pour déterminer les colonnes disponibles à inclure dans un flux de données :

### Architecture d’Adobe Analytics

Une liste statique prédéfinie de variables peut être incluse en tant que colonnes de flux de données.

Il est facile d’inclure toutes les colonnes, comme le font de nombreux clients, même si les données contenues dans ces colonnes ne sont pas utilisées dans l’ensemble de l’organisation.

### Architecture de Customer Journey Analytics

Tous les composants inclus dans le schéma de vue de données peuvent être inclus en tant que colonnes de flux de données. Pour plus d’informations sur ce processus pour chaque colonne de flux de données Adobe Analytics potentielle, voir [Référence des colonnes de données](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

Les composants sont inclus dans le schéma de vue de données de l’une des manières décrites dans le tableau suivant :

| Méthode à inclure dans le schéma de la vue de données | Informations supplémentaires |
|---------|----------|
| Les champs de schéma XDM sont traités comme des composants dans la vue de données | Les champs qui existent dans votre schéma XDM font partie du schéma de vue de données dans Customer Journey Analytics après avoir été traités en tant que composants dans la vue de données. <p>Le nombre de champs disponibles par défaut dans votre schéma XDM Customer Journey Analytics peut varier en fonction de la manière dont les données sont collectées pour votre implémentation Customer Journey Analytics, comme suit :</p><ul><li>**Nouvelles implémentations de Web SDK** : si votre implémentation de Customer Journey Analytics utilise un schéma personnalisé, de nombreuses colonnes existant dans les flux de données Adobe Analytics n’existent probablement pas dans Customer Journey Analytics. De même, Customer Journey Analytics peut contenir des champs qui n’existent pas dans les flux de données Adobe Analytics.<p>Si possible, consultez l’équipe ou la personne qui a conçu le schéma XDM pour l’implémentation Customer Journey Analytics de votre organisation. La plupart des décisions concernant les champs Adobe Analytics nécessaires dans Customer Journey Analytics ont été prises lors de la création du schéma XDM. Pour plus d’informations, consultez [Concevoir le schéma à utiliser avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).</p></li><li>**Implémentations du connecteur Source Analytics** : les mappages de champs un-à-un existent par défaut pour de nombreuses colonnes de flux de données, car le connecteur Source Analytics utilise le groupe de champs Événement d’expérience Analytics dans le schéma XDM. Pour plus d’informations sur les champs Adobe Analytics mappés aux champs de ce groupe de champs, consultez [Mappages de champs Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) dans la documentation d’Experience Platform.</li></ul> |
| Les composants sont créés dans la vue de données à l’aide de champs dérivés | Vous pouvez créer des composants directement dans une vue de données, créant ainsi des colonnes de flux de données qui ne sont pas disponibles dans le schéma XDM. |

## Traitement des données

Les différences de traitement des données entre Adobe Analytics et Customer Journey Analytics affectent les colonnes de flux de données disponibles à l’exportation, comme suit :

* **** : de nombreux champs de flux de données sont exportés sous la forme de deux colonnes distinctes : l’une contenant des données prétraitées et l’autre des données post-traitées. (Les données post-traitées incluent la logique côté serveur, les règles de traitement, les règles VISTA, les règles de persistance des dimensions, etc.)

  Comme Adobe Analytics exporte les données de certains champs dans deux colonnes distinctes (une pour les données prétraitées et une pour les données post-traitées), Adobe Analytics contient plus de colonnes de flux de données que Customer Journey Analytics. Gardez cela en tête lors du mappage des champs.

* **** : les champs sont disponibles pour les flux de données après leur création dans la vue de données. En règle générale, les champs des vues de données Customer Journey Analytics incluent uniquement les données post-traitées. Cependant, vous pouvez généralement faire une estimation de la version prétraitée d’Adobe Analytics d’un champ en créant une deuxième version du champ dans la vue de données Customer Journey Analytics et en le configurant pour qu’il expire au moment de l’accès.

## Colonnes non utilisées

Plus de 1 100 colonnes de flux de données peuvent être exportées dans Adobe Analytics. De ces colonnes, toutes ne seront pas utilisées dans vos flux de données Customer Journey Analytics. Cette incohérence n’est pas une indication que vos colonnes de flux de données Customer Journey Analytics sont insuffisantes.

Identifiez les colonnes de flux de données Adobe Analytics que votre organisation utilise. Cela permet de déterminer les colonnes nécessaires dans vos flux de données Customer Journey Analytics. Pour déterminer les colonnes à utiliser :

* **Identifier les champs qui s’appliquent uniquement à Adobe Analytics** : certaines colonnes des flux de données Adobe Analytics sont spécifiques au moteur de traitement des données d’Adobe Analytics et ne s’appliquent donc pas à Customer Journey Analytics. `exclude_hit` et `hit_source` sont des exemples de ces colonnes.

* **Identifier les champs qui s’appliquent à votre organisation** : bien que tous les clients Adobe Analytics n’exportent pas toutes les colonnes disponibles, de nombreux clients exportent plus qu’ils n’utilisent réellement.

  Avant de commencer à exporter des flux de données à partir de Customer Journey Analytics, vous devez d’abord déterminer quelles colonnes de flux de données Adobe Analytics votre organisation utilise actuellement, puis vous assurer que ces composants existent dans votre schéma de vue de données Customer Journey Analytics. Pour collecter ces informations, contactez les équipes ou les personnes de votre entreprise qui utilisent le contenu des flux de données pour Adobe Analytics.

## Colonnes cross-canal

Customer Journey Analytics prend en charge les données cross-canal (telles que les données de centre d’appels), qui ne sont pas disponibles dans Adobe Analytics. Ces champs cross-canal sont des exemples de nouvelles colonnes qui peuvent être incluses dans les flux de données Customer Journey Analytics, qui ne sont pas pris en charge dans Adobe Analytics.

<!--

1. View the data views throughout your organization to make sure that corresponding dimensions are available. If a corresponding dimension does not exist in the data view, create it.

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view.

   

1. For each Adobe Analytics data feed field that is being used, ensure that a similar field exists in the XDM schema.

1. Verify that and that corresponding dimensions are available in the data view. If not, you need to create them. 

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 

## Map data feed columns from Adobe Analytics to Customer Journey Analytics

### Step 1 - Map the default columns included in Customer Journey Analytics

There are roughly 20 default fields included in all WebSDK implementations. 

Before you can map these default columns, make sure that your Customer Journey Analytics environment meets the following prerequisites:

* It uses a WebSDK implementation.

* The appropriate field groups that contain the default WebSDK fields are added to your XDM schema.If the field is not added to your schema, it is included in the payload, but ultimately dropped.

* Each default field must be curated as a component in a Customer Journey Analytics data view.

* The component settings in the data view must be equivalent to how Analytics treats it (Visit persistence or hit-level persistence).

To map the default dimensions:

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that are included by default

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

### Step 2: Discover which additional data feed columns your consumers use

There are over 1,100 data feed columns available to be exported in Adobe Analytics. While not all Adobe Analytics customers export all of the available columns, many customers export more than they actually use. 

Before you begin mapping data feed columns, you should first:

1. Contact the teams or individuals who consume data feed content and determine which data feed columns they use.

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 


### Step 3 - Map each additional column

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that could be mapped if they are included in your schema and data views

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

Notes below here. Ignore:

Do we group these columns by if you're using the WebSDK, or if you're using specific field groups.

Here's what is in Analytics, and here's what it maps to in CJA. Customers want us to "give them the mappings."

Some of these fields there is probably something like it that you could get in WebSDK. There will be some fields that aren't. Or some that are in AEP that aren't in here (like call center data).

We have an XDM field mappings to Analytics variables. "Adobe analytics XDM Var - first hit on Google." If you set your XDM payload to the given field on the left, it will automatically be associated to the Analytics variable on the right. But we're looking for a reverse mapping of this. 









If you're using ADC, you'll have the AA column name in there. We also have an ADC mapping doc page. (Analytics field mappings doc page maps the fields)



Make a table (or a section) that talks about fields that are new to CJA, like cross-channel fields (call center, etc.) 

The number of AA columns that they can map is not going to be that big (maybe 100). The number of columns that don't map will be huge.

## Data feed column reference

### Adobe Analytics data feed columns that are included by default in Customer Journey Analytics WebSDK implementations

### Adobe Analytics data feed columns that can be included in Customer Journey Analytics data feed

### Adobe Analytics data feed columns that don't apply to Customer Journey Analytics


### Columns, descriptions, and data types

Use this section to learn what data is contained in each column. Most implementations don't use every column, so this section can be referenced when determining which columns to include in a data feed export.

-->
