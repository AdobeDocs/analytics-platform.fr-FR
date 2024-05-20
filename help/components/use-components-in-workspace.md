---
description: Découvrez comment ajouter des composants à un projet dans Analysis Workspace
title: Utilisation de composants dans Analysis Workspace
feature: Components
role: User
source-git-commit: d3f90414494b52aba9736fef83423e4a1b2508b5
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 16%

---

# Utilisation de composants dans Analysis Workspace

Les composants constituent les données réelles de tout projet dans Analysis Workspace. Les composants se composent de dimensions, de mesures, de segments et de périodes. Vous pouvez ajouter des composants à un projet en les faisant glisser dans des visualisations ou des panneaux.

Pour obtenir des informations d’aperçu sur les types de composants que vous pouvez ajouter, voir [Présentation des composants](/help/components/overview.md).

>[!TIP]
>
>Pour plus d’informations sur chaque composant, cliquez sur l’icône Infos en regard du nom d’un composant dans le rail de gauche d’Analysis Workspace.

## Commencer à ajouter des composants à un projet

1. [Création d’un projet dans Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md) si vous ne l&#39;avez pas déjà fait.

1. [Ajouter un panneau](/help/analysis-workspace/c-panels/panels.md) ou [ajouter une visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) au projet dans Analysis Workspace.

   Si vous ajoutez un composant à un projet vierge, une visualisation de tableau à structure libre est automatiquement créée.

1. Sélectionnez l’icône **[!UICONTROL Composants]** dans le rail de gauche.

   ![](assets/build-components.png)

1. Faites défiler l’écran jusqu’au composant que vous souhaitez ajouter ou recherchez-le, puis faites-le glisser vers un panneau ou une visualisation dans votre projet.

   Par exemple, vous pouvez faire glisser un segment vers la zone de dépôt des segments dans un en-tête de panneau.

   ![déposer un segment dans la zone de dépôt ;](assets/filter-dropzone.png)

1. Pour plus d’informations, passez à l’une des sections suivantes, selon le type de composant que vous ajoutez :

   * [Ajout de dimensions à un projet](#add-dimensions-to-a-project)

   * [Ajout de mesures à un projet](#add-metrics-to-a-project)

   * [Ajout de segments à un projet](#add-segments-to-a-project)

   * [Ajout de périodes à un projet](#add-date-ranges-to-a-project)

## Ajout de dimensions à un projet

[Dimensions](/help/components/dimensions/overview.md) sont des variables d’Adobe Analytics qui contiennent généralement des valeurs de chaîne. En revanche, les [mesures](/help/components/calc-metrics/calc-metr-overview.md) contiennent des valeurs numériques liées à une dimension. Un rapport de base présente des lignes de valeurs de chaîne (dimension) en fonction d’une colonne de valeurs numériques (mesure).

1. Commencez à ajouter une dimension à votre projet dans Analysis Workspace, comme décrit dans la section [Commencer à ajouter des composants à un projet](#begin-adding-components-to-a-project).

1. Choisissez l’une des méthodes suivantes pour ajouter des dimensions et déterminer le type de données à analyser :

   * Faites glisser une dimension sur une visualisation (un tableau à structure libre, par exemple) dans Analysis Workspace.

     ![Ajout de dimensions à un projet](assets/add-dimensions.png)

   * Faites glisser une ou plusieurs dimensions du rail de gauche sur la zone de dépôt de segments pour créer un segment ad hoc, comme décrit dans la section [Ajout de segments à un projet](#add-segments-to-a-project).

Pour plus d’informations sur l’utilisation des dimensions dans Analysis Workspace, voir [Aperçu des dimensions](/help/components/dimensions/view-dimensions.md), [Ventilation des dimensions](/help/components/dimensions/t-breakdown-fa.md), et [Dimensions de répartition du temps](/help/components/dimensions/time-parting-dimensions.md).

## Ajout de mesures à un projet

Les mesures vous permettent de quantifier les points de données dans Analysis Workspace. Elles sont généralement utilisées comme colonnes dans une visualisation et liées aux dimensions.

Pour ajouter une mesure à un projet dans Analysis Workspace :

1. Commencez à ajouter une mesure à votre projet dans Analysis Workspace, comme décrit dans la section [Commencer à ajouter des composants à un projet](#begin-adding-components-to-a-project).

1. Choisissez l’une des méthodes suivantes pour ajouter une mesure dans Analysis Workspace :

   * Faites glisser une mesure sur la zone de dépôt des mesures dans un tableau à structure libre vide pour afficher les tendances de cette mesure sur la période du projet.

     ![Ajout d’une mesure à un projet](assets/add-metrics.png)

   * Faire glisser une mesure lorsqu’une dimension est présente pour la comparer à chaque élément de la dimension.

   * Faire glisser une mesure au-dessus d’un en-tête de mesure existant pour le remplacer.

   * Faire glisser une mesure près d’un en-tête pour afficher les deux côte à côte.

Pour plus d’informations sur les mesures, voir [Mesures calculées - Aperçu](/help/components/calc-metrics/calc-metr-overview.md).

## Ajout de filtres à un projet

[Filtres](/help/components/filters/filters-overview.md) vous permettent d’identifier des sous-ensembles de visiteurs en fonction de caractéristiques ou d’interactions spécifiques.

Pour ajouter un filtre à un projet dans Analysis Workspace :

1. Commencez à ajouter un filtre à votre projet dans Analysis Workspace, comme décrit dans la section [Commencer à ajouter des composants à un projet](#begin-adding-components-to-a-project).

1. Choisissez l’une des méthodes suivantes pour commencer à filtrer votre panneau :

   * Faites glisser un filtre individuel du rail de gauche vers la zone de dépôt des segments.

     ![Déposer un filtre dans la zone de dépôt](assets/filter-dropzone.png)

   * Maintenez la touche Maj ou Ctrl enfoncée pour sélectionner plusieurs segments dans le rail de gauche, puis maintenez la touche Maj enfoncée lorsque vous les déposez sur la zone de dépôt des segments.

     ![déposer plusieurs filtres dans la zone de dépôt](assets/filter-dropzone-multiple.png)

     Cela crée un menu déroulant qui permet aux utilisateurs du panneau de choisir le filtre à appliquer. Le menu déroulant contient un [!UICONTROL **Aucun filtre**] que les utilisateurs peuvent sélectionner, ce qui permet de ne pas filtrer le panneau.

     Vous pouvez sélectionner (x) pour supprimer n’importe quelle option du menu déroulant. Si vous supprimez la variable [!UICONTROL **Aucun filtre**] , un filtre est requis.

   * Créez des segments ad hoc en faisant glisser des composants non liés aux segments sur la zone de dépôt. Cela peut vous faire gagner du temps et vous faire gagner du temps lorsque vous passez dans le créateur de segments. Les segments ainsi créés sont automatiquement définis comme des segments de niveau accès. Vous pouvez modifier cette définition en cliquant sur l’icône d’informations (i) à côté du segment, puis sur l’icône de modification en forme de crayon, et la modifier dans le créateur de segments.

     Les segments ad hoc sont un type de segment rapide et sont locaux au projet. Ils ne s’affichent pas dans le rail de gauche à moins que vous ne les rendiez publics.

     Pour en savoir plus, voir [Filtres rapides](/help/components/filters/quick-filters.md).

Pour plus d’informations sur l’utilisation de la zone de dépôt de segments dans un panneau pour filtrer le panneau, voir [Zone de dépôt](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Panneaux - Aperçu](/help/analysis-workspace/c-panels/panels.md).

## Ajout de périodes à un projet

[Plages de dates](/help/components/date-ranges/custom-date-ranges.md) détermine la période de création de rapports dans Analysis Workspace et peut être appliquée à un ou plusieurs panneaux au sein d’un projet.

Par défaut, chaque panneau comprend une plage de dates. Il existe plusieurs façons de mettre à jour une période pour un panneau. Pour mettre à jour une période pour un panneau dans Analysis Workspace, faites glisser un composant de période depuis le rail de gauche :

1. Commencez à ajouter une période à votre projet dans Analysis Workspace, comme décrit dans la section [Commencer à ajouter des composants à un projet](#begin-adding-components-to-a-project).

1. Faites glisser une plage de dates du rail de gauche vers la plage de dates actuelle dans la partie supérieure droite du panneau.

   ![déposer une période ;](assets/daterange-drop.png)

Pour plus d’informations sur l’utilisation des calendriers et des plages de dates dans Analysis Workspace, voir [Calendrier et plages de dates - Aperçu](/help/components/date-ranges/custom-date-ranges.md).
