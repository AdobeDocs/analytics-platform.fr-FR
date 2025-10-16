---
title: Ingérer et utiliser des audiences Experience Platform
description: Explique comment ingérer et utiliser des audiences Experience Platform dans Customer Journey Analytics pour une analyse plus approfondie.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
role: Admin
source-git-commit: fc62e87c3a69302c4084bf8c0f6c16520e65d60d
workflow-type: tm+mt
source-wordcount: '1570'
ht-degree: 11%

---

# Ingérer et utiliser des audiences Experience Platform

Ce cas pratique explore une solution intermédiaire pour ingérer des audiences Experience Platform dans Customer Journey Analytics. Ces audiences peuvent avoir été créées dans le créateur de segments d’Experience Platform, Adobe Audience Manager ou d’autres outils et sont stockées dans le profil client en temps réel. Les audiences se composent d’un ensemble d’identifiants de profil, ainsi que des attributs, événements et autres éléments applicables. Vous souhaitez importer ces données d’audience dans Customer Journey Analytics pour une analyse plus approfondie.

## Conditions préalables

* Accès à [Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/home), en particulier au profil client en temps réel.
* Accès à la création et à la gestion d’Experience Platform [schémas](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/home) et [jeux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/catalog/datasets/overview).
* Accès à [Experience Platform Query Service](https://experienceleague.adobe.com/fr/docs/experience-platform/query/home) (et possibilité d’écrire du code SQL).
* Accès à un outil qui peut effectuer certaines transformations des données.
* Accédez à Customer Journey Analytics. Vous devez être un administrateur de produit [Customer Journey Analytics](/help/technotes/access-control.md) pour créer et modifier des connexions Customer Journey Analytics et des vues de données.
* [Authentification et accès aux API Experience Platform (API Catalog Service et API Segmentation Service)](https://experienceleague.adobe.com/fr/docs/experience-platform/landing/platform-apis/api-authentication). Vous devez créer un projet dans Developer Console de l’entreprise et de la sandbox et vous assurer que vous disposez des informations requises pour envoyer des appels API avec succès.

## Étapes

La solution intermédiaire comprend les étapes suivantes :

1. [Sélectionnez des audiences (interface utilisateur d’Experience Platform)](#select-audiences).
1. [Créez un jeu de données activé pour le profil (API Experience Platform)](#create-a-profile-enabled-dataset).
1. [Exporter des audiences (API Experience Platform)](#export-audiences).
1. [ Transformer la sortie (interface utilisateur d’Experience Platform, etc.)](#transform-the-output)
1. [Création d’un schéma et d’un jeu de données (interface utilisateur d’Experience Platform)](#create-a-schema-and-dataset)
1. [Ajouter ou modifier une connexion (interface utilisateur de Customer Journey Analytics)](#add-or-edit-a-connection).
1. [Configurer une vue de données (interface utilisateur de Customer Journey Analytics)](#configure-a-data-view).
1. [Rapport et analyse (interface utilisateur de Customer Journey Analytics)](#report-and-analyze).


### Sélectionner des audiences

La solution commence par l’identification des audiences que vous souhaitez ingérer dans Customer Journey Analytics.

+++ Identification des audiences

Dans l’interface utilisateur d’Experience Platform :

1. Sélectionnez **[!UICONTROL Client]** > ![SegmentAudience](/help/assets/icons2/SegmentAudience.svg) **[!UICONTROL Audiences]**.
1. Sélectionnez **[!UICONTROL Parcourir]** et recherchez les audiences que vous souhaitez ingérer et utiliser dans Customer Journey Analytics. Notez l’**[!UICONTROL ID d’audience]** pour chacune des audiences en vue d’une utilisation ultérieure.

   ![Audiences](assets/audiences.png)

+++

### Créer un jeu de données activé pour le profil

Vous devez créer un jeu de données basé sur le schéma principal **[!UICONTROL XDM Individual Profile]**. Vous ne pouvez pas sélectionner ce profil individuel XDM basé sur le cœur comme schéma lorsque vous créez un jeu de données dans l’interface utilisateur d’Experience Platform. Utilisez plutôt l’API [Catalog Service) pour créer un jeu de données](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/create#create-a-dataset) basé sur le schéma `_xdm.context.profile__union`.

+++ Créer une requête de jeu de données

#### Requête

```shell
curl -X POST \
  'https://platform.adobe.io/data/foundation/catalog/dataSets?requestDataSource=true' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'Content-Type: application/json' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
   "name": "{DATASET_NAME}",
   "schemaRef": {
      "id": "_xdm.context.profile__union",
      "contentType": "application/vnd.adobe.xed+json;version=1"
   },
   "fileDescription": {
      "persistet": true,
      "containerFormat": "parquet",
      "format": "parquet"
   }
}'
```

Où ce qui suit est vrai :

* `DATASET_NAME` est le nom convivial du jeu de données. Par exemple : `Segment Export Job Dataset for CJA`.

#### Réponse

```json
["@/dataSets/{DATASET_ID}"]
```

Où ce qui suit est vrai :

* `DATASET_ID` est l’identifiant du jeu de données créé.

+++

### Exporter les audiences

Exportez les audiences sélectionnées dans le jeu de données que vous venez de créer. Utilisez l’API [Segmentation Service) pour créer une tâche d’exportation](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/api/export-jobs#create) qui envoie les audiences dans le jeu de données.

+++ Exporter la demande de traitement

```shell
curl -X POST https://platform.adobe.io/data/core/ups/export/jobs \
 -H 'Authorization: Bearer {ACCESS_TOKEN}' \
 -H 'Content-Type: application/json' \
 -H 'x-gw-ims-org-id: {ORG_ID}' \
 -H 'x-api-key: {API_KEY}' \
 -H 'x-sandbox-name: {SANDBOX_NAME}' \
 -d '{
    "fields": "{COMMA_SEPARATED_LIST_OF_FULLY_QUALIFIED_FIELD_NAMES}",
    "filter": {
        "segments": [
            {
                "segmentId": "{AUDIENCE_ID_1}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ],
                "segmentId": "{AUDIENCE_ID_2}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ],
                "segmentId": "{AUDIENCE_ID_3}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ]             
             }
        ]
    },
    "destination":{
        "datasetId": "{DATASET_ID}",
        "segmentPerBatch": false
    },
    "schema":{
        "name": "_xdm.context.profile"
    }
}'
```

où

* `COMMA_SEPARATED_LIST_OF_FULLY_QUALIFIED_FIELD_NAMES` pourrait être quelque chose comme `_demoemea.identification.core.ecid, _demoemea.identification.core.email, _demoemea.identification.core.phoneNumber, person.gender, person.name.firstName, person.name.lastName`. Veillez à inclure au moins les champs pertinents (tels que l’ID de personne (e-mail)) que vous souhaitez utiliser dans votre analyse du Parcours client.
* `AUDIENCE_ID_x` identifiants d’audience des audiences que vous souhaitez exporter.
* `DATASET_ID` est le jeu de données que vous avez créé.


### Réponse

```json
{
  "..."
  "id": "{EXPORT_JOB_ID}",
  "..."
}
```

où

* `EXPORT_JOB_ID` est l’identifiant de la tâche d’exportation.


+++

Utilisez l’API [ Segmentation Service pour vérifier le statut de la tâche d’exportation](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/api/export-jobs#get).

+++ Récupération d’une requête de tâche d’exportation spécifique

#### Requête

```shell
curl -X GET https://platform.adobe.io/data/core/ups/export/jobs/{EXPORT_JOB_ID} \
 -H 'Authorization: Bearer {ACCESS_TOKEN}' \
 -H 'x-gw-ims-org-id: {ORG_ID}' \
 -H 'x-api-key: {API_KEY}' \
 -H 'x-sandbox-name: {SANDBOX_NAME}'
```

#### Réponse

```json
{
  "..."
  "id": "{EXPORT_JOB_ID}",
  "..."
  "status": "SUCCEEDED",
  "..."
}
```

+++

Une fois la tâche d’exportation terminée, vérifiez si le jeu de données contient des lots ingérés avec succès.

+++ Vérifier le statut d’ingestion

Dans l’interface utilisateur d’Experience Platform :

1. Sélectionnez **[!UICONTROL Gestion des données]** > ![Données](/help/assets/icons2/Data.svg) **[!UICONTROL Jeux de données]**.
1. Sélectionnez le jeu de données que vous avez créé, par exemple : **[!UICONTROL Jeu de données de la tâche d’exportation de segments pour CJA]**.

   ![Activité du jeu de données](assets/dataset-activity.png)

1. Vérifiez les lots ingérés. Si le jeu de données contient des lots ayant échoué, utilisez **[!UICONTROL Gestion des données]** > ![Surveillance](/help/assets/icons2/Monitoring.svg) **[!UICONTROL Surveillance]** pour en connaître la raison. Par exemple, vous avez utilisé un nom de champ qui n’existe pas dans le schéma.
1. Copiez le **[!UICONTROL nom de la table]** du jeu de données. Par exemple : **[!UICONTROL segment_export_job_dataset_for_cja]**.  Utilisez ce nom à l’étape suivante.

+++


### Transformer la sortie

Les données du jeu de données ne sont pas au format correct pour Customer Journey Analytics. Pour transformer les données, utilisez le Query Service d’Experience Platform pour récupérer les données.

+++ SQL pour récupérer les données d’audience exportées

Utilisez un client PSQL qui se connecte à Experience Platform Query Service.

Dans l’interface utilisateur d’Experience Platform :

1. Sélectionnez **[!UICONTROL Gestion des données]** > ![Recherche de données](/help/assets/icons2/DataSearch.svg) **[!UICONTROL Requêtes]**.
1. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Credentials]**.

Utilisez les informations d’identification pour configurer votre client PSQL afin de vous connecter à Customer Journey Analytics Query Service.

#### Requête

```sql
SELECT ROW_NUMBER() OVER (ORDER BY key)::text as _id, personID, key as audienceMembershipId
FROM (
   SELECT {IDENTITY_TO_USE_AS_PERSON_ID} AS personID, explode(segmentMembership.ups)
   FROM {DATASET_TABLE_NAME}
)
WHERE value.status = 'realized' AND (key = '{AUDIENCE_ID_1}' OR key = 'AUDIENCE_ID_2' OR key = 'AUDIENCE_ID_3')
```

Où ce qui suit est vrai :

* `IDENTITY_TO_USE_AS_PERSON_ID` est l’un des champs que vous avez définis dans le cadre de la tâche d’exportation. Par exemple : `_demoemea.identification.core.email`.
* `AUDIENCE_ID_x` audiences que vous avez définies dans le cadre de la tâche d’exportation. Vous devez spécifier ces audiences une nouvelle fois, car la spécification dans la tâche d’exportation est un filtre au niveau des lignes. Ce filtre au niveau de la ligne renvoie les profils des segments spécifiés avec toutes les appartenances aux segments pour chacun des profils.


#### Résultats

Le résultat de la requête, au format JSON, doit ressembler à ceci :

```json
[
   {
      "_id": "1",
      "personID": "{PERSON_ID_x}",
      "audienceMembershipId": "{AUDIENCE_ID_x}"
   },
   {
      "_id": "2",
      "personID": "PERSON_ID_y",
      "audienceMembershipId": "{AUDIENCE_ID_x}"
   }

]
```

Où ce qui suit est vrai :

* `PERSON_ID_x` valeurs d’identifiant correspondent à l’identifiant que vous souhaitez utiliser comme ID de personne. Par exemple, `john.doe@gmail.com` lorsque vous utilisez l’e-mail.
* `AUDIENCE_ID_x` sont les identifiants de l’audience.

+++

Vous devez transformer ces données JSON pour ajouter le nom du client de l’environnement et fournir un nom plus convivial à l’audience.

+++ Transformer le JSON

Le fichier JSON final doit se présenter comme suit :

```json
[
   {
      "_id": "1",
      "personID": "{PERSON_ID_x}",
      "{TENANT_NAME}": {
         "audienceMembershipId": "{AUDIENCE_ID_x}",
         "audienceMembershipName": "{AUDIENCE_FRIENDLY_NAME_x}"
      }
  },
  {
      "_id": "2",
      "personID": "{PERSON_ID_y}",
      "{TENANT_NAME}": {
         "audienceMembershipId": "{AUDIENCE_ID_y}",
         "audienceMembershipName": "{AUDIENCE_FRIENDLY_NAME_y}"
      }
    }
  }

]
```

Où ce qui suit est vrai :

* `TENANT_NAME` est le nom du client. Par exemple : `_demoemea`.
* `PERSON_ID_x` valeurs d’identifiant correspondent à l’identifiant que vous souhaitez utiliser comme ID de personne. Par exemple, `john.doe@gmail.com` lorsque vous utilisez l’e-mail.
* `AUDIENCE_ID_x` sont les identifiants de l’audience.
* `AUDIENCE_FRIENDLY_NAME_x` noms d’audience conviviaux pour les identifiants d’audience. Par exemple : `Luma - Blue+ Members`.

Utilisez votre outil préféré pour transformer le fichier JSON d’origine en ce format.

+++


### Création d’un schéma et d’un jeu de données

Pour utiliser le fichier JSON transformé en tant que données d’audience exportées dans Customer Journey Analytics, vous devez créer un schéma dédié.

+++ Créer un schéma

Pour créer le schéma :

Dans l’interface utilisateur d’Experience Platform :

1. Sélectionnez **[!UICONTROL Gestion des données]** > ![Schéma](/help/assets/icons2/Schema.svg) **[!UICONTROL Schémas]**.
1. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create schema]**. Sélectionnez **[!UICONTROL Standard]** dans le menu déroulant.
1. Sélectionnez **[!UICONTROL Manuel]** dans la boîte de dialogue **[!UICONTROL Créer un schéma]** et utilisez **[!UICONTROL Sélectionner]** pour continuer.
1. Dans l’assistant **[!UICONTROL Créer un schéma]**, à l’étape **[!UICONTROL Sélectionner une classe]** :
   1. Sélectionnez **[!UICONTROL Profil individuel]**.
   1. Sélectionnez **[!UICONTROL Suivant]**.
1. Dans l’assistant **[!UICONTROL Créer un schéma]**, à l’étape **[!UICONTROL Nom et révision]** :
   1. Saisissez un **[!UICONTROL nom d’affichage du schéma]**. Par exemple : `Audience Export for CJA Schema`.
   1. (facultatif) Saisissez une **[!UICONTROL Description]**.
   1. Sélectionnez **[!UICONTROL Terminer]**.
1. Configurez votre schéma pour qu’il contienne un groupe de champs personnalisés (nommé, par exemple, **[!UICONTROL Appartenance à une audience]**) qui contient deux champs nommés **[!UICONTROL audienceMembershipId]** et **[!UICONTROL audienceMembershipName]**.
1. Assurez-vous que le champ **[!UICONTROL personID]** est une **[!UICONTROL Identité]**, une **[!UICONTROL Identité de Principal]** et qu’il contient **[!UICONTROL E-mail]** comme I**[!UICONTROL espace de noms d’identité]**.

   ![ Segment à exporter ](assets/segment-for-export.png)

1. **[!UICONTROL Appliquer]** toutes les modifications. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer le schéma.

+++

Créez un jeu de données et utilisez-le pour ingérer les données JSON transformées.

+++ Créer un jeu de données et ingérer des données

Dans l’interface utilisateur d’Experience Platform :

1. Sélectionnez **[!UICONTROL Gestion des données]** > ![Schéma](/help/assets/icons2/Schema.svg) **[!UICONTROL Jeux de données]**.
1. Sélectionnez ![AjouterCercle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Créer un jeu de données]**.
1. Sélectionnez **[!UICONTROL Créer un jeu de données à partir d’un schéma]**.
1. Dans l’assistant **[!UICONTROL Créer un jeu de données à partir d’un schéma]**, à l’étape **[!UICONTROL Sélectionner un schéma]** :
   1. Sélectionnez le schéma que vous venez de créer. Par exemple : **[!UICONTROL Exportation d’audiences pour le schéma CJA]**.
   1. Sélectionnez **[!UICONTROL Suivant]**.
1. Dans l’assistant **[!UICONTROL Créer un jeu de données à partir d’un schéma]**, à l’étape **[!UICONTROL Configurer le jeu de données]** :
   1. Saisissez un **[!UICONTROL Nom]** pour le jeu de données.
   1. (facultatif) Saisissez une **[!UICONTROL Description]** pour le jeu de données.
   1. Sélectionnez **[!UICONTROL Terminer]**.
1. Dans le **[!UICONTROL Jeux de données]** > **[!UICONTROL _nom du jeu de données_]**, faites glisser le fichier de données JSON transformé et déposez le fichier sur **[!UICONTROL Glisser-déposer des fichiers]**. Cette action lance l’ingestion des données JSON exportées dans le jeu de données.
1. Vérifiez les lots ingérés. Si le jeu de données contient des lots ayant échoué, utilisez **[!UICONTROL Gestion des données]** > ![Surveillance](/help/assets/icons2/Monitoring.svg) **[!UICONTROL Surveillance]** pour en connaître la raison. Par exemple, vous avez défini un nom de champ dans le fichier JSON qui n’existe pas dans le schéma.


+++

### Ajouter ou modifier une connexion

Une fois les données JSON transformées contenant les données d’audience d’Experience Platform ingérées, vous pouvez ajouter le jeu de données à une connexion nouvelle ou existante dans Customer Journey Analytics.

+++ Ajouter un jeu de données à la connexion

Dans l’interface utilisateur de Customer Journey Analytics :

1. Sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Connexions]**.
1. Créer une connexion/Définir **[!UICONTROL Paramètres de connexion]** et **[!UICONTROL Paramètres de données]**. Vous pouvez également sélectionner une connexion existante et utiliser ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier la connexion]** pour la modifier.
1. Sélectionnez ![DataAdd](/help/assets/icons/DataAdd.svg) **[!UICONTROL Ajouter des jeux de données]**.
1. Sélectionnez le jeu de données que vous avez créé et dans lequel vous avez ingéré les données JSON transformées.
1. Configurez le jeu de données. Par exemple :

   ![Connexion - Jeu de données avec les données d’audience exportées](assets/connection-add-dataset.png)

1. **[!UICONTROL Enregistrez]** la connexion.

+++

### Configuration d’une vue de données

Configurez une vue de données pour la connexion que vous venez de créer ou de modifier.

+++ Définition des composants d’audience

1. Sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Vues de données]**.
1. Modifier une vue de données existante ou en créer une nouvelle.
1. Dans l’onglet **[!UICONTROL Composants]** de la vue de données, assurez-vous que **[!UICONTROL ID d’appartenance à l’audience]** et **[!UICONTROL Nom d’appartenance à l’audience]** sont ajoutés en tant que composants de dimension.

   ![Composants de vue de données](assets/dataview-components.png)

1. Sélectionnez **[!UICONTROL Enregistrer et continuer]** pour enregistrer la vue de données.

+++

### Rapport et analyse

Enfin, utilisez Analysis Workspace pour créer des rapports sur les données d’audience Experience Platform dans un ou plusieurs panneaux qui utilisent la vue de données avec les composants d’appartenance à l’audience tels que `audienceMembershipId`, `audienceMembershipIdName` et `personID`.



<!--

## Step 1: Select audiences in Real-time Customer Profile {#audience}

Experience Platform [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html) lets you see a holistic view of each individual customer by combining data from multiple channels, including online, offline, CRM, and third party. 

You likely already have audiences in RTCP that may have come from various sources. Select one or more audiences to ingest into Customer Journey Analytics. For example, WKND Fly Platinum and Gold Fly Club Members.




## Step 2: Create a Profile Union dataset for the export

In order to export the audience to a dataset that you can ingest in Customer Journey Analytics as profiles, create a dataset whose schema is a Profile [Union schema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html#understanding-union-schemas).

Union schemas are composed of multiple schemas that share the same class and have been enabled for Profile. The union schema enables you to see an amalgamation of all of the fields contained within schemas sharing the same class. Real-time Customer Profile uses the union schema to create a holistic view of each individual customer.

## Step 3: Export an audience to the Profile Union dataset via API call {#export}

Before you can bring an audience into Customer Journey Analytics, you need to export it to an Adobe Experience Platform dataset. This can only be done using the Segmentation API, and specifically the [Export Jobs API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html). 

You can create an export job using the audience ID of your choice, and put the results in the Profile Union Adobe Experience Platform dataset you created in Step 2. Although you can export various attributes/events for the audience, you only need to export the specific profile ID field that matches the person ID field used in the Customer Journey Analytics connection you will be leveraging (see below in Step 5).

## Step 4: Edit the export output 

The results of the export job need to be transformed into a separate Profile dataset in order to be ingested into Customer Journey Analytics.  This transformation can be done with [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html), or another transformation tool of your choice. We only need the Profile ID (that will match the Person ID in Customer Journey Analytics) and one or more audience ID(s) to do the reporting in Customer Journey Analytics.

The standard export job, however, contains more data and so we need to edit this output to remove extraneous data, as well as move some things around.  Also, you need to create a schema/dataset first before you add the transformed data to it.

Here is an example of the export output in the Profile union dataset, **before** any editing:

![Unedited output](../assets/export-unedited.png)

Note the following:

* The audience ID is contained under `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* The status has to be "realized", or "entered", but not "exited".

This is the format of the Profile dataset that you can send into Customer Journey Analytics.

![Edited output](../assets/export-edited.png)

Here are the data elements that need to be present:

* `_aresprodvalidation` string field: Refers to your Organization ID. Yours will be different.
* `personID` string field: This is the standard XDM schema field on Profile datasets to identity the person. Use the Profile ID from the export.
* `audienceMembershipId` string field: The audience ID from the export.  NOTE: This field can be named whatever you want (from your own schema).
* Add a friendly name for the audience (`audienceMembershipIdName`), such as

   ![Friendly audience name](../assets/audience-name.png)
   
* Add other audience metadata if you desire.

## Step 5: Add this Profile dataset to an existing connection in Customer Journey Analytics

You could [create a new connection](/help/connections/create-connection.md), but most customers will want to add the Profile dataset to an existing connection. The audience IDs "enrich" the existing data in Customer Journey Analytics.

## Step 6: Modify existing (or create new) Customer Journey Analytics data view

Add `audienceMembershipId`, `audienceMembershipIdName` and `personID` to the data view.

## Step 7: Report in Workspace

You can now report on `audienceMembershipId`, `audienceMembershipIdName` and `personID` in Workspace.

-->


## Remarques supplémentaires

* Vous devez effectuer ce processus régulièrement, de sorte que les données d’audience soient constamment actualisées dans Customer Journey Analytics.
* Vous pouvez importer plusieurs audiences dans une seule connexion Customer Journey Analytics. Cela ajoute une complexité supplémentaire au processus, mais c’est possible. Pour que cela fonctionne, vous devez apporter quelques modifications au processus ci-dessus :
   1. Effectuez ce processus pour chaque audience souhaitée dans votre collection d’audiences dans RTCP.
   1. Customer Journey Analytics prend en charge les tableaux/tableaux d’objets dans les jeux de données de profil. Utiliser un [tableau d’objets](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html?lang=fr) pour le `audienceMembershipId` ou le `audienceMembershipIdName` est la meilleure option.
   1. Dans votre vue de données, créez une dimension à l’aide de la transformation Sous-chaîne sur le champ `audienceMembershipId` pour convertir la chaîne de valeurs séparées par des virgules en tableau. REMARQUE : le tableau contient actuellement une limite de 10 valeurs.
   1. Vous pouvez désormais créer des rapports sur ce nouveau `audienceMembershipIds` de dimension dans Customer Journey Analytics Workspace.
