---
description: Un histogramme est semblable à un graphique à barres, à ceci près qu’il regroupe les chiffres par classes (intervalles).
title: Histogramme
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 75%

---

# Histogramme {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histogramme"
>abstract="Créez une visualisation sous forme d’histogramme représentant la distribution des données numériques en groupes de plages."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Cet article présente la visualisation de l’histogramme dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Voir [Histogramme](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/histogram) pour la version_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de cet article._

>[!ENDSHADEBOX]


La visualisation ![Histogramme](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogramme]** est semblable à une visualisation [!UICONTROL Barres], à ceci près qu’elle regroupe les chiffres par classes (intervalles). Analytics automatise la classification des chiffres. Vous pouvez toutefois modifier les paramètres dans les [Paramètres avancés](#advanced-settings).

## Utilisation

Pour créer un histogramme, procédez comme suit :

1. Ajoutez une visualisation ![Histogramme](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogramme]**. Voir [Ajouter une visualisation à un panneau](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Faites glisser une mesure à partir de la liste des composants **[!UICONTROL Mesures]** ou sélectionnez une mesure dans le menu déroulant [!UICONTROL *Ajouter une mesure*].
1. (Facultatif) Sélectionnez **[!UICONTROL Afficher les paramètres avancés]**. Voir [Paramètres avancés](#advanced-settings).
1. Sélectionnez la **[!UICONTROL Version]**.

>[!NOTE]
>
>Les histogrammes prennent seulement en charge les mesures standard, et non les mesures calculées.

Dans l’exemple ci-dessous, un histogramme est utilisé pour regrouper les sessions pour le nombre de personnes. L’histogramme indique que la plupart des personnes disposent de 16 à 21 sessions pour la période sélectionnée.

![Histogramme](assets/histogram.png)

## Paramètres avancés

Dans le cadre de la visualisation, des paramètres d’histogramme spécifiques sont disponibles.

| Paramètres de l’histogramme | Description |
|---|---|
| **[!UICONTROL Intervalle de début]** | Détermine par quel intervalle commence l’histogramme. « 1 » par défaut. Peut être défini sur 0 à l’infini (aucun nombre négatif). |
| **[!UICONTROL Intervalles de mesures]** | Permet d’augmenter ou de réduire le nombre de plages de données (intervalles). Le nombre maximal d’intervalles est de 50. |
| **[!UICONTROL Taille de l’intervalle de mesures]** | Permet de définir la taille de chaque intervalle. Vous pouvez par exemple modifier la taille de l’intervalle d’une page vue à deux pages vues. |
| **[!UICONTROL Méthode de comptage]** | Faites votre choix parmi **[!UICONTROL Compte global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Compte]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Groupe d’achat]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Opportunité]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Person]**, **[!UICONTROL Session]** ou **[!UICONTROL Event]**. Par exemple, pages vues par compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, pages vues par session ou pages vues par personne, ou pages vues par événement. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exemples** :

| Intervalle de début | Intervalles de mesures | Taille de l’intervalle de mesures | Résultats |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histogramme, intervalle de début 1, intervalle de mesures 5, intervalle de mesures 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histogramme, intervalle de début 0, intervalles de mesures 3, taille de l’intervalle de mesures 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Paramètres de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu contextuel de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>[Utiliser des histogrammes pour identifier les valeurs de données inattendues](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

