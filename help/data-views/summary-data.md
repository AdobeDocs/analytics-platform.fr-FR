---
title: Données de résumé
description: Détails et informations sur l’utilisation et la configuration des données de résumé dans une vue de données.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 97%

---

# Données de résumé

Les données de résumé sont des données de série temporelle qui ne sont pas liées à un ID de personne individuel. Les données de résumé représentent des données agrégées à un niveau d’agrégation différent, par exemple des campagnes. Vous pouvez utiliser ces données dans Customer Journey Analytics pour prendre en charge divers cas d’utilisation. Par exemple, les données contenant une date et une valeur de mesure unique, ou les données contenant plusieurs dimensions et mesures.

Ces données de résumé peuvent ensuite être utilisées pour présenter des indicateurs de performances de haut niveau ou effectuer une analyse. Des exemples de données de résumé peuvent être les impressions publicitaires, les ouvertures d’e-mails, les dépenses publicitaires, le coût des biens vendus, les indices S&amp;P, etc. Vous pouvez également utiliser des données de résumé pour charger des cibles ou des objectifs sur une base horaire ou quotidienne.

>[!NOTE]
>
>Les données de résumé sont des données de série temporelle provenant d’un jeu de données de résumé. Ce jeu de données de résumé est basé sur un schéma qui utilise la classe XDM Mesures de résumé comme classe de base.
>&#x200B;>Seules les données de série temporelle basées sur une heure ou une journée sont prises en charge.

>[!TIP]
>
>Vous pouvez configurer une connexion, une vue de données, puis créer des rapports **uniquement** sur des données de résumé. Il n’est pas nécessaire d’avoir des données d’événement, de profil ou de recherche supplémentaires dans le cadre de votre configuration.


## Exemple

Un exemple d’utilisation des données de résumé consiste à combiner les données de campagne publicitaire résumées avec les données de flux de clics sur site pour la création de rapports.

### Données de résumé

Vos données de résumé contiennent les données de campagne publicitaire suivantes.

| Code de campagne | Impressions | Coût |
|---|---:|---:|
| abc123 | 1 250 | 1 500 $ |
| def456 | 775 | 650 $ |
| ghi789 | 500 | 500 $ |


### Données d’événement

Vos données de flux de clics sur site contiennent les événements suivants.

| Code de suivi | Clics publicitaires | Chiffre dʼaffaires |
|---|---:|---:|
| abc123 | 1 250 | 7 200 $ |
| def456 | 775 | 1 250 $ |
| ghi789 | 500 | 750 $ |

### Données combinées

Comme expliqué dans la section [Jeu de données d’événement combiné](/help/connections/combined-dataset.md), lorsque vous définissez une connexion, Customer Journey Analytics crée un jeu de données d’événement combiné global. Lorsque vous configurez votre vue de données pour les dimensions provenant d’un jeu de données de résumé, des options sont disponibles pour regrouper et masquer les dimensions dans le cadre de la préparation des rapports dans Workspace. Pour les données de résumé, elles sont combinées avec les données d’événement, en fonction de la configuration [composant du groupe de données de résumé](component-settings/summary-data-group.md).

| Code de suivi | Code de campagne | Impressions | Coût | Clics publicitaires | Chiffre dʼaffaires |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1 250 | 1 500 $ | 1 250 | 7 200 $ |
| def456 | def123 | 775 | 650 $ | 775 | 1 250 $ |
| ghi789 | ghi789 | 500 | 500 $ | 500 | 750 $ |



### Création de rapports

La combinaison des données d’événement de résumé et des données de flux de clics sur site vous permet de générer des rapports dans Workspace sur le retour sur dépenses publicitaires (ROAS).

| Code de suivi | Impressions | Coût | Clics publicitaires | Chiffre dʼaffaires | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1 250 | 1 500 $ | 1 250 | 7 200 $ | 4,80 |
| def456 | 775 | 650 $ | 775 | 1 250 $ | 1,92 |
| ghi789 | 500 | 500 $ | 500 | 750 $ | 1,50 |


### Données de recherche

Si vous souhaitez créer des rapports à l’aide d’une dimension définie dans un jeu de données de recherche supplémentaire (par exemple, le nom de la campagne), procédez comme suit :

1. Créez un champ dérivé qui utilise la fonction [Recherche](/help/data-views/derived-fields/derived-fields.md#lookup) pour rechercher le nom de la campagne à partir du jeu de données de recherche. Dans la définition de la fonction [Recherche](/help/data-views/derived-fields/derived-fields.md#lookup), vous utilisez la correspondance entre le code de campagne et le code de suivi pour rechercher le nom de la campagne.
1. Ajoutez le champ dérivé nouvellement créé en tant que composant de dimension à votre vue de données.
1. Configurez le composant de dimension Nom de la campagne (à partir du jeu de données de recherche) pour obtenir un regroupement des données de résumé avec le champ dérivé nouvellement créé.

Consultez le cas d’utilisation [Ingérer et générer des rapports sur les données de résumé](/help/use-cases/data-views/summary-data.md) pour un article détaillé sur l’utilisation, la création de rapports et l’analyse de données de résumé dans Customer Journey Analytics.


## Conditions préalables

Pour utiliser correctement les données de résumé dans vos rapports et analyses, un certain nombre de conditions préalables s’appliquent. Les sections suivantes détaillent ces conditions préalables.

### Granularité et fuseau horaire

Lors de la configuration du jeu de données contenant les données de résumé dans Customer Journey Analytics, vous remarquerez que la granularité est automatiquement dérivée des données. Les sélections des menus déroulants **[!UICONTROL Horodatage]** et **[!UICONTROL Fuseau horaire]** sont désactivées, car les deux sont dérivés de la définition du schéma.

#### Granularité

Vous ne pouvez pas combiner et faire correspondre la granularité horaire et quotidienne de vos données de résumé dans un jeu de données (ou avec différents jeux de données), en utilisant un schéma de données de résumé. Par exemple, si vous disposez de données de résumé granulaires quotidiennes et horaires pour les données de campagnes publicitaires, vous avez besoin de deux schémas : l’un pour les données de résumé quotidiennes et l’autre pour les données de résumé horaires. Puis chargez les données granulaires appropriées dans les jeux de données associés au schéma approprié (par exemple, chargez des données horaires dans un jeu de données associé au schéma de données de résumé horaire).

#### Fuseau horaire

Le fuseau horaire de vos données de résumé est défini au niveau du schéma de résumé dans Experience Platform. Le fuseau horaire s’applique uniquement aux données granulaires horaires.

- Pour une granularité quotidienne, Experience Platform suppose le fuseau horaire UTC, sauf si un décalage de fuseau horaire est inclus dans l’horodatage. Lors de l’ajout du jeu de données de résumé contenant les données de résumé quotidiennes, Customer Journey Analytics ignore la définition de fuseau horaire définie sur le schéma et respecte le jour associé à l’horodatage à partir des données du jeu de données.
- Pour une granularité horaire, Customer Journey Analytics respecte le fuseau horaire configuré sur le schéma de données de résumé dans Experience Platform lors de l’interprétation de l’horodatage. Le tableau ci-dessous fournit quelques exemples de cette interprétation.

  | Horodatage<br/>Données source | Fuseau horaire<br/>Schéma | Horodatage<br/>Experience<br/>Platform | Fuseau horaire<br/>Données<br/>Vue | Horodatage<br/>Customer<br/>Journey<br>Analytics |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *GMT par défaut* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *GMT par défaut* | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT par défaut* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT par défaut* | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 2024-08-02 | *GMT par défaut* | 2024-08-02T00:00:00 | IST | 2024-08-02T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles` | 2024-07-28T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  Pour les fuseaux horaires avec un décalage de 30 minutes (par exemple, IST, Heure standard de l’Inde), le décalage de 30 minutes est ignoré lors de la création de rapports sur les données de résumé. Par exemple : 12:30 est signalé comme 12:00.


Pour vous assurer que le fuseau horaire approprié est utilisé pour vos données de résumé granulaires horaires, vous devez vous assurer que le schéma utilisé pour les données de résumé comporte le fuseau horaire approprié configuré.

Pour configurer la granularité et le fuseau horaire de votre schéma de données de résumé, vous devez utiliser l’appel API suivant, car aucune interface d’utilisation équivalente n’est disponible.

```shell
curl -X POST \
https://platform.adobe.io/data/foundation/schemaregistry/tenant/descriptors \
 -H "Authorization: Bearer {$ACCESS_TOKEN}" \
 -H 'Content-Type: application/json' \
 -H 'x-api-key: {$API_KEY}' \
 -H 'x-gw-ims-org-id: {$ORG_ID}' \
 -H 'x-sandbox-name: {$SANDBOX_NAME}' \
 -d '{  
    "@type": "xdm:descriptorTimeSeriesGranularity",
    "xdm:sourceSchema": "{$SCHEMA_ID}",
    "xdm:sourceVersion": 1,
    "xdm:granularity": "{$GRANULARITY}",
    "xdm:ianaTimezone": "{$TIMEZONE}" 
 }'
```

| Variable | Valeur |
|---|---|
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | Consultez [Authentification et accès aux API Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/landing/platform-apis/api-authentication) pour plus d’informations sur la spécification des valeurs de ces variables. |
| `$SCHEMA_ID` | L’identifiant de votre schéma se trouve dans l’interface d’utilisation d’Experience Platform. Sélectionnez votre schéma de résumé dans la liste des schémas, puis recherchez **[!UICONTROL Utilisation de l’API]** > **[!UICONTROL Identifiant du schéma]** dans le panneau de droite. Utilisez cet ID comme valeur. |
| `$GRANULARITY` | Spécifiez `hour` ou `day` comme valeur. |
| `$TIMEZONE` | Indiquez la valeur d’identifiant de fuseau horaire appropriée dans la colonne Identifiant TZ de la [Liste des fuseaux horaires de la base de données TZ](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). Par exemple : `America/Los_Angeles`. |

## Paramètres de composant

Assurez-vous que les paramètres des composants pour un groupe de données de résumé sont identiques. Pour plus d’informations, consultez [Paramètres des composants du groupe de données de résumé](component-settings/summary-data-group.md#same-component-settings).

>[!MORELIKETHIS]
>
>- Consultez l’article [Utiliser des données de résumé](/help/use-cases/data-views/summary-data.md) pour obtenir un exemple de cas d’utilisation détaillé sur l’utilisation des données de résumé et la création de rapports les concernant.
>- Blog : [comment les données de résumé améliorent les jeux de données Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-summary-data-enhances-adobe-customer-journey-analytics/ba-p/704635?profile.language=fr)

