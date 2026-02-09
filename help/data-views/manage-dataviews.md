---
title: Gérer les vues de données
description: Découvrez comment gérer les vues de données.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: cb5baf2ec8d3ad4449a9b08d0a025a2d39a11425
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 11%

---


# Gestion des vues de données


Une fois que vous avez [créé ou modifié une ou plusieurs vues de données](/help/data-views/create-dataview.md), vous pouvez les gérer dans les **[!UICONTROL vues de données]**.

Sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Vues de données]** dans la barre de menus principale de Customer Journey Analytics.

L’interface **[!UICONTROL Vues de données]** affiche un tableau de toutes les vues de données disponibles.

![Interface des vues de données](/help/data-views/assets/data-views.png)

Les colonnes et icônes suivantes sont disponibles dans le tableau :

| Colonne ou icône | Description |
| --- | --- |
| **[!UICONTROL Nom]** | Nom de la vue de données. |
| ![Informations](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Pour afficher des informations sur la vue de données, sélectionnez ![InfoOutline](/help/assets/icons/InfoOutline.svg) en regard du nom de la vue de données.<br/>Une fenêtre pop-up affiche des détails sur la vue de données. |
| ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Sélectionnez ![Plus](/help/assets/icons/More.svg) pour ouvrir un menu contextuel. Vous pouvez sélectionner :<br/>![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** pour [modifier](#edit-data-views) une vue de données.<br/>![Copier](/help/assets/icons/Copy.svg) **[!UICONTROL Copier]** pour [copier une vue de données](#copy-data-views).<br/>![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]** pour [supprimer](#delete-data-views) une vue de données.<br/>![FichierCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exporter au format CSV]** pour [exporter les détails de la vue de données dans un fichier CSV](#export-data-views-to-csv).<br/>![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Créer un projet]** pour [créer un projet Workspace](#create-project-from-data-views) pour la vue de données. |
| **[!UICONTROL Connexion]** | Nom de la connexion associée à la vue de données. |
| **[!UICONTROL Sandbox]** | Nom du sandbox associé à la vue de données. |
| **[!UICONTROL Propriétaire]** | Propriétaire de la vue de données. |
| **[!UICONTROL Data Insights Agent]** ![InfoOutline](/help/assets/icons/InfoOutline.svg) | Indique si le paramètre [Data Insights Agent](/help/data-analysis-ai.md) est **[!UICONTROL Activé]** ou **[!UICONTROL Désactivé]** pour la vue de données. <br/>Sélectionnez ![InfoOutline](/help/assets/icons/InfoOutline.svg) pour afficher un pop-up avec le statut **[!UICONTROL Data Insights Agent]** dans vos vues de données. <br/>![Utilisation de Data Insights Agent](/help/data-views/assets/data-views-dia-status.png) |
| **[!UICONTROL Intégrations]** | Répertorier les intégrations à d’autres solutions. Par exemple : Adobe Audience Analysis, Content Analytics, Brand Concierge, Journey Optimizer, GenStudio et Usage Analytics. |
| **[!UICONTROL Utiliser dans CJA]** | Indiquez si la vue de données est utilisée dans Customer Journey Analytics. Cette valeur n’est **[!UICONTROL Désactivée]** que pour les vues de données générées automatiquement dans le cadre de l’intégration de Adobe Journey Optimizer. |
| **[!UICONTROL Date de création]** | Date et heure de création de la vue de données. |
| **[!UICONTROL Dernière modification]** | Date et heure de la dernière modification de la vue de données. |

Pour configurer les colonnes à afficher dans le tableau, sélectionnez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). Dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]**, sélectionnez les colonnes à afficher. Sélectionnez ensuite **[!UICONTROL Appliquer]**.


## Rechercher des vues de données

Vous pouvez rechercher rapidement une vue de données à l’aide de la zone Rechercher ![Rechercher](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

## Filtrer les vues de données

Pour appliquer un filtre à la liste des vues de données, sélectionnez l&#39;icône ![Filtrer](/help/assets/icons/Filter.svg) puis choisissez l&#39;une des options de filtre suivantes :

| Option de filtre | Description |
|---------|----------|
| **[!UICONTROL Connexions]** | Seules les vues de données associées aux connexions sélectionnées s’affichent. |
| **[!UICONTROL Propriétaire]** | Seules les vues de données appartenant aux personnes que vous sélectionnez s’affichent. |
| **[!UICONTROL Sandbox]** | Seules les vues de données disponibles dans les sandbox que vous sélectionnez s’affichent. |
| **[!UICONTROL Intégrations]** | Seules les vues de données avec les intégrations sélectionnées s’affichent. |
| **[!UICONTROL Utiliser dans CJA]** | Sélectionnez **[!UICONTROL Activé]** pour afficher uniquement les vues de données activées pour une utilisation avec Customer Journey Analytics. Sélectionnez **[!UICONTROL Désactivé]** pour afficher uniquement les vues de données qui ne sont pas encore activées pour une utilisation avec Customer Journey Analytics. |


## Créer une vue de données

Pour [créer une vue de données](/help/data-views/create-dataview.md), sélectionnez **[!UICONTROL Créer une vue de données]**.


## Modifier les vues de données

Pour [modifier une vue de données](/help/data-views/create-dataview.md) :

1. Sélectionnez ![Plus](/help/assets/icons/More.svg) en regard du nom de la vue de données.
1. Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** dans le menu contextuel.

Vous pouvez également effectuer les opérations suivantes :

1. Sélectionnez la ligne de la vue de données.
1. Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** dans la barre d’action bleue.


## Copier les vues de données

Si vous souhaitez copier une vue de données :

1. Sélectionnez ![Plus](/help/assets/icons/More.svg) en regard du nom de la vue de données.
1. Sélectionnez ![ Copier ](/help/assets/icons/Copy.svg) **[!UICONTROL Copier]** dans le menu contextuel.

Vous pouvez également effectuer les opérations suivantes :

1. Sélectionnez une ou plusieurs lignes de la vue de données.
1. Sélectionnez ![Copier](/help/assets/icons/Copy.svg) **[!UICONTROL Copier]** dans la barre d’actions bleue.

La vue de données est copiée et ajoutée à la liste avec **[!UICONTROL (Copie)]** ajouté au nom.


## Supprimer des vues de données

Si vous souhaitez supprimer une vue de données :

1. Sélectionnez ![Plus](/help/assets/icons/More.svg) en regard du nom de la vue de données.
1. Sélectionnez ![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]** dans le menu contextuel.

Vous pouvez également effectuer les opérations suivantes :

1. Sélectionnez une ou plusieurs lignes de la vue de données.
1. Sélectionnez ![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]** dans la barre d’action bleue.

Lorsque vous supprimez une ou plusieurs vues de données, un panneau **[!UICONTROL Supprimer la vue de données]** indique les projets affectés.

![Supprimer la vue de données](/help/data-views/assets/delete-data-view.png)


* Dans ➊ **[!UICONTROL Confirmation]**, les implications de la suppression des vues de données s’affichent.
* Sélectionnez **[!UICONTROL Supprimer]** pour supprimer définitivement les vues de données. Sélectionnez **[!UICONTROL Annuler]** pour annuler.


## Exporter les vues de données au format CSV

Vous pouvez exporter une vue de données vers un fichier CSV.

1. Sélectionnez ![Plus](/help/assets/icons/More.svg) en regard du nom de la vue de données.
1. Sélectionnez ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** dans le menu contextuel.

Vous pouvez également effectuer les opérations suivantes :

1. Sélectionnez une ou plusieurs lignes de la vue de données.
1. Sélectionnez ![FichierCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exporter au format CSV]** dans la barre d’actions bleue.

Les détails des vues de données sélectionnées sont exportés dans un fichier CSV nommé `Data views List (x).csv` dans le dossier Téléchargements de votre navigateur.


## Créer un projet à partir des vues de données

Vous pouvez créer un projet Workspace directement à partir de l’interface Vues de données .

1. Sélectionnez ![Plus](/help/assets/icons/More.svg) en regard du nom de la vue de données.
1. Sélectionnez ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Créer un projet]** dans le menu contextuel.

Vous pouvez également effectuer les opérations suivantes :

1. Sélectionnez une ligne de la vue de données.
1. Sélectionnez ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Créer un projet]** dans la barre d’actions bleue.


## Activation ou désactivation des vues de données pour Data Insights Agent

Vous pouvez activer ou désactiver une vue de données pour le [Data Insights Agent](/help/data-analysis-ai.md).

1. Sélectionnez ![Plus](/help/assets/icons/More.svg) en regard du nom de la vue de données.
1. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable for Data Insights Agent]** ou ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disable for Data Insights Agent]** dans le menu contextuel.

Vous pouvez également effectuer les opérations suivantes :

1. Sélectionnez une ou plusieurs lignes de la vue de données désactivées ou activées pour le Data Insights Agent.
1. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable for Data Insights Agent]** ou ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disable for Data Insights Agent]** dans la barre d’actions bleue.

