---
title: Visualisations
description: Cas d’utilisation des visualisations pour l’extension BI dans divers outils BI de Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: cb0102923f10f39becd40cc4187d2e11fb8c4e2f
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 25%

---

# Visualisations


Vous souhaitez comprendre comment les visualisations, disponibles dans Customer Journey Analytics, peuvent être créées de manière similaire à l’aide des visualisations disponibles dans les outils de BI.

+++ Customer Journey Analytics

Customer Journey Analytics comporte plusieurs visualisations. Consultez [Visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) pour une introduction et un aperçu de toutes les visualisations possibles.

+++

+++ Outils de BI

>[!BEGINTABS]

>[!TAB Bureau Power BI]

## Comparaison

Pour la plupart des visualisations Customer Journey Analytics, Power BI Desktop offre des expériences équivalentes. Voir le tableau ci-dessous.

| Icône | Visualisation Customer Journey Analytics | Visualisation de Power BI Desktop |
| :---: | --- | ---|
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [Surface](/help/analysis-workspace/visualizations/area.md) | [Graphique en aires, Graphique en aires empilées et Graphique en aires 100 %](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#area-charts-basic-layered-and-stacked) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barre](/help/analysis-workspace/visualizations/bar.md) | [Graphique à colonnes groupées](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [Barres empilées](/help/analysis-workspace/visualizations/bar.md) | [Graphique à colonnes empilées et Graphique à colonnes 100 %empilées](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![Graphique à puces](/help/assets/icons/GraphBullet.svg)</p> | [Puces](/help/analysis-workspace/visualizations/bullet-graph.md) |  |
| ![ChiffresTexte](/help/assets/icons/TextNumbered.svg) | [Table de cohorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![Combo](/help/assets/icons/ComboChart.svg) | [Combo](/help/analysis-workspace/visualizations/combo-charts.md) | [Graphique en courbes et histogrammes empilés, et Graphique en courbes et histogramme organisé en grappes](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#combo-charts) |
| ![Graphique à anneaux](/help/assets/icons/GraphDonut.svg) | [Anneau](/help/analysis-workspace/visualizations/donut.md) | [Graphique en anneau](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#doughnut-charts) |
| ![Entonnoir de conversion](/help/assets/icons/ConversionFunnel.svg) | [Abandon](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | [Funnel](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#funnel-charts). |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [Flux](/help/analysis-workspace/visualizations/c-flow/flow.md) | Arborescence de décomposition ? |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [Tableau](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#tables) et [Matrice](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#matrix) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [Histogramme](/help/analysis-workspace/visualizations/histogram.md) |  |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [Barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Graphique à barres groupées](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [Barres empilées horizontales](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Graphique à barres empilées et Graphique à barres empilées 100 %](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![Branch3](/help/assets/icons/Branch3.svg) | [Zone de travail de parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | [&#x200B; Arborescence de décomposition &#x200B;](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#decomposition-tree) |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [Résumé des mesures clés](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Ligne](/help/analysis-workspace/visualizations/line.md) | [Graphique linéaire](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#line-charts) |
| ![Nuage de points](/help/assets/icons/GraphScatter.svg) | [Dispersion](/help/analysis-workspace/visualizations/scatterplot.md) | [Graphique de dispersion](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#scatter) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [En-tête de section](/help/analysis-workspace/visualizations/section-header.md) | [Zone de texte](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![DéplacementHautBas](/help/assets/icons/MoveUpDown.svg) | [Résumé des changements](/help/analysis-workspace/visualizations/summary-number-change.md) | [Carte](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![123](/help/assets/icons/123.svg)</p> | [Numéro de résumé](/help/analysis-workspace/visualizations/summary-number-change.md) | [Carte](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![Texte](/help/assets/icons/Text.svg) | [Texte](/help/analysis-workspace/visualizations/text.md) | [Zone de texte](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [Plan en arborescence](/help/analysis-workspace/visualizations/treemap.md)<p> | [Plan en arborescence](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#treemaps) |
| ![Type](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) | |


## Accéder en profondeur

Power BI prend en charge un [mode d’exploration](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill) pour explorer les détails détaillés de certaines visualisations. Dans l’exemple ci-dessous, vous analysez le chiffre d’affaires des achats pour les catégories de produits. Dans le menu contextuel d’une barre représentant une catégorie de produits, vous pouvez sélectionner **[!UICONTROL Analyser en profondeur]**.

![Zoom Power BI](../assets/uc15-powerbi-drilldown.png)

L’analyse en profondeur met à jour la visualisation avec le chiffre d’affaires des achats des produits de la catégorie de produits sélectionnée.

![Exploration vers le haut de Power BI](../assets/uc15-powerbi-drillup.png)

L’analyse aboutit à la requête SQL suivante qui utilise une clause `WHERE` :

```sql
select "_"."product_category" as "c25",
    "_"."product_name" as "c26",
    "_"."a0" as "a0"
from 
(
    select "_"."product_category",
        "_"."product_name",
        "_"."a0"
    from 
    (
        select "_"."product_category",
            "_"."product_name",
            "_"."a0"
        from 
        (
            select "rows"."product_category" as "product_category",
                "rows"."product_name" as "product_name",
                sum("rows"."purchase_revenue") as "a0"
            from 
            (
                select "_"."product_category",
                    "_"."product_name",
                    "_"."purchase_revenue"
                from "public"."cc_data_view" "_"
                where ("_"."daterange" >= date '2023-01-01' and "_"."product_category" = 'Fishing') and "_"."daterange" < date '2024-01-01'
            ) "rows"
            group by "product_category",
                "product_name"
        ) "_"
        where not "_"."a0" is null
    ) "_"
) "_"
order by "_"."product_category",
        "_"."product_name"
limit 1001
```

>[!TAB  Tableau Desktop ]

## Comparaison

Pour la plupart des visualisations Customer Journey Analytics, Tableau Desktop offre des expériences équivalentes. Voir le tableau ci-dessous.

| Icône | Visualisation Customer Journey Analytics | Visualisation de Power BI Desktop |
| :---: | --- | ---|
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [Surface](/help/analysis-workspace/visualizations/area.md) | [Graphique en aires](https://help.tableau.com/current/pro/desktop/en-us/qs_area_charts.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barre](/help/analysis-workspace/visualizations/bar.md) | [Graphique à barres](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [Barres empilées](/help/analysis-workspace/visualizations/bar.md) |  |
| ![Graphique à puces](/help/assets/icons/GraphBullet.svg)</p> | [Puces](/help/analysis-workspace/visualizations/bullet-graph.md) | [Graphique à puces](https://help.tableau.com/current/pro/desktop/en-us/qs_bullet_graphs.htm) |
| ![ChiffresTexte](/help/assets/icons/TextNumbered.svg) | [Table de cohorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![Combo](/help/assets/icons/ComboChart.svg) | [Combo](/help/analysis-workspace/visualizations/combo-charts.md) | [Graphiques combinés](https://help.tableau.com/current/pro/desktop/en-us/qs_combo_charts.htm) |
| ![Graphique à anneaux](/help/assets/icons/GraphDonut.svg) | [Anneau](/help/analysis-workspace/visualizations/donut.md) | |
| ![Entonnoir de conversion](/help/assets/icons/ConversionFunnel.svg) | [Abandon](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [Flux](/help/analysis-workspace/visualizations/c-flow/flow.md) |  |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [Tableau de texte](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_text.htm) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [Histogramme](/help/analysis-workspace/visualizations/histogram.md) | [Histogramme](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_histogram.htm) |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [Barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Graphique à barres](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [Barres empilées horizontales](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Graphique à barres](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![Branch3](/help/assets/icons/Branch3.svg) | [Zone de travail de parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [Résumé des mesures clés](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Ligne](/help/analysis-workspace/visualizations/line.md) | [Graphique linéaire](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_line.htm) |
| ![Nuage de points](/help/assets/icons/GraphScatter.svg) | [Dispersion](/help/analysis-workspace/visualizations/scatterplot.md) | [Graphique de dispersion](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_scatter.htm) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [En-tête de section](/help/analysis-workspace/visualizations/section-header.md) |  |
| ![DéplacementHautBas](/help/assets/icons/MoveUpDown.svg) | [Résumé des changements](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![123](/help/assets/icons/123.svg)</p> | [Numéro de résumé](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![Texte](/help/assets/icons/Text.svg) | [Texte](/help/analysis-workspace/visualizations/text.md) | |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [Plan en arborescence](/help/analysis-workspace/visualizations/treemap.md)<p> | [Plan en arborescence](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_treemap.htm) |
| ![Type](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) | |


## Accéder en profondeur

Tableau prend en charge [mode de hiérarchisation](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill) via [hiérarchies](https://help.tableau.com/current/pro/desktop/en-us/qs_hierarchies.htm). Dans l’exemple ci-dessous, vous créez une hiérarchie lorsque vous sélectionnez le champ **[!UICONTROL Nom du produit]** dans **[!UICONTROL Tableaux]** et que vous le faites glisser en haut de **[!UICONTROL Catégorie de produits]**. Ensuite, dans le menu contextuel d’une barre représentant une catégorie de produits, vous pouvez sélectionner **[!UICONTROL + Analyser en profondeur]**.

![Analyse Tableau](../assets/uc15-tableau-drilldown.png)

L’analyse en profondeur met à jour la visualisation avec le chiffre d’affaires des achats des produits de la catégorie de produits sélectionnée.

![Exploration Tableau](../assets/uc15-tableau-drillup.png)

L’analyse aboutit à la requête SQL suivante qui utilise une clause GROUP BY :

```sql
SELECT CAST("cc_data_view"."product_category" AS TEXT) AS "product_category",
  CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1,
  2
```

La requête ne limite **pas** les résultats à la catégorie de produits sélectionnée ; seule la visualisation affiche la catégorie de produits sélectionnée.

![Exploration Tableau](../assets/uc15-tableau-drillup2.png)

Vous pouvez également créer un tableau de bord d’exploration en profondeur dans lequel un élément visuel est le résultat de la sélection dans un autre élément visuel. Dans l’exemple ci-dessous, la visualisation **[!UICONTROL Catégories de produits]** est utilisée comme filtre pour mettre à jour le tableau **[!UICONTROL Noms de produits]**. Ce filtre de visualisation est destiné aux clients uniquement et n’entraîne pas de requête SQL supplémentaire.

![Filtre de visualisation Tableau](../assets/uc15-tableau-visualizationfilter.png)


>[!TAB Looker]

## Comparaison

Pour la plupart des visualisations Customer Journey Analytics, Looker offre des expériences équivalentes. Voir le tableau ci-dessous.

| Icône | Visualisation Customer Journey Analytics | Visualisation de Power BI Desktop |
| :---: | --- | ---|
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [Surface](/help/analysis-workspace/visualizations/area.md) | [Graphique en aires](https://cloud.google.com/looker/docs/area-options) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barre](/help/analysis-workspace/visualizations/bar.md) | [Graphique à barres](https://cloud.google.com/looker/docs/bar-options) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [Barres empilées](/help/analysis-workspace/visualizations/bar.md) | [Graphique à barres](https://cloud.google.com/looker/docs/bar-options) |
| ![Graphique à puces](/help/assets/icons/GraphBullet.svg)</p> | [Puces](/help/analysis-workspace/visualizations/bullet-graph.md) | [Graphique à puces](https://cloud.google.com/looker/docs/bullet-chart) |
| ![ChiffresTexte](/help/assets/icons/TextNumbered.svg) | [Table de cohorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![Combo](/help/assets/icons/ComboChart.svg) | [Combo](/help/analysis-workspace/visualizations/combo-charts.md) | [Personnalisation des visualisations](https://cloud.google.com/looker/docs/creating-visualizations#customizing_visualizations_with_chart_settings) |
| ![Graphique à anneaux](/help/assets/icons/GraphDonut.svg) | [Anneau](/help/analysis-workspace/visualizations/donut.md) | [Anneau](https://cloud.google.com/looker/docs/donut-multiples-options) |
| ![Entonnoir de conversion](/help/assets/icons/ConversionFunnel.svg) | [Abandon](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | [Entonnoir](https://cloud.google.com/looker/docs/funnel-options) |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [Flux](/help/analysis-workspace/visualizations/c-flow/flow.md) | [&#x200B; Sankey &#x200B;](https://cloud.google.com/looker/docs/sankey) |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [Tableau](https://cloud.google.com/looker/docs/table-options) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [Histogramme](/help/analysis-workspace/visualizations/histogram.md) | |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [Barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Graphique à barres](https://cloud.google.com/looker/docs/bar-options) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [Barres empilées horizontales](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Graphique à barres](https://cloud.google.com/looker/docs/bar-options) |
| ![Branch3](/help/assets/icons/Branch3.svg) | [Zone de travail de parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) |  |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [Résumé des mesures clés](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Ligne](/help/analysis-workspace/visualizations/line.md) | [Graphique linéaire](https://cloud.google.com/looker/docs/line-options) |
| ![Nuage de points](/help/assets/icons/GraphScatter.svg) | [Dispersion](/help/analysis-workspace/visualizations/scatterplot.md) | [Graphique de dispersion](https://cloud.google.com/looker/docs/scatter-options) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [En-tête de section](/help/analysis-workspace/visualizations/section-header.md) |  |
| ![DéplacementHautBas](/help/assets/icons/MoveUpDown.svg) | [Résumé des changements](/help/analysis-workspace/visualizations/summary-number-change.md) | [Valeur unique](https://cloud.google.com/looker/docs/single-value-options) |
| ![123](/help/assets/icons/123.svg)</p> | [Numéro de résumé](/help/analysis-workspace/visualizations/summary-number-change.md) | [Valeur unique](https://cloud.google.com/looker/docs/single-value-options) |
| ![Texte](/help/assets/icons/Text.svg) | [Texte](/help/analysis-workspace/visualizations/text.md) | [Valeur unique](https://cloud.google.com/looker/docs/single-value-options) |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [Plan en arborescence](/help/analysis-workspace/visualizations/treemap.md) | [Plan en arborescence](https://cloud.google.com/looker/docs/treemap) |
| ![Type](/help/assets/icons/TwoDots.svg) | [&#x200B; Diagramme de Venn &#x200B;](/help/analysis-workspace/visualizations/venn.md) | [&#x200B; Diagramme de Venn &#x200B;](https://cloud.google.com/looker/docs/venn) |

>[!TAB Notebook Jupyter]

La comparaison des fonctionnalités de visualisation de **matplotlib.pyplot**, l’interface basée sur l’état de matplotlib, va au-delà de l’objectif de cet article. Consultez les exemples ci-dessus pour trouver de l’inspiration et la documentation [matplotlib.pyplot](https://matplotlib.org/3.5.3/api/_as_gen/matplotlib.pyplot.html).


>[!TAB RStudio]

La comparaison des fonctionnalités de visualisation de **ggplot2**, le package de visualisation de données en R, va au-delà de l’objectif de cet article. Consultez les exemples ci-dessus pour trouver de l’inspiration et la documentation [ggplot2](https://ggplot2.tidyverse.org/articles/ggplot2.html).

>[!ENDTABS]

