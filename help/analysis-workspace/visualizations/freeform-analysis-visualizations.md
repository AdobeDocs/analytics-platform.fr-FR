---
description: Représentez visuellement vos données dans Analysis Workspace.
keywords: Analysis Workspace
title: Visualisations - Aperçu
feature: Visualizations
exl-id: ca9e0561-7a54-487a-9fdc-3bcf34f9bdb1
role: User
source-git-commit: 714e37433b12713e45a66ebd64771c050edb89a5
workflow-type: tm+mt
source-wordcount: '1592'
ht-degree: 15%

---

# Visualisations - Aperçu

Workspace propose un certain nombre de visualisations qui vous permettent de générer des représentations visuelles de vos données. tels que les graphiques à barres, les graphiques en anneau, les histogrammes, les graphiques en courbes, les cartes, les tracés différés, etc.

## Types

Voici les types de visualisation disponibles dans Analysis Workspace :

| Icône | Nom | Description |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [Surface](/help/analysis-workspace/visualizations/area.md) | Visualisation de diagrammes de surface. Semblable à un graphique linéaire, mais avec une zone colorée sous la ligne. Utilisez un diagramme de surface si vous avez plusieurs mesures et souhaitez visualiser la zone exprimée par l’intersection de plusieurs mesures. |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barre](/help/analysis-workspace/visualizations/bar.md) | Visualisation en graphique à barres avec des barres verticales représentant différentes valeurs pour une ou plusieurs mesures. |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [Barre empilée](/help/analysis-workspace/visualizations/bar.md) | Visualisation en barres empilées avec des barres verticales représentant différentes valeurs pour une ou plusieurs mesures. |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [Puce](/help/analysis-workspace/visualizations/bullet-graph.md) | Visualisation de graphique à puces qui montre comment une valeur qui vous intéresse compare ou mesure par rapport à d’autres plages de performances (objectifs). |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [Tableau de cohortes](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Une visualisation de cohortes est un groupe de personnes partageant des caractéristiques communes au cours d’une période donnée. Un tableau de cohortes est utile pour l’analyse de la rétention, de la perte de clientèle ou de la latence. |
| ![Combo](/help/assets/icons/ComboChart.svg) | [Combo](combo-charts.md) | Un graphique combiné vous permet de créer rapidement une visualisation de comparaison sans avoir à créer un tableau au préalable. |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [Anneau](/help/analysis-workspace/visualizations/donut.md) | Tout comme un graphique circulaire, une visualisation en anneau affiche les données sous forme de parties ou de filtres d’un tout. |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [Abandon](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | Une visualisation Abandons montre où les personnes ont quitté (abandonné) une séquence prédéfinie de pages et ont poursuivi leur visite (chuté). |
| ![GraphPath](/help/assets/icons/GraphPathing.svg) | [Flux](/help/analysis-workspace/visualizations/c-flow/flow.md) | Une visualisation de flux affiche les chemins exacts des clients sur vos sites web et dans vos applications. |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | Une visualisation de tableau à structure libre est une visualisation interactive. La visualisation de tableau à structure libre est la base de l’analyse des données dans Workspace. |
| ![GraphHistogramme](/help/assets/icons/Histogram.svg) | [Histogramme](/help/analysis-workspace/visualizations/histogram.md) | Une visualisation sous forme d’histogramme regroupe les personnes, les visites ou les événements en intervalles en fonction d’un volume de mesure. |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [Barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) | Une visualisation en barres horizontales affiche des barres horizontales représentant différentes valeurs pour une ou plusieurs mesures. |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [Barre horizontale empilée](/help/analysis-workspace/visualizations/horizontal-bar.md) | Une visualisation en barres horizontales empilées affiche des barres horizontales représentant différentes valeurs pour une ou plusieurs mesures. |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [Synthèse des mesures clés](/help/analysis-workspace/visualizations/key-metric.md) | Une visualisation Synthèse des mesures clés combine les visualisations Ligne, Synthèse des changements et Nombre de résumés. |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Ligne](/help/analysis-workspace/visualizations/line.md) | Une visualisation en ligne représente les mesures à l’aide d’une ligne afin d’indiquer de quelle façon changent les valeurs au fil du temps. Un graphique en courbes utilise le temps le long de lʼaxe X. |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [Dispersion](/help/analysis-workspace/visualizations/scatterplot.md) | Une visualisation en graphique à dispersion affiche la relation entre les éléments de dimension et trois mesures au maximum. |
| ![PageRule](/help/assets/icons/PageRule.svg) | [En-tête de section](section-header.md) | Pour identifier et articuler des sections dans un panneau. |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [Résumé des changements](/help/analysis-workspace/visualizations/summary-number-change.md) | Une visualisation Synthèse des changements affiche la modification entre les cellules sélectionnées sous la forme d’un grand nombre ou d’un pourcentage. |
| ![123](/help/assets/icons/123.svg)</p> | [Numéro de résumé](/help/analysis-workspace/visualizations/summary-number-change.md) | Une visualisation de nombre récapitulatif affiche la cellule sélectionnée sous la forme d’un grand nombre. |
| ![Texte](/help/assets/icons/Text.svg) | [Texte](/help/analysis-workspace/visualizations/text.md) | Une visualisation de texte vous permet d’ajouter du texte défini par l’utilisateur à votre Workspace. Utile pour ajouter du contexte supplémentaire à votre analyse et à vos informations, en plus de tirer parti des descriptions des panneaux/visualisations. |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [Treemap](/help/analysis-workspace/visualizations/treemap.md)<p> | Une visualisation de graphique Treemap affiche des données hiérarchiques (structurées en arborescence) sous la forme d’un ensemble de rectangles imbriqués. |
| ![Type](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) | Une visualisation de Venn utilise des cercles pour représenter le chevauchement des mesures de trois filtres au maximum. |

<!-- Add beneath Horizontal bar in the table above: | [Journey canvas](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | Similar to Fallout, Journey canvas shows where persons left (fell out) and continued through (fell through) a predefined sequence of pages. <p>Unlike Fallout, Journey canvas supports not only linear journeys, but any number of entry points and paths. Furthermore, journeys can be created in Adobe Journey Optimizer and then analyzed in Journey canvas.</p> | -->

## Ajout de visualisations à un panneau

1. Ouvrez le projet Workspace dans lequel vous souhaitez ajouter une visualisation.

1. Utilisez l’une des méthodes suivantes pour ajouter la visualisation :

   ![Ajouter une visualisation](assets/add-visualization.png)

   * Dans le panneau de gauche, sélectionnez ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) **Visualisations**, puis faites glisser une visualisation sur le panneau auquel vous souhaitez ajouter la visualisation.

   * Dans le panneau où vous souhaitez ajouter la visualisation, sélectionnez ![Ajouter un cercle](/help/assets/icons/AddCircle.svg), puis choisissez l’icône représentant la visualisation que vous souhaitez ajouter. Passez la souris sur l’icône de chaque visualisation pour afficher le nom.

   * Ajoutez un [panneau vierge](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/blank-panel), puis sélectionnez la visualisation que vous souhaitez ajouter.

   * Dans le menu contextuel d’une visualisation existante dans votre projet Analysis Workspace, sélectionnez **[!UICONTROL Dupliquer la visualisation]** ou **[!UICONTROL Copier la visualisation]**.

   * Utilisez le menu **[!UICONTROL Insérer]** de Workspace pour insérer une visualisation.

   * Dans le menu contextuel d’une table à structure libre, sélectionnez **[!UICONTROL Visualiser]**. Sélectionnez ensuite la visualisation dans le sous-menu. En fonction de la sélection actuelle dans le tableau, Workspace détermine la visualisation à proposer et interprète les données pour créer la visualisation demandée.


## Légende

Une légende de visualisation vous permet de relier les données dʼun tableau source à une série tracée dans la visualisation. La légende est interactive : vous pouvez sélectionner un élément de légende pour afficher/masquer une série dans la visualisation, ce qui s’avère utile si vous souhaitez simplifier les données en cours de visualisation.

De plus, vous pouvez renommer les étiquettes de légende pour rendre les visuels plus exploitables. Remarque : **il nʼest pas** possible de modifier les légendes des visualisations Treemap, Puce, Résumé des changements, Synthèse des chiffres, Texte, Structure libre, Histogramme, Cohorte ou Flux.

Pour modifier une étiquette de légende :

1. Effectuez un clic droit sur l’une des étiquettes de légende.
1. Cliquez sur **[!UICONTROL Modifier l’étiquette]**.

   ![Une étiquette de légende et l&#39;option Editer l&#39;étiquette.](assets/edit-label.png)

1. Saisissez le nouveau texte de l’étiquette.
1. Appuyez sur **[!UICONTROL Entrée]** pour enregistrer.


## Paramètres

Chaque visualisation possède ses propres paramètres. Pour accéder aux paramètres de visualisation, sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Paramètres]** dans l’en-tête de visualisation afin d’afficher une fenêtre contextuelle.

Selon la visualisation, vous pouvez configurer

* des détails sur la source de données de la visualisation via l’onglet [**[!UICONTROL Source de données]**](#data-source) et
* paramètres de la visualisation via l’onglet [**[!UICONTROL Paramètres]**](#settings-1).

![Paramètres de visualisation](assets/visualization-settings.png)

### Source de données

Vous pouvez contrôler la source de données, les éléments ou les positions de cette source de données qui correspondent à une visualisation. Voir [Gérer les sources de données](t-sync-visualization.md) pour plus d’informations.

### Paramètres

Les paramètres de visualisation disponibles dépendent de la visualisation. Le tableau ci-dessous résume les paramètres les plus courants. Certaines visualisations comportent des paramètres spécifiques. Pour plus d’informations, consultez la documentation de visualisation individuelle.

| Option | Description |
| --- | --- |
| **[!UICONTROL Type de visualisation]** | Modifiez le type de visualisation utilisé pour visualiser les données. |
| **[!UICONTROL Granularité]** | Modifiez la granularité temporelle des visualisations de tendances. Cette modification sʼapplique également au tableau de source de données. |
| **[!UICONTROL Pourcentages]** | Afficher les valeurs en pourcentages. |
| **[!UICONTROL 100 % empilé]** | Convertissez le graphique en une visualisation 100 % empilée.  Applicable uniquement pour une visualisation à zones, à barres et à barres horizontales empilées. |
| **[!UICONTROL Légende visible]** | Afficher le texte de légende. |
| **[!UICONTROL Nombre max d’éléments]** | Limitez le nombre d’éléments affichés dans une visualisation. Lorsque cette option est sélectionnée, définissez le nombre d’éléments max. |
| **[!UICONTROL Afficher les annotations]** | Afficher les annotations créées pour cette visualisation. |
| **[!UICONTROL Masquer le titre]** | Masquez le titre de la visualisation. |
| **[!UICONTROL Faire commencer l’axe Y sur zéro]** | Forcer le bas de l’axe des ordonnées à zéro. Si toutes les valeurs mappées sur le graphique sont considérablement supérieures à zéro, la valeur par défaut du graphique rend le bas de l’axe des ordonnées non nul. Si vous activez cette option, l’axe des ordonnées est forcé à zéro (et le graphique est redessiné). |
| **[!UICONTROL Afficher l’axe double]** | Afficher les axes y gauche et droit pour deux mesures différentes. Cette option ne s’applique que si vous avez deux mesures. Les doubles axes s’avèrent utiles lorsque les mesures tracées présentent des dimensions différentes. |
| **[!UICONTROL Afficher l’axe X]** | Afficher l’axe des x dans la visualisation. |
| **[!UICONTROL Afficher l’axe Y]** | Afficher l’axe des ordonnées dans la visualisation. |
| **[!UICONTROL Afficher les barbells sur les lignes]** | Afficher des barres sur la visualisation en ligne dans une visualisation en graphique modifiable. |
| **[!UICONTROL Normalisation]** | Forcer les mesures à des proportions égales. Des proportions égales s’avèrent utiles lorsque les mesures tracées sont de tailles différentes. |
| **[!UICONTROL Afficher les anomalies]** | Améliorez les graphiques linéaires et les tableaux à structure libre en affichant la détection des anomalies. La détection des anomalies dans les visualisations linéaires comprend une valeur attendue (ligne en pointillé) et une plage attendue (bande ombrée). |
| **[!UICONTROL Afficher la prévision]** | Améliorez les graphiques linéaires et les tableaux à structure libre en affichant les valeurs de prévision. |
| **[!UICONTROL Afficher min]** | Afficher la valeur minimale dans la visualisation. |
| **[!UICONTROL Afficher max]** | Afficher la valeur maximale dans la visualisation. |
| **[!UICONTROL Afficher la courbe de tendance]** | Afficher une courbe de tendance dans la visualisation. Lorsque cette option est sélectionnée, vous pouvez sélectionner le type de tendance dans le menu déroulant. |



Vous pouvez personnaliser les paramètres de toutes les visualisations que vous créez. Pour plus d’informations, consultez [Préférences utilisateur](/help/analysis-workspace/user-preferences.md).


## Menu contextuel {#right-click}

Utilisez le menu contextuel (disponible par le biais d’une sélection alternative, par exemple lorsque vous utilisez la souris) sur un en-tête de visualisation pour accéder à des fonctionnalités supplémentaires pour une visualisation. Toutes les options ne sont pas disponibles pour toutes les visualisations.

![ Des paramètres de visualisation supplémentaires avec les options de clic droit s’affichent. Les options sont décrites dans la section suivante.](assets/right-click.png)

| Option | Description |
| --- | --- |
| **[!UICONTROL Insérer une visualisation copiée]** | Collez (insérez) une visualisation copiée à un autre emplacement du projet ou dans un projet complètement différent. |
| **[!UICONTROL Copier des données dans le Presse-papiers]** | Copiez les données de la visualisation dans le Presse-papiers. |
| **[!UICONTROL Copier la sélection dans le Presse-papiers]** | Copiez la sélection de la visualisation dans le Presse-papiers. |
| **[!UICONTROL Télécharger des éléments au format CSV (*nom de dimension*)]** | Téléchargez les éléments de dimension (jusqu’à 50 000 au maximum) de la visualisation sur votre appareil local. 50 000 éléments de dimension au maximum pour la dimension sélectionnée. |
| **[!UICONTROL Copier la visualisation]** | Copiez la visualisation afin de pouvoir insérer la visualisation à un autre emplacement du projet ou dans un projet complètement différent. |
| **[!UICONTROL Télécharger des données CSV]** | Téléchargez les données affichées de la visualisation sur votre appareil local. |
| **[!UICONTROL Exporter la table complète]** | Exportez le tableau complet vers des emplacements cloud désignés. Voir [Exporte des rapports de Customer Journey Analytics vers le cloud](../export/export-cloud.md) |
| **[!UICONTROL Dupliquer la visualisation]** | Effectuez un double exact de la visualisation. |
| **[!UICONTROL Modifier la description]** | Ajoutez (ou modifiez) une description textuelle pour la visualisation. Voir [Texte](text.md). |
| **[!UICONTROL Obtenir le lien de visualisation]** | Copiez et partagez un lien directement vers la visualisation. Une boîte de dialogue Partager le lien s’affiche. Sélectionnez Copier pour copier le lien dans le presse-papiers. |
| **[!UICONTROL Recommencer]** | Supprimez la configuration de la visualisation actuelle pour pouvoir la reconfigurer entièrement. |

## Configuration

Certaines visualisations (tableau de cohortes, Abandons, Flux, etc.) comportent une boîte de dialogue de configuration pour vous aider à créer la visualisation. Utilisez ![Modifier](/help/assets/icons/Edit.svg) en haut de la visualisation pour accéder à la configuration et la modifier.

![Volet de configuration](assets/configuration.png)

## Visualiser

Si vous ne savez pas quelle visualisation choisir, sélectionnez ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg) **[!UICONTROL Visualize]** dans n’importe quelle ligne de tableau à structure libre (disponible au survol). Cette sélection est la méthode la plus rapide pour ajouter une visualisation. Analysis Workspace devine avec précision quelle visualisation serait la mieux adaptée à vos données. Par exemple, si une ligne est sélectionnée, un [graphique linéaire](line.md) est créé. Si trois lignes de filtre sont sélectionnées, un diagramme [venn](venn.md) est créé.

![Visualisation rapide](assets/quick-viz.png)
