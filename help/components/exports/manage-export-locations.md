---
description: Gérer l’emplacement d’exportation dans le cloud où les données du Customer Journey Analytics peuvent être envoyées
keywords: Analysis Workspace
title: Gestion des emplacements et des comptes d’exportation dans le cloud
feature: Components
hide: true
hidefromtoc: true
source-git-commit: eb7ba8dd7809164bdcddb0d484754376d5b7ca9e
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 6%

---

# Gestion des emplacements et des comptes d’exportation dans le cloud

Vous pouvez afficher, modifier et supprimer des emplacements d’exportation dans le cloud.

Pour plus d’informations sur la création d’un emplacement, voir [Configuration des emplacements d’exportation cloud](/help/components/exports/cloud-export-locations.md).

## Filtrage et recherche d’emplacements

Pour trouver les informations dont vous avez besoin, vous pouvez filtrer la liste des emplacements ou rechercher un emplacement.

### Filtrer la liste des emplacements

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Emplacement**] .

1. Sélectionnez la variable **Filtrer** Icône

   <!-- add screenshot -->

   Vous pouvez filtrer selon les critères suivants :

   | Filtre | Description |
   |---------|----------|
   | [!UICONTROL **Type d’emplacement**]<!--should this be changed to Account type?--> | Type de compte auquel l’emplacement est associé. Les types de compte suivants peuvent être disponibles : <ul><li>[!UICONTROL **Zone d’entrée des données Adobe Experience Platform**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **SAS Azure**]</li><li>[!UICONTROL **RBAC Azure**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **Compte**] | Nom du compte auquel l’emplacement est associé. |
   | [!UICONTROL **Créé par**] | Adresse électronique de l’utilisateur qui a créé l’emplacement. |

   {style="table-layout:auto"}

### Recherche d’emplacements

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Emplacement**] .

1. Dans l’onglet de recherche, commencez à saisir les informations associées à l’emplacement que vous recherchez. Vous pouvez rechercher des données dans n’importe quelle colonne du tableau.

## Modifier des emplacements

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Emplacement**] , puis sélectionnez l’emplacement à modifier.

   <!-- add screenshot? -->

1. Sélectionnez [!UICONTROL **Modifier**].

1. Effectuez les modifications souhaitées, puis sélectionnez [!UICONTROL **Enregistrer**].

## Suppression d’emplacements

Si vous supprimez un emplacement, les exportations qui utilisent cet emplacement sont également supprimées.

Avant de supprimer un emplacement, vérifiez d’abord s’il est utilisé par les exportations en sélectionnant l’icône d’information en regard du nom de l’emplacement.

![exports connectés](assets/location-connected-exports.png)

Pour supprimer un emplacement :

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Emplacement**] , puis sélectionnez un ou plusieurs emplacements à supprimer.

   <!-- add screenshot? -->

1. Sélectionner [!UICONTROL **Supprimer**], puis sélectionnez [!UICONTROL **Supprimer**] à nouveau dans la boîte de dialogue de confirmation.

## Modifier des comptes

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Comptes d’emplacement**] .

   ![Page Comptes](assets/account-page.png)

1. Sélectionner [!UICONTROL **Afficher les détails**] sur le compte que vous souhaitez modifier.

1. Effectuez les modifications souhaitées, puis sélectionnez [!UICONTROL **Enregistrer**].

## Supprimer des comptes

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Comptes d’emplacement**] .

   ![Page Comptes](assets/account-page.png)

1. Sélectionnez l’icône à 3 points sur le compte que vous souhaitez modifier, puis sélectionnez [!UICONTROL **Supprimer un compte**].

1. Sélectionner [!UICONTROL **Supprimer**] à nouveau dans la boîte de dialogue de confirmation.
