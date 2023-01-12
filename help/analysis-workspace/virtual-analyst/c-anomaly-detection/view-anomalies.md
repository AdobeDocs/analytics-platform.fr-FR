---
description: Vous pouvez afficher les anomalies dans un tableau ou un graphique en courbes.
title: Affichage des anomalies dans Analysis Workspace
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
source-git-commit: e62261d1d440c0a85e4cab95611c6e6272de6724
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 14%

---

# Affichage des anomalies dans Analysis Workspace

Vous pouvez afficher les anomalies dans un tableau ou un graphique en courbes.

## Affichage des anomalies dans un tableau {#section_869A87B92B574A38B017A980ED8A29C5}

Vous pouvez afficher les anomalies dans un tableau à structure libre à série chronologique.

1. Sélectionnez l’icône des paramètres de colonne dans l’en-tête de colonne, puis assurez-vous que la variable [!UICONTROL **Anomalies**] est sélectionnée dans la liste des options. Pour plus d’informations, voir [Paramètres des colonnes](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Cliquez en dehors du menu des paramètres pour afficher le tableau mis à jour.

   ![](assets/anomaly_detected.png)

1. Le tableau présente les anomalies comme suit :

   A **triangle gris foncé** s’affiche dans le coin supérieur droit de chaque ligne où une anomalie des données est détectée.

   La couleur **ligne verticale** dans chaque ligne indique la valeur attendue. La couleur **zone ombrée** dans chaque ligne indique la valeur réelle. La manière dont la ligne (valeur attendue) se compare à la zone ombrée (valeur réelle) détermine s’il existe une anomalie. (Une observation est considérée comme anormale en fonction des techniques statistiques avancées décrites dans la section [Techniques statistiques de la détection des anomalies](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).)

1. Sélectionnez le triangle gris dans le coin supérieur droit d’une ligne pour afficher les détails sur l’anomalie. Cela indique l’étendue (en pourcentage) à laquelle la valeur réelle varie au-dessus ou en dessous de la valeur attendue.

## Affichage des anomalies dans un graphique en courbes {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

Les graphiques en courbes sont la seule visualisation qui vous permet d’afficher les anomalies.

Pour afficher les anomalies dans un graphique en courbes :

1. Sélectionnez l’icône des paramètres dans l’en-tête de visualisation, puis assurez-vous que la variable [!UICONTROL **Afficher les anomalies**] est sélectionnée dans la liste des options. Pour plus d’informations, voir [Ligne](/help/analysis-workspace/visualizations/line.md).

1. (Facultatif) Pour permettre à l’intervalle de confiance de mettre le graphique à l’échelle, sélectionnez l’icône des paramètres dans l’en-tête de visualisation, puis sélectionnez l’option, **[!UICONTROL Autoriser les anomalies à mettre à l’échelle l’axe Y]**.

   Cette option n’est pas sélectionnée par défaut, car elle peut parfois rendre le graphique moins lisible.

1. Cliquez en dehors du menu des paramètres pour afficher le graphique en courbes mis à jour.

   ![](assets/anomaly_linechart.png)

   Les anomalies sont présentées dans le graphique en courbes comme suit :

   A **point blanc** s’affiche sur la ligne chaque fois qu’une anomalie des données est détectée. (Une observation est considérée comme anormale en fonction des techniques statistiques avancées décrites dans la section [Techniques statistiques de la détection des anomalies](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).)

   Le **zone ombrée claire** est la plage de confiance, ou la plage attendue, où les valeurs doivent se produire. Toute valeur située en dehors de cette plage prévue est une anomalie.

   Si le graphique en courbes comporte plusieurs mesures, seules les anomalies sont affichées et vous devez pointer sur chaque anomalie pour afficher la marge de confiance pour cette mesure.

   Le **ligne pointillée** est la valeur exacte attendue.

1. Cliquez sur une anomalie (point blanc) pour afficher les informations suivantes :

   * Date à laquelle l’anomalie s’est produite

   * la valeur brute de l’anomalie ;

   * la valeur en pourcentage au-dessus ou en dessous de la valeur attendue, représentée par une ligne continue vert foncé ;

