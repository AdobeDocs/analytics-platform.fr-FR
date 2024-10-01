---
title: Gestion des périodes
description: Partagez, renommez ou supprimez des périodes dans Analysis Workspace.
feature: Calendar
exl-id: 694758c4-d740-4fd7-9fb0-3ff7f6b25a3d
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 9%

---

# Gestion des périodes


Vous pouvez partager, filtrer, baliser, approuver, copier, partager et supprimer des plages de dates et marquer des plages de dates comme favorites depuis une interface de gestion [!UICONTROL  centrale des plages de dates]. Pour gérer les plages de dates :

* Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis **[!UICONTROL Plages de dates]**.


## Gestionnaire de plages de dates

Le gestionnaire de plages de dates comprend les éléments d’interface suivants :

![Interface des plages de dates](assets/date-ranges-manager.png)

### Liste des plages de dates

La liste des plages de dates affiche toutes les plages de dates. La liste contient les colonnes suivantes :

| Colonne | Description |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Sélectionnez pour favoriser ![Star](/help/assets/icons/Star.svg) ou pour annuler ![StarOutline](/help/assets/icons/StarOutline.svg) une période. |
| **[!UICONTROL Titre et description]** | Pour modifier le titre et la description, sélectionnez le lien du titre, qui ouvre le [créateur de plages de dates](/help/components/date-ranges/create.md#date-range-builder). |
| **[!UICONTROL Propriétaire]** | Propriétaire de la période. |
| **[!UICONTROL Balises]** | Les balises pour cette période. |
| **[!UICONTROL Partagé avec]** | Les individus ou les groupes avec lesquels vous avez partagé la période. Sélectionnez cette option pour ouvrir la boîte de dialogue **[!UICONTROL Partager la plage de dates]**. |
| **[!UICONTROL Date de modification]** | Affiche la date et l’heure de la dernière modification de la période. |

{style="table-layout:auto"}

Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour spécifier les colonnes à afficher.

### Barre d’actions

Vous pouvez agir sur les plages de dates à l’aide de la barre d’actions. La barre d’actions contient les actions suivantes :

| Action | Description |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** | Ajoutez une autre plage de dates à l’aide du [créateur de plages de dates](create.md#date-range-builder). |
| ![Rechercher](/help/assets/icons/Search.svg) [!UICONTROL *Rechercher par titre*] | Lorsqu’aucune période n’est sélectionnée dans la liste, recherchez des périodes à l’aide de ce champ de recherche. |
| ![Libellé](/help/assets/icons/Label.svg) **[!UICONTROL Balise]** | Balisez les plages de dates sélectionnées. Dans la boîte de dialogue **[!UICONTROL Baliser la plage de dates]**, sélectionnez ou désélectionnez les balises pour les plages de dates sélectionnées. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les balises pour les périodes sélectionnées. |
| ![Partager](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Partager]** | Partagez les périodes sélectionnées. Dans la boîte de dialogue **[!UICONTROL Partager la plage de dates]**, vous pouvez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des individus ou des groupes* ou sélectionner **[!UICONTROL Organisation]** ou **[!UICONTROL Groupes]**. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les détails du partage pour les périodes sélectionnées. |
| ![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]** | Supprimer les périodes sélectionnées. Vous êtes invité à faire une confirmation. |
| ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Renommer]** | Renommez une seule période sélectionnée. Lorsque cette option est sélectionnée, vous pouvez renommer la période intégrée. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Approuvez les périodes sélectionnées. |
| ![Copier](/help/assets/icons/Copy.svg) **[!UICONTROL Copier]** | Copiez les périodes sélectionnées. De nouvelles plages de dates sont créées avec le même nom et le même suffixe (Copier). |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exporter au format CSV]** | Exportez les plages de dates sélectionnées vers un fichier `Date ranges List.csv`. |

### Barre de filtres active

La barre de filtre affiche les filtres actifs (le cas échéant). Vous pouvez supprimer rapidement un filtre à l’aide de ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si plusieurs filtres sont spécifiés, utilisez **[!UICONTROL Tout supprimer]** pour supprimer tous les filtres.

### Panneau Filtrer

Vous pouvez filtrer les périodes à l’aide du panneau de gauche **[!UICONTROL Filtre]** . Le panneau de filtrage affiche le type de filtre et le nombre de plages de dates qui respectent le filtre. Sélectionnez ![Filtre](/help/assets/icons/Filter.svg) pour activer/désactiver l’affichage du panneau de filtrage.

Pour filtrer la liste des filtres :

1. Sélectionnez ![Filter](/help/assets/icons/Filter.svg) pour ouvrir le panneau Filtres. Si vous avez besoin d’espace supplémentaire pour la liste Filtres, vous pouvez sélectionner à nouveau ![Filtre](/help/assets/icons/Filter.svg) pour fermer le panneau.
1. Vous pouvez filtrer les plages de dates à l’aide des [sections de filtrage](#filter-sections) disponibles.

   >[!INFO]
   >
   >*Les éléments* se rapportent aux éléments de la période affichés dans la [liste de plages de dates](#date-ranges-list).
   > 

#### Filtrage des sections

{{tagfiltersection}}
{{ownerfiltersection}}
{{otherfiltersfiltersection}}


La [liste des plages de dates](#date-ranges-list) est automatiquement mise à jour en fonction de la configuration de votre filtre. Vous pouvez voir les filtres configurés dans la [barre de filtres actifs](#active-filter-bar).


## Modification des plages de dates

Vous pouvez modifier une période de deux manières différentes :

* Dans un projet Workspace, utilisez l’icône [Informations sur le composant](/help/components/use-components-in-workspace.md#component-info).

* Dans la liste [[!UICONTROL Plages de dates]](#date-ranges-list), sélectionnez le titre de la plage de dates.

Vous utilisez le [créateur de plages de dates](/help/components/date-ranges/create.md#date-range-builder) pour modifier la plage de dates.




Utilisez le gestionnaire de périodes pour partager, renommer ou supprimer des périodes. Pour accéder au gestionnaire de dates :

1. Connectez-vous à [analytics.adobe.com](https://analytics.adobe.com) à lʼaide de vos identifiants Adobe ID.
1. Accédez à [!UICONTROL Composants] > [!UICONTROL Périodes].


<!--

## Interface

![Date Ranges with Example range highlighted.](../assets/date-range-ui.png)

The date range manager includes the following options:

* **Add**: Create a new date range. See [create a date range](create.md) for more information.
* **Search by title**: Search for a date range by title. Results are filtered based on text entered here.
* **Filter**: Filter date ranges using the left column. You can filter by custom tag, owner, created by you, your favorites, approved, or shared with you. You can also search for desired filters.
* **Favorite**: Click the ![star](../assets/star.png) icon next to a date range to add it to your favorites.
* **Customize columns**: Click the ![columns](../assets/columns.png) icon to show or hide columns in the date range manager.

Click the checkbox next to one or more date ranges for more options.

* **Tag**: Apply a tag to all selected date ranges. Tags help you organize date ranges, and let you filter them using the left column.
* **Share**: Share a date range to other Experience Cloud users. If you are a product administrator, you can also share to the entire organization or groups. Date ranges that are shared to other users in your organization include a ![shared](../assets/shared.png) icon next to the title.
* **Delete**: Permanently delete the selected date range(s).
* **Rename**: If a single date range is selected, you can change its title.
* **Approve**: If you are a product admin, you can add a stamp of approval to a date range. Approved date ranges inform users in your organization that they are 'official', differentiating them from date ranges created by other users in your organization. Approved date ranges include a ![approved](../assets/approved.png) icon next to the title.
* **Unapprove**: If you are a product admin and select a date range that is already approved, you can unapprove it.
* **Copy**: Create a copy of the selected date range(s). Copying date ranges appends `(Copy)` to the end of the title of the newly copied date range(s).
* **Export to CSV**: Exports all selected date ranges into a CSV file. Columns in the resulting CSV file include all visible columns in the date range manager.
-->