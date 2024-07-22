---
description: Gérer l’emplacement d’exportation dans le cloud où les données du Customer Journey Analytics peuvent être envoyées
keywords: Analysis Workspace
title: Gestion des emplacements et des comptes d’exportation dans le cloud
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
role: User, Admin
source-git-commit: 8fc8e3e4057663bd4bdf38e41bb3129df442f749
workflow-type: tm+mt
source-wordcount: '1370'
ht-degree: 1%

---

# Gestion des emplacements et des comptes d’exportation dans le cloud

Vous pouvez afficher, modifier et supprimer des emplacements d’exportation dans le cloud.

Pour plus d’informations sur la création d’un emplacement, voir [Configuration des emplacements d’exportation dans le cloud](/help/components/exports/cloud-export-locations.md).

## Filtrage et recherche d’emplacements

Pour trouver les informations dont vous avez besoin, vous pouvez filtrer la liste des emplacements ou rechercher un emplacement.

### Filtrer la liste des emplacements

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Emplacements**] .

1. Sélectionnez l&#39;icône **Filtre** .

   <!-- add screenshot -->

   Vous pouvez filtrer selon les critères suivants :

   | Filtre | Description |
   |---------|----------|
   | [!UICONTROL **Type d’emplacement**]<!--should this be changed to Account type?--> | Type de compte auquel l’emplacement est associé. Les types de compte suivants peuvent être disponibles : <ul><li>[!UICONTROL **Zone d’entrée de données AEP**]</li><li>[!UICONTROL **{Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Plateforme cloud Google**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **Compte**] | Nom du compte auquel l’emplacement est associé. |
   | [!UICONTROL **Créé par**] | Adresse électronique de l’utilisateur qui a créé l’emplacement. |

   {style="table-layout:auto"}

### Recherche d’emplacements

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Emplacements**] .

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer l’option [!UICONTROL **Afficher les emplacements pour tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Dans le champ de recherche, commencez à saisir les informations associées à l’emplacement que vous recherchez. Vous pouvez rechercher des données dans n’importe quelle colonne du tableau.

## Modifier des emplacements

Un emplacement ne peut être modifié que par l’utilisateur qui l’a créé ou par un administrateur système.

Pour modifier un emplacement :

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Emplacements**] .

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer l’option [!UICONTROL **Afficher les emplacements pour tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Sélectionnez l’emplacement à modifier.

   ![Fenêtre d&#39;exports affichant l&#39;onglet Emplacements et la liste des emplacements.](assets/locations-edit.png)

1. Sélectionnez [!UICONTROL **Modifier**].

1. Apportez les modifications souhaitées, puis sélectionnez [!UICONTROL **Enregistrer**].

## Suppression d’emplacements

Si vous supprimez un emplacement, les exportations qui utilisent cet emplacement sont également supprimées. Vérifiez la boîte de dialogue de confirmation lors de la suppression pour vous assurer qu’aucun export n’est associé à l’emplacement.

Pour supprimer un emplacement :

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Emplacements**] .

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer l’option [!UICONTROL **Afficher les emplacements pour tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Sélectionnez un ou plusieurs emplacements à supprimer.

   ![Fenêtre Exportations affichant l’onglet Emplacements et la liste des emplacements](assets/locations-edit.png)

1. Sélectionnez [!UICONTROL **Supprimer**].

   La boîte de dialogue Supprimer l’emplacement s’affiche.

1. Dans la boîte de dialogue Supprimer l’emplacement , assurez-vous que l’emplacement n’est associé à aucune exportation avant de confirmer la suppression.

   ![Boîte de dialogue de confirmation de suppression de l’emplacement](assets/delete-location-confirmation-dialog.png)

1. Sélectionnez à nouveau [!UICONTROL **Supprimer**] pour confirmer.

## Modifier des comptes

Un compte ne peut être modifié que par l’utilisateur qui l’a créé ou par un administrateur système.

Pour modifier un compte :

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Comptes de localisation**] .

   ![ Fenêtre d’exportation affichant l’onglet Comptes de localisation](assets/account-add.png)

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer l’option [!UICONTROL **Afficher les comptes de tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Sélectionnez [!UICONTROL **Afficher les détails**] sur le compte que vous souhaitez modifier.

1. Apportez les modifications souhaitées, puis sélectionnez [!UICONTROL **Enregistrer**].

## Afficher les clés de compte

Après avoir créé un compte, vous pouvez afficher toutes les clés de compte associées pour ce compte. Vous devrez peut-être afficher ces informations si vous n’avez pas terminé la configuration du compte avec votre fournisseur de cloud [ lors de la configuration initiale du compte](/help/components/exports/cloud-export-accounts.md).

Pour visualiser les clés associées à un compte d&#39;export :

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Comptes de localisation**] .

   ![ Fenêtre d’exportation affichant l’onglet Comptes de localisation](assets/account-add.png)

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer l’option [!UICONTROL **Afficher les comptes de tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Sélectionnez l’icône à 3 points sur le compte que vous souhaitez modifier, puis sélectionnez [!UICONTROL **Clés de compte**].

## Supprimer des comptes

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Comptes de localisation**] .

   ![ Fenêtre d’exportation affichant l’onglet Comptes de localisation](assets/account-add.png)

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer l’option [!UICONTROL **Afficher les comptes de tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Sélectionnez l’icône à 3 points sur le compte que vous souhaitez modifier, puis sélectionnez [!UICONTROL **Supprimer le compte**].

1. Sélectionnez à nouveau [!UICONTROL **Supprimer**] dans la boîte de dialogue de confirmation.

## Configuration des paramètres à l’échelle de l’entreprise (administrateurs uniquement)

Les administrateurs système peuvent empêcher les utilisateurs de créer des comptes et des emplacements ou limiter les types de comptes que les utilisateurs peuvent créer et utiliser.

![Onglet Paramètres d’administration](assets/locations-admin-settings.png)

### Configuration de la création et de la modification de comptes par les utilisateurs

Par défaut, tous les utilisateurs de l’organisation peuvent créer des comptes et modifier les comptes qu’ils créent dans votre environnement de Customer Journey Analytics, comme décrit dans la section [Configuration des comptes d’exportation cloud](/help/components/exports/cloud-export-accounts.md).

Vous pouvez empêcher les utilisateurs de créer des comptes. Lorsque vous le faites, les utilisateurs peuvent toujours utiliser les comptes qu’ils ont déjà créés, mais ils ne peuvent plus les modifier. Vous pouvez supprimer les comptes créés par les utilisateurs, comme décrit dans la section [Suppression d’un compte](#delete-an-account).

Pour empêcher tous les utilisateurs de créer et de modifier des comptes :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Exports]**, puis sélectionnez l’onglet [!UICONTROL **Paramètres d’administration**].

1. Dans la section [!UICONTROL **Comptes d’emplacements**], désélectionnez l’option [!UICONTROL **Autoriser les utilisateurs à créer et gérer des comptes d’emplacement**].

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. (Facultatif) Supprimez tous les comptes que les utilisateurs ont créés et que vous ne souhaitez plus utiliser, comme décrit dans la section [Suppression d’un compte](#delete-an-account).

### Configurer si les utilisateurs peuvent créer et modifier des emplacements

Par défaut, tous les utilisateurs de l’entreprise peuvent créer des emplacements et modifier les emplacements qu’ils créent dans votre environnement de Customer Journey Analytics, comme décrit dans la section [configuration des emplacements d’exportation dans le cloud](/help/components/exports/cloud-export-locations.md).

Vous pouvez empêcher les utilisateurs de créer des emplacements. Dans ce cas, les utilisateurs peuvent toujours utiliser les emplacements qu’ils ont déjà créés, mais ils ne peuvent plus les modifier. Vous pouvez supprimer les emplacements créés par les utilisateurs, comme décrit dans [Supprimer les emplacements](#delete-a-location).

Pour empêcher tous les utilisateurs de créer et de modifier des emplacements :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Rapports]**, puis sélectionnez l’onglet [!UICONTROL **Paramètres d’administration**].

1. Dans la section [!UICONTROL **Emplacements**], désélectionnez l’option [!UICONTROL **Autoriser les utilisateurs à créer et gérer des emplacements**].

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. (Facultatif) Supprimez tous les emplacements que les utilisateurs ont créés et que vous ne souhaitez plus utiliser, comme décrit dans la section [Suppression d’un emplacement](#delete-a-location).

### Limitation des types de comptes que les utilisateurs peuvent créer et utiliser

Vous pouvez limiter les types de compte que les utilisateurs voient dans les cas suivants :

* Lors de la [création de nouveaux comptes](/help/components/exports/cloud-export-accounts.md).
* Lors du choix des comptes à utiliser lors de l&#39;export de fichiers à l&#39;aide de [l&#39;export de table complète](/help/analysis-workspace/export/export-cloud.md).

Lorsque vous limitez les types de compte comme décrit dans cette section, les comptes du type que vous limitez ne sont plus visibles par les utilisateurs. Cela signifie qu&#39;il n&#39;est pas possible de créer de nouveaux comptes de ce type et que les comptes existants de ce type ne peuvent pas être utilisés lors de l&#39;export de fichiers à l&#39;aide de l&#39;export de table complet.

Toutefois, les comptes existants configurés pour les exportations planifiées doivent être supprimés si vous souhaitez empêcher leur utilisation.

#### S’assurer que les comptes ne sont pas utilisés pour les exportations planifiées

Lorsque vous limitez les types de compte, les comptes existants sont masqués et non supprimés.

Si des plannings sont déjà configurés pour envoyer des données à un compte du type que vous limitez, les plannings continueront à s’exécuter même après avoir limité le type de compte et les données continueront à être envoyées au compte. Par exemple, si un export de table complet est programmé pour envoyer des données vers un type de compte que vous limitez, le planning continuera à fonctionner.

Si vous devez vous assurer que les comptes d’un certain type ne sont pas utilisés dans les exportations planifiées, vous pouvez supprimer les comptes avant de [limiter les types de compte](#limit-the-account-types-that-are-available-to-users).

Pour supprimer des comptes :

1. Localisez les comptes du type de compte que vous prévoyez de limiter et qui sont utilisés pour les exportations planifiées.

1. Supprimez les comptes, comme décrit dans la section [Suppression d&#39;un compte](#delete-an-account).

1. Passez à la section suivante, [Limitez les types de compte disponibles pour les utilisateurs](#limit-the-account-types-that-are-available-to-users).

#### Limitation des types de compte disponibles pour les utilisateurs

Pour limiter les types de compte disponibles pour les utilisateurs lors de la création et de l’utilisation de comptes :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Exports]**, puis sélectionnez l’onglet [!UICONTROL **Paramètres d’administration**].

1. Recherchez la section [!UICONTROL **Types de compte autorisé**] .

   Par défaut, les types de compte suivants sont disponibles pour les utilisateurs. Désélectionnez l’un de ces types de compte que vous souhaitez empêcher l’utilisation des utilisateurs.

   * [!UICONTROL **Zone d’entrée de données AEP**]

   * [!UICONTROL **{Amazon S3 Role ARN**]

   * [!UICONTROL **Plateforme cloud Google**]

   * [!UICONTROL **Azure SAS**]

   * [!UICONTROL **Azure RBAC**]

   * [!UICONTROL **Snowflake**]

1. Sélectionnez [!UICONTROL **Enregistrer**].
