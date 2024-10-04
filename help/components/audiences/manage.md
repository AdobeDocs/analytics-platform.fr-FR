---
title: Découvrez comment gérer les audiences créées dans Customer Journey Analytics
description: Apprenez à gérer les audiences dans Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 8676497c9341e3ff74d1b82ca79bc1e73caf514f
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 20%

---

# Gérer des audiences

Les audiences peuvent être gérées en Customer Journey Analytics à l’aide de **[!UICONTROL Composants]** > **[!UICONTROL Audiences]**.

La gestion des audiences créées précédemment permet :

* **Planifier ou déplanifier** l’actualisation/mise à jour automatique de l’audience. L’expiration maximale du planning est d’un an.
* **Renouveler un planning d’actualisation d’audience** sur le point d’expirer. Les audiences arrivant à expiration sont traitées de la même manière que les rapports planifiés arrivant à expiration : l’administrateur ou l’administratrice reçoit un e-mail un mois avant l’expiration du planning.
* Afficher l&#39;**intervalle d&#39;actualisation** et la **dernière fois où une audience a été mise à jour**
* Découvrez le **temps nécessaire pour produire une audience** à partir de Customer Journey Analytics. Et le temps nécessaire pour que l’audience apparaisse dans la plateforme client en temps réel à des fins d’activation.
* Vérifiez si les audiences en Customer Journey Analytics sont **activement utilisées par la plateforme client en temps réel**. Ou (idéalement) toute application Experience Platform qui utilise les audiences créées par Customer Journey Analytics.

Si vous disposez d’un accès [Audience View](/help/technotes/access-control.md#user-level-access), vous pouvez afficher les audiences. Si vous avez accès à [Audience Create](/help/technotes/access-control.md#user-level-access), vous pouvez modifier et supprimer des audiences. La [liste Audiences](#audiences-list) affiche les audiences.

## Liste Audiences

La liste des audiences affiche des colonnes pour les éléments suivants :

| Colonne | Description |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Lorsqu’une ou plusieurs audiences sont sélectionnées, une barre d’actions bleue s’affiche au bas de l’interface Audiences. Voir [Actions](#actions) pour plus d’informations. |
| **[!UICONTROL Titre et description]** | Titre et description que vous avez saisis lors de la création de l’audience. |
| **[!UICONTROL Vue de données]** | Vue de données dans laquelle cette audience a été créée. |
| **[!UICONTROL Taille de l’audience]** | Nombre total de personnes dans cette audience. |
| **[!UICONTROL Propriétaire]** | Propriétaire de l’audience : personne qui a créé l’audience. |
| **[!UICONTROL Fréquence d’actualisation]** | Intervalle d’actualisation configuré lors de la création de l’audience. |
| **[!UICONTROL Balises]** | Toutes les balises qui sont appliquées à cette audience. |
| **[!UICONTROL Statut de publication]** | Peut afficher ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Ready]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL In progress]** ou ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Error]**. |
| **[!UICONTROL Dernière actualisation]** | Horodatage de la dernière actualisation de l’audience. |
| **[!UICONTROL Dernière modification]** | Horodatage de la dernière modification ou de la dernière modification de l’audience. |

Vous pouvez utiliser ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour configurer les colonnes à afficher. Recherchez une audience à l’aide de ![Search](/help/assets/icons/Search.svg).

Pour modifier une audience :

1. Sélectionnez le titre de l’audience. Utilisez la boîte de dialogue **[!UICONTROL Modifier le projet d’audience]** pour mettre à jour l’audience. Voir [Audience Builder](publish.md#audience-builder) pour plus d’informations.

1. Sélectionnez **[!UICONTROL Republier]** pour republier l’audience.


## Actions

Vous trouverez ci-dessous des actions courantes dans le Gestionnaire de projets planifiés. Vous pouvez sélectionner des actions dans le menu contextuel :

| Icône | Action | Description |
|:---:|---|---|
| ![Étiquettes](/help/assets/icons/Labels.svg) | **[!UICONTROL Balise]** | Marquez les audiences sélectionnées. Dans la boîte de dialogue **[!UICONTROL Mettre à jour les balises : *nom de l’audience *]**, sélectionnez des balises dans le menu déroulant ou saisissez une ou plusieurs nouvelles balises. Sélectionnez**[!UICONTROL Enregistrer ]**pour enregistrer. |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimer les audiences sélectionnées. |
| ![Modifier](/help/assets/icons/Edit.svg) | **[!UICONTROL Renommer]** | Renommez l’audience sélectionnée. Utilisez la boîte de dialogue **[!UICONTROL Renommer : *nom de l&#39;audience *]**pour renommer l&#39;audience et sélectionnez**[!UICONTROL Enregistrer ]**pour l&#39;enregistrer. |

Les actions suivantes sont disponibles à partir de la barre d’actions bleue lors de la sélection d’un ou de plusieurs projets planifiés.

| Icône | Action | Description |
|:---:|---|---|
| ![Fermer](/help/assets/icons/Close.svg) | **[!UICONTROL *x *sélectionné]** | Sélectionnez cette option pour désélectionner les audiences sélectionnées. |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimer les audiences sélectionnées. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exporter dans un fichier CSV]** | Exportez les audiences sélectionnées vers un fichier nommé `audiences.csv`. |

## Filtre

Vous pouvez filtrer la [liste d’audiences](#audiences-list) à l’aide du panneau de filtrage. Pour afficher ou masquer le panneau de filtrage, utilisez ![Filter](/help/assets/icons/Filter.svg).

Le panneau Filtre se compose des sections suivantes.

### Vue de données

| Vue de données | Description |
|---|---|
| ![Propriétaires](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | La section **[!UICONTROL Vue des données]** vous permet de filtrer les données selon les vues. <ul><li>Vous utilisez ![Rechercher](/help/assets/icons/Search.svg) pour rechercher les vues de données que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs vues de données.</li></ul> |

### Propriétaires

| Propriétaire | Description |
|---|---|
| ![Propriétaires](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | La section **[!UICONTROL Propriétaire]** vous permet de filtrer les propriétaires. <ul><li>Vous utilisez ![Rechercher](/help/assets/icons/Search.svg) pour rechercher les propriétaires que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs propriétaires. </li></ul> |

## Fréquence d’actualisation

| Fréquence d’actualisation | Description |
|---|---|
| ![Fréquence d’actualisation](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | La section **[!UICONTROL Fréquence d&#39;actualisation]** permet de filtrer selon la fréquence d&#39;actualisation. <ul><li>Vous utilisez ![Rechercher](/help/assets/icons/Search.svg) pour rechercher la fréquence d&#39;actualisation que vous souhaitez utiliser pour filtrer.</li><li>Seules les fréquences d’actualisation définies pour les audiences<br/> dans la [liste d’audiences](#audiences-list) s’affichent sous forme d’options disponibles.</li></ul> |


### Balises

| Balises | Description |
|---|---|
| ![Balises](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | La section **[!UICONTROL Balises]** vous permet de filtrer par balises. <ul><li>Vous utilisez ![Rechercher](/help/assets/icons/Search.svg) pour rechercher les balises que vous souhaitez utiliser pour filtrer. |
