---
description: Un histogramme est semblable à un graphique à barres, à ceci près qu’il regroupe les chiffres par classes (intervalles).
title: Histogramme
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 42%

---

# Histogramme {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_histogram_button"
>title="Histogramme"
>abstract="Créez une visualisation sous forme d’histogramme représentant la distribution des données numériques en groupes de plages."

<!-- markdownlint-enable MD034 -->


La visualisation ![Histogramme](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogramme]** est similaire à une visualisation [!UICONTROL Barre], mais elle regroupe les nombres en plages (intervalles). Analytics automatise la classification des chiffres. Vous pouvez toutefois modifier les paramètres dans les [Paramètres avancés](#advanced-settings).

## Sélectionnez l’option  

Pour créer un histogramme, procédez comme suit :

1. Ajoutez une visualisation ![Histogramme](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogramme]**. Voir [Ajout d’une visualisation à un panneau](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Faites glisser une mesure depuis la liste des composants **[!UICONTROL Mesures]** ou sélectionnez une mesure dans le menu déroulant [!UICONTROL *Ajouter une mesure*] .
1. (Facultatif) Sélectionnez **[!UICONTROL Afficher les paramètres avancés]**. Voir [Paramètres avancés](#advanced-settings).
1. Sélectionnez la **[!UICONTROL Version]**.

>[!NOTE]
>
>Les histogrammes prennent seulement en charge les mesures standard, et non les mesures calculées.

Dans l’exemple ci-dessous, un histogramme est utilisé pour regrouper des sessions pour le nombre de personnes. L’histogramme montre que la plupart des personnes ont entre 16 et 21 sessions pour la période sélectionnée.

![](assets/histogram.png)

## Paramètres avancés

Dans le cadre de la visualisation, des paramètres d’histogramme spécifiques sont disponibles.

| Paramètres de l’histogramme | Description |
|---|---|
| **[!UICONTROL Pointeur de démarrage]** | Détermine par quel intervalle commence l’histogramme. « 1 » par défaut. Peut être défini sur 0 à l’infini (aucun nombre négatif). |
| **[!UICONTROL Buckets de mesure]** | Permet d’augmenter ou de réduire le nombre de classes de données (intervalles). Il ne peut pas y avoir plus de 50 intervalles. |
| **[!UICONTROL Taille du compartiment de mesure]** | Permet de définir la taille de chaque intervalle. Vous pouvez par exemple modifier la taille de l’intervalle d’une page vue à deux pages vues. |
| **[!UICONTROL Méthode de comptage]** | Sélectionnez **[!UICONTROL Personne]**, **[!UICONTROL Session]** ou **[!UICONTROL Événement]**. Par exemple, pages vues par session, pages vues par personne ou pages vues par événement. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exemples** :

| Commencer le compartiment | Blocs de mesures | Taille de l’intervalle de mesures | Résultats |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histogramme, compartiment de départ 1, intervalles de mesure 5, taille de compartiment de mesure 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histogramme, regroupement de démarrage 0, regroupement de mesures 3, taille de regroupement de mesures 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Paramètres de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu contextuel de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>


## Blog post

Reportez-vous à cet article de blog sur les informations relatives à l&#39;[utilisation d&#39;histogrammes pour identifier des valeurs de données inattendues](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168).
