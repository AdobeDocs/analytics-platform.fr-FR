---
description: Le gestionnaire de mesures calculées vous permet de partager, filtrer, baliser, approuver, copier, supprimer et marquer comme favoris.
title: Gestionnaire de mesures calculées
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: a8d33db669259cef470b8514f244c29148f57561
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 5%

---

# Gestion des mesures calculées

Vous pouvez partager, filtrer, baliser, approuver, renommer, copier, supprimer, exporter des mesures calculées et marquer les mesures calculées comme favorites depuis une interface de gestion centrale de [!UICONTROL mesures calculées]. Pour gérer les mesures calculées :


* Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis **[!UICONTROL Mesures calculées]**.


## Gestionnaire de mesures calculées

Le gestionnaire des mesures calculées comprend les éléments d’interface suivants :


![Interface des filtres](assets/calculated-metrics-manager.png)

### Liste des filtres

La liste des filtres du rapport affiche toutes les mesures calculées que vous possédez ou qui ont été partagées avec vous. La liste contient les colonnes suivantes :

<!-- I think this table incorrectly talks about quick calculated metrics -->

| Colonne | Description |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Sélectionnez pour favoriser ![Star](/help/assets/icons/Star.svg) ou annuler la faveur de ![StarOutline](/help/assets/icons/StarOutline.svg) d’une mesure calculée. Voir [Marquer la mesure calculée comme favorite](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Titre et description]** | Pour modifier la mesure calculée, sélectionnez le lien de titre qui ouvre le [créateur de mesures calculées](cm-build-metrics.md). Une mesure calculée partagée est indiquée avec ![Partager](/help/assets/icons/Share.svg). |
| **[!UICONTROL Vue de données]** | Les vues de données auxquelles cette mesure calculée s’applique. |
| **[!UICONTROL Propriétaire]** | Propriétaire de la mesure calculée. En tant qu’utilisateur, vous ne voyez que les annotations que vous possédez ou les annotations qui sont partagées avec vous. |
| **[!UICONTROL Balises]** | Répertorie les balises de cette mesure calculée. |
| **[!UICONTROL Partagé avec]** | Répertorie le nombre d’individus ou de groupes avec lesquels vous avez partagé la mesure calculée. Sélectionnez cette option pour ouvrir la boîte de dialogue **[!UICONTROL Partager la mesure calculée]**. Pour plus d’informations, voir [Partage des mesures calculées](cm-sharing.md) . |
| **[!UICONTROL Date de modification]** | Date et heure de la dernière modification de la mesure calculée. |
| **[!UICONTROL Utilisé dans]** | Indique l’endroit où les mesures calculées sont actuellement utilisées et le nombre de fois où elles sont utilisées dans chaque zone. <p>Par exemple, si la mesure calculée est utilisée dans 40 projets et 2 alertes, la valeur de cette colonne s’affiche sous la forme [!UICONTROL **42 composants**]. <p>Sélectionnez la valeur de cette colonne pour voir la répartition de l’utilisation des mesures calculées (par exemple, [!UICONTROL **Projets (40)**], [!UICONTROL **Fiches d’évaluation mobiles (2)**]). De plus, vous pouvez afficher la liste des éléments pour lesquels les mesures calculées sont utilisées. Par exemple, pour voir la liste des projets dans lesquels ils sont utilisés, sélectionnez le lien [!UICONTROL **Projets (40)**] .</p><p>Chacune des zones suivantes indique le nombre d’instances de mesures calculées utilisées dans cette zone :</p> <ul><li>[!UICONTROL **Projets**]<p>Contient les mesures calculées [créées dans le créateur de mesures calculées ](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) et disponibles pour tous les projets.</p></li><li>[!UICONTROL **Composants ad hoc**]<p>Contient des mesures calculées [créées en tant que mesures calculées rapides](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) et disponibles uniquement dans un seul projet.</p></li><li>[!UICONTROL **Projets planifiés**]</li><li>[!UICONTROL **Fiches d’évaluation mobiles**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Report Builder**]<p>La sélection de cette option télécharge un fichier CSV, avec les colonnes de données suivantes :</p><ul><li>Nom du Report Builder</li><li>Dernier accès</li><li>Dernier identifiant utilisateur IMS accessible</li><li>Dernier nom d’utilisateur</li></ul></li></ul><p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié.</p><p>Tenez compte des points suivants lorsque vous affichez cette colonne :</p><ul><li>Ces informations sont disponibles uniquement pour les administrateurs système.</li><li>La colonne [!UICONTROL **Utilisé dans**] ne s’affiche pas par défaut. Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour configurer l’affichage de cette colonne.</li><li>Ces informations n’incluent pas l’utilisation de l’API ou du Data Warehouse.</li><li>Si cette colonne ne contient pas de données pour un composant donné mais qu’elle a une date [!UICONTROL **Dernière utilisation**], le composant peut avoir été utilisé dans une analyse sans avoir été enregistré.</li><li>Les informations d’utilisation sont disponibles à partir de septembre 2023.</li></ul><p>Vous pouvez utiliser le [dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md) avec ces informations pour vous aider à suivre et à mieux comprendre comment les composants sont utilisés dans votre organisation.</p> |
| **[!UICONTROL Dernière utilisation]** | Dernière utilisation de la mesure calculée. |

{style="table-layout:auto"}

Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour spécifier les colonnes à afficher.

### Barre d’actions

Vous pouvez agir sur les filtres à l’aide de la barre d’actions de la. La barre d’actions contient les actions suivantes :

| Action | Description |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** | Ajoutez d’autres mesures calculées à l’aide du [créateur de mesures calculées](cm-build-metrics.md). |
| ![Rechercher](/help/assets/icons/Search.svg) [!UICONTROL *Rechercher par titre*] | Lorsqu’aucune mesure calculée n’est sélectionnée dans la liste, recherchez les filtres utilisant ce champ de recherche. |
| ![Libellé](/help/assets/icons/Label.svg) **[!UICONTROL Balise]** | Balisez les mesures calculées sélectionnées. Dans la boîte de dialogue **[!UICONTROL Baliser la mesure calculée]**, sélectionnez ou désélectionnez les balises de la mesure calculée sélectionnée. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les balises des mesures calculées sélectionnées. Pour plus d’informations, voir [Balisage des mesures calculées](cm-tagging.md) . |
| ![Partager](/help/assets/icons/Share.svg) **[!UICONTROL Partager]** | Partagez les mesures calculées sélectionnées. Dans la boîte de dialogue **[!UICONTROL Partager les mesures calculées]**, vous pouvez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des individus ou des groupes* ou sélectionner **[!UICONTROL Organisation]** ou **[!UICONTROL Groupes]**. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les détails du partage pour les mesures calculées sélectionnées. Pour plus d’informations, voir [Partage des mesures calculées](cm-sharing.md) . |
| ![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]** | Supprimer les mesures calculées sélectionnées. Vous êtes invité à faire une confirmation. |
| ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Renommer]** | Renommez une seule mesure calculée sélectionnée. Lorsque cette option est sélectionnée, vous pouvez renommer la mesure calculée intégrée. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Approuvez les mesures calculées sélectionnées. Voir [Approbation des mesures calculées](cm-approving.md). |
| ![Copier](/help/assets/icons/Copy.svg) **[!UICONTROL Copier]** | Copiez les mesures calculées sélectionnées. De nouvelles mesures calculées sont créées avec le même nom et le même suffixe `(Copy)` |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exporter au format CSV]** | Exportez les mesures calculées dans un fichier `Calculated  metric List.csv`. |

### Barre de filtres active

La barre de filtrage affiche les filtres actifs appliqués du panneau à la liste des mesures calculées (le cas échéant). Vous pouvez supprimer rapidement un filtre à l’aide de ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si plusieurs filtres sont spécifiés, vous pouvez les supprimer à l’aide de **[!UICONTROL Tout supprimer]**.

### Panneau Filtrer

Vous pouvez filtrer la liste des mesures calculées à l’aide du panneau de gauche ![Filtre](/help/assets/icons/Filter.svg) **[!UICONTROL Filtre]**. Le panneau Filtre affiche le type de filtre et le nombre de mesures calculées qui respectent le filtre spécifique. Sélectionnez ![Filtre](/help/assets/icons/Filter.svg) pour activer/désactiver l’affichage du panneau de filtrage.

Pour plus d’informations, voir [Filtrage de la liste des mesures calculées](cm-filter.md) .


<!-- OLD CONTENT 

The Calculated metric manager shows you all the filters you own and that have been shared with you. Admin-level users can see all custom metrics in the organization. This overview presents the user interface and the capabilities of the Calculated metric manager.

![Calculated metrics window showing available filters.](assets/calc-metric-manager.png)

## Access the Calculated metrics manager

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Calculated metrics**].

## Available actions in the Calculated metrics manager

In the Calculated metrics manager, you can:

* [Filter calculated metrics](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Approve calculated metrics](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Tag calculated metrics](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Share calculated metrics](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Export a calculated metric to a CSV file. 

* [Copy calculated metrics](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Delete calculated metrics

## Configure columns

You can configure the information displayed for each calculated metric in the Calculated metrics manager by configuring the columns that are displayed.

To configure the visible columns in the Calculated metrics manager:

1. In Customer Journey Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Calculated metrics]**. 

1. In the Calculated metrics manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Calculated metrics manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Favorites  | Displays star icons next to each calculated metric, allowing you to mark calculated metrics as favorites. For more information, see [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Title and description | These values are provided in the Calculated metric builder. To edit the title and description, select the title link to open the Calculated metric builder.  |
   | Report suite | Indicates in which report suite the metric was last saved.  |
   | Owner | Indicates who owns the custom metric. As a non-admin, you can see only metrics you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the metric, either by you or by people who shared the calculated metric with you.  |
   | Shared with | Lists individuals or groups (admin only) or All (admin only) that you shared the calculated metric with. <p>When a calculated metric is being shared, a share icon displays next to the calculated metric name.</p>  |
   | Date modified | Indicates the date when the custom metric was last modified.  |
   | Used in | Shows where calculated metrics are currently being used, and how many times they are being used in each area. <p>For example, if the calculated metric is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**]. <p>Select the value in this column to see the breakdown of where the calculated metrics are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Furthermore, you can view the list of items where the calculated metrics are being used. For example, to see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of calculated metrics being used in that area:</p> <ul><li>[!UICONTROL **Projects**]<p>Contains calculated metrics that were [created in the calculated metric builder](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains calculated metrics that were [created as quick calculated metrics ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a calculated metric includes another calculated metric in its definition, any use of that calculated metric is not shown in the [!UICONTROL **Used in**] column. If a calculated metric is included in the definition of another type of component (such as a filter), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p> |
   | Last used | Shows the date when the calculated metric was last used in any of the following component types: <ul><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, or whether it should be deleted.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |

   {style="table-layout:auto"}

-->