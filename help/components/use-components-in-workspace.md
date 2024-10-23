---
description: Découvrez comment ajouter des composants à un projet dans Analysis Workspace
title: Utiliser des composants dans Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 7%

---

# Utiliser des composants dans Analysis Workspace

Les composants constituent les données réelles de tout projet dans Analysis Workspace. Les composants se composent de dimensions, de mesures, de filtres et de périodes. Vous pouvez ajouter des composants à un projet en les faisant glisser dans des visualisations ou des panneaux.

Pour plus d’informations sur les types de composants que vous pouvez ajouter, consultez la [présentation des composants](/help/components/overview.md) .

>[!TIP]
>
>Pour plus d’informations sur chaque composant, utilisez ![InfoOutline](/help/assets/icons/InfoOutline.svg). Voir [Informations sur le composant](#component-info) pour plus d’informations.

## Ajout de composants à un projet

1. [Créez un projet dans Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md).

1. [Ajoutez un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel) ou [ajoutez une visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) au projet dans Analysis Workspace. Si vous ajoutez un composant à un projet vierge, une visualisation de tableau à structure libre est déjà créée.

1. Sélectionnez ![Traiter](/help/assets/icons/Curate.svg) **[!UICONTROL Composants]** dans le panneau des boutons. Tous les composants disponibles s’affichent dans le panneau de gauche. Voir [Interface](/help/analysis-workspace/home.md#interface) pour plus d’informations.

1. Faites défiler l’écran jusqu’au composant que vous souhaitez ajouter ou recherchez-le, puis faites-le glisser vers un panneau ou une visualisation dans votre projet.

1. Vous pouvez éventuellement faire glisser un composant vers la zone de dépôt de filtre dans un en-tête de panneau. Ce glisser-déposer définit le composant comme un filtre et applique le filtre à tout le contenu du panneau.
Pour plus d’informations sur l’utilisation de la zone de dépôt de filtre sur un panneau pour filtrer votre panneau, voir [Zone de dépôt](/help/analysis-workspace/c-panels/panels.md#drop-zone) dans la [présentation des panneaux](/help/analysis-workspace/c-panels/panels.md).

1. Pour plus d’informations, reportez-vous aux sections suivantes :

   * [Ajout de dimensions à un projet](#add-dimensions-to-a-project)

   * [Ajout de mesures à un projet](#add-metrics-to-a-project)

   * [Ajout de filtres à un projet](#add-filters-to-a-project)

   * [Ajout de périodes à un projet](#add-date-ranges-to-a-project)

### Ajout de dimensions à un projet

[Dimensions](/help/components/dimensions/overview.md) sont des variables en Customer Journey Analytics qui contiennent généralement des valeurs de chaîne. En revanche, les [mesures](/help/components/calc-metrics/calc-metr-overview.md) contiennent des valeurs numériques liées à une dimension. Un rapport de base présente des lignes de valeurs de chaîne (dimension) en fonction d’une colonne de valeurs numériques (mesure).

1. Commencez à ajouter une dimension à votre projet dans Analysis Workspace, comme décrit dans [Ajout de composants à un projet](#add-components-to-a-project).

1. Choisissez l’une des méthodes suivantes pour ajouter des dimensions et déterminer le type de données à analyser :

   ![Ajouter une dimension](/help/components/assets/add-dimension.gif)

   * Faites glisser une dimension sur une visualisation (un tableau à structure libre, par exemple) dans Analysis Workspace.

   * Faites glisser une ou plusieurs dimensions du panneau de gauche sur la zone de dépôt des filtres pour créer un filtre rapide, comme décrit dans la section [Ajout de filtres à un projet](#add-filters-to-a-project).

1. Vous pouvez éventuellement ventiler des dimensions et des éléments de dimension dans Analysis Workspace avec d’autres composants. Pour plus d’informations, voir [Ventilation des dimensions dans Workspace](/help/components/dimensions/t-breakdown-fa.md).

Pour plus d’informations sur l’utilisation des dimensions dans Analysis Workspace, voir [Aperçu des dimensions](/help/components/dimensions/view-dimensions.md), [Ventilation des dimensions](/help/components/dimensions/t-breakdown-fa.md) et [Dimensions de répartition du temps](/help/components/dimensions/time-parting-dimensions.md).

### Ajout de mesures à un projet

Les mesures vous permettent de quantifier les points de données dans Analysis Workspace. Elles sont généralement utilisées comme colonnes dans une visualisation et liées aux dimensions.

Pour ajouter une mesure à un projet dans Analysis Workspace :

1. Commencez à ajouter une mesure à votre projet dans Analysis Workspace, comme décrit dans [Ajout de composants à un projet](#add-components-to-a-project).



1. Choisissez l’une des méthodes suivantes pour ajouter une mesure dans Analysis Workspace :

   ![Ajout d’une mesure](/help/components/assets/add-metric.gif)

   * Faites glisser une mesure sur la zone de dépôt des mesures dans un tableau à structure libre vide pour afficher les tendances de cette mesure sur la période du projet.

   * Faites glisser une mesure lorsqu’une dimension est présente pour afficher cette mesure pour chaque élément de dimension.

   * Faire glisser une mesure au-dessus d’un en-tête de mesure existant pour le remplacer.

   * Faites glisser une mesure en regard du côté gauche d’un en-tête de mesure existant pour ajouter la nouvelle mesure.

   * Faites glisser une mesure au-dessus ou au-dessous d’un en-tête de mesure existant pour créer un chevauchement de mesures.


Pour plus d’informations sur les mesures, voir [Mesures](/help/components/apply-create-metrics.md).

### Ajout de filtres à un projet

[Les filtres](/help/components/filters/filters-overview.md) vous permettent d’identifier des sous-ensembles de personnes, de sessions ou d’événements en fonction de caractéristiques ou d’interactions spécifiques.

Vous pouvez utiliser des filtres dans Analysis Workspace de l’une des manières suivantes :

* Ajout de filtres à un panneau
Lorsque vous ajoutez des filtres à un panneau, ils s’appliquent à tout le contenu du panneau.
Pour plus d’informations sur l’utilisation de la zone de dépôt de filtre sur un panneau pour filtrer votre panneau, voir [Zone de dépôt](/help/analysis-workspace/c-panels/panels.md#drop-zone) dans la [présentation des panneaux](/help/analysis-workspace/c-panels/panels.md).

* Ajout de filtres à une visualisation
Lorsque vous ajoutez des filtres à une colonne d’un tableau à structure libre, les filtres s’appliquent à tout le contenu de la colonne du tableau. Vous pouvez également ajouter des filtres dans le cadre d’une visualisation Abandons.

* Utilisation de filtres dans les composants
Lorsque vous définissez des composants tels que des [mesures calculées](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md), des [annotations](/help/components/annotations/create-annotations.md#annotation-builder) ou même des [filtres](/help/components/filters/filter-builder.md), vous pouvez utiliser des filtres dans le cadre de la définition.


### Ajout de périodes à un projet

[ Les périodes](/help/components/date-ranges/overview.md) déterminent la période de création de rapports dans Analysis Workspace et peuvent être appliquées à un ou plusieurs panneaux au sein d’un projet, ainsi qu’à certaines visualisations (comme le tableau à structure libre).

Par défaut, chaque panneau comprend une plage de dates. Il existe plusieurs façons de mettre à jour une période pour un panneau. Pour mettre à jour une période pour un panneau dans Analysis Workspace, faites glisser un composant de période depuis le panneau de gauche :

1. Vous pouvez éventuellement ajouter une période à votre projet dans Analysis Workspace, comme décrit dans la section [Ajout de composants à un projet](#add-components-to-a-project).

1. Faites glisser et déposez une période du panneau de gauche vers :

   * La période actuelle, afin de modifier la période du panneau.

     ![Déposer une période](assets/add-date-range.gif)

   * Mesure ou dimension dans une visualisation de tableau à structure libre. Pour plus d’informations, voir [Utilisation des plages de dates](/help/components/date-ranges/overview.md#use-date-ranges) .

Pour plus d’informations sur l’utilisation et la gestion des plages de dates dans Analysis Workspace, consultez la [présentation des plages de dates](/help/components/date-ranges/overview.md).

## Informations sur le composant

Vous pouvez placer le pointeur de la souris sur un composant pour afficher ![Plus d’informations](/help/assets/icons/InfoOutline.svg). Lorsqu’elle est sélectionnée, une fenêtre contextuelle s’affiche avec des informations supplémentaires sur le composant.

![Informations sur le composant](assets/component-info.png)

En fonction de votre contrôle d’accès, vous pouvez :

* Accédez à la définition de ![signet](/help/assets/icons/Bookmark.svg) [!UICONTROL dictionnaire de données] pour le composant.
* Accédez au créateur de composants ![Edit](/help/assets/icons/Edit.svg) ou à la vue de données dans laquelle le composant est défini.
