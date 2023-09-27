---
description: Configuration de l’emplacement d’exportation dans le cloud où les données du Customer Journey Analytics peuvent être envoyées
keywords: Analysis Workspace
title: Configuration des emplacements d’exportation cloud
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 2da2b4b2931f28dc373a2c634c38e9dfcbdd2788
workflow-type: tm+mt
source-wordcount: '1417'
ht-degree: 4%

---

# Configuration des emplacements d’exportation cloud

Avant de pouvoir exporter des rapports Customer Journey Analytics vers une destination cloud comme décrit dans [Exportation des rapports des Customer Journey Analytics dans le cloud](/help/analysis-workspace/export/export-cloud.md), vous devez ajouter et configurer l’emplacement où vous souhaitez que les données soient envoyées.

Ce processus consiste à ajouter et configurer le compte (comme Amazon S3, Google Cloud Platform, etc.), comme décrit dans la section [Configuration des comptes d’exportation cloud](/help/components/exports/cloud-export-accounts.md), puis en ajoutant et en configurant l’emplacement dans ce compte (un dossier dans le compte, par exemple), comme décrit dans cet article.

Pour plus d’informations sur la gestion des emplacements existants, notamment l’affichage, la modification et la suppression d’emplacements, voir [Gestion des emplacements et des comptes d’exportation dans le cloud](/help/components/exports/manage-export-locations.md).

## Commencer à créer un emplacement d’exportation dans le cloud

1. Vous devez ajouter un compte avant de pouvoir ajouter un emplacement. Si ce n’est déjà fait, ajoutez un compte comme décrit à la section [Configuration des comptes d’exportation cloud](/help/components/exports/cloud-export-accounts.md).

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Emplacements**] , puis sélectionnez [!UICONTROL **Ajouter un emplacement**].

   ![bouton ajouter un emplacement](assets/location-add.png)

   Ou

   Sélectionnez la variable [!UICONTROL **Comptes d’emplacement**] , sélectionnez l’icône à 3 points sur un compte existant dans lequel vous souhaitez ajouter un emplacement, puis sélectionnez [!UICONTROL **Ajouter un emplacement**].

   ![Ajouter un emplacement au compte existant](assets/add-location-existing-account.png)

   La boîte de dialogue Emplacement s’affiche.

1. Indiquez les informations suivantes : |Field | Fonction | |—|—| | [!UICONTROL **Nom**] | Nom de l’emplacement.  | | [!UICONTROL **Description**] | Fournissez une brève description du compte pour le différencier des autres comptes du même type de compte. | | [!UICONTROL **Compte d’emplacement**] | Sélectionnez le compte dans lequel vous souhaitez créer l’emplacement. Pour plus d’informations sur la création d’un compte, voir [Configuration des comptes d’exportation cloud](/help/components/exports/cloud-export-accounts.md). |

1. Dans le [!UICONTROL **Propriétés de l’emplacement**] , indiquez les informations spécifiques au type de compte de votre compte d’emplacement.

   Passez à la section ci-dessous qui correspond au type de compte sélectionné dans la [!UICONTROL **Compte d’emplacement**] champ .

### Zone d’entrée des données Adobe Experience Platform

>[!IMPORTANT]
>
>Lors de l’exportation de rapports Customer Journey Analytics vers la zone d’entrée des données Adobe Experience Platform, veillez à télécharger les données dans les 7 jours, puis supprimez-les dans la zone d’entrée des données AEP. Au bout de 7 jours, les données sont automatiquement supprimées de la zone d’entrée des données AEP.

1. [Commencer à créer un emplacement d’exportation dans le cloud](#begin-creating-a-cloud-export-location), comme décrit ci-dessus.

1. Dans le [!UICONTROL **Propriétés de l’emplacement**] de la [!UICONTROL **Ajouter un emplacement**] , spécifiez les informations suivantes pour configurer un emplacement de zone d’entrée de données Adobe Experience Platform :

   <!-- still need to update; can't create AEP account -->

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Identifiant de l’organisation IMS**] | L’identifiant de l’organisation IMS est fourni par Adobe. Cliquez sur l’icône Copier en regard de l’option [!UICONTROL **Identifiant de l’organisation IMS**] pour copier le contenu du champ, puis utilisez l’identifiant dans votre compte Adobe Experience Platform. |
   | [!UICONTROL **Préfixe**] | Le dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier.   Par exemple : `folder_name/` |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Vous pouvez désormais exporter les données d’Analysis Workspace vers le compte et l’emplacement que vous avez configurés. Pour plus d’informations sur l’exportation de données vers le cloud, voir [Exportation des données de projet dans le cloud](/help/analysis-workspace/export/export-cloud.md).

### Amazon S3 Role ARN

1. [Commencer à créer un emplacement d’exportation dans le cloud](#begin-creating-a-cloud-export-location), comme décrit ci-dessus.

1. Dans le [!UICONTROL **Propriétés de l’emplacement**] de la [!UICONTROL **Ajouter un emplacement**] , spécifiez les informations suivantes pour configurer un emplacement d’acquisition du rôle Amazon S3 :

   <!-- still need to update; can't create S3 role ARN account -->

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Compartiment**] | Le compartiment de votre compte Amazon S3 dans lequel vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous que le User ARN fourni par Adobe a accès aux fichiers de chargement vers ce compartiment. |
   | [!UICONTROL **Préfixe**] | Le dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, folder_name/ |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Vous pouvez désormais exporter les données d’Analysis Workspace vers le compte et l’emplacement que vous avez configurés. Pour plus d’informations sur l’exportation de données vers le cloud, voir [Exportation des données de projet dans le cloud](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. [Commencer à créer un emplacement d’exportation dans le cloud](#begin-creating-a-cloud-export-location), comme décrit ci-dessus.

1. Dans le [!UICONTROL **Propriétés de l’emplacement**] de la [!UICONTROL **Ajouter un emplacement**] , spécifiez les informations suivantes pour configurer un emplacement Google Cloud Platform :

   <!-- still need to update; can't create GCP account -->

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Compartiment**] | Le compartiment de votre compte GCP où vous souhaitez que les données de Customer Journey Analytics soient envoyées. Assurez-vous que vous avez autorisé l’entité de sécurité fournie par Adobe pour charger des fichiers dans ce compartiment. (L’entité de sécurité est fournie lors de la [configuration du compte Google Cloud Platform](/help/components/exports/cloud-export-accounts.md).) Pour plus d’informations sur l’octroi d’autorisations, voir [Ajout d’une entité à une stratégie de niveau compartiment](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) dans la documentation de Google Cloud. |
   | [!UICONTROL **Préfixe**] | Le dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, folder_name/ |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Vous pouvez désormais exporter les données d’Analysis Workspace vers le compte et l’emplacement que vous avez configurés. Pour plus d’informations sur l’exportation de données vers le cloud, voir [Exportation des données de projet dans le cloud](/help/analysis-workspace/export/export-cloud.md).

### SAS Azure

1. [Commencer à créer un emplacement d’exportation dans le cloud](#begin-creating-a-cloud-export-location), comme décrit ci-dessus.

1. Dans le [!UICONTROL **Propriétés de l’emplacement**] de la [!UICONTROL **Ajouter un emplacement**] , spécifiez les informations suivantes pour configurer un emplacement Azure SAS :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom du conteneur**] | Conteneur dans le compte que vous avez spécifié à l’emplacement où vous souhaitez que les données de Customer Journey Analytics soient envoyées. |
   | [!UICONTROL **Préfixe**] | Le dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier.   Par exemple : `folder_name/` |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Vous pouvez désormais exporter les données d’Analysis Workspace vers le compte et l’emplacement que vous avez configurés. Pour plus d’informations sur l’exportation de données vers le cloud, voir [Exportation des données de projet dans le cloud](/help/analysis-workspace/export/export-cloud.md).

### RBAC Azure

1. [Commencer à créer un emplacement d’exportation dans le cloud](#begin-creating-a-cloud-export-location), comme décrit ci-dessus.

1. Dans le [!UICONTROL **Propriétés de l’emplacement**] de la [!UICONTROL **Ajouter un emplacement**] , spécifiez les informations suivantes pour configurer un emplacement Azure RBAC :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Conteneur**] | Conteneur dans le compte que vous avez spécifié à l’emplacement où vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous d’accorder les autorisations de chargement de fichiers vers l’application Azure que vous avez créée précédemment. |
   | [!UICONTROL **Préfixe**] | Le dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier.   Par exemple : `folder_name/` |
   | [!UICONTROL **Compte**] | Compte de stockage Azure. |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Vous pouvez désormais exporter les données d’Analysis Workspace vers le compte et l’emplacement que vous avez configurés. Pour plus d’informations sur l’exportation de données vers le cloud, voir [Exportation des données de projet dans le cloud](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. [Commencer à créer un emplacement d’exportation dans le cloud](#begin-creating-a-cloud-export-location), comme décrit ci-dessus.

1. Dans le [!UICONTROL **Propriétés de l’emplacement**] de la [!UICONTROL **Ajouter un emplacement**] , spécifiez les informations suivantes pour configurer un emplacement de Snowflake :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **DB**] | La base de données spécifiée doit être une base de données existante. Le rôle que vous avez créé doit disposer de droits d’accès à cette base de données.<p>Il s’agit de la base de données associée au nom de l’étape.</p><p>Vous pouvez accorder ces privilèges de rôle à la base de données en Snowflake à l’aide de la commande suivante : `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>Pour plus d’informations, voir [Page Base de données, schéma et commandes de partage dans la documentation du Snowflake](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Schéma**] | Le schéma spécifié doit être un schéma existant. Le rôle que vous avez créé doit disposer de privilèges pour accéder à ce schéma.<p>Il s’agit du schéma associé au nom de l’étape.<p>Vous pouvez accorder au schéma en Snowflake le rôle que vous avez créé avec la commande suivante : `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>Pour plus d’informations, voir [Page Base de données, schéma et commandes de partage dans la documentation du Snowflake](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Nom de l’étape**] | Nom de l’étape interne dans laquelle les fichiers de données sont stockés dans Snowflake.<p>Assurez-vous que le rôle que vous avez spécifié sur le compte dispose d’un accès en lecture et en écriture à ce nom d’étape. (Puisque vous accordez l’accès en lecture et en écriture, nous vous recommandons d’utiliser une étape utilisée uniquement par Adobe.)<p>Vous pouvez accorder l’accès en lecture et en écriture au nom de l’étape en Snowflake à l’aide de la commande suivante : `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>Pour plus d’informations sur l’octroi de privilèges à un rôle, voir [Octroi de privilèges dans la documentation du Snowflake](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>Pour plus d’informations sur le nom de l’étape, voir [Sélection d’une page Interne pour les fichiers locaux dans la documentation du Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **Parcours par étape**] | Chemin d’accès à l’emplacement où les fichiers de données sont stockés dans Snowflake. <p>Pour plus d’informations, voir [Sélection d’une page Interne pour les fichiers locaux dans la documentation du Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Vous pouvez désormais exporter les données d’Analysis Workspace vers le compte et l’emplacement que vous avez configurés. Pour plus d’informations sur l’exportation de données vers le cloud, voir [Exportation des données de projet dans le cloud](/help/analysis-workspace/export/export-cloud.md).
