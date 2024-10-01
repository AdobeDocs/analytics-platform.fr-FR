---
title: Données de résumé
description: Détails et informations sur l’utilisation et la configuration des données récapitulatives dans une vue de données.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: 6cd4fadc28117ed88b68d17274ab8de2b0edff10
workflow-type: tm+mt
source-wordcount: '1135'
ht-degree: 7%

---

# Données de résumé

Les données récapitulatives sont des données de série temporelle qui ne sont pas liées à un ID de personne individuel. Les données de résumé représentent des données agrégées à un niveau d’agrégation différent, par exemple des campagnes. Vous pouvez utiliser ces données dans Customer Journey Analytics pour prendre en charge divers cas d’utilisation. Par exemple, des données contenant une date et une valeur de mesure unique ou des données contenant plusieurs dimensions et mesures.

Ces données récapitulatives peuvent ensuite être utilisées pour présenter des indicateurs de performances de haut niveau ou effectuer des analyses. Il peut s’agir par exemple d’impressions publicitaires, d’ouvertures de courriers électroniques, de dépenses publicitaires, du coût des ventes, des indices S&amp;P, etc. Vous pouvez également utiliser des données récapitulatives pour transférer des cibles ou des objectifs sur une base horaire ou quotidienne.

>[!NOTE]
>
>Les données récapitulatives sont des données de série temporelle provenant d’un jeu de données de résumé. Ce jeu de données de résumé est basé sur un schéma qui utilise la classe XDM Summary Metrics comme classe de base.
>Seules les données de série temporelle horaire ou quotidienne sont prises en charge.

>[!TIP]
>
>Vous pouvez configurer une connexion, une vue de données et un rapport ultérieur sur les données récapitulatives **uniquement**. Il n’est pas nécessaire de disposer de données d’événement, de profil ou de recherche supplémentaires dans le cadre de votre configuration.


## Exemple

Un exemple d’utilisation de données récapitulatives est la combinaison de données résumées de campagne publicitaire avec des données de parcours de navigation sur site pour la création de rapports.

### Données de résumé

Vos données récapitulatives contiennent les données de campagne publicitaire suivantes.

| Code de campagne | Impressions | Coût |
|---|---:|---:|
| abc123 | 1 250 | 1 500 $ |
| def456 | 775 | 650 $ |
| ghi789 | 500 | 500 $ |


### Données d’événement

Vos données de parcours de navigation sur site contiennent les événements suivants.

| Code de suivi | Clics publicitaires | Chiffre dʼaffaires |
|---|---:|---:|
| abc123 | 1 250 | 7 200 $ |
| def456 | 775 | 1 250 $ |
| ghi789 | 500 | 750 $ |

### Données combinées

Comme expliqué dans la section [Jeu de données d’événement combiné](/help/connections/combined-dataset.md), lors de la définition d’une connexion, Customer Journey Analytics crée un jeu de données d’événement combiné global. Lorsque vous configurez votre vue de données pour les dimensions issues d’un jeu de données de résumé, des options sont disponibles pour regrouper et masquer les dimensions en tant que préparation aux rapports dans Workspace. Plus précisément pour les données récapitulatives, les données récapitulatives sont combinées avec les données d’événement, en fonction de la configuration du [composant de groupe de données récapitulatives](component-settings/summary-data-group.md).

| Code de suivi | Code de campagne | Impressions | Coût | Clics publicitaires | Chiffre dʼaffaires |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1 250 | 1 500 $ | 1 250 | 7 200 $ |
| def456 | def123 | 775 | 650 $ | 775 | 1 250 $ |
| ghi789 | ghi789 | 500 | 500 $ | 500 | 750 $ |



### Création de rapports

La combinaison des données d’événement résumées et des données de parcours de navigation sur site vous permet de créer des rapports dans Workspace sur le retour sur dépenses publicitaires (ROAS).

| Code de suivi | Impressions | Coût | Clics publicitaires | Chiffre dʼaffaires | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1 250 | 1 500 $ | 1 250 | 7 200 $ | 4,80 |
| def456 | 775 | 650 $ | 775 | 1 250 $ | 1,92 |
| ghi789 | 500 | 500 $ | 500 | 750 $ | 1,50 |


### Données de recherche

Si vous souhaitez créer des rapports à l’aide d’une dimension définie dans un jeu de données de recherche supplémentaire (par exemple, le nom de la campagne), vous devez suivre les étapes supplémentaires suivantes :

1. Créez un champ dérivé qui utilise la fonction [Recherche](/help/data-views/derived-fields/derived-fields.md#lookup) pour rechercher le nom de la campagne à partir du jeu de données de recherche. Dans la définition de la fonction [Recherche](/help/data-views/derived-fields/derived-fields.md#lookup) , vous utilisez la correspondance entre le code de campagne et le code de suivi pour rechercher le nom de la campagne.
1. Ajoutez le nouveau champ dérivé en tant que composant de dimension à votre vue de données.
1. Configurez le composant de dimension Nom de la campagne (à partir du jeu de données de recherche) pour qu’il dispose d’un regroupement de données récapitulatif avec le champ dérivé nouvellement créé.

Consultez le cas d’utilisation [Ingest and report on summary data](/help/use-cases/data-views/summary-data.md) pour obtenir un article détaillé sur l’utilisation, la création de rapports et l’analyse de données récapitulatives dans Customer Journey Analytics.


## Conditions préalables

Pour utiliser correctement les données récapitulatives dans vos rapports et analyses, plusieurs conditions préalables s’appliquent. Les sections suivantes décrivent ces conditions préalables.

### Granularité et fuseau horaire

Lors de la configuration du jeu de données contenant les données récapitulatives dans Customer Journey Analytics, vous remarquerez que la granularité est automatiquement dérivée des données. Les sélections pour les listes déroulantes **[!UICONTROL Horodatage]** et **[!UICONTROL Fuseau horaire]** sont désactivées, car elles sont dérivées de la définition de schéma.

#### Granularité

Vous ne pouvez pas mélanger et faire correspondre la granularité horaire et quotidienne de vos données récapitulatives dans un jeu de données (ou avec différents jeux de données) à l’aide d’un schéma de données de résumé. Si, par exemple, vous disposez de données de synthèse quotidienne et horaire granulaires pour les données de campagne publicitaire, vous avez besoin de deux schémas : un pour les données de synthèse quotidienne et un autre pour les données de synthèse horaire. Ensuite, transférez les données granulaires pertinentes dans des jeux de données associés au schéma approprié (par exemple, transférez les données horaires dans un jeu de données associé au schéma de données de résumé horaire).

#### Fuseau horaire

Le fuseau horaire de vos données de résumé est défini au niveau du schéma de résumé dans Experience Platform. Le fuseau horaire s’applique uniquement aux données horaires granulaires.

- Pour la granularité quotidienne, Experience Platform utilise le format UTC, sauf si un décalage de fuseau horaire est inclus dans l’horodatage. Lors de l’ajout du jeu de données de résumé contenant les données de résumé quotidiennes, Customer Journey Analytics ignore la définition de fuseau horaire définie sur le schéma et respecte le jour associé à l’horodatage des données du jeu de données.
- Pour la granularité horaire, Customer Journey Analytics respecte le fuseau horaire configuré sur le schéma de données de résumé dans Experience Platform lors de l’interprétation de l’horodatage. Le tableau ci-dessous fournit quelques exemples de cette interprétation.

  | Horodatage <br/> des données source | Fuseau horaire<br/>schema | Horodatage<br/>Experience<br/>Platform | Fuseau horaire<br/> données<br/>view | Horodatage<br/>Client<br/>Parcours<br>Analytics |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *GMT* par défaut | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *GMT* par défaut | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT* par défaut | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT* par défaut | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 2024-08-02 | *GMT* par défaut | 2024-08-02T00:00:00 | IST | 2024-08-02T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles` | 2024-07-28T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  Pour les fuseaux horaires avec un décalage de 30 minutes (par exemple, heure normale de l’Inde), le décalage de 30 minutes est ignoré lors de la création de rapports sur les données de résumé. Par exemple : 12 h 30 est reporté à 12 h 00.


Pour garantir que le fuseau horaire approprié est utilisé pour vos données de résumé horaires granulaires, vous devez vous assurer que le fuseau horaire approprié est configuré pour le schéma utilisé pour les données de résumé.

Pour configurer la granularité et le fuseau horaire de votre schéma de données de résumé, vous devez utiliser l’appel API suivant, car aucune interface utilisateur équivalente n’est disponible.

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
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | Voir [Authentification et accès aux API Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication) pour plus d’informations sur la spécification de valeurs pour ces variables. |
| `$SCHEMA_ID` | L’identifiant de votre schéma est accessible dans l’interface utilisateur de l’Experience Platform. Sélectionnez votre schéma de résumé dans la liste des schémas et recherchez l’**[!UICONTROL utilisation de l’API]** > **[!UICONTROL ID de schéma]** dans le panneau de droite. Utilisez cet identifiant comme valeur. |
| `$GRANULARITY` | Spécifiez `hour` ou `day` comme valeur. |
| `$TIMEZONE` | Indiquez la valeur d’identifiant de fuseau horaire appropriée de la colonne d’identifiant TZ dans la [Liste des fuseaux horaires de la base de données tz](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). Par exemple : `America/Los_Angeles`. |

## Paramètres de composant

Assurez-vous que les paramètres de composant d’un groupe de données de résumé sont identiques. Pour plus d’informations, voir [Paramètres du composant de groupe de données récapitulatifs](component-settings/summary-data-group.md#same-component-settings) .

>[!MORELIKETHIS]
>
>Consultez l’article [Utiliser les données récapitulatives](/help/use-cases/data-views/summary-data.md) pour obtenir un exemple détaillé de cas d’utilisation sur l’utilisation des données récapitulatives et la création de rapports sur ces données.
