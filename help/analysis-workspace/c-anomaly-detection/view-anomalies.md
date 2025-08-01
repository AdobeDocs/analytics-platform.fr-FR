---
description: Découvrez comment afficher et analyser les anomalies de données dans Analysis Workspace.
title: Affichage des anomalies
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 50%

---


# Afficher les anomalies

Vous pouvez afficher les anomalies dans Analysis Workspace sous forme de tableau ou de graphique en courbes.

## Affichage des anomalies dans un tableau {#section_869A87B92B574A38B017A980ED8A29C5}

Vous pouvez afficher les anomalies dans un tableau à structure libre de série temporelle.

1. Sélectionnez l’option ![Paramètre](/help/assets/icons/Setting.svg) dans l’en-tête de colonne, puis assurez-vous que l’option **[!UICONTROL Afficher les anomalies]** est sélectionnée dans la liste des options. Pour plus d’informations, consultez [Paramètres de colonne](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Le tableau présente les anomalies comme suit :

   ![ Anomalies détectées ](assets/anomaly-detected.png)

   Un ◥ s’affiche dans le coin supérieur droit de chaque ligne où une anomalie des données est détectée.

   La **ligne verticale colorée** de chaque ligne indique ➋ la valeur attendue. La **zone ombrée de couleur** dans chaque ligne ➊ indique la valeur réelle. La comparaison entre la ligne (valeur attendue) et la zone ombrée (valeur réelle) permet de déterminer la présence d’une anomalie. (Une observation est considérée comme anormale en fonction des techniques statistiques avancées décrites dans la section [Techniques statistiques utilisées dans la détection des anomalies](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

1. Sélectionnez ◥ dans le coin supérieur droit d’une ligne pour afficher les détails sur l’anomalie. Cela indique l’ampleur (en pourcentage) de l’écart supérieur ou inférieur entre la valeur réelle et la valeur attendue.

## Affichage des anomalies dans un graphique en courbes

Les graphiques en courbes sont la seule visualisation qui vous permet d’afficher les anomalies.

Afficher des anomalies dans un graphique en courbes :

1. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) dans l’en-tête de visualisation, puis assurez-vous que l’option [!UICONTROL **Afficher les anomalies**] est sélectionnée dans la liste des options. Pour plus d’informations, consultez [Ligne](/help/analysis-workspace/visualizations/line.md).

1. (Facultatif) Pour permettre à l’intervalle de confiance de mettre le graphique à l’échelle, sélectionnez ![Paramétrage](/help/assets/icons/Setting.svg) dans l’en-tête de visualisation, puis sélectionnez l’option **[!UICONTROL Autoriser les anomalies à mettre à l’échelle l’axe Y]**.

   Cette option n’est pas sélectionnée par défaut, car elle peut parfois rendre le graphique moins lisible.

   Le graphique en courbes présente les anomalies comme suit :

   ![Visualisation en ligne des anomalies détectées](assets/anomaly-detected-line.png)

   Un **point blanc** s’affiche sur la ligne chaque fois qu’une anomalie des données est détectée. (Une observation est considérée comme anormale en fonction des techniques statistiques avancées décrites dans la section [Techniques statistiques utilisées dans la détection des anomalies](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

   La **zone ombrée claire** est la marge de confiance, ou la plage attendue, où les valeurs doivent apparaître. Toute valeur située en dehors de cette plage attendue est une anomalie.

   Si le graphique en courbes comporte plusieurs mesures, seules les anomalies sont présentées et vous devez survoler chacune d’elles pour en connaître la marge de confiance.

   La **ligne pointillée** est la valeur exacte attendue.

1. Sélectionnez une anomalie (point blanc) pour afficher les informations suivantes :

   * Date à laquelle l’anomalie s’est produite.

   * Valeur brute de l’anomalie.

   * la valeur en pourcentage au-dessus ou en dessous de la valeur attendue, représentée par une ligne continue vert foncé ;








<!--
# View anomalies in Analysis Workspace

You can view anomalies in a table or in a line chart.

## View anomalies in a table {#table}

You can view anomalies in a time-series Freeform Table.

1. Select the column settings icon in the column header, then ensure that the [!UICONTROL **Anomalies**] option is selected in the list of options. For more information, see [Column settings](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Click away from the settings menu to view the updated table.

   ![An anomaly detection notification indicating 15% below expected.](assets/anomaly_detected.png)

1. Anomalies are shown in the table as follows:

   A **dark gray triangle** appears in the upper-right corner of each row where a data anomaly is detected.

   The colored **vertical line** in each row indicates the expected value. The colored **shaded area** in each row indicates the actual value. How the line (expected value) compares with the shaded area (actual value) determines whether there is an anomaly. (An observation is considered anomolous based on the advanced statistical techniques described in [Statistical techniques used in anomaly detection](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

1. Select the gray triangle in the upper-right corner of a row to view details about the anomaly. This shows the extent (as a percentage) to which the actual value diverges either above or below the expected value.

## View anomalies in a line chart {#line-chart}

A Line chart is the only visualization that allows you to view anomalies.

To view anomalies in a line chart:

1. Select the settings icon in the visualization header, then ensure that the [!UICONTROL **Show anomalies**] option is selected in the list of options. For more information, see [Line](/help/analysis-workspace/visualizations/line.md).

1. (Optional) To allow the confidence interval to scale the chart, select the settings icon in the visualization header, then select the option, **[!UICONTROL Allow anomalies to Scale Y-axis]**. 

   This option is not selected by default because it can sometimes make the chart less legible.
   
1. Click away from the settings menu to view the updated line chart.

      ![A line chart with an anomaly detected message indicating 15% above expected.](assets/anomaly_linechart.png)

   Anomalies are shown in the line chart as follows:
   
   A **white dot** appears on the line wherever a data anomaly is detected. (An observation is considered anomolous based on the advanced statistical techniques described in [Statistical techniques used in anomaly detection](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

   The **light shaded area** is the confidence band, or expected range, where values should occur. Any value that falls outside of this expected range is an anomaly. 

   If you have multiple metrics in the line chart, only the anomalies are shown and you have to hover over each anomaly to see the confidence band for that metric. 

   The **dotted line** is the exact expected value.

1. Click an anomaly (white dot) to view the following information:

   * The date the anomaly occurred 
   
   * The raw value of the anomaly 
   
   * The percentage value above or below the expected value, which is represented by the solid green line.
   
-->
