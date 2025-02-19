---
description: Dans Analysis Workspace, vous pouvez utiliser les mesures de deux façons.
title: Mesures
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 14%

---

# Mesures

Les mesures vous permettent de quantifier les points de données dans Analysis Workspace. Elles sont généralement utilisées comme colonnes dans une visualisation et liées aux dimensions.

## Utiliser des mesures dans Analysis Workspace

Les mesures sont flexibles dans leur utilisation dans Analysis Workspace. Faire glisser une mesure vers un tableau à structure libre vide pour afficher les tendances de cette mesure sur la période du projet. Vous pouvez également faire glisser une mesure lorsqu’une dimension est présente pour la comparer à chaque élément de dimension. Faire glisser une mesure au-dessus d’un en-tête de mesure existant la remplace et faire glisser une mesure près d’un en-tête permet d’afficher les deux côte à côte.

Pour plus d’informations sur l’ajout de mesures et d’autres types de composants à Analysis Workspace, voir [Utiliser des composants dans Analysis Workspace](/help/components/use-components-in-workspace.md).


## Types de mesures

Adobe propose plusieurs types de mesures à utiliser dans Analysis Workspace :


* **Mesures standard** : les mesures standard sont par exemple les personnes, les sessions, les événements.

  Contrairement à Adobe Analytics, Customer Journey Analytics vous permet de définir des mesures standard de manière flexible dans le cadre d’une connexion et d’une vue de données.

   * **Personnes** : la mesure Personnes dans Customer Journey Analytics est le nombre distinct des ID de personne. Selon ce que vous choisissez comme ID de personne lorsque vous configurez des jeux de données dans votre connexion, la mesure Personnes peut signifier différentes choses.
   * **Sessions** : la mesure Sessions dans Customer Journey Analytics est ce que vous définissez dans le cadre de la configuration des paramètres Sessions dans votre vue de données. Voir [ Paramètres de session ](/help/data-views/session-settings.md).
   * **Événements** : la mesure Événements en Customer Journey Analytics est composée des événements qui font partie de tout jeu de données d’événement que vous avez configuré dans le cadre de votre connexion.

* **Mesures calculées** ![Calculateur](/help/assets/icons/Calculator.svg) : mesures définies par l’utilisateur ou l’utilisatrice et basées sur des mesures standard, des nombres statiques ou des fonctions algorithmiques.

* **Modèles de mesures calculées** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : mesures définies par l’Adobe qui se comportent de la même manière que les mesures calculées. Vous pouvez les utiliser tels quels dans les projets Workspace ou enregistrer une copie pour personnaliser la logique. Voir [ Mesures calculées par défaut ](calc-metrics/cm-workflow/../default-calcmetrics.md).

Vous pouvez voir si une mesure est approuvée ![icône Approuvée](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) ou non. Si vous souhaitez plus de détails sur une mesure, pointez sur la mesure, puis sélectionnez ![Icône Infos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Voir [Informations sur les composants](use-components-in-workspace.md#component-info) pour plus d’informations.



## Mesures calculées

Les mesures calculées vous permettent de configurer facilement la manière dont les mesures sont liées les unes aux autres à l’aide d’opérateurs simples ou de fonctions statistiques. Consultez [ Présentation des mesures calculées ](/help/components/calc-metrics/calc-metr-overview.md) pour plus d’informations.

<!--

There are several ways to create calculated metrics. See [Create calculated metrics]()

### Create calculated metrics for all projects

You can use the calculated metric builder to create calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. 

For information about how to access the calculated metrics builder, see [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Create calculated metrics for a single project

You can create quick calculated metrics that are available only for the project where they were created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, select **[!UICONTROL Create metric from selection]** from the context menu in a column header.

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the following options:

   * [!UICONTROL **Divide**]
   
   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Add**]

   * [!UICONTROL **Multiply**]

   Or, to open the calculated metric builder and create the calculated metric for all projects, select [!UICONTROL **Open in Calculated Metric Builder**], then continue with [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).


<!-- This video really shows an AA example using hits, etc.  Not suitable for CJA... >
+++ See the following video on how to create an implementation-less calculated metric from within Analysis Workspace.

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)


>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12&learn=on)

+++

-->

## Comparaison de mesures avec différents modèles d’attribution

Si vous souhaitez comparer rapidement et facilement deux modèles d’attribution pour une mesure, sélectionnez **[!UICONTROL Comparer les modèles d’attribution]** dans le menu contextuel d’une mesure.

Panneau ![Workspace mettant en surbrillance Comparer les modèles d’attribution](assets/compare-attribution.png)

Ce raccourci vous permet de comparer rapidement et facilement des modèles d’attribution.
