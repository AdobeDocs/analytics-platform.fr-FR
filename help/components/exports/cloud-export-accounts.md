---
description: Configuration du compte d’exportation cloud où les données de Customer Journey Analytics peuvent être envoyées
keywords: Analysis Workspace
title: Configurer des comptes d’export cloud
feature: Components
exl-id: 7c9d100f-0dbd-4dd2-b20b-d2ee117f1b7a
role: User, Admin
source-git-commit: 1ba2ef57a6ecc8246c1481f02d28ebeb62cc9909
workflow-type: tm+mt
source-wordcount: '2010'
ht-degree: 28%

---

# Configurer des comptes d’export cloud

Avant de pouvoir exporter des rapports de Customer Journey Analytics vers une destination cloud comme décrit dans la section [Exporter des rapports de Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md), vous devez ajouter et configurer la destination vers laquelle les données doivent être envoyées.

Ce processus consiste à ajouter et à configurer le compte (par exemple, Amazon S3, Google Cloud Platform, etc.) comme décrit dans cet article, puis à ajouter et à configurer l’emplacement dans ce compte (par exemple, un dossier dans le compte) comme décrit dans la section [Configuration des emplacements d’exportation cloud](/help/components/exports/cloud-export-locations.md).

Pour plus d’informations sur la gestion des comptes existants, y compris l’affichage, la modification et la suppression de comptes, voir [Gestion des emplacements et des comptes d’exportation cloud](/help/components/exports/manage-export-locations.md).

## Commencer à créer un compte d’exportation dans le cloud

1. Assurez-vous de respecter la [configuration minimale requise](/help/analysis-workspace/export/export-cloud.md#minimum-requirements) pour exporter des rapports vers le cloud.
1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].
1. Sur la page [!UICONTROL Exports], sélectionnez l’onglet [!UICONTROL **Location accounts**].

   ![Exporte les options de page affichant Ajouter un autre compte](assets/account-add.png)

1. Sélectionnez [!UICONTROL **Ajouter un compte**].

   La boîte de dialogue Ajouter un compte s’affiche.

1. Dans le champ [!UICONTROL **Nom du compte d’emplacement**], spécifiez un nom pour le compte d’emplacement. Ce nom apparaît lors de la création d’un emplacement.

1. Dans le champ [!UICONTROL **Description du compte de localisation**], fournissez une brève description du compte pour l’aider à le différencier des autres comptes du même type de compte.

1. Activez l’option [!UICONTROL **Rendre le compte disponible pour tous les utilisateurs de votre organisation**] si vous souhaitez autoriser d’autres utilisateurs de votre organisation à utiliser le compte.

   Tenez compte des points suivants lors du partage de comptes :

   * Les comptes que vous partagez ne peuvent pas être annulés.

   * Les comptes partagés ne peuvent être modifiés que par le propriétaire du compte.

   * N’importe qui peut créer un emplacement pour le compte partagé.

1. Dans le champ [!UICONTROL **Type de compte**] , sélectionnez le type de compte cloud vers lequel vous exportez. Les types de compte disponibles sont Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake et AEP Data Landing Zone.

1. Passez à la section ci-dessous qui correspond au [!UICONTROL **Type de compte**] que vous avez sélectionné.

   * [Zone de destination des données AEP](#aep-data-landing-zone)

   * [Amazon S3 Role ARN](#amazon-s3-role-arn)

   * [Google Cloud Platform](#google-cloud-platform)

   * [SAS Azure](#azure-sas)

   * [RBAC Azure](#azure-rbac)

   * [Snowflake](#snowflake)

### Zone de destination des données AEP

>[!IMPORTANT]
>
>Lors de l’exportation de rapports Customer Journey Analytics vers la zone d’entrée des données Adobe Experience Platform, veillez à télécharger les données dans les 7 jours, puis supprimez-les dans la zone d’entrée des données AEP. Au bout de 7 jours, les données sont automatiquement supprimées de la zone d’entrée des données AEP.

1. Commencez à créer un compte d’exportation dans le cloud de l’une des façons suivantes :

   * Sur la page Exports, comme décrit ci-dessus, dans [Commencer la création d’un compte d’exportation cloud](#begin-creating-a-cloud-export-account)

   * Lors de l&#39; [exportation de tables complètes à partir d&#39;Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Sélectionnez [!UICONTROL **Enregistrer**].

   La boîte de dialogue [!UICONTROL **Exporter le compte créé**] s’affiche.

   ![Boîte de dialogue d’exportation du compte AEP Data Landing Zone](assets/export-account-aep.png)

1. Copiez le contenu du champ [!UICONTROL **SAS URI**] dans le presse-papiers. Vous utiliserez cet URI SAS pour accéder aux données exportées depuis Analysis Workspace à partir de la zone d’entrée des données AEP.

   Si ce champ est vide, vous devez disposer de l’autorisation d’accès à Adobe Experience Platform.

1. Dans Adobe Experience Platform, configurez votre conteneur de zones d’entrée de données pour utiliser l’URI SAS que vous avez copié.

   >[!NOTE]
   >
   >Le compte Zone d’entrée des données AEP étant basé sur Azure, la méthode la plus simple pour accéder aux rapports que vous exportez vers la zone d’entrée des données AEP consiste à utiliser l’Explorateur de stockage Azure. Les étapes suivantes utilisent cette méthode.

   1. Si vous ne l’avez pas déjà fait, téléchargez le [Microsoft Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Dans la documentation Adobe Experience Platform, suivez les étapes décrites dans [Connectez votre conteneur de zone d’entrée de données à Azure Storage Explorer](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#connect-your-data-landing-zone-container-to-azure-storage-explorer).

      Vous pouvez ignorer les tâches décrites dans les sections [Récupérez les informations d’identification de votre zone d’entrée de données](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#retrieve-dlz-credentials) et [Mettre à jour les informations d’identification de la zone d’entrée de données](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#update-dlz-credentials), car l’URI que vous avez copié contient ces informations d’identification.

   1. Lorsque vous suivez la documentation Adobe Experience Platform et que vous accédez au champ [!UICONTROL **Blob container SAS URL**] , collez l’URI SAS que vous avez copié à l’étape 3.

      >[!NOTE]
      >
      >Vous devez effectuer cette action tous les 7 jours, car l’URI SAS expire 7 jours après sa création. Vous pouvez créer un script pour automatiser ce processus.


      ![Fenêtre d’informations de connexion indiquant le champ URL SAS](assets/blob-container-sas-uri.png)

   1. Sélectionnez [!UICONTROL **Suivant**] > [!UICONTROL **Se connecter**].

1. Dans Customer Journey Analytics, dans la boîte de dialogue [!UICONTROL **Export account created**], sélectionnez [!UICONTROL **OK**].

   ![Boîte de dialogue d’exportation du compte AEP Data Landing Zone](assets/export-account-aep.png)

1. Passez à la [configuration des emplacements d’exportation dans le cloud](/help/components/exports/cloud-export-locations.md).

### Amazon S3 Role ARN

1. Commencez à créer un compte d’exportation dans le cloud de l’une des façons suivantes :

   * Sur la page Exports, comme décrit ci-dessus, dans [Commencer la création d’un compte d’exportation cloud](#begin-creating-a-cloud-export-account)

   * Lors de l&#39; [exportation de tables complètes à partir d&#39;Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Dans la section [!UICONTROL **Propriétés du compte**] de la boîte de dialogue [!UICONTROL **Ajouter un compte**], spécifiez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **ARN de rôle**] | Vous devez fournir un ARN de rôle (nom de ressource Amazon) qu’Adobe peut utiliser pour accéder au compte Amazon S3. Pour ce faire, vous créez une politique d’autorisation IAM pour le compte source, vous la joignez à un utilisateur ou à une utilisatrice, puis vous créez un rôle pour le compte de destination. Pour plus d’informations, consultez [cette documentation AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

   La boîte de dialogue [!UICONTROL **Exporter le compte créé**] s’affiche.

   ![Boîte de dialogue de création du compte d’exportation Rôle Amazon S3 ARN](assets/export-account-amazons3.png)

1. Copiez le contenu du champ [!UICONTROL **User ARN**] dans le presse-papiers. L’ARN d’utilisateur ou d’utilisatrice (nom de ressource Amazon) est fourni par Adobe. Vous devez associer cet utilisateur à la stratégie que vous avez créée dans l’outil d’apprentissage des rôles Amazon S3.

1. Sélectionnez [!UICONTROL **OK**].

1. Passez à la [configuration des emplacements d’exportation dans le cloud](/help/components/exports/cloud-export-locations.md).

### Google Cloud Platform

1. Commencez à créer un compte d’exportation dans le cloud de l’une des façons suivantes :

   * Sur la page Exports, comme décrit ci-dessus, dans [Commencer la création d’un compte d’exportation cloud](#begin-creating-a-cloud-export-account)

   * Lors de l&#39; [exportation de tables complètes à partir d&#39;Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Dans la section [!UICONTROL **Propriétés du compte**] de la boîte de dialogue [!UICONTROL **Ajouter un compte**], spécifiez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Identifiant du projet**] | Identifiant de projet Google Cloud que vous copiez depuis votre compte Google Cloud. Consultez la [documentation de Google Cloud sur l’obtention d’un ID de projet](https://cloud.google.com/resource-manager/docs/creating-managing-projects?hl=fr#identifying_projects). |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

   La boîte de dialogue [!UICONTROL **Exporter le compte créé**] s’affiche.

   ![Boîte de dialogue de création de compte d’exportation](assets/export-account-gcp.png)

1. Copiez le contenu du champ [!UICONTROL **Principal**] dans le presse-papiers, puis assurez-vous que vous accordez l’autorisation à l’entité de sécurité de charger des fichiers dans ce compartiment dans Google Cloud Platform. <!-- add link to Google Cloud docs on how to do this -->

1. Sélectionnez [!UICONTROL **OK**].

1. Passez à la [configuration des emplacements d’exportation dans le cloud](/help/components/exports/cloud-export-locations.md).

### SAS Azure

1. Commencez à créer un compte d’exportation dans le cloud de l’une des façons suivantes :

   * Sur la page Exports, comme décrit ci-dessus, dans [Commencer la création d’un compte d’exportation cloud](#begin-creating-a-cloud-export-account)

   * Lors de l&#39; [exportation de tables complètes à partir d&#39;Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Dans la section [!UICONTROL **Propriétés du compte**] de la boîte de dialogue [!UICONTROL **Ajouter un compte**], spécifiez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **ID de l’application**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistreement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **ID de cliente ou client**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, consultez la [documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **URI du coffre de clés**] | <p>Chemin d’accès à l’URI SAS dans Azure Key Vault.  Pour configurer une signature d’accès partagé Azure (SAS), vous devez stocker un URI SAS en tant que secret à l’aide d’Azure Key Vault. Pour plus d’informations, consultez la [documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Une fois l’URI de coffre de clés créé :<ul><li>Ajoutez une politique d’accès sur Key Vault afin d’accorder l’autorisation à l’application Azure que vous avez créée.<p><p>Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’affectation d’une politique d’accès Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p>Ou</p><p>Si vous souhaitez accorder un rôle d’accès directement sans créer de stratégie d’accès, consultez la [documentation de Microsoft Azure sur l’affectation de rôles Azure à l’aide du portail Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). Cela ajoute l’affectation de rôle pour l’ID d’application pour accéder à l’URI de coffre-fort de clé. </p></li><li>Assurez-vous que l’ID de l’application a bien reçu le rôle intégré `Key Vault Certificate User` afin d’accéder à l’URI de coffre de clés.</br><p>Pour plus d’informations, voir [Rôles intégrés Azure](https://learn.microsoft.com/fr-fr/azure/role-based-access-control/built-in-roles).</p></li></ul> |
   | [!UICONTROL **Nom secret du coffre de clés**] | Le nom du secret que vous avez créé lors de l’ajout du secret à Azure Key Vault. Dans Microsoft Azure, ces informations se trouvent dans le coffre Key Vault que vous avez créé, sur la page de paramètres de **Key Vault**. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Secret du compte de localisation**] | Copiez le secret depuis l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur l’onglet **Certificats et secrets** dans votre application. Pour plus d’informations, consultez la [documentation de Microsoft Azure sur l’enregistrement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

   La boîte de dialogue [!UICONTROL **Exporter le compte créé**] s’affiche.

   ![Boîte de dialogue de création de compte d’exportation](assets/export-account-azure.png)

1. Si ce n&#39;est déjà fait, assurez-vous d&#39;accorder des autorisations au compartiment dans Azure SAS. <!-- add link to Google Cloud docs on how to do this -->

1. Sélectionnez [!UICONTROL **OK**].

1. Passez à la [configuration des emplacements d’exportation dans le cloud](/help/components/exports/cloud-export-locations.md).

### RBAC Azure

1. Commencez à créer un compte d’exportation dans le cloud de l’une des façons suivantes :

   * Sur la page Exports, comme décrit ci-dessus, dans [Commencer la création d’un compte d’exportation cloud](#begin-creating-a-cloud-export-account)

   * Lors de l&#39; [exportation de tables complètes à partir d&#39;Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Dans la section [!UICONTROL **Propriétés du compte**] de la boîte de dialogue [!UICONTROL **Ajouter un compte**], spécifiez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **ID de l’application**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistreement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **ID de cliente ou client**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistreement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **Secret du compte de localisation**] | Copiez le secret depuis l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur l’onglet **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistrement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

   La boîte de dialogue [!UICONTROL **Exporter le compte créé**] s’affiche.

   ![Boîte de dialogue de création de compte d’exportation](assets/export-account-azure.png)

1. Si ce n&#39;est déjà fait, assurez-vous d&#39;accorder des autorisations au compartiment dans Azure RBAC. <!-- add link to Google Cloud docs on how to do this -->

1. Sélectionnez [!UICONTROL **OK**].

1. Passez à la [configuration des emplacements d’exportation dans le cloud](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. Commencez à créer un compte d’exportation dans le cloud de l’une des façons suivantes :

   * Sur la page Exports, comme décrit ci-dessus, dans [Commencer la création d’un compte d’exportation cloud](#begin-creating-a-cloud-export-account)

   * Lors de l&#39; [exportation de tables complètes à partir d&#39;Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Dans la section [!UICONTROL **Propriétés du compte**] de la boîte de dialogue [!UICONTROL **Ajouter un compte**], spécifiez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Identifiant de compte**] | Identifie de manière unique un compte de Snowflake au sein de votre organisation, ainsi que dans le réseau global de plateformes cloud et de régions cloud prises en charge par les Snowflake. <p>Vous devez obtenir l’identifiant de compte à partir de votre compte de Snowflake, puis coller les informations ici.</p><p>Pour savoir où obtenir ces informations, consultez la page [ Identifiants de compte dans la documentation du Snowflake ](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **Utilisateur**] | Nom de connexion de l’utilisateur qui sera utilisé pour la connexion. Nous vous recommandons de créer un nouvel utilisateur qui sera utilisé spécifiquement pour Adobe. Indiquez le nom ici, puis créez un utilisateur portant le même nom dans Snowflake. Vous pouvez créer un utilisateur en Snowflake à l’aide de la commande `CREATE USER`.  <p>Pour plus d’informations, voir [Commandes utilisateur, rôle et privilèges](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |
   | [!UICONTROL **Rôle**] | Rôle qui sera attribué à l’utilisateur. Nous vous recommandons de créer un nouveau rôle qui sera utilisé spécifiquement pour l’Adobe. Indiquez le rôle ici, puis créez un rôle dans Snowflake portant le même nom et attribuez-le à l’utilisateur. Vous pouvez créer un rôle dans Snowflake à l’aide de la commande `CREATE ROLE`. <p>Pour plus d’informations, voir [Commandes utilisateur, rôle et privilèges](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**].

   La boîte de dialogue [!UICONTROL **Exporter le compte créé**] s’affiche.

   ![Boîte de dialogue de création de compte d’exportation](assets/export-account-snowflake.png)

1. Copiez le contenu du champ [!UICONTROL **Clé publique**] dans le presse-papiers. La Clé publique est fournie par Adobe.

   Utilisez la clé publique de Snowflake pour vous connecter à votre compte de Snowflake. Vous devez associer l’utilisateur que vous avez créé à cette clé publique.

   Par exemple, en Snowflake, spécifiez la commande suivante :

   ```
   CREATE USER <your_adobe_user> RSA_PUBLIC_KEY = '<your_public_key>';
   ```

   Pour plus d’informations, consultez la page [ Authentification des paires de clés et rotation des paires de clés dans la documentation du Snowflake ](https://docs.snowflake.com/en/user-guide/key-pair-auth).

1. Sélectionnez [!UICONTROL **OK**].

1. Passez à la [configuration des emplacements d’exportation dans le cloud](/help/components/exports/cloud-export-locations.md).
