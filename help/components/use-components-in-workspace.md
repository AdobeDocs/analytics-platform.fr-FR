---
description: Découvrez comment utiliser des composants dans un projet dans Analysis Workspace
title: Utilisation De Composants Dans Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 97%

---

# Utilisation de composants dans un projet

Les composants représentent les données réelles de n’importe quel projet dans Analysis Workspace. Les composants comprennent les dimensions, les mesures, les segments et les périodes. Vous pouvez ajouter des composants à un projet en les faisant glisser dans des visualisations ou des panneaux.

Pour plus d’informations sur les types de composants que vous pouvez ajouter, consultez [Vue d’ensemble des composants](/help/components/overview.md).

>[!TIP]
>
>Pour plus d’informations sur chaque composant, utilisez ![Aperçu des informations](/help/assets/icons/InfoOutline.svg). Pour plus d’informations, consultez [Informations sur le composant](#component-info).

## Ajouter des composants à un projet

1. [Créez un projet dans Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md).

1. [Ajoutez un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel) ou [ajoutez une visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) au projet dans Analysis Workspace. Si vous ajoutez un composant à un projet vierge, une visualisation de tableau à structure libre est déjà créée pour vous.

1. Sélectionnez ![Traiter](/help/assets/icons/Curate.svg) **[!UICONTROL Composants]** dans le panneau de boutons. Tous les composants disponibles s’affichent dans le panneau de gauche. Pour plus de détails, consultez [Interface](/help/analysis-workspace/home.md#interface).

1. Faites défiler l’écran jusqu’au composant à ajouter ou recherchez-le, puis faites-le glisser vers un panneau ou une visualisation de votre projet.

1. Vous pouvez éventuellement faire glisser un composant vers la zone de dépôt des segments dans un en-tête de panneau. Ce glisser-déposer définit le composant comme un segment et applique le segment à tout le contenu du panneau.
Pour plus d’informations sur l’utilisation de la zone de dépôt des segments sur un panneau pour segmenter votre panneau, voir [Zone de dépôt](/help/analysis-workspace/c-panels/panels.md#drop-zone) dans [Vue d’ensemble des panneaux](/help/analysis-workspace/c-panels/panels.md).

1. Pour des informations plus détaillées, voir les sections suivantes :

   * [Ajouter des dimensions à un projet](#add-dimensions-to-a-project)

   * [Ajouter des mesures à un projet](#add-metrics-to-a-project)

   * [Ajouter des segments à un projet](#add-segments-to-a-project)

   * [Ajouter des périodes à un projet](#add-date-ranges-to-a-project)

### Ajouter des dimensions à un projet

Les [dimensions](/help/components/dimensions/overview.md) sont des variables de Customer Journey Analytics qui contiennent généralement des valeurs de chaîne. En revanche, les [mesures](/help/components/calc-metrics/calc-metr-overview.md) contiennent des valeurs numériques liées à une dimension. Un rapport de base présente des lignes de valeurs de chaîne (dimension) en fonction d’une colonne de valeurs numériques (mesure).

1. Commencez par ajouter une dimension à votre projet dans Analysis Workspace, comme décrit dans la section [Ajouter des composants à un projet](#add-components-to-a-project).

1. Choisissez l’une des méthodes suivantes pour ajouter des dimensions et déterminer le type de données à analyser :

   ![Ajouter une dimension](/help/components/assets/add-dimension.gif)

   * Faites glisser une dimension vers une visualisation (un tableau à structure libre, par exemple) dans Analysis Workspace.

   * Faites glisser une ou plusieurs dimensions du panneau de gauche vers la zone de dépôt des segments pour créer un segment rapide, comme décrit dans la section [Ajouter des segments à un projet](#add-filters-to-a-project).

1. Vous pouvez éventuellement ventiler les dimensions et les éléments de dimension dans Analysis Workspace avec d’autres composants. Pour plus d’informations, voir [Ventiler des dimensions dans Workspace](/help/components/dimensions/t-breakdown-fa.md).

Pour plus d’informations sur l’utilisation des dimensions dans Analysis Workspace, voir [Prévisualiser les dimensions](/help/components/dimensions/view-dimensions.md), [Ventiler les dimensions](/help/components/dimensions/t-breakdown-fa.md) et [Dimensions de répartition du temps](/help/components/dimensions/time-parting-dimensions.md).

### Ajouter des mesures à un projet

Les mesures vous permettent de quantifier les points de données dans Analysis Workspace. Elles sont généralement utilisées comme colonnes dans une visualisation et liées aux dimensions.

Pour ajouter une mesure à un projet dans Analysis Workspace :

1. Commencez par ajouter une mesure à votre projet dans Analysis Workspace, comme décrit dans la section [Ajouter des composants à un projet](#add-components-to-a-project).



1. Choisissez l’une des méthodes suivantes pour ajouter une mesure dans Analysis Workspace :

   ![Ajouter une mesure](/help/components/assets/add-metric.gif)

   * Faites glisser une mesure vers la zone de dépôt des mesures dans un tableau à structure libre vide pour afficher les tendances de cette mesure sur la période du projet.

   * Faites glisser une mesure lorsqu’une dimension est présente pour la comparer à chaque élément de dimension.

   * Faire glisser une mesure au-dessus d’un en-tête de mesure existant pour le remplacer.

   * Faites glisser une mesure à côté de la gauche ou de la droite d’un en-tête de mesure existant pour ajouter la nouvelle mesure.

   * Faites glisser une mesure au-dessus ou en dessous d’un en-tête de mesure existant pour créer un chevauchement de mesures.


Pour plus d’informations sur les mesures, voir [Mesures](/help/components/apply-create-metrics.md).

### Ajouter des segments à un projet

Les [segments](/help/components/segments/seg-overview.md) vous permettent d’identifier des sous-ensembles de personnes, de sessions ou d’événements en fonction de caractéristiques ou d’interactions spécifiques.

Vous pouvez utiliser des segments dans Analysis Workspace de l’une des manières suivantes :

* Ajouter des segments à un panneau
Lorsque vous ajoutez des segments à un panneau, les segments s’appliquent à tout le contenu du panneau.
Pour plus d’informations sur l’utilisation de la zone de dépôt des segments sur un panneau pour segmenter votre panneau, voir [Zone de dépôt](/help/analysis-workspace/c-panels/panels.md#drop-zone) dans [Vue d’ensemble des panneaux](/help/analysis-workspace/c-panels/panels.md).

* Ajouter des segments à une visualisation
Lorsque vous ajoutez des segments à une colonne d’un tableau à structure libre, les segments s’appliquent à tout le contenu de la colonne du tableau. Vous pouvez également ajouter des segments dans le cadre d’une visualisation des abandons.

* Utiliser des segments dans des composants
Lorsque vous définissez des composants tels que des [mesures calculées](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md), des [annotations](/help/components/annotations/create-annotations.md#annotation-builder), voire des [segments](/help/components/segments/seg-builder.md), vous pouvez utiliser des segments dans le cadre de la définition.


### Ajouter des périodes à un projet

Les [périodes](/help/components/date-ranges/overview.md) déterminent la période de création de rapports dans Analysis Workspace. Elles peuvent être appliquées à un ou plusieurs panneaux au sein d’un projet, ainsi qu’à certaines visualisations (telles que le tableau à structure libre).

Par défaut, chaque panneau comprend une période. Il existe plusieurs façons de mettre à jour une période pour un panneau. Une méthode de mise à jour d’une période pour un panneau dans Analysis Workspace consiste à faire glisser un composant de période depuis le panneau de gauche :

1. Vous pouvez éventuellement ajouter une période à votre projet dans Analysis Workspace, comme décrit dans la section [Ajouter des composants à un projet](#add-components-to-a-project).

1. Faites glisser et déposez une période depuis le panneau de gauche sur :

   * La période en cours, pour modifier la période du panneau.

     ![Déposer une période](assets/add-date-range.gif)

   * Une mesure ou une dimension dans une visualisation de tableau à structure libre. Pour plus d’informations, consultez [Utiliser des périodes](/help/components/date-ranges/overview.md#use-date-ranges).

Pour plus d’informations sur l’utilisation et la gestion des périodes dans Analysis Workspace, consultez [Vue d’ensemble des périodes](/help/components/date-ranges/overview.md).

## Informations sur le composant

Vous pouvez pointer sur n’importe quel composant pour afficher ![Plus d’informations](/help/assets/icons/InfoOutline.svg). Lorsque cette option est sélectionnée, une fenêtre contextuelle s’affiche avec des informations supplémentaires sur le composant.

![Informations sur le composant](assets/component-info.png)

Selon votre contrôle d’accès, vous pouvez :

* Accéder à la définition ![Signet](/help/assets/icons/Bookmark.svg) [!UICONTROL Dictionnaire de données] du composant.
* Accéder au créateur de composants ![Modifier](/help/assets/icons/Edit.svg) ou à la vue de données dans laquelle le composant est défini.
