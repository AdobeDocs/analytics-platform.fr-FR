---
description: Configuration du compte d’exportation cloud où les données de Customer Journey Analytics peuvent être envoyées
keywords: Analysis Workspace
title: Configuration des comptes d’exportation cloud
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '1289'
ht-degree: 5%

---

# Configuration des comptes d’exportation cloud

{{select-package}}

Avant de pouvoir exporter des données Customer Journey Analytics vers une destination cloud comme décrit dans [Exportation des données de Customer Journey Analytics dans le cloud](/help/analysis-workspace/export/export-cloud.md), vous devez ajouter et configurer l’emplacement où vous souhaitez que les données soient envoyées.

Ce processus consiste à ajouter et configurer le compte (par exemple, Amazon S3, Google Cloud Platform, etc.) comme décrit dans cet article, puis à ajouter et configurer l’emplacement dans ce compte (par exemple, un dossier dans le compte) comme décrit dans la section [Configuration des emplacements d’exportation cloud](/help/components/exports/cloud-export-locations.md).

Pour plus d’informations sur la gestion des comptes existants, notamment l’affichage, la modification et la suppression de comptes, voir [Gestion des emplacements et des comptes d’exportation dans le cloud](/help/components/exports/manage-export-locations.md).

Vous devez configurer Customer Journey Analytics avec les informations nécessaires pour accéder à votre compte de destination cloud.

Pour configurer un compte d’exportation cloud :

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].
1. Sur le [!UICONTROL Exportations] , sélectionnez [!UICONTROL **Comptes d’emplacement**] .
1. Sélectionner [!UICONTROL **Ajouter un compte**].

   ![Ajouter un compte](assets/account-add.png)

   La boîte de dialogue Ajouter un compte s’affiche.
1. Indiquez les informations suivantes : |Field | Fonction | |—|—| | [!UICONTROL **Nom du compte d’emplacement**] | Nom du compte de l’emplacement. Ce nom apparaît lors de la création d’un emplacement. | | [!UICONTROL **Description du compte d’emplacement**] | Fournissez une brève description du compte pour le différencier des autres comptes du même type de compte. | | [!UICONTROL **Type de compte**] | Sélectionnez le type de compte cloud vers lequel vous exportez. Les types de compte disponibles sont Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake et Adobe Experience Platform. |
1. Dans le [!UICONTROL **Propriétés du compte**] , indiquez les informations spécifiques au type de compte sélectionné.

   Pour obtenir des instructions sur la configuration, développez la section ci-dessous qui correspond à la variable [!UICONTROL **Type de compte**] que vous avez sélectionné.

   +++Amazon S3 Role ARN

   Indiquez les informations suivantes pour configurer un compte RGPD de rôle Amazon S3 :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **ARN du rôle**] | Vous devez fournir un Rôle ARN (nom de ressource Amazon) que l’Adobe peut utiliser pour accéder au compte Amazon S3. Pour ce faire, vous créez une stratégie d’autorisation IAM pour le compte source, vous la joignez à un utilisateur, puis vous créez un rôle pour le compte de destination. Pour plus d’informations, voir [cette documentation AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
   | [!UICONTROL **ARN de l’utilisateur ou de l’utilisatrice**] | Le User ARN (nom de ressource Amazon) est fourni par Adobe. Vous devez associer cet utilisateur à la stratégie que vous avez créée. |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Indiquez les informations suivantes pour configurer un compte Google Cloud Platform :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Identifiant du projet**] | Identifiant de projet Google Cloud que vous copiez depuis votre compte Google Cloud. Voir [Documentation de Google Cloud sur l’obtention d’un ID de projet](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |
   | [!UICONTROL **Principal**] | L’entité de sécurité est fournie par Adobe. Cliquez sur le bouton [!UICONTROL **Copier**] en regard de l’icône [!UICONTROL **Principal**] pour copier le contenu du champ, puis assurez-vous que vous accordez l’autorisation à l’entité de sécurité de charger les fichiers dans ce compartiment dans Google Cloud Platform. <!-- add link to Google Cloud docs on how to do this --> |

   {style="table-layout:auto"}

+++

   +++SAS Azure

   Indiquez les informations suivantes pour configurer un compte Azure SAS :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **ID d’application**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID de cliente ou client**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI du coffre de clés**] | <p>Chemin d’accès au jeton SAS dans Azure Key Vault.  Pour configurer Azure SAS, vous devez stocker un jeton SAS en tant que secret à l’aide du Key Vault Azure. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Une fois l’URI de coffre-fort de clé créé, ajoutez une stratégie d’accès à Key Vault afin d’accorder l’autorisation sur l’application Azure que vous avez créée. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’affectation d’une stratégie d’accès Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nom secret du coffre de clés**] | Le nom du secret que vous avez créé lors de l’ajout du secret au Key Vault Azure. Dans Microsoft Azure, ces informations se trouvent dans le Key Vault que vous avez créé, sur la page **Key Vault** des pages de paramètres. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Clé du compte d’emplacement**] | Copiez le secret de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

+++

   +++RBAC Azure

   Indiquez les informations suivantes pour configurer un compte Azure RBAC :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **ID d’application**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID de cliente ou client**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Clé du compte d’emplacement**] | Copiez le secret de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Snowflake

   Indiquez les informations suivantes pour configurer un compte de Snowflake :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Identifiant du compte**] | Identifie de manière unique un compte de Snowflake au sein de votre organisation, ainsi que dans le réseau global de plateformes cloud et de régions cloud prises en charge par les Snowflake. <p>Pour plus d’informations, voir [Page Identifiants de compte dans la documentation du Snowflake](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **Utilisateur**] | Indique le nom de connexion de l’utilisateur pour la connexion. Il s’agit d’un utilisateur qui sera utilisé spécifiquement pour l’Adobe. Vous pouvez créer l’utilisateur dans Snowflake après y avoir spécifié son nom d’utilisateur. <p>Pour plus d’informations, voir [Page de référence des paramètres de connexion du pilote JDBC dans la documentation du Snowflake](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Rôle**] | Rôle de contrôle d’accès par défaut à utiliser dans la session du Snowflake initiée par le pilote. Vous devez créer un rôle spécifique à l’Adobe disposant d’un accès en lecture et en écriture.<p>Pour plus d’informations, voir [Page de référence des paramètres de connexion du pilote JDBC dans la documentation du Snowflake](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Clé publique**] | La Clé publique est fournie par Adobe. Cliquez sur l’icône Copier en regard de l’option [!UICONTROL **Clé publique**] pour copier le contenu du champ, puis utilisez la clé publique dans votre compte de Snowflake. Pour plus d’informations, voir [Authentification des paires de clés et rotation des paires de clés dans la documentation du Snowflake](https://docs.snowflake.com/en/user-guide/key-pair-auth). |

+++

   +++Adobe Experience Platform

   Tous les clients Adobe Experience Platform peuvent exporter des données vers la zone d’entrée AEP.

   Indiquez les informations suivantes pour configurer un compte Adobe Experience Platform.

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Identifiant de l’organisation IMS**] | L’identifiant de l’organisation IMS est fourni par Adobe. Cliquez sur l’icône Copier en regard de l’option [!UICONTROL **Identifiant de l’organisation IMS**] pour copier le contenu du champ, puis utilisez l’identifiant dans votre compte Adobe Experience Platform. |

+++

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Passez à la [Configuration des emplacements d’exportation cloud](/help/components/exports/cloud-export-locations.md).

