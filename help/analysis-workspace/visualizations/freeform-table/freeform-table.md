---
title: Vue d’ensemble du tableau à structure libre
description: Les tableaux à structure libre constituent la base de l’analyse des données dans Workspace.
feature: Visualizations
exl-id: e5ba9089-c575-47b3-af85-b8b2179396ac
role: User
source-git-commit: 55b312552d32070875714a77e1177bf0da5f9d87
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 25%

---

# Vue d’ensemble du tableau à structure libre {#freeform-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="Tableau à structure libre"
>abstract="Créez une visualisation sous forme de tableau à structure libre vide à l’aide de dimensions, de segments, de mesures et de périodes. Vous pouvez utiliser le tableau à structure libre comme base pour d’autres visualisations."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Cet article présente la visualisation des tableaux à structure libre dans_![ CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Voir [Tableau à structure libre](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table) pour la version_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de cet article._

>[!ENDSHADEBOX]


Dans Analysis Workspace, une visualisation ![Tableau](/help/assets/icons/Table.svg) **[!UICONTROL Tableau à structure libre]** est la base de l’analyse interactive des données. Vous pouvez faire glisser et déposer un ensemble de [composants](/help/components/overview.md) dans les lignes et les colonnes afin de créer un tableau personnalisé pour votre analyse. Lorsque chaque composant est déposé, le tableau se met immédiatement à jour afin que vous puissiez rapidement l’analyser et approfondir vos connaissances.

![Tableau à structure libre présentant les composants dans les lignes et les colonnes, y compris les visites et les commandes en ligne pour plusieurs pages web.](assets/opening-section.png)

Pour créer et configurer un [!UICONTROL tableau à structure libre] :

* Ajoutez une visualisation ![Tableau](/help/assets/icons/Table.svg) **[!UICONTROL Tableau à structure libre]**. Voir [Ajouter une visualisation à un panneau](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

## Tableaux automatisés

Le moyen le plus rapide de créer un tableau consiste à déposer les composants directement dans un projet, un panneau ou un tableau à structure libre vierge. Un tableau à structure libre est créé pour vous dans un format recommandé. [Regarder le tutoriel](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace).

![Un nouveau Panneau avec le composant Visites déposé sur l’espace de travail.](assets/automated-table.png)

## Créateur de tableau à structure libre

Si vous préférez d’abord ajouter plusieurs composants à votre tableau, puis effectuer le rendu des données, vous pouvez sélectionner **[!UICONTROL Activer le générateur de tableau]**. Lorsque le créateur est activé, vous pouvez faire glisser et déposer des dimensions, des répartitions, des mesures et des filtres afin de créer des tableaux qui répondent à des questions plus complexes. Les données sont mises à jour une fois que vous avez sélectionné **[!UICONTROL Créer]**.

![Un Créateur de tableau à structure libre affichant ](assets/table-builder.png)

## Interactions

Vous pouvez interagir et personnaliser un tableau à structure libre de différentes manières :

### Filtrer et trier

* Vous pouvez [filtrer et trier](filter-and-sort.md) les données d’un tableau.

### Lignes

* Vous pouvez rapidement [créer une visualisation](../freeform-analysis-visualizations.md#visualize) à partir d’une ou de plusieurs lignes à l’aide de ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg).
* Vous pouvez afficher davantage de lignes sur un seul écran en réglant la [densité d’affichage](/help/analysis-workspace/build-workspace-project/view-density.md) du projet.
* Chaque ligne de dimension peut afficher jusqu’à 400 lignes avant la pagination. Sélectionnez le nombre en regard de **[!UICONTROL Lignes]** dans le premier en-tête de colonne, pour afficher d’autres lignes sur une page. Accédez à une autre page à l’aide de ![ChevronRight](/help/assets/icons/ChevronRight.svg) dans le premier en-tête de colonne.
* Vous pouvez répartir les lignes en fonction de composants supplémentaires. Pour répartir plusieurs lignes à la fois, sélectionnez plusieurs lignes, puis faites glisser le composant suivant au-dessus des lignes sélectionnées. En savoir plus sur la [répartition](/help/components/dimensions/t-breakdown-fa.md).
* Les lignes peuvent être [filtrées](/help/components/filters/filters-overview.md) pour n’afficher que certains éléments. D’autres paramètres sont disponibles dans les [Paramètres des lignes](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md).

### Colonnes

* Les composants peuvent être empilés dans des colonnes afin de créer des mesures filtrées, des analyses sur plusieurs onglets, etc.
* La vue de chaque colonne peut être ajustée dans les [Paramètres des colonnes](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).
* Plusieurs actions sont disponibles via le [menu contextuel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu). Le menu propose différentes actions selon que vous sélectionnez l’en-tête, les lignes ou les colonnes du tableau.


## Paramètres

Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) pour afficher **[!UICONTROL Paramètres du tableau]**. Les visualisations spécifiques [paramètres](../freeform-analysis-visualizations.md#settings) suivantes sont disponibles :

### Source de données

| Option | Description |
|---|---|
| **[!UICONTROL Visualisations liées]**. | Répertorie toutes les visualisations liées. |
| **[!UICONTROL Afficher la source de données]** | Lorsque cette option n’est pas cochée, le tableau à structure libre qui fonctionne comme source de données pour la visualisation est masqué dans Workspace. |

### Paramètres

| Option | Description |
|---|---|
| **[!UICONTROL Aligner les dates de chaque colonne pour qu’elles commencent toutes sur la même ligne]** | Pour aligner ou non les dates de chaque colonne afin qu’elles commencent toutes sur la même ligne. |


## Menu contextuel

Les options [menu contextuel](../freeform-analysis-visualizations.md#context-menu) suivantes sont disponibles à partir de l’en-tête de la visualisation :

| Option | Description |
| --- | --- |
| **[!UICONTROL Insérer la visualisation copiée]**n | Collez (insérez) une visualisation copiée à un autre emplacement du projet, ou dans un tout autre projet. |
| **[!UICONTROL Copier les données dans le presse-papiers]** | Copiez les données de la visualisation dans le presse-papiers. |
| **[!UICONTROL Copier la sélection dans le presse-papiers]** | Copiez la sélection de la visualisation dans le presse-papiers. |
| **[!UICONTROL Télécharger les éléments au format CSV (*nom de dimension*)]** | Téléchargez immédiatement les éléments de dimension (jusqu’à 50 000 au maximum) de la visualisation sur votre appareil local. Un maximum de 50 000 éléments de dimension pour la dimension sélectionnée. |
| **[!UICONTROL Copier la visualisation]** | Copiez la visualisation afin de pouvoir l’insérer à un autre emplacement du projet, ou dans un tout autre projet. |
| **[!UICONTROL Télécharger les données CSV]** | Téléchargez immédiatement les données affichées de la visualisation sur votre appareil local. |
| **[!UICONTROL Exporter le tableau complet...]** | Exportez le tableau complet vers des emplacements cloud désignés. Voir [ Exporte des rapports de Customer Journey Analytics vers le cloud](../../export/export-cloud.md) |
| **[!UICONTROL Dupliquer la visualisation]** | Créez un doublon exact de la visualisation. |
| **[!UICONTROL Modifier la description]** | Ajoutez (ou modifiez) une description textuelle de la visualisation. Voir [Texte](../text.md). |
| **[!UICONTROL Obtenir le lien de la visualisation]** | Copiez et partagez un lien directement vers la visualisation. Une boîte de dialogue Partager le lien affiche le lien. Sélectionnez Copier pour copier le lien dans le presse-papiers. |
| **[!UICONTROL Recommencer]** | Supprimez la configuration de la visualisation actuelle afin de pouvoir la reconfigurer de zéro. |


>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Paramètres de visualisation ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu contextuel de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
