---
description: Découvrez comment travailler avec des projets dans Analysis Workspace. Utilisez le gestionnaire de projets pour gérer les projets (créer, supprimer, déplacer, partager, approuver, épingler, copier et baliser).
keywords: Analysis Workspace
title: Vue d’ensemble des projets
feature: Workspace Basics
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
role: User
source-git-commit: 9d293854ab1da90ea22865392daf9204679f4fd3
workflow-type: tm+mt
source-wordcount: '1684'
ht-degree: 97%

---

# Vue d’ensemble des projets

Les projets Workspace vous permettent de combiner des tableaux, des visualisations et des composants afin d’élaborer votre analyse et de la partager avec qui vous le souhaitez au sein de votre entreprise. Avant de démarrer votre premier projet, découvrez comment accéder à vos projets, les parcourir et les gérer.

Pour accéder aux projets dans Customer Journey Analytics, sélectionnez **[!UICONTROL Workspace]**.  Le gestionnaire **[!UICONTROL Projets]** répertorie tous les projets que vous possédez ou les projets partagés avec vous. Le gestionnaire de projets avec la liste Projet est également la page de destination par défaut de Customer Journey Analytics, sauf configuration contraire dans les Préférences.

![Page de destination du projet affichant la liste des projets.](assets/projects.png)


## Zone de titre

Dans la zone de titre ➊, vous pouvez créer un projet, créer un dossier, modifier vos préférences et afficher ou masquer un panneau avec des vignettes supplémentaires.

* Pour afficher ou masquer un panneau de gauche qui vous permet de choisir entre **[!UICONTROL Projets]** et **[!UICONTROL Formation]**, sélectionnez ![Rail](/help/assets/icons/Rail.svg).
* Le titre affiche les projets, éventuellement ajoutés avec un chemin d’accès au dossier que vous avez sélectionné. Par exemple, [!UICONTROL Projets] > **[!UICONTROL Dossier Entreprise]**. Vous pouvez sélectionner des parties de sous-dossier individuelles pour accéder directement au dossier spécifique.
* Pour afficher les tuiles d’un [**[!UICONTROL Projet vierge]**](create-projects.md), d’une [**[!UICONTROL Carte de performance mobile vierge]**](/help/mobile-app/create-scorecard.md), d’une [**[!UICONTROL Analyse guidée]**](/help/guided-analysis/overview.md), de l’option **[!UICONTROL Ouvrez la documentation]** et de l’option **[!UICONTROL Ouvrez les notes de mise à jour]**, sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Afficher plus]**. Pour masquer la zone avec les tuiles, sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Afficher moins]**.
* En fonction de ce que vous sélectionnez pour l’affichage, à l’aide du [sélecteur Afficher](#show-selector), vous pouvez modifier les préférences et effectuer des actions sur le dossier actif visible dans **[!UICONTROL Projets]** :

  | Action | Description |
  |---|---|
  | **[!UICONTROL Créer un projet]** | Sélectionnez pour [créer un projet](create-projects.md). |
  | **[!UICONTROL Créer un dossier]** | Sélectionnez pour [créer un dossier](workspace-folders/create-folders.md). |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Modifier les préférences]** | [Modifiez les préférences](/help/analysis-workspace/user-preferences.md) pour tous vos projets. Lorsque le chemin de navigation se traduit par un espace limité, cette action fait partie du sous-menu ![Plus](/help/assets/icons/More.svg). |
  | **[!UICONTROL Ajouter des projets]** | Sélectionnez cette option pour [ajouter des projets](workspace-folders/add-projects.md) au dossier actif. Lorsque le chemin de navigation se traduit par un espace limité, cette action fait partie du sous-menu ![Plus](/help/assets/icons/More.svg). |
  | **[!UICONTROL Renommer le dossier]** | [Renomme](workspace-folders/manage-folders.md#rename-folders) le dossier actif. |
  | **[!UICONTROL Déplacer le dossier]** | [Déplace](workspace-folders/manage-folders.md#move-folders) le dossier actif. |
  | **[!UICONTROL Supprimer le dossier]** | [Supprime](workspace-folders/manage-folders.md#delete-folders) le dossier actif. |




## Liste de projets


La liste de projets ➋ affiche tous les projets que vous possédez et qui ont été partagés avec vous. La liste comporte les colonnes suivantes :

| Colonne | Description |
| --- | --- | 
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Lorsqu’un ou plusieurs projets sont sélectionnés, une barre d’actions bleue s’affiche au bas de l’interface Projet. Pour plus de détails, consultez [Actions](#actions). |
| ![Contour en forme d’étoile](/help/assets/icons/StarOutline.svg) | Sélectionnez ![Étoile](/help/assets/icons/Star.svg) pour mettre en favori ou ![StarOutline](/help/assets/icons/StarOutline.svg) pour retirer des favoris un projet. |
| **[!UICONTROL Titre et description]** | Pour modifier le projet, sélectionnez le lien du titre, qui ouvre le [projet Workspace](/help/analysis-workspace/home.md). Les projets partagés avec vous sont indiqués par ![Partager](/help/assets/icons/ShareAlt.svg). Sélectionnez ![InfoOutline](/help/assets/icons/InfoOutline.svg) pour afficher un menu contextuel contenant plus de détails sur le projet. Sélectionnez ![Plus](/help/assets/icons/More.svg) pour ouvrir un menu contextuel avec des actions. Pour plus de détails, consultez [Actions](#actions). |
| **[!UICONTROL Type]** | Un projet Workspace, un dossier ![FolderUser](/help/assets/icons/FolderUser.svg) ou une [Carte de performance mobile](/help/mobile-app/home.md). |
| **[!UICONTROL Étiquettes]** | Balises appliquées au projet. |
| **[!UICONTROL Planifié]** | Indique si un projet doit être envoyé par e-mail aux destinataires. Les options sont ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL On]** ou ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Off]**. Consultez [Envoyer des données de projet à d’autres personnes](/help/analysis-workspace/export/t-schedule-report.md). |
| **[!UICONTROL Lien partagé (tout le monde)]** | Partager ou non un projet avec tout le monde, même avec des personnes qui n’ont pas accès à Analysis Workspace. Les options sont ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Actif]** ou ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Inactif]**. Consultez [Partager un projet avec tout le monde (aucune connexion requise)](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required) dans [Partager des projets](/help/analysis-workspace/curate-share/share-projects.md) pour plus d’informations. |
| **[!UICONTROL Rôle de projet]** | Votre rôle pour le projet. Les options sont les suivantes : Modifier, Dupliquer et Afficher. Consultez [Rôles de projet](/help/analysis-workspace/curate-share/curate.md) pour plus d’informations. |
| **[!UICONTROL Vue de données]** | Vue de données à laquelle le projet est associé. |
| **[!UICONTROL Propriétaire]** | Personne qui a créé ce projet (vous ou quelqu’un qui a partagé le projet avec vous). |
| **[!UICONTROL Partagé avec]** | Utilisateurs et utilisatrices avec lesquels le projet a été partagé. |
| **[!UICONTROL Dernière modification]** | Date et heure de dernière modification du projet. |
| **[!UICONTROL Dernière ouverture]** | Date et heure de dernière ouverture du projet. |
| **[!UICONTROL Identifiant du projet]** | ID du projet. |
| **[!UICONTROL Période la plus longue]** | Période la plus longue de l’un des panneaux ou de l’une des visualisations du projet. |
| **[!UICONTROL Nombre de requêtes]** | Nombre total de requêtes contenues dans le projet. |
| **[!UICONTROL Emplacement]** | Dossier dans lequel réside le projet. |

Pointez sur un en-tête de colonne pour afficher ![ChevronDown](/help/assets/icons/ChevronDown.svg) et sélectionnez dans le menu contextuel les options suivantes :

* **[!UICONTROL Tri ascendant]**
* **[!UICONTROL Tri descendant]**
* **[!UICONTROL Redimensionnez la colonne]**. Une ligne bleue s’affiche pour vous aider à redimensionner la colonne.

### Actions

Vous pouvez agir sur un ou plusieurs projets à l’aide du menu contextuel ![Plus](/help/assets/icons/More.svg) ou de la barre d’actions bleue.

| Icône | Action | Description |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *sélectionné]** | Désélectionnez les projets et dossiers sélectionnés et supprimez la barre d’actions bleue. |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimez un ou plusieurs projets ou dossiers. Il vous est demandé de confirmer.<p>Projets que vous supprimez :</p><ul><li>Impossible de récupérer</li><li>Sont supprimés de la liste des projets</li><li>ne sont plus accessibles avec leur URL ;</li><li>ne sont plus incluses dans les diffusions planifiées (dans le cas où elles étaient précédemment configurées pour des diffusions planifiées)<br/>Pour plus d’informations sur les diffusions planifiées, voir [Projets planifiés](/help/components/scheduled-projects-manager.md).  </p> |
| ![Partager](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Partager]** | Partagez un projet. Consultez [Partager un projet](/help/analysis-workspace/curate-share/share-projects.md) pour plus d’informations. |
| ![Modifier](/help/assets/icons/Edit.svg) | **[!UICONTROL Renommer]** | Renommez un projet. Ouvre une **[!UICONTROL boîte de dialogue Renommer : *nom du projet *]**. Saisissez un nouveau nom et sélectionnez&#x200B;**[!UICONTROL Enregistrer &#x200B;]**. |
| ![Copier](/help/assets/icons/Copy.svg) | **[!UICONTROL Copier]** | Copiez un ou plusieurs projets. Les projets reçoivent le même nom et le même suffixe `(Copy)`. |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL Épingler]** ou **[!UICONTROL Détacher]** | Épinglez ou détacher un ou plusieurs projets ou dossiers. Les projets et dossiers épinglés apparaissent en haut de la liste et ignorent l’ordre de tri que vous spécifiez. |
| ![ArrowUp](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL Déplacer vers le haut]** | Déplacez un projet ou un dossier épinglé vers le haut dans la liste des projets. |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL Déplacer vers le bas]** | Déplacez un projet ou un dossier épinglé vers le bas dans la liste des projets. |
| ![Libellé](/help/assets/icons/Label.svg) | **[!UICONTROL Étiquette]** | Balisez un ou plusieurs projets ou dossiers. La boîte de dialogue **[!UICONTROL Composants de balise]** s’affiche pour sélectionner une ou plusieurs balises. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les balises pour les projets ou dossiers sélectionnés. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approuver]** ou **[!UICONTROL Annuler l’approbation]** | Approuver un projet ou en annuler l’approbation. Seuls les administrateurs et administratrices peuvent approuver les projets. |
| ![Fichier CSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exporter au format CSV]** | Exportez les projets sélectionnés dans un fichier CSV portant le nom `Project List.csv`. |
| ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL Ajouter des projets]** | Ajoutez un ou plusieurs projets à un dossier sélectionné. Dans **[!UICONTROL Ajouter des projets]**, vous pouvez sélectionner un ou plusieurs projets. Sélectionnez **[!UICONTROL Ajouter]** pour ajouter les projets au dossier. Consultez [Ajouter des projets à des dossiers](workspace-folders/add-projects.md#from-inside-a-folder) pour plus d’informations. |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL Déplacer vers]** | Déplacez un ou plusieurs projets sélectionnés vers un dossier. Dans **[!UICONTROL Sélectionner un dossier]**, sélectionnez le dossier dans lequel déplacer le projet sélectionné et sélectionnez **[!UICONTROL Déplacer]**. Consultez [Ajouter des projets à des dossiers](workspace-folders/add-projects.md#from-the-project-list) pour plus d’informations. |



## Sélecteur Afficher

Vous pouvez changer l’aspect de l’interface Projets à l’aide des sélecteurs **[!UICONTROL Afficher]** ➌. Le sélecteur **[!UICONTROL Afficher]** définit les options disponibles dans la [Zone de titre](#title-area) et les colonnes affichées dans la [Liste de projets](#project-list).

* Pour modifier les options disponibles pour la [Zone de titre](#title-area), sélectionnez **[!UICONTROL Afficher]** **[!UICONTROL Tous les projets]** ou **[!UICONTROL Afficher]** **[!UICONTROL Dossiers et projets]**.

* Pour définir les colonnes à afficher pour la [liste de projets](#project-list), sélectionnez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) et dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]**, sélectionnez ou désélectionnez les colonnes. Sélectionnez **[!UICONTROL Appliquer]** pour appliquer la personnalisation. Consultez [Liste de projets](#project-list) pour plus d’informations sur les colonnes.

## Panneau Filtrer

Vous pouvez filtrer les projets et les dossiers dans la [Liste des projets](#project-list) à l’aide du panneau Filtrer ➍. Pour afficher ou masquer le panneau Filtrer, utilisez ![Filtrer](/help/assets/icons/Filter.svg).

Le panneau Filtrer se compose des sections suivantes.

### Balises

| Balises | Description |
|---|---|
| ![Étiquettes](/help/analysis-workspace/build-workspace-project/assets/projects-filters-tags.png){width="300"} | La section **[!UICONTROL Balises]** permet de filtrer par balise. <ul><li>Vous utilisez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des balises* pour rechercher les balises que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionnez plusieurs balises. Les balises disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**2︎⃣** : nombre de balises disponibles pour les projets résultant du filtre actuel.</li><li>7︎⃣ : nombre de projets associés à la balise spécifique.</li></ul></li></ul> |


### Vue de données

| Vue de données | Description |
|---|---|
| ![Vues de données](/help/analysis-workspace/build-workspace-project/assets/projects-filters-dataviews.png){width="300"} | La section **[!UICONTROL Vue de données]** vous permet de filtrer les vues de données. <ul><li>Utilisez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher dans les vues de données* pour rechercher les vues de données à utiliser pour le filtrage.</li><li>Vous pouvez sélectionner plusieurs vues de données. Les vues de données disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**3︎⃣** : nombre de vues de données disponibles pour les projets résultant du filtre actuel.</li><li>4︎⃣ : nombre de projets associés à la vue de données spécifique.</li></ul></li></ul> |


### Propriétaires

| Propriétaire | Description |
|---|---|
| ![Propriétaires](/help/analysis-workspace/build-workspace-project/assets/projects-filters-owners.png){width="300"} | La section **[!UICONTROL Propriétaire]** vous permet de filtrer les propriétaires. <ul><li>Utilisez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des propriétaires* pour rechercher les propriétaires que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs propriétaires. Les propriétaires disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**3︎⃣** : nombre de propriétaires disponibles pour les projets résultant du filtre actuel.</li><li>4︎⃣ : nombre de projets associés à la personne propriétaire spécifique.</li></ul></li></ul> |


### Type

| Type | Description |
|---|---|
| ![Type](/help/analysis-workspace/build-workspace-project/assets/projects-filters-type.png){width="300"} | La section **[!UICONTROL Type]** permet de filtrer selon le type de projets ou de dossiers.<ul><li>Vous pouvez sélectionner l’une ou plusieurs des options suivantes :<ul><li> **[!UICONTROL Dossier]**</li><li>**[!UICONTROL Projet Espace de travail]**</li><li>**[!UICONTROL Carte de performance mobile]**</li></ul> <li>Vous pouvez sélectionner plusieurs filtres. Les autres filtres disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**5︎⃣** : nombre d’autres filtres disponibles pour les projets résultant du filtre actuel.</li><li>4︎⃣ : nombre de projets associés à l’autre filtre spécifique.</li></ul></li></ul> |


### Autres filtres

| Autres filtres | Description |
|---|---|
| ![Autres filtres](/help/analysis-workspace/build-workspace-project/assets/projects-filters-others.png){width="300"} | La section **[!UICONTROL Autres filtres]** vous permet de filtrer selon un autre filtre prédéfini.<ul><li>Vous pouvez sélectionner l’une ou plusieurs des options suivantes :<ul><li> **[!UICONTROL Tout afficher]**</li><li>**[!UICONTROL Partagé avec moi]**</li><li>**[!UICONTROL À moi]**</li><li>**[!UICONTROL Approuvés]**</li><li>**[!UICONTROL Favoris]**</li></ul> Ce que vous pouvez sélectionner dépend de votre rôle et de vos autorisations.</li><li>Vous pouvez sélectionner plusieurs filtres. Les autres filtres disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**5︎⃣** : nombre d’autres filtres disponibles pour les projets résultant du filtre actuel.</li><li>4︎⃣ : nombre de projets associés à l’autre filtre spécifique.</li></ul></li></ul> |

## Recherche

Utilisez la zone de recherche ➎ pour rechercher des projets et des dossiers à l’aide du champ ![Rechercher](/help/assets/icons/Search.svg). Commencez la saisie et la [liste de projets](#project-list) filtre automatiquement selon votre entrée de recherche.

La zone de recherche affiche également les filtres appliqués à partir du panneau Filtrer.

* Pour supprimer un filtre, sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) dans le filtre.
* Pour supprimer tous les filtres, sélectionnez Effacer tout.

Si l’espace est limité pour l’affichage des filtres individuels, le message **[!UICONTROL Segmentation avec *x* filtres]** s’affiche.

* Pour supprimer un filtre, procédez comme suit :

   1. Utilisez **[!UICONTROL *x * filtres]**![ChevronDown](/help/assets/icons/ChevronDown.svg) pour ouvrir un menu contextuel répertoriant les types de filtres et les filtres individuels.
   1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer un filtre.


<!--

The Projects page contains the following information: 

>[!NOTE]
>
>Some columns are not displayed by default. To customize the columns you see, click the **Customize table** icon ![Customize table](assets/projects-page-customize-columns-icon.png).

|  Element  | Description  |
|---|---|
| [Edit preferences](/help/analysis-workspace/user-preferences.md) | Manage settings for Analysis Workspace and its related components for all new projects or panels that you create.  |
| [Create folder](/help/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)  | Add a new folder or subfolder to the list of projects and folders. |
| [Create project](/help/analysis-workspace/build-workspace-project/create-projects.md)  | Start a new project from scratch.  |
|  Show more  |Reveals options for creating a blank project or mobile scorecard, [viewing training tutorials](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html?lang=fr), or [viewing release notes](/help/release-notes/latest.md).  |
| Show Folders & Projects| Choose whether to show the folder structure of projects. For more information, see [About Folders in Analytics](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
|  Customize table (icon)  | Allows you to customize the information that shows for each project on the Projects page.  |
|  Name  | Name of the Workspace project.  |
| Type | Indicates whether this is a Workspace Project, a folder, or a [Mobile Scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html?lang=fr). |
|  Tags  |Tags that were applied to the project.  |
| Scheduled | Indicates whether projects are scheduled to be emailed to recipients on a schedule. See [Send project data to others](/help/analysis-workspace/export/t-schedule-report.md). |
| Shared link (anyone) | Projects can be shared with anyone--even with people who don't have access to Analysis Workspace. This column shows whether projects have been shared in this way. See [Share a project with anyone (no login required)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Share projects](/help/analysis-workspace/curate-share/share-projects.md) for more information. |
| Data view | The data view that the project is associated with. |
| [Project Role](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=fr) | Indicates your role for the project - owners, edit, duplicate, view. |
|  Owner  | The person who created this project (either you or someone who shared the project with you.)  |
|  Shared with  | Users that the project has been shared with.  |
|  Last Modified  | Date and time when the project was last modified.  |
|  Last Opened  | Date and time when the project was last opened.  |
|  Project ID  | The ID of the project.  |
|  Longest Date Range  | The longest date range of the project.  |
|  Number of Queries  | The total number of queries contained in the project.  |
|  Location  | The folder where the project resides.  |

## Menu bar {#menu-bar}

Within a project, the menu provides options for managing your project, adding components, finding help, and more. Each menu option can also be accessed by keyboard [shortcuts](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![New Project options including the Project, Edit, Insert, Components, Share, and Help options.](assets/menu.png)

|  Menu item  | Description  |
|---|---|
|  Project  | Includes common actions for project management, including New, Open, Save, and Save As. You can also refresh the entire project to retrieve the most recent data and definitions by clicking Refresh Project. [Download project data](/help/analysis-workspace/export/download-send.md) options enable you to export data from Workspace. **Project Info & Settings** (see below) offers many options for managing your project.  |
|  Edit  | Undo or redo your last action. Clear All will reset your project to a blank starting point. |
|  Insert  | Insert new panels or visualizations from this menu. You can also insert new panels and visualizations from the left panel.  |
|  [Components](/help/components/overview.md)  | Create new segments, calculated metric, date range, or alert components from your project. You can also create new components from the left panel. If your component definitions have recently changed, Refresh Components will retrieve the latest definitions. |
|  [Share](/help/analysis-workspace/curate-share/send-schedule-files.md)  | Curate, share and schedule PDF/CSV projects to recipients in your organization.  |
|  Help  | Access help documentation, videos, and the Analytics [Experience League community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=fr). Manage the visibility of Workspace tips as well as the [debugger](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/apis/using-analysis-workspace-to-build-api-2-requests). Find details about Workspace and factors that impact project [performance](/help/technotes/optimizing-performance.md).  |
|  Share button or Owner  | If you are in an Own or Edit for the project, the Share button in the top-right gives you one-click access to manage your project recipients. If you are in a Duplicate or View role for the project, you will see the project owner's name. |

### Project Info & Settings {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project info & settings]** provides project-level information on the currently active project.

![The Project Info & Settings window.](assets/projectinfo.png)

Settings include:

|  Setting  | Description  |
|---|---|
|  Project Name  | The name given to the project. You can double-click the name to edit it.  |
|  Created By  | Project owner name  |
|  Last Modified  | Date of last modification to the project.  |
|  Tags  |Lists any tags applied to a project for easier categorization.  |
|  Description  | A description is useful for clarifying the purpose of a project. You can double-click the description to edit it.  |
|  Count repeat instances in project  | Specifies whether repeat instances are counted in reports. Note: this setting does not apply to Flow or Fallout visualizations.  |
|  [Project color palette](/help/analysis-workspace/build-workspace-project/color-palettes.md)  | You can change the categorical color palette used in Workspace, by choosing from out-of-the-box palettes that have been optimized for color blindness, or by specifying your custom palette. This feature affects many things in Workspace, including most visualizations.  |
| [View Density](/help/analysis-workspace/build-workspace-project/view-density.md) | Lets you see more data on the screen by reducing the vertical padding of the left panel, freeform tables and cohort tables. |

## Left panel

Within a project, various icons are available in the left panel, and each represents important parts of a project:

* [Panels](/help/analysis-workspace/c-panels/panels.md) ![panels icon](assets/panels-icon.png)

* [Visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)![visualizations icon](assets/visualizations-icon.png)

* [Components](/help/components/overview.md)![components icon](assets/components-icon.png)

* [Data dictionary](/help/components/data-dictionary/data-dictionary-overview.md)![data dictionary icon](assets/data-dictionary-icon.png)

* [Table of contents](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md) ![toc icon](assets/toc-icon.png)

Components (Dimensions, Metrics, Segments, Date Ranges) in the left panel relate to the active panel data view. The active panel is identified by the blue border that surrounds it, and the active data view is listed at the top of the component panel.

![The components relating to the active panel data view for Cross-Industry Demo Data data view.](assets/left-rail.png)

## Project canvas {#canvas}

The project canvas is where you bring together panels, tables, visualizations, and components to build your analysis. A project can contain many panels, and each panel can contain many tables and visualizations.

Panels are helpful when you want to organize your projects according to time periods, data views, or analysis use case. The active panel will have a blue border around it, and determines what components are available in the left panel.

Depending on the starting point you chose for your projects, you will either have a [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) or a [blank panel](/help/analysis-workspace/c-panels/blank-panel.md) in the canvas to begin with. The quickest way to start analyzing is to select one or many components and simply drag & drop them into the project canvas. A table of data will automatically be rendered for you. [Learn more](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) about the different options for building a table, or leverage our [training tutorial](/help/analysis-workspace/home.md) for more guidance on building your first project.

![A Freeform Table for the project.](assets/canvas.png)

## Project Manager {#manager}

Analysis Workspace projects can be managed under **Analytics > Components >  Projects**. The Project Manager shows the projects that a specific user created. You can transfer project ownership to a new user under Admin > Analytics Users & Assets > Transfer Assets.

In Projects Manager, you can add, tag, share, duplicate/copy, and more. Search for a project in the search bar or by using the filter options in the left panel. You can filter by tag, owners, project type and more.

![Project Manager Tags search field and Title search field.](assets/project-manager.png)

The following are common actions in the Projects manager, and can be taken on one or many projects at once:

|  Action  | Description  |
|---|---|
|  Add  | Create a new project from scratch.  |
|  Tag or Approve  | Choose "Tag" or "Approve" to organize your projects and make them easier to search for.  |
|  [Share](/help/analysis-workspace/curate-share/share-projects.md)  | Make a project available to other Analysis Workspace users in your organization.  |
|  Delete  | Delete your project.  |
|  Rename  | Edit the name of your project.  |
|  Copy  | Create a duplicate copy of your project. This creates a new project and project ID. Any shares or schedules tied to the original project will not be copied. |
|  Export to CSV  | Download your project as a CSV file, which includes plain-text data.  |

-->

