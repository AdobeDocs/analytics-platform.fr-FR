---
description: Découvrez comment ajouter des composants à un projet dans Analysis Workspace
title: Utiliser des composants dans Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 697503bba56f44159df7a2f6a0e60a0a4178266d
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 16%

---

# Utiliser des composants dans Analysis Workspace

Les composants constituent les données réelles de tout projet dans Analysis Workspace. Les composants se composent de dimensions, de mesures, de filtres et de périodes. Vous pouvez ajouter des composants à un projet en les faisant glisser dans des visualisations ou des panneaux.

Pour obtenir des informations d’aperçu sur les types de composants que vous pouvez ajouter, voir [Présentation des composants](/help/components/overview.md).

>[!TIP]
>
>Pour plus d’informations sur chaque composant, cliquez sur l’icône Infos en regard du nom d’un composant dans le rail de gauche d’Analysis Workspace.

## Commencer à ajouter des composants à un projet

1. [Créez un projet dans Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md) si ce n’est déjà fait.

1. [Ajoutez un panneau](/help/analysis-workspace/c-panels/panels.md) ou [ajoutez une visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) au projet dans Analysis Workspace.

   Si vous ajoutez un composant à un projet vierge, une visualisation de tableau à structure libre est automatiquement créée.

1. Sélectionnez l’icône **[!UICONTROL Composants]** dans le rail de gauche.

   ![](assets/build-components.png)

1. Faites défiler l’écran jusqu’au composant que vous souhaitez ajouter ou recherchez-le, puis faites-le glisser vers un panneau ou une visualisation dans votre projet.

1. (Facultatif) Faites glisser un composant vers la zone de dépôt de filtre dans un en-tête de panneau.

   Les filtres s’appliquent à tout le contenu du panneau.

   Pour plus d’informations sur l’utilisation de la zone de dépôt de filtre sur un panneau pour filtrer votre panneau, voir [Zone de dépôt](/help/analysis-workspace/c-panels/panels.md#drop-zone) dans la [présentation des panneaux](/help/analysis-workspace/c-panels/panels.md).

   ![déposer un filtre dans la zone de dépôt](assets/filter-dropzone.png)

1. Pour plus d’informations, passez à l’une des sections suivantes, selon le type de composant que vous ajoutez :

   * [Ajout de dimensions à un projet](#add-dimensions-to-a-project)

   * [Ajout de mesures à un projet](#add-metrics-to-a-project)

   * [Ajout de filtres à un projet](#add-filters-to-a-project)

   * [Ajout de périodes à un projet](#add-date-ranges-to-a-project)

## Ajout de dimensions à un projet

[Dimensions](/help/components/dimensions/overview.md) sont des variables dans Adobe Analytics qui contiennent généralement des valeurs de chaîne. En revanche, les [mesures](/help/components/calc-metrics/calc-metr-overview.md) contiennent des valeurs numériques liées à une dimension. Un rapport de base présente des lignes de valeurs de chaîne (dimension) en fonction d’une colonne de valeurs numériques (mesure).

1. Commencez à ajouter une dimension à votre projet dans Analysis Workspace, comme décrit dans [Commencer à ajouter des composants à un projet](#begin-adding-components-to-a-project).

1. Choisissez l’une des méthodes suivantes pour ajouter des dimensions et déterminer le type de données à analyser :

   * Faites glisser une dimension sur une visualisation (un tableau à structure libre, par exemple) dans Analysis Workspace.

     ![Ajouter des dimensions à un projet](assets/add-dimensions.png)

   * Faites glisser une ou plusieurs dimensions du rail de gauche sur la zone de dépôt des filtres pour créer un filtre ad hoc, comme décrit dans la section [Ajout de filtres à un projet](#add-filters-to-a-project).

1. (Facultatif) Vous pouvez ventiler des dimensions et des éléments de dimension dans Analysis Workspace avec d’autres composants.

   Pour plus d’informations, voir [Ventilation des dimensions dans Workspace](/help/components/dimensions/t-breakdown-fa.md).

Pour plus d’informations sur l’utilisation des dimensions dans Analysis Workspace, voir [Aperçu des dimensions](/help/components/dimensions/view-dimensions.md), [Ventilation des dimensions](/help/components/dimensions/t-breakdown-fa.md) et [Dimensions de répartition du temps](/help/components/dimensions/time-parting-dimensions.md).

## Ajout de mesures à un projet

Les mesures vous permettent de quantifier les points de données dans Analysis Workspace. Elles sont généralement utilisées comme colonnes dans une visualisation et liées aux dimensions.

Pour ajouter une mesure à un projet dans Analysis Workspace :

1. Commencez à ajouter une mesure à votre projet dans Analysis Workspace, comme décrit dans [Commencer à ajouter des composants à un projet](#begin-adding-components-to-a-project).

1. Choisissez l’une des méthodes suivantes pour ajouter une mesure dans Analysis Workspace :

   * Faites glisser une mesure sur la zone de dépôt des mesures dans un tableau à structure libre vide pour afficher les tendances de cette mesure sur la période du projet.

     ![Ajouter une mesure à un projet](assets/add-metrics.png)

   * Faire glisser une mesure lorsqu’une dimension est présente pour la comparer à chaque élément de la dimension.

   * Faire glisser une mesure au-dessus d’un en-tête de mesure existant pour le remplacer.

   * Faire glisser une mesure près d’un en-tête pour afficher les deux côte à côte.

Pour plus d’informations sur les mesures, voir [Présentation des mesures calculées](/help/components/calc-metrics/calc-metr-overview.md).

## Ajout de filtres à un projet

Les [filtres](/help/components/filters/filters-overview.md) vous permettent d’identifier des sous-ensembles de visiteurs en fonction de caractéristiques ou d’interactions spécifiques.

Vous pouvez utiliser des filtres dans Analysis Workspace de l’une des manières suivantes :

### Ajout de filtres à un panneau

Lorsque vous ajoutez des filtres à un panneau, ils s’appliquent à tout le contenu du panneau.

Pour plus d’informations sur l’utilisation de la zone de dépôt de filtre sur un panneau pour filtrer votre panneau, voir [Zone de dépôt](/help/analysis-workspace/c-panels/panels.md#drop-zone) dans la [présentation des panneaux](/help/analysis-workspace/c-panels/panels.md).

### Ajout de filtres à une colonne d’un tableau à structure libre

Lorsque vous ajoutez des filtres à une colonne d’un tableau à structure libre, les filtres s’appliquent à tout le contenu de la colonne du tableau.

### Utilisation de filtres lors de la création de mesures calculées

Dans le créateur de mesures calculées, vous pouvez appliquer des filtres dans votre définition de mesure.

Pour plus d’informations, voir [Mesures filtrées](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md).

## Ajout de périodes à un projet

[Les plages de dates](/help/components/date-ranges/custom-date-ranges.md) déterminent la période de création de rapports dans Analysis Workspace et peuvent être appliquées à un ou plusieurs panneaux au sein d’un projet.

Par défaut, chaque panneau comprend une plage de dates. Il existe plusieurs façons de mettre à jour une période pour un panneau. Pour mettre à jour une période pour un panneau dans Analysis Workspace, faites glisser un composant de période depuis le rail de gauche :

1. Commencez à ajouter une période à votre projet dans Analysis Workspace, comme décrit dans [Commencer à ajouter des composants à un projet](#begin-adding-components-to-a-project).

1. Faites glisser une plage de dates du rail de gauche vers la plage de dates actuelle dans la partie supérieure droite du panneau.

   ![déposer une plage de dates](assets/daterange-drop.png)

Pour plus d’informations sur l’utilisation des calendriers et des plages de dates dans Analysis Workspace, consultez la [présentation du calendrier et des plages de dates](/help/components/date-ranges/custom-date-ranges.md).
