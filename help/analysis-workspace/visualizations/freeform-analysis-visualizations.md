---
description: Représenter visuellement vos données en Analysis Workspace.
keywords: Analysis Workspace
title: Visualisations - Aperçu
translation-type: tm+mt
source-git-commit: d14817f28e757e94435c3b1059765fabe7cec54b
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 42%

---


# Visualisations - Aperçu

Workspace offre un certain nombre de visualisations qui vous permettent de générer des représentations visuelles de vos données, telles que des graphiques à barres, des graphiques en anneau, des histogrammes, des graphiques en courbes, des cartes, des tracés différés, etc. La plupart des types de visualisation vous seront familiers si vous utilisez Adobe Analytics. Néanmoins, Analysis Workspace fournit des paramètres de visualisation et de nombreux types de visualisation nouveaux ou uniques, dotés de fonctionnalités interactives.

Vous pouvez accéder aux visualisations à partir de l’icône située en haut à gauche de Workspace, d’un [panneau vierge](https://experienceleague.adobe.com/docs/analytics/analysis-workspace/panels/blank-panel.html) ou via le menu contextuel de votre flux de travail.

![](assets/viz-rail.png)

Les types de visualisation suivants sont disponibles en Analysis Workspace :

| Nom de la visualisation | Description |
| --- | --- |
| [Surface](/help/analysis-workspace/visualizations/area.md) | Comme un graphique linéaire, mais avec une zone colorée sous la ligne. Utilisez un diagramme de surface si vous avez plusieurs mesures et souhaitez visualiser la zone exprimée par l’intersection de plusieurs mesures. |
| [Barre](/help/analysis-workspace/visualizations/bar.md) | Des barres verticales représentent plusieurs valeurs pour une ou plusieurs mesures. |
| [Graphique à puces](/help/analysis-workspace/visualizations/bullet-graph.md) | Permet de comparer ou de mesurer une valeur qui vous intéresse par rapport à d’autres plages de performances (objectifs). |
| [Tableau de cohortes](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Une *`cohort`* est un groupe de personnes partageant des caractéristiques communes au cours d’une période spécifique. L’Analyse de cohortes est utile pour la rétention, l’exécution ou l’analyse de latence. |
| [Anneau](/help/analysis-workspace/visualizations/donut.md) | Semblable à un graphique circulaire, cette visualisation présente les données comme des portions ou des segments d’un tout. |
| [Abandon](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | Ceux-ci indiquent où les visiteurs ont quitté (abandonné) une suite prédéfinie de pages et où ils ont poursuivi leur visite à travers ces pages (diminution). Peut être défini sur des séquences éventuelles ou exactes |
| [Flux](/help/analysis-workspace/visualizations/c-flow/flow.md) | Indique les chemins d’accès exacts des clients à travers vos sites Web et applications. |
| [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | Un tableau à structure libre n’est pas simplement un tableau de données, mais également une visualisation interactive. Il constitue la base de l’analyse des données dans Workspace. |
| [Histogramme](/help/analysis-workspace/visualizations/histogram.md) | Un histogramme regroupe les visiteurs, les visites ou les accès en intervalles en fonction d’un volume de mesures. |
| [Barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) | Des barres horizontales représentent plusieurs valeurs pour une ou plusieurs mesures. |
| [Ligne](/help/analysis-workspace/visualizations/line.md) | Les mesures sont représentées sous la forme d’une ligne afin d’indiquer de quelle façon changent les valeurs au fil du temps. Un graphique en courbes utilise le temps le long de l’axe X. |
| [Graphique de dispersion](/help/analysis-workspace/visualizations/scatterplot.md) | Affiche la relation entre les éléments de dimension et trois mesures au maximum. |
| [Numéro de résumé](/help/analysis-workspace/visualizations/summary-number-change.md) | Affiche la cellule sélectionnée sous la forme d’un grand nombre. |
| [Résumé des changements](/help/analysis-workspace/visualizations/summary-number-change.md) | Affiche le changement entre les cellules sélectionnées sous la forme d’un grand nombre/pourcentage. |
| [Texte](/help/analysis-workspace/visualizations/text.md) | Permet d’ajouter du texte défini par l’utilisateur dans l’Workspace. Utile pour ajouter du contexte supplémentaire à votre analyse et à vos informations, en plus de tirer parti des descriptions de panneau/visualisation |
| [Treemap](/help/analysis-workspace/visualizations/treemap.md) | Présente les données hiérarchiques (structurées en arbre) sous la forme d’un ensemble de rectangles imbriqués. |
| [Venn](/help/analysis-workspace/visualizations/venn.md) | Utilise des cercles pour représenter le chevauchement des mesures de 3 segments au maximum. |

## Paramètres {#settings}

Chaque visualisation possède ses propres paramètres que vous pouvez gérer. Pour accéder à [!UICONTROL Paramètres de visualisation], cliquez sur l&#39;icône [!UICONTROL Paramètres de visualisation] de l&#39;engrenage.

![](assets/settings.png)

| Paramètre | Description |
| --- | --- |
| Type de visualisation | Modifiez le type de visuel utilisé pour représenter les données. |
| Granularité | Pour les visualisations de tendances, vous pouvez modifier la granularité temporelle (jour, semaine, mois, etc.) de cette liste déroulante. Cette modification s’applique également à la table de source de données. |
| Pourcentages | Affiche les valeurs en pourcentages. |
| 100 % empilé | Ce paramètre sur les visualisations empilées, empilées ou empilées à barres horizontales transforme le graphique en une visualisation à 100 % empilée. Exemple : ![Empilé à 100 %](assets/stacked_100_percent.png) |
| Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Synthèse des chiffres/Résumé des changements. |
| Nb max. d’éléments | Permet de limiter le nombre d’éléments affichés dans une visualisation. |
| Axe Y de l’ancre à zéro | Si toutes les valeurs mappées dans le graphique sont considérablement supérieures à zéro, le seuil de l’axe des ordonnées est par défaut NON NUL. Si cette option est activée, l’axe des ordonnées est obligatoirement ancré à zéro (et le graphique est retracé). |
| Normalisation | Force les mesures en proportions égales. Cela s’avère utile lorsque les mesures tracées présentent des dimensions très différentes. |
| Afficher l’axe double | S’applique seulement s’il existe deux mesures : vous pouvez afficher un axe des ordonnées sur la gauche (pour une mesure) et un sur la droite (pour l’autre mesure). Cela s’avère utile lorsque les mesures tracées présentent des dimensions très différentes. |
| Afficher les anomalies | Améliore les graphiques en courbes et les tableaux à structure libre en affichant la détection des anomalies. La détection des anomalies dans les visualisations en ligne comprend une valeur attendue (ligne en pointillé) et une plage attendue (bande ombrée). |

## Légende {#legend}

Une légende de visualisation vous permet de relier une date d’un tableau source à une série tracée dans la visualisation. La légende est interactive : vous pouvez cliquer sur un élément de légende pour afficher/masquer une série dans la visualisation. Cela s’avère utile si vous souhaitez simplifier les données visualisées.

De plus, vous pouvez renommer les libellés de légende pour rendre les visuels plus consommables. Remarque : l&#39;édition de légende ne s&#39;applique pas à **not** : Visualisations Treemap, Bullet, Summary Change/Number, Text, Freeform, Histogramme, Cohort ou Flux.

Pour modifier une étiquette de légende :

1. Effectuez un clic droit sur l’une des étiquettes de légende.
1. Cliquez sur **[!UICONTROL Modifier l’étiquette]**.

   ![](assets/edit-label.png)

1. Saisissez le nouveau texte de l’étiquette.
1. Appuyez sur **[!UICONTROL Entrée]** pour enregistrer.

Suivez le [lien vers la vidéo](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/series-label-editing.html) relative à cette rubrique.

## Menu contextuel {#right-click}

D’autres fonctionnalités d’une visualisation sont disponibles en cliquant avec le bouton droit sur l’en-tête de visualisation. Les paramètres varient selon la visualisation. Certains des paramètres disponibles sont les suivants :

![](assets/right-click.png)

| Paramètre | Description |
| --- | --- |
| Insérer un panneau copié/visualisation | Permet de coller (&quot;insérer&quot;) un panneau ou une visualisation copié à un autre emplacement du projet ou dans un projet complètement différent. |
| Copier la visualisation | Permet de cliquer avec le bouton droit de la souris et de copier une visualisation afin de l’insérer à un autre emplacement du projet ou dans un projet complètement différent. |
| [Télécharger les éléments au format CSV](/help/analysis-workspace/curate-share/download-send.md) | Téléchargez jusqu’à 50 000 éléments de dimension pour la dimension sélectionnée au format CSV. |
| [Télécharger les données au format CSV](/help/analysis-workspace/curate-share/download-send.md) | Téléchargez la source de données de visualisation au format CSV. |
| Dupliquer la visualisation | Crée un double exact de la visualisation actuelle, que vous pouvez ensuite modifier. |
| Modifier la description | Ajoutez (ou modifiez) une description textuelle de la visualisation. |
| Obtenir le lien de la visualisation | Permet d’orienter une personne vers une visualisation spécifique au sein d’un projet. Lorsque vous cliquez sur le lien, le destinataire doit se connecter avant d’être dirigé vers la visualisation exacte à laquelle il est lié. |
| Recommencer | (Fonctionne pour le flux, l’affichage, l’histogramme) Supprime la configuration de la visualisation actuelle afin que vous puissiez la reconfigurer de zéro. |

## Icône Créer un visuel {#quick-viz}

Si vous n’êtes pas sûr de la visualisation à sélectionner, cliquez sur l’icône **[!UICONTROL Créer un visuel]** dans une ligne de tableau (disponible au survol). Il s’agit de la méthode la plus rapide pour ajouter une visualisation. Analysis Workspace s’affiche alors et détermine quelle visualisation serait la mieux adaptée à vos données. Par exemple, si 1 ligne est sélectionnée, un graphique de tendance est créé. Si 3 lignes de segment sont sélectionnées, un diagramme de Venn est créé.

![](assets/quick-viz.png)
