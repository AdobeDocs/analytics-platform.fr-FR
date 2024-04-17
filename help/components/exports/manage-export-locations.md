---
description: Gérer l’emplacement d’exportation dans le cloud où les données du Customer Journey Analytics peuvent être envoyées
keywords: Analysis Workspace
title: Gestion des emplacements et des comptes d’exportation dans le cloud
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
role: User, Admin
source-git-commit: cdf99e31790f089950de8063445b6264158131dd
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 1%

---

# Gestion des emplacements et des comptes d’exportation dans le cloud

Vous pouvez afficher, modifier et supprimer des emplacements d’exportation dans le cloud.

Pour plus d’informations sur la création d’un emplacement, voir [Configuration des emplacements d’exportation cloud](/help/components/exports/cloud-export-locations.md).

## Filtrage et recherche d’emplacements

Pour trouver les informations dont vous avez besoin, vous pouvez filtrer la liste des emplacements ou rechercher un emplacement.

### Filtrer la liste des emplacements

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Emplacements**] .

1. Sélectionnez la variable **Filtrer** Icône

   <!-- add screenshot -->

   Vous pouvez filtrer selon les critères suivants :

   | Filtre | Description |
   |---------|----------|
   | [!UICONTROL **Type d’emplacement**]<!--should this be changed to Account type?--> | Type de compte auquel l’emplacement est associé. Les types de compte suivants peuvent être disponibles : <ul><li>[!UICONTROL **Zone d’entrée des données AEP**]</li><li>[!UICONTROL **APERÇU du rôle Amazon S3**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **Compte**] | Nom du compte auquel l’emplacement est associé. |
   | [!UICONTROL **Créé par**] | Adresse électronique de l’utilisateur qui a créé l’emplacement. |

   {style="table-layout:auto"}

### Recherche d’emplacements

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Emplacements**] .

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer la variable [!UICONTROL **Affichage des emplacements pour tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Dans le champ de recherche, commencez à saisir les informations associées à l’emplacement que vous recherchez. Vous pouvez rechercher des données dans n’importe quelle colonne du tableau.

## Modifier des emplacements

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Emplacements**] .

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer la variable [!UICONTROL **Affichage des emplacements pour tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Sélectionnez l’emplacement à modifier.

   ![Fenêtre Exports affichant l’onglet Emplacements et la liste des emplacements.](assets/locations-edit.png)

1. Sélectionnez [!UICONTROL **Modifier**].

1. Effectuez les modifications souhaitées, puis sélectionnez [!UICONTROL **Enregistrer**].

## Suppression d’emplacements

Si vous supprimez un emplacement, les exportations qui utilisent cet emplacement sont également supprimées. Vérifiez la boîte de dialogue de confirmation lors de la suppression pour vous assurer qu’aucun export n’est associé à l’emplacement.

Pour supprimer un emplacement :

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Emplacements**] .

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer la variable [!UICONTROL **Affichage des emplacements pour tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Sélectionnez un ou plusieurs emplacements à supprimer.

   ![Fenêtre Exports affichant l’onglet Emplacements et la liste des emplacements](assets/locations-edit.png)

1. Sélectionnez [!UICONTROL **Supprimer**].

   La boîte de dialogue Supprimer l’emplacement s’affiche.

1. Dans la boîte de dialogue Supprimer l’emplacement , assurez-vous que l’emplacement n’est associé à aucune exportation avant de confirmer la suppression.

   ![Boîte de dialogue de confirmation de suppression de l’emplacement](assets/delete-location-confirmation-dialog.png)

1. Sélectionner [!UICONTROL **Supprimer**] pour confirmer.

## Modifier des comptes

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Comptes d’emplacement**] .

   ![Fenêtre d’exportation affichant l’onglet Comptes de localisation](assets/account-add.png)

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer la variable [!UICONTROL **Affichage des comptes de tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Sélectionner [!UICONTROL **Afficher les détails**] sur le compte que vous souhaitez modifier.

1. Effectuez les modifications souhaitées, puis sélectionnez [!UICONTROL **Enregistrer**].

## Afficher les clés de compte

Après avoir créé un compte, vous pouvez afficher toutes les clés de compte associées pour ce compte. Vous devrez peut-être consulter ces informations si vous n’avez pas terminé la configuration du compte avec votre fournisseur de cloud. [lorsque vous avez initialement configuré le compte.](/help/components/exports/cloud-export-accounts.md).

Pour visualiser les clés associées à un compte d&#39;export :

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Comptes d’emplacement**] .

   ![Fenêtre d’exportation affichant l’onglet Comptes de localisation](assets/account-add.png)

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer la variable [!UICONTROL **Affichage des comptes de tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Sélectionnez l’icône à 3 points sur le compte que vous souhaitez modifier, puis sélectionnez [!UICONTROL **Clés de compte**].

## Supprimer des comptes

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Comptes d’emplacement**] .

   ![Fenêtre d’exportation affichant l’onglet Comptes de localisation](assets/account-add.png)

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer la variable [!UICONTROL **Affichage des comptes de tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Sélectionnez l’icône à 3 points sur le compte que vous souhaitez modifier, puis sélectionnez [!UICONTROL **Supprimer un compte**].

1. Sélectionner [!UICONTROL **Supprimer**] à nouveau dans la boîte de dialogue de confirmation.
