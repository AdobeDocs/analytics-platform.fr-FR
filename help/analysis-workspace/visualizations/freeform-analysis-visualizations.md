---
description: Découvrez les visualisations et les paramètres de visualisation d’Analysis Workspace.
keywords: Analysis Workspace
title: Visualisations - Aperçu
translation-type: tm+mt
source-git-commit: 1759bbf965e6b8d07e5a25867b73c3242dc49005
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 95%

---


# Visualisations - Aperçu

Workspace offre un certain nombre de visualisations qui vous permettent de générer des représentations visuelles de vos données, telles que des graphiques à barres, des graphiques en anneau, des histogrammes, des graphiques en courbes, des cartes, des tracés différés, etc. Chaque visualisation possède ses propres paramètres que vous pouvez gérer. Cliquez sur le nom de la visualisation pour obtenir des informations plus détaillées.

Didacticiel vidéo : [Types de visualisation en Analysis Workspace](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/visualization-types.html) (2:57)

| Nom de la visualisation | Description |
| --- | --- |
| [Surface](/help/analysis-workspace/visualizations/area.md) | Comme un graphique linéaire, mais avec une zone colorée sous la ligne. Utilisez un diagramme de surface si vous avez plusieurs mesures et souhaitez visualiser la zone exprimée par l’intersection de plusieurs mesures. |
| [Barre](/help/analysis-workspace/visualizations/bar.md) | Des barres verticales représentent plusieurs valeurs pour une ou plusieurs mesures. |
| [Graphique à puces](/help/analysis-workspace/visualizations/bullet-graph.md) | Permet de comparer ou de mesurer une valeur qui vous intéresse par rapport à d’autres plages de performances (objectifs). |
| [Tableau de cohortes](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Une cohorte est un groupe de personnes partageant des caractéristiques communes au cours d’une période spécifique. L’analyse des cohortes s’avère utile, par exemple, pour savoir de quelle façon une cohorte réagit par rapport à une marque. Vous pouvez facilement déceler des changements de tendances, pour y réagir en conséquence. |
| [Anneau](/help/analysis-workspace/visualizations/donut.md) | Semblable à un graphique circulaire, cette visualisation présente les données comme des portions ou des segments d’un tout. |
| [Abandon](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | Ceux-ci indiquent où les visiteurs ont quitté (abandonné) une suite prédéfinie de pages et où ils ont poursuivi leur visite à travers ces pages (diminution). |
| [Flux](/help/analysis-workspace/visualizations/c-flow/flow.md) | Présente les parcours des clients sur vos sites web et dans vos applications. |
| [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | Un tableau à structure libre n’est pas simplement un tableau de données, mais également une visualisation interactive. |
| [Histogramme](/help/analysis-workspace/visualizations/histogram.md) | Un histogramme est semblable à un graphique à barres, à ceci près qu’il répartit les chiffres en classes (intervalles). |
| [Barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) | Des barres horizontales représentent plusieurs valeurs pour une ou plusieurs mesures. |
| [Ligne](/help/analysis-workspace/visualizations/line.md) | Les mesures sont représentées sous la forme d’une ligne afin d’indiquer de quelle façon changent les valeurs au fil du temps. Pour pouvoir utiliser un graphique en courbes, le temps doit être défini comme une dimension. |
| [Graphique de dispersion](/help/analysis-workspace/visualizations/scatterplot.md) | Affiche la relation entre les éléments de dimension et trois mesures au maximum. |
| [Numéro de résumé](/help/analysis-workspace/visualizations/summary-number-change.md) | Selon la cellule sélectionnée, cette visualisation affiche les totaux et les résumés. |
| [Résumé des changements](/help/analysis-workspace/visualizations/summary-number-change.md) | Selon les cellules sélectionnées, cette visualisation compare les cellules les unes aux autres. |
| [Texte](/help/analysis-workspace/visualizations/text.md) | Permet d’ajouter du texte défini par l’utilisateur dans Workspace. |
| [Treemap](/help/analysis-workspace/visualizations/treemap.md) | Présente les données hiérarchiques (structurées en arbre) sous la forme d’un ensemble de rectangles imbriqués. |
| [Venn](/help/analysis-workspace/visualizations/venn.md) | Vous permet de faire glisser jusqu’à trois segments (depuis les composants) et une mesure afin de générer un diagramme de Venn. |

## Panneau Visualisations {#section_DC07F032FBEF4046A40F7B95C28DA018}

Pour afficher le panneau Visualisations, cliquez sur **[!UICONTROL Visualisations]** dans le rail de gauche.

![Résultat de l’étape](assets/visualizations.png)

Si vous utilisez Adobe Analytics, vous connaissez sans doute déjà la plupart des types de visualisation (les graphiques de surface, à barres, en anneau, en courbes). Néanmoins, Analysis Workspace fournit des paramètres de visualisation et de nombreux types de visualisation nouveaux ou uniques, dotés de fonctionnalités interactives.

## Paramètres de visualisation {#section_D3BB5042A92245D8BF6BCF072C66624B}

Pour accéder aux [!UICONTROL Paramètres de visualisation], faites glisser une visualisation sur le [!UICONTROL panneau Structure libre], puis cliquez sur l’icône d’engrenage [!UICONTROL Paramètres de visualisation].

>[!IMPORTANT]
>
>Les paramètres de visualisation visibles dépendent de la visualisation. Tous les paramètres ne s’appliquent pas à toutes les visualisations. En outre, certains paramètres avancés, tels les [paramètres d’histogramme](/help/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477), apparaissent **uniquement** pour certaines visualisations.

![](assets/visualization_settings.png)

| Paramètre | Description |
| --- | --- |
| Pourcentages | Affiche les valeurs en pourcentages. |
| 100 % empilé | Ce paramètre appliqué aux graphiques à zones empilées, à barres empilées ou à barres horizontales empilées offre un aperçu « 100 % empilé » du diagramme. Exemple : ![](assets/stacked_100_percent.png) |
| Légende visible | Permet de masquer le texte des détails du filtre pour la visualisation Synthèse des chiffres/Résumé des changements. |
| Nb max. d’éléments | Permet de limiter le nombre d’éléments affichés dans une visualisation. |
| Axe Y de l’ancre à zéro | Si toutes les valeurs mappées dans le graphique sont considérablement supérieures à zéro, le seuil de l’axe des ordonnées est par défaut NON NUL. Si cette option est activée, l’axe des ordonnées est obligatoirement ancré à zéro (et le graphique est retracé). |
| Normalisation | Force les mesures en proportions égales. |
| Afficher l’axe double | S’applique seulement s’il existe deux mesures : vous pouvez afficher un axe des ordonnées sur la gauche (pour une mesure) et un sur la droite (pour l’autre mesure). |
| Afficher les anomalies | Affine les graphiques linéaires et les tableaux à structure libre afin d’afficher les anomalies des données. |

## Icône Créer un visuel {#section_9C11D9DEDC42413AA53E69A71A509DFC}

Si vous ne savez pas quelle visualisation choisir, cliquez sur l’icône **[!UICONTROL Créer un visuel]** dans une ligne de tableau. Cette icône s’affiche quand vous pointez sur la ligne du tableau. Analysis Workspace s’affiche alors et détermine quelle visualisation serait la mieux adaptée à vos données. Si, par exemple, trois segments sont sélectionnés, un diagramme de Venn est créé. S’il y a plus de trois segments, un graphique à barres est créé. Pour d’autres types de données, cela peut aussi être un graphique linéaire, etc.

![](assets/create-visual.png)

## Clic droit sur le menu Visualisation/Panneau {#section_05B7914D4C9E443F97E2BFFDEC70240C}

Les paramètres qui dépendent d’un graphique sont accessibles en cliquant avec le bouton droit de la souris près d’un en-tête de visualisation. Certains ou tous les paramètres suivants sont disponibles :

![](assets/right-click_menu.png)

| Paramètre | Description |
| --- | --- |
| Insérer une visualisation/un panneau copié | Permet de coller (« insérer ») l’élément copié à un autre emplacement du projet, ou dans un tout autre projet. |
| Copier une visualisation/un panneau | Permet d’effectuer un clic droit et de copier une visualisation ou un panneau. |
| Dupliquer une visualisation/un panneau | Crée un double exact de la visualisation actuelle, que vous pouvez ensuite modifier. |
| Réduire tous les panneaux | Réduit tous les panneaux du projet. |
| Réduire toutes les visualisations dans le panneau | Réduit toutes les visualisations dans ce panneau de projet. |
| Développer tous les panneaux | Développe tous les projets du panneau. |
| Développer toutes les visualisations dans le panneau | Développe toutes les visualisations dans ce panneau de projet. |
| Modifier la description | Permet d’ajouter (ou de modifier) une description textuelle de la visualisation ou du panneau. Cette description s’affiche sous Projet > Informations et paramètres du projet. |
| Obtenir un lien vers le panneau | Permet de renvoyer un utilisateur vers un panneau spécifique dans un projet. |
| Obtenir le lien de la visualisation | Permet de copier et de partager le lien pour permettre à d’autres personnes d’accéder directement à cette visualisation. Les utilisateurs devront se connecter. |
| Recommencer | (Flux, diagramme de Venn, histogramme) Permet de supprimer la configuration de la visualisation actuelle et ouvre un nouveau panneau d’où vous pouvez la reconfigurer. |

## Modifier des étiquettes de légende {#section_94F1988CB4B9434BA1D9C6034062C3DE}

Permet de renommer les séries dans les légendes de visualisation (Abandons, Surface, Aires empilées, Barre, Barres empilées, Anneau, Histogramme, Barre horizontale, Barres empilées horizontales, Ligne, Graphique de dispersion et Venn) afin de créer un environnement plus convivial.

**Il n’est pas** possible de modifier les légendes pour les visualisations suivantes : Treemap, Puce, Résumé des changements, Synthèse des chiffres, Texte, Structure libre, Histogramme, Cohorte ou Flux.

Par exemple, pour modifier une étiquette de légende dans un graphique en ligne :

1. Effectuez un clic droit sur l’une des étiquettes de légende.
1. Cliquez sur **[!UICONTROL Modifier l’étiquette]**.

   ![](assets/edit-label.png)

1. Saisissez le nouveau texte de l’étiquette.
1. Appuyez sur **[!UICONTROL Entrée]** pour enregistrer.

Suivez le [lien vers la vidéo](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/series-label-editing.html) relative à cette rubrique.
