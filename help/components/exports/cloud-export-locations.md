---
description: Configurer l’emplacement d’exportation cloud où les données Customer Journey Analytics peuvent être envoyées
keywords: Analysis Workspace
title: Configurer des emplacements d’export cloud
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: 5adcab1df932f5c8af1f140fb6707f2d56726ae3
workflow-type: tm+mt
source-wordcount: '2030'
ht-degree: 19%

---

# Configurer des emplacements d’export cloud {#configure-cloud-export-locations}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-prefix"
>title="Préfixe"
>abstract="Le dossier racine dans le conteneur dans lequel vous souhaitez placer les données. Spécifiez un nom de dossier statique, puis ajoutez une barre oblique à la suite du nom pour créer le dossier. Par exemple, `folder_name/`"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-file-name"
>title="Nom et chemin du fichier"
>abstract="Spécifiez un nom de fichier personnalisé dynamique à utiliser pour les exportations automatisées envoyées à cet emplacement. Vous pouvez également faire précéder le nom du fichier d’un chemin d’accès au fichier personnalisé dynamique. &lt;br\>Utilisez des variables dans le nom et le chemin du fichier pour les rendre dynamiques. &lt;br\>Par exemple, si vous spécifiez `${yyyy}/${mm}/${dd}/my-report-${instance_id}-${idx}`, une exportation automatiquement envoyée vers cette destination le 15 janvier 2026 aurait le chemin d’accès au fichier et le nom suivants : `[prefix_folder_name]/2026/01/15/my-report-[UUID]-1.csv` &lt;br\>Cliquez sur le lien ci-dessous pour obtenir une liste des variables disponibles."

<!-- markdownlint-enable MD034 -->

Avant de pouvoir exporter des rapports Customer Journey Analytics vers une destination cloud (depuis Analysis Workspace, comme décrit dans [Exporter des rapports Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md) ou depuis Report Builder, comme décrit dans [Exporter des rapports depuis Report Builder](/help/report-builder/report-builder-export.md)), comme décrit dans [Exporter des rapports Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md), vous devez ajouter et configurer l’emplacement où vous souhaitez que les données soient envoyées.

Ce processus consiste à ajouter et à configurer le compte (Amazon S3, Google Cloud Platform, etc.) comme décrit dans la section [Configurer des comptes d’exportation cloud](/help/components/exports/cloud-export-accounts.md), puis à ajouter et à configurer l’emplacement au sein de ce compte (un dossier au sein du compte, par exemple) comme décrit dans cet article.

Pour plus d’informations sur la gestion des emplacements existants, notamment l’affichage, la modification et la suppression d’emplacements, consultez [Gérer les emplacements et comptes d’exportation dans le cloud](/help/components/exports/manage-export-locations.md).

## Commencer à créer un emplacement d’exportation dans le cloud

1. Vous devez ajouter un compte avant de pouvoir ajouter un emplacement. Si ce n’est pas déjà fait, ajoutez un compte, comme décrit dans la section [Configurer des comptes d’exportation cloud](/help/components/exports/cloud-export-accounts.md).

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Emplacements**], puis sélectionnez [!UICONTROL **Ajouter un emplacement**].

   ![Fenêtre Exporte avec l’onglet Emplacement sélectionné mettant en surbrillance le bouton Ajouter un emplacement](assets/location-add.png)

   Ou

   Sélectionnez l’onglet [!UICONTROL **Comptes d’emplacement**], cliquez sur l’icône en forme de point 3 sur un compte existant auquel vous souhaitez ajouter un emplacement, puis sélectionnez [!UICONTROL **Ajouter un emplacement**].

   ![Compte GCP et menu déroulant avec points de suspension affichant Ajouter l’emplacement sélectionné](assets/add-location-existing-account.png)

   La boîte de dialogue Emplacement s’affiche.

1. Indiquez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom**] | Nom de l’emplacement. |
   | [!UICONTROL **Description**] | Fournissez une brève description de l’emplacement pour aider à le différencier des autres emplacements du compte. |
   | [!UICONTROL **Rendre l’emplacement disponible pour tous les utilisateurs de votre organisation**] | Activez cette option pour permettre à d’autres utilisateurs de votre organisation d’utiliser l’emplacement. <p>Tenez compte des points suivants lors du partage d’emplacements :</p><ul><li>Les emplacements partagés ne peuvent pas être annulés.</li><li>Les emplacements partagés ne peuvent être modifiés que par le propriétaire de l’emplacement.</li><li>Les emplacements ne peuvent être partagés que si le compte auquel l’emplacement est associé est également partagé.</li></ul> |
   | [!UICONTROL **Compte d’emplacement**] | Sélectionnez le compte sur lequel vous souhaitez créer l’emplacement. Pour plus d’informations sur la création d’un compte, voir [Configurer des comptes d’exportation cloud](/help/components/exports/cloud-export-accounts.md). |

1. Dans la section [!UICONTROL **Propriétés d’emplacement**], indiquez les informations spécifiques au type de votre compte d’emplacement.

   Continuez avec la section ci-dessous qui correspond au type de compte que vous avez sélectionné dans le champ [!UICONTROL **Compte d’emplacement**].

   * [Zone de destination des données AEP](#aep-data-landing-zone)
   * [Amazon S3 Role ARN](#amazon-s3-role-arn)
   * [Google Cloud Platform](#google-cloud-platform)
   * [SAS Azure](#azure-sas)
   * [RBAC Azure](#azure-rbac)
   * [Snowflake](#snowflake)

### Zone de destination des données AEP

>[!IMPORTANT]
>
>Lors de l’exportation de rapports Customer Journey Analytics vers la zone d’atterrissage de données de Adobe Experience Platform, veillez à télécharger les données dans les 7 jours, puis à les supprimer de la zone d’atterrissage de données d’AEP. Au bout de 7 jours, les données sont automatiquement supprimées de la zone d’atterrissage des données d’AEP.

1. Commencez à créer un emplacement d’exportation dans le cloud de l’une des façons suivantes :

   * Sur la page Exports , comme décrit ci-dessus, dans [Commencez à créer un emplacement d’exportation dans le cloud](#begin-creating-a-cloud-export-location)

   * Lors de [exportation de tables complètes à partir d’Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Dans la section [!UICONTROL **Propriétés de l’emplacement**] de la boîte de dialogue [!UICONTROL **Ajouter un emplacement**], spécifiez les informations suivantes pour configurer un emplacement de zone d’atterrissage de données Adobe Experience Platform :

   <!-- still need to update; can't create AEP account -->

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Préfixe**] | Dossier du conteneur dans lequel vous souhaitez placer les données. Spécifiez un nom de dossier, puis ajoutez une barre oblique à sa suite pour créer le dossier. Par exemple, `folder_name/` |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Vous pouvez désormais exporter des données d’Analysis Workspace vers le compte et l’emplacement que vous avez configurés. Pour plus d’informations sur l’exportation de données vers le cloud, voir [ Exporter des données de projet vers le cloud](/help/analysis-workspace/export/export-cloud.md).

1. Le moyen le plus simple d’accéder à vos données dans la zone d’atterrissage de données AEP consiste à utiliser l’explorateur de stockage Azure Microsoft. Il s’agit du même outil que celui utilisé dans les instructions pour configurer le compte de zone d’atterrissage de données [AEP](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone).

   1. Ouvrez l’explorateur de stockage Azure [Microsoft](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Accédez à [!UICONTROL **Comptes de stockage**] > [!UICONTROL **(Conteneurs attachés)**] > [!UICONTROL **Conteneurs Blob**] > **[!UICONTROL cjaexport-_number_]**>*** your_container_name ***.

      >[!NOTE]
      >
      >Le nom de dossier **[!UICONTROL cjaexport-_number_]**est le nom par défaut fourni par Azure Storage Explorer. Si une seule connexion est associée à votre URI SAS (ce qui est normal), le nom de ce dossier est **[!UICONTROL cjaexport-1]**.


      ![Accès aux fichiers dans l’explorateur de stockage Azure](assets/azure-storage-explorer-access.png)

   1. Sélectionnez l’exportation à télécharger, puis sélectionnez [!UICONTROL **Télécharger**] pour la télécharger.

### Amazon S3 Role ARN

1. Commencez à créer un emplacement d’exportation dans le cloud de l’une des façons suivantes :

   * Sur la page Exports , comme décrit ci-dessus, dans [Commencez à créer un emplacement d’exportation dans le cloud](#begin-creating-a-cloud-export-location)

   * Lors de [exportation de tables complètes à partir d’Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Dans la section [!UICONTROL **Propriétés de l’emplacement**] de la boîte de dialogue [!UICONTROL **Ajouter un emplacement**], spécifiez les informations suivantes pour configurer un emplacement ARN de rôle Amazon S3 :

   <!-- still need to update; can't create S3 role ARN account -->

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **compartiment**] | Compartiment de votre compte Amazon S3 dans lequel vous souhaitez que les données Customer Journey Analytics soient envoyées. <p>Assurez-vous que l’ARN utilisateur fourni par Adobe dispose de l’autorisation `S3:PutObject` pour charger des fichiers dans ce compartiment. </p><p>Les noms des compartiments doivent respecter des règles de nommage spécifiques. Par exemple, ils doivent avoir une longueur comprise entre 3 et 63 caractères, ne peuvent être composés que de lettres minuscules, de chiffres, de points (.) et de traits d’union (-), et doivent commencer et se terminer par une lettre ou un chiffre. [Une liste complète des règles de nommage est disponible dans la documentation AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
   | [!UICONTROL **Préfixe**] | Dossier dans le compartiment où vous souhaitez placer les données. Spécifiez un nom de dossier, puis ajoutez une barre oblique à sa suite pour créer le dossier. Par exemple, folder_name/ |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Vous pouvez désormais exporter des données d’Analysis Workspace vers le compte et l’emplacement que vous avez configurés. Pour plus d’informations sur l’exportation de données vers le cloud, voir [ Exporter des données de projet vers le cloud](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. Commencez à créer un emplacement d’exportation dans le cloud de l’une des façons suivantes :

   * Sur la page Exports , comme décrit ci-dessus, dans [Commencez à créer un emplacement d’exportation dans le cloud](#begin-creating-a-cloud-export-location)

   * Lors de [exportation de tables complètes à partir d’Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Dans la section [!UICONTROL **Propriétés de l’emplacement**] de la boîte de dialogue [!UICONTROL **Ajouter un emplacement**], spécifiez les informations suivantes pour configurer un emplacement de Google Cloud Platform :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **compartiment**] | Compartiment de votre compte GCP dans lequel vous souhaitez que les données Customer Journey Analytics soient envoyées. <p>Assurez-vous d’avoir accordé l’autorisation `roles/storage.objectCreator` au principal de sécurité fourni par Adobe. (L’entité de sécurité est fournie lors de la [configuration du compte Google Cloud Platform](/help/components/exports/cloud-export-accounts.md).) <p>Pour plus d’informations sur l’octroi d’autorisations, consultez [Ajouter un compte principal à une stratégie au niveau du compartiment](https://cloud.google.com/storage/docs/access-control/using-iam-permissions?hl=fr#bucket-add) dans la documentation de Google Cloud.</p><p>Si votre entreprise utilise des [Contraintes applicables aux politiques des organisations](https://cloud.google.com/storage/docs/org-policy-constraints?hl=fr) pour n’autoriser que le compte Google Cloud Platform dans votre liste autorisée, vous avez besoin de cet identifiant d’organisation Google Cloud Platform détenu par Adobe : <ul><li>`DISPLAY_NAME` : `adobe.com`</li><li>`ID` : `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID` : `C02jo8puj`</li></ul> </p> |
   | [!UICONTROL **Préfixe**] | Dossier dans le compartiment où vous souhaitez placer les données. Spécifiez un nom de dossier, puis ajoutez une barre oblique à sa suite pour créer le dossier. Par exemple, folder_name/ |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Vous pouvez désormais exporter des données d’Analysis Workspace vers le compte et l’emplacement que vous avez configurés. Pour plus d’informations sur l’exportation de données vers le cloud, voir [ Exporter des données de projet vers le cloud](/help/analysis-workspace/export/export-cloud.md).

### SAS Azure

1. Commencez à créer un emplacement d’exportation dans le cloud de l’une des façons suivantes :

   * Sur la page Exports , comme décrit ci-dessus, dans [Commencez à créer un emplacement d’exportation dans le cloud](#begin-creating-a-cloud-export-location)

   * Lors de [exportation de tables complètes à partir d’Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Dans la section [!UICONTROL **Propriétés de l’emplacement**] de la boîte de dialogue [!UICONTROL **Ajouter un emplacement**], spécifiez les informations suivantes pour configurer un emplacement SAS Azure :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom du conteneur**] | Conteneur dans le compte que vous avez spécifié où vous souhaitez que les données Customer Journey Analytics soient envoyées. |
   | [!UICONTROL **Préfixe**] | Dossier du conteneur dans lequel vous souhaitez placer les données. Spécifiez un nom de dossier, puis ajoutez une barre oblique à sa suite pour créer le dossier. Par exemple, `folder_name/`<p>Assurez-vous que le magasin de jetons SAS que vous avez spécifié dans le champ Nom du secret Key Vault lors de la configuration du compte Azure SAS dispose de l’autorisation `Write`. Cela permet au jeton SAS de créer des fichiers dans votre conteneur Azure. <p>Si vous souhaitez que le jeton SAS remplace également les fichiers, assurez-vous que le magasin de jetons SAS dispose de l’autorisation `Delete`.</p><p>Pour plus d’informations, consultez [Ressources de stockage Blob](https://learn.microsoft.com/fr-fr/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) dans la documentation Azure Blob Storage.</p> |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Vous pouvez désormais exporter des données d’Analysis Workspace vers le compte et l’emplacement que vous avez configurés. Pour plus d’informations sur l’exportation de données vers le cloud, voir [ Exporter des données de projet vers le cloud](/help/analysis-workspace/export/export-cloud.md).

### RBAC Azure

1. Commencez à créer un emplacement d’exportation dans le cloud de l’une des façons suivantes :

   * Sur la page Exports , comme décrit ci-dessus, dans [Commencez à créer un emplacement d’exportation dans le cloud](#begin-creating-a-cloud-export-location)

   * Lors de [exportation de tables complètes à partir d’Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Dans la section [!UICONTROL **Propriétés de l’emplacement**] de la boîte de dialogue [!UICONTROL **Ajouter un emplacement**], spécifiez les informations suivantes pour configurer un emplacement Azure RBAC :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Conteneur**] | Conteneur dans le compte que vous avez spécifié où vous souhaitez que les données Customer Journey Analytics soient envoyées. Assurez-vous d’accorder les autorisations de chargement de fichiers vers l’application Azure que vous avez créée précédemment. |
   | [!UICONTROL **Préfixe**] | Dossier du conteneur dans lequel vous souhaitez placer les données. Spécifiez un nom de dossier, puis ajoutez une barre oblique à sa suite pour créer le dossier. Par exemple, `folder_name/`.<p>Assurez-vous que l’ID d’application que vous avez spécifié lors de la configuration du compte Azure RBAC a reçu le rôle `Storage Blob Data Contributor` pour accéder au conteneur (dossier).</p> <p>Pour plus d’informations, consultez [Rôles intégrés Azure](https://learn.microsoft.com/fr-fr/azure/role-based-access-control/built-in-roles).</p> |
   | [!UICONTROL **Compte**] | Compte de stockage Azure. |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Vous pouvez désormais exporter des données d’Analysis Workspace vers le compte et l’emplacement que vous avez configurés. Pour plus d’informations sur l’exportation de données vers le cloud, voir [ Exporter des données de projet vers le cloud](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. Commencez à créer un emplacement d’exportation dans le cloud de l’une des façons suivantes :

   * Sur la page Exports , comme décrit ci-dessus, dans [Commencez à créer un emplacement d’exportation dans le cloud](#begin-creating-a-cloud-export-location)

   * Lors de [exportation de tables complètes à partir d’Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Dans la section [!UICONTROL **Propriétés de l’emplacement**] de la boîte de dialogue [!UICONTROL **Ajouter un emplacement**], spécifiez les informations suivantes pour configurer un emplacement Snowflake :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **DB**] | La base de données spécifiée doit être existante. Le rôle que vous avez créé doit disposer de droits pour accéder à cette base de données.<p>Base de données associée au nom de l’étape.</p><p>Vous pouvez accorder des privilèges de ce rôle à la base de données dans Snowflake à l’aide de la commande suivante : `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>Pour plus d’informations, consultez la page [Base de données, schéma et commandes de partage) de la documentation de Snowflake](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Schéma**] | Le schéma spécifié doit être un schéma existant. Le rôle que vous avez créé doit disposer de privilèges pour accéder à ce schéma.<p>Il s’agit du schéma associé au nom de l’étape.<p>Vous pouvez accorder au rôle que vous avez créé des privilèges sur le schéma dans Snowflake à l’aide de la commande suivante : `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>Pour plus d’informations, consultez la page [Base de données, schéma et commandes de partage) de la documentation de Snowflake](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Nom de l’étape**] | Nom de l’étape interne dans laquelle les fichiers de données sont stockés dans Snowflake.<p>Assurez-vous que le rôle que vous avez spécifié sur le compte dispose d’un accès en lecture et écriture à ce nom d’étape. (Puisque vous accordez un accès en lecture et écriture, nous vous recommandons d’utiliser une étape utilisée uniquement par Adobe.)<p>Vous pouvez accorder un accès en lecture et écriture au nom de l’étape dans Snowflake à l’aide de la commande suivante : `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>Pour plus d’informations sur l’octroi de privilèges à un rôle, voir [Octroi de privilèges dans la documentation de Snowflake](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>Pour plus d’informations sur le nom de l’étape, consultez la page [ Choix d’une étape interne pour les fichiers locaux dans la documentation de Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **Chemin de l’étape**] | Chemin d’accès à l’emplacement où les fichiers de données sont stockés dans Snowflake. <p>Pour plus d’informations, consultez la page [Choix d’une étape interne pour les fichiers locaux ) de la documentation de Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Vous pouvez désormais exporter des données d’Analysis Workspace vers le compte et l’emplacement que vous avez configurés. Pour plus d’informations sur l’exportation de données vers le cloud, voir [ Exporter des données de projet vers le cloud](/help/analysis-workspace/export/export-cloud.md).
