---
description: Dans Analysis Workspace, vous pouvez utiliser les mesures de deux façons.
title: Mesures
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
source-git-commit: a9751cad1ba49fe3e8c2c484e34d1725e063c2d4
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 23%

---

# Mesures

Les mesures vous permettent de quantifier les points de données dans Analysis Workspace. Elles sont généralement utilisées comme colonnes dans une visualisation et liées aux dimensions.


## Types de mesures

Adobe propose plusieurs types de mesures à utiliser dans Analysis Workspace :

* **Mesures standard**: Les exemples de mesures standard sont Personnes, Sessions, Événements.

* **Mesures calculées** ![Icône Mesure calculée](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg): Mesures définies par l’utilisateur et basées sur des mesures standard, des nombres statiques ou des fonctions algorithmiques.

* **Modèles de mesures calculées**  <img src="./assets/adobe-logo.svg" width="18"> : Mesures définies par l’Adobe qui se comportent de la même manière que les mesures calculées. Vous pouvez les utiliser tels quels dans les projets Workspace ou enregistrer une copie pour personnaliser sa logique.


![Mesures dans l’interface utilisateur](assets/cja-metrics.png)

Vous pouvez voir si une mesure est approuvée. ![Icône Approuvé](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  ou pas. Si vous souhaitez plus de détails sur une mesure, passez la souris sur la mesure, puis sélectionnez ![Icône Infos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


Leur utilisation dans Analysis Workspace est flexible. Faites glisser une mesure vers un tableau à structure libre vide pour afficher les tendances de cette mesure sur la période du projet. Vous pouvez également faire glisser une mesure lorsqu’une dimension est présente pour la comparer à chaque élément de dimension. Le fait de faire glisser une mesure au-dessus d’un en-tête de mesure existant la remplace, tandis que le fait de faire glisser une mesure en regard d’un en-tête vous permet d’afficher les deux mesures côte à côte.

## Mesures calculées 

Les mesures calculées vous permettent de voir facilement comment les mesures sont liées les unes aux autres à l’aide d’opérateurs simples ou de fonctions statistiques. Il existe plusieurs façons de créer des mesures calculées :

Vous pouvez sélectionner **[!UICONTROL Composants]** > **[!UICONTROL Mesures calculées]**. Vous accédez alors au [Créateur de mesures calculées](/help/components/calc-metrics/calc-metr-overview.md), où vous pouvez créer des mesures personnalisées à partir de mesures existantes.

Afin de faciliter la création rapide de mesures calculées, l’option **[!UICONTROL Créer une mesure d’après la sélection]** a été ajoutée au menu contextuel des colonnes dans les tableaux à structure libre. Cette option s’affiche lorsqu’une ou plusieurs cellules de colonne d’en-tête sont sélectionnées.

![Créer d’après une sélection](assets/create-metric-from-selection.png)

[Mesures calculées : mesures sans implémentation](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=fr) (3:42)

## Comparaison de mesures avec différents modèles d’attribution

Si vous souhaitez comparer rapidement et facilement un modèle d’attribution à un autre, cliquez avec le bouton droit de la souris sur une mesure et sélectionnez **[!UICONTROL Comparaison des modèles d’attribution]**:

![Comparer l’attribution](assets/compare-attribution.png)

Ce raccourci vous permet de comparer rapidement et facilement deux modèles d’attribution sans faire glisser une mesure et la configurer deux fois.
