---
description: Découvrez comment vous préparer à mapper les colonnes de flux de données d’Adobe Analytics à Customer Journey Analytics.
keywords: flux de clics;flux de données;flux des données;Flux de données
title: Préparation du mappage des colonnes de flux de données d’Adobe Analytics vers Customer Journey Analytics
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 5dada1744a479cd4736c9fb7f3c807471e8da226
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 2%

---

# Préparer le mappage des colonnes de flux de données d’Adobe Analytics vers Customer Journey Analytics

Lors de la transition des flux de données Adobe Analytics aux flux de données Customer Journey Analytics, il est naturel de vouloir mapper chaque colonne de flux de données Adobe Analytics à une colonne de flux de données dans Customer Journey Analytics.

Cependant, le mappage des colonnes de flux de données d’Adobe Analytics vers Customer Journey Analytics est rarement un mappage un-à-un. Cela est dû aux facteurs suivants :

* **[Architecture des schémas](#schema-architecture)** : les colonnes de flux de données d’Adobe Analytics sont dérivées des variables Analytics, tandis que les colonnes de flux de données de Customer Journey Analytics sont dérivées des champs de schéma XDM dans Experience Platform et des composants de vue de données dans Customer Journey Analytics.

* **[Type d’implémentation](#implementation-type)** : Adobe Analytics et Customer Journey Analytics prennent chacun en charge plusieurs configurations d’implémentation. Les étapes requises pour mapper des champs individuels dépendent de ces implémentations.

* **[Traitement des données](#data-processing)** : il existe des différences fondamentales de traitement des données entre Adobe Analytics et Customer Journey Analytics.

* **[Colonnes inutilisées](#unused-columns)** : Adobe Analytics contient plus de 1 100 colonnes de flux de données. Identifiez les colonnes que votre entreprise utilise afin de ne mapper que les colonnes nécessaires.

Avant de commencer à mapper les colonnes de flux de données Adobe Analytics aux colonnes de flux de données Customer Journey Analytics, consultez les sections ci-dessous pour mieux comprendre ces facteurs clés qui affectent le mappage.

Après avoir consulté ces informations, suivez les instructions de mappage pour chaque colonne de flux de données Adobe Analytics que vous prévoyez de conserver dans Customer Journey Analytics, comme décrit dans la section [Référence des colonnes de données](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

## Architecture des schémas

Le schéma Modèle de données d’expérience (XDM), ainsi que les vues de données utilisées dans Customer Journey Analytics, sont plus flexibles que le modèle basé sur les variables Adobe Analytics. Par conséquent, le schéma XDM de votre organisation ne contient probablement pas de champs qui se traduisent par des mappages de colonnes de flux de données un-à-un.

Tenez compte des points suivants à propos de l’architecture des schémas :

* L’absence de mappages de colonne un-à-un ne signifie pas que votre schéma XDM Customer Journey Analytics est insuffisant. Cela signifie plutôt que vous devez d’abord déterminer quelles colonnes de flux de données Adobe Analytics vous utilisez actuellement, puis mapper uniquement ces colonnes aux flux de données Customer Journey Analytics.

* Le schéma XDM Customer Journey Analytics prend en charge les données cross-canal (telles que les données de centre d’appels), qui ne sont pas disponibles dans Adobe Analytics. Ces champs cross-canal sont des exemples de nouvelles colonnes qui peuvent être incluses dans les flux de données Customer Journey Analytics qui ne sont pas pris en charge dans Adobe Analytics.

* Les champs ne peuvent être inclus dans un flux de données Customer Journey Analytics qu’après avoir été inclus dans le schéma XDM d’Experience Platform, puis traités pour être utilisés dans la vue de données de Customer Journey Analytics.

  Pour plus d’informations sur ce processus pour chaque colonne de flux de données Adobe Analytics potentielle, voir [Référence des colonnes de données](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

>[!TIP]
>
>Si possible, consultez l’équipe ou la personne qui a conçu le schéma XDM pour l’implémentation Customer Journey Analytics de votre organisation. La plupart des décisions concernant les champs Adobe Analytics nécessaires dans Customer Journey Analytics ont été prises lors de la création du schéma XDM. Pour plus d’informations, consultez [Concevoir le schéma à utiliser avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

## Type d’implémentation

<!--  tons of different AA implementations + tons of different CJA schemas -->

Le nombre de champs disponibles pour mapper dans votre schéma XDM Customer Journey Analytics peut varier en fonction de la manière dont les données sont collectées pour votre implémentation Customer Journey Analytics, comme suit :

* **Nouvelles implémentations de Web SDK** : si votre implémentation de Customer Journey Analytics utilise un schéma personnalisé, de nombreuses colonnes existant dans les flux de données Adobe Analytics n’existent probablement pas dans Customer Journey Analytics. De même, Customer Journey Analytics peut contenir des champs qui n’existent pas dans les flux de données Adobe Analytics.

* **Implémentations du connecteur Source Analytics** : les mappages de champs un-à-un existent par défaut pour de nombreuses colonnes de flux de données, car le connecteur Source Analytics utilise le groupe de champs Événement d’expérience Analytics dans le schéma XDM. Pour plus d’informations sur les champs Adobe Analytics mappés aux champs de ce groupe de champs, consultez [Mappages de champs Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) dans la documentation d’Experience Platform.

<!-- **Data layer**: ??? -->

## Traitement des données

Le traitement des données diffère entre Adobe Analytics et Customer Journey Analytics, comme suit :

**&#x200B;**&#x200B;: de nombreux champs de flux de données sont exportés sous la forme de deux colonnes distinctes : l’une contenant des données prétraitées et l’autre des données post-traitées. (Les données post-traitées incluent la logique côté serveur, les règles de traitement, les règles VISTA, les règles de persistance des dimensions, etc.)

Comme Adobe Analytics exporte les données de certains champs dans deux colonnes distinctes (une pour les données prétraitées et une pour les données post-traitées), Adobe Analytics contient plus de colonnes de flux de données que Customer Journey Analytics. Gardez cela en tête lors du mappage des champs.

**&#x200B;**&#x200B;: les champs sont disponibles pour les flux de données après leur création dans la vue de données. En règle générale, les champs des vues de données Customer Journey Analytics incluent uniquement les données post-traitées. Cependant, vous pouvez généralement faire une estimation de la version prétraitée d’Adobe Analytics d’un champ en créant une deuxième version du champ dans la vue de données Customer Journey Analytics et en le configurant pour qu’il expire au moment de l’accès.

## Colonnes non utilisées

Plus de 1 100 colonnes de flux de données peuvent être exportées dans Adobe Analytics. De ces colonnes, toutes ne seront pas utilisées dans vos flux de données Customer Journey Analytics.

Pour déterminer les colonnes à utiliser :

* **Identifier les champs qui s’appliquent uniquement à Adobe Analytics** : certaines colonnes des flux de données Adobe Analytics sont spécifiques au moteur de traitement des données d’Adobe Analytics et ne s’appliquent donc pas à Customer Journey Analytics. `exclude_hit` et `hit_source` sont des exemples de ces colonnes.

* **Identifier les champs qui s’appliquent à votre organisation** : bien que tous les clients Adobe Analytics n’exportent pas toutes les colonnes disponibles, de nombreux clients exportent plus qu’ils n’utilisent réellement.

  Avant de commencer à mapper les colonnes de flux de données, identifiez les champs réellement utilisés dans l’ensemble de votre organisation. Pour collecter ces informations, contactez les équipes ou les personnes qui consomment du contenu de flux de données pour Adobe Analytics.



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
