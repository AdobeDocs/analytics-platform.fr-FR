---
title: Apprendre à gérer les audiences créées dans Customer Journey Analytics
description: Apprenez à gérer les audiences dans Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 76%

---

# Gérer des audiences

Les audiences peuvent être gérées dans Customer Journey Analytics en utilisant **[!UICONTROL Composants]** > **[!UICONTROL Audiences]**.

## Comprendre les tâches de gestion des audiences

La gestion des audiences créées précédemment permet d’effectuer les opérations suivantes :

* **Planifier ou déplanifier** l’actualisation/mise à jour automatique de l’audience. L’expiration maximale du planning est d’un an.
* **Renouveler un planning d’actualisation d’audience** sur le point d’expirer. Les audiences arrivant à expiration sont traitées de la même manière que les rapports planifiés arrivant à expiration : l’administrateur ou l’administratrice reçoit un e-mail un mois avant l’expiration du planning.
* Afficher l’**intervalle d’actualisation** et la **dernière fois qu’une audience a été mise à jour**.
* Obtenez des informations sur le **temps nécessaire à la production d’une audience** de Customer Journey Analytics. Et le temps nécessaire pour que l’audience apparaisse dans Real-time Customer Platform à des fins d’activation.
* Vérifiez si les audiences dans Customer Journey Analytics sont **utilisées activement par Real-time Customer Platform**. Ou (idéalement) toute application Experience Platform qui utilise les audiences créées par Customer Journey Analytics.

Si vous disposez d’un accès [Affichage de l’audience](/help/technotes/access-control.md#user-level-access), vous pouvez afficher les audiences. Si vous disposez d’un accès [Création d’audience](/help/technotes/access-control.md#user-level-access), vous pouvez modifier et supprimer des audiences.

## Affichage des audiences dans la liste Audiences

La liste Audiences affiche ➊ les audiences existantes.

![Gestionnaire d’audiences](assets/audiences-manager.png)

Pour afficher la liste Audience :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Audiences]**.

1. (Facultatif) Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour configurer les colonnes à afficher.

1. (Facultatif) Recherchez une audience à l’aide de ![Rechercher](/help/assets/icons/Search.svg).

   Les colonnes suivantes sont disponibles avec des informations sur chaque audience :

   | Colonne | Description |
   | --- | --- |
   | ![SelectBox](/help/assets/icons/SelectBox.svg) | Lorsqu’une ou plusieurs audiences sont sélectionnées, une barre d’actions bleue s’affiche au bas de l’interface Audiences. Pour plus de détails, consultez [Actions](#actions). |
   | **[!UICONTROL Titre et description]** | Titre et description saisis lors de la création de l’audience. |
   | **[!UICONTROL Vue de données]** | Vue de données dans laquelle cette audience a été créée. |
   | **[!UICONTROL Taille de l’audience]** | Nombre total de personnes dans cette audience. |
   | **[!UICONTROL Propriétaire]** | Propriétaire de l’audience : personne qui l’a créée. |
   | **[!UICONTROL Fréquence d’actualisation]** | Intervalle d’actualisation qui a été configuré lors de la création de l’audience. |
   | **[!UICONTROL Balises]** | Toutes les balises qui sont appliquées à cette audience. |
   | **[!UICONTROL Statut de publication]** | Peut afficher ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Prêt]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL En cours]** ou ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Erreur]**. |
   | **[!UICONTROL Dernière actualisation]** | Horodatage de la dernière actualisation de l’audience. |
   | **[!UICONTROL Dernière modification]** | Horodatage de la dernière édition ou modification de l’audience. |

## Modifier les audiences

Vous pouvez modifier les paramètres d’une audience à tout moment. Lorsque vous modifiez une audience (une audience unique ou récurrente), une republication est requise.

Pour modifier une audience, procédez comme suit :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Audiences]**.

   La page Audiences s’affiche.

1. Sélectionnez le titre de l’audience à modifier.

   La boîte de dialogue **[!UICONTROL Modifier l’audience]** s’affiche.

1. Vous pouvez mettre à jour n’importe quel champ disponible pour l’audience. Pour plus d’informations sur les champs que vous pouvez mettre à jour, voir [Créateur d’audiences](/help/components/audiences/publish.md#audience-builder) dans l’article [Création et publication d’audiences](/help/components/audiences/publish.md).

1. Sélectionnez **[!UICONTROL Republier]**.

## Actions

Voici des actions courantes du gestionnaire de projets planifiés : Vous pouvez sélectionner des actions dans le menu contextuel :

| Icône | Action | Description |
|:---:|---|---|
| ![Étiquettes](/help/assets/icons/Labels.svg) | **[!UICONTROL Étiquette]** | Balisez les audiences sélectionnées. Dans la boîte de dialogue **[!UICONTROL Mettre à jour les balises : *nom de l’audience *]**, sélectionnez des balises dans le menu déroulant ou saisissez une ou plusieurs nouvelles balises. Sélectionnez**[!UICONTROL Enregistrer ]**pour enregistrer. |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimez l’audience sélectionnée. |
| ![Modifier](/help/assets/icons/Edit.svg) | **[!UICONTROL Renommer]** | Renommez l’audience sélectionnée. Utilisez la boîte de dialogue **[!UICONTROL Renommer : *nom de l’audience *]**pour renommer l’audience et sélectionnez**[!UICONTROL Enregistrer ]**pour enregistrer. |

Les actions suivantes sont disponibles à partir de la barre d’actions bleue lors de la sélection d’un ou de plusieurs projets planifiés.

| Icône | Action | Description |
|:---:|---|---|
| ![Fermer](/help/assets/icons/Close.svg) | **[!UICONTROL *x *sélectionné]** | Sélectionnez pour désélectionner les audiences sélectionnées. |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimez l’audience sélectionnée. |
| ![Fichier CSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exporter dans un fichier CSV]** | Exportez les audiences sélectionnées dans un fichier nommé `audiences.csv`. |

## Filtrer la liste des audiences

Vous pouvez filtrer la [liste des audiences](#audiences-list) à l’aide du panneau Filtrer ➋. Pour afficher ou masquer le panneau Filtrer, utilisez ![Filtrer](/help/assets/icons/Filter.svg).

![Gestionnaire d’audiences](assets/audiences-manager.png)

Le panneau Filtrer se compose des sections suivantes.

### Vue de données

| Vue de données | Description |
|---|---|
| ![Propriétaires](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | La section **[!UICONTROL Vue de données]** vous permet de filtrer les vues de données. <ul><li>Utilisez la fonction ![Rechercher](/help/assets/icons/Search.svg) pour rechercher les vues de données à utiliser pour le filtrage.</li><li>Vous pouvez sélectionner plusieurs vues de données.</li></ul> |

### Propriétaires

| Propriétaire | Description |
|---|---|
| ![Propriétaires](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | La section **[!UICONTROL Propriétaire]** vous permet de filtrer les propriétaires. <ul><li>Vous utilisez ![Rechercher](/help/assets/icons/Search.svg) pour rechercher les propriétaires que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs propriétaires. </li></ul> |

## Fréquence d’actualisation

| Fréquence d’actualisation | Description |
|---|---|
| ![Fréquence d’actualisation](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | La section **[!UICONTROL Fréquence d’actualisation]** permet de filtrer selon la fréquence d’actualisation. <ul><li>Utilisez ![Rechercher](/help/assets/icons/Search.svg) pour rechercher la fréquence d’actualisation à utiliser pour le filtrage.</li><li>Seules les fréquences d’actualisation définies pour les audiences<br/> dans la [liste des audiences](#audiences-list) s’affichent comme des options disponibles.</li></ul> |


### Balises

| Balises | Description |
|---|---|
| ![Étiquettes](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | La section **[!UICONTROL Balises]** permet de filtrer par balise. <ul><li>Utilisez la fonction ![Rechercher](/help/assets/icons/Search.svg) pour rechercher les balises à utiliser pour le filtrage. |
