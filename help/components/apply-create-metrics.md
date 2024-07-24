---
description: Dans Analysis Workspace, vous pouvez utiliser les mesures de deux façons.
title: Mesures
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: cdab5d8b674527a1c3f950284daac65d0ab01900
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 18%

---

# Mesures

Les mesures vous permettent de quantifier les points de données dans Analysis Workspace. Elles sont généralement utilisées comme colonnes dans une visualisation et liées aux dimensions.

## Types de mesures

Adobe propose plusieurs types de mesures à utiliser dans Analysis Workspace :

* **Mesures standard** : les exemples de mesures standard sont Personnes, Sessions, Événements.

* **Mesures calculées** ![Icône Mesure calculée](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) : mesures définies par l’utilisateur et basées sur des mesures standard, des nombres statiques ou des fonctions algorithmiques.

* **Modèles de mesure calculée**  <img src="./assets/adobe-logo.svg" width="18"> : mesures définies par Adobe qui se comportent de la même manière que les mesures calculées. Vous pouvez les utiliser tels quels dans les projets Workspace ou enregistrer une copie pour personnaliser sa logique.


![Panneau Workspace mettant en surbrillance les mesures dans le volet de gauche.](assets/cja-metrics.png)

Vous pouvez voir si une mesure est approuvée ![Icône approuvée](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) ou non. Si vous souhaitez plus de détails sur une mesure, passez la souris sur la mesure, puis sélectionnez ![Icône Infos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


L’utilisation des mesures dans Analysis Workspace est flexible. Faites glisser une mesure vers un tableau à structure libre vide pour afficher les tendances de cette mesure sur la période du projet. Vous pouvez également faire glisser une mesure lorsqu’une dimension est présente pour la comparer à chaque élément de dimension. Le fait de faire glisser une mesure au-dessus d’un en-tête de mesure existant la remplace, tandis que le fait de faire glisser une mesure en regard d’un en-tête vous permet d’afficher les deux mesures côte à côte.

## Utilisation des mesures de dans Analysis Workspace

Les mesures peuvent être utilisées de différentes manières dans Analysis Workspace. Pour plus d’informations sur l’ajout de mesures et d’autres types de composants à Analysis Workspace, voir [Utilisation de composants dans Analysis Workspace](/help/components/use-components-in-workspace.md).

## Création de mesures calculées

Les mesures calculées vous permettent de voir facilement comment les mesures sont liées les unes aux autres à l’aide d’opérateurs simples ou de fonctions statistiques.

Il existe plusieurs façons de créer des mesures calculées. La méthode que vous choisissez détermine si la mesure calculée est disponible dans la liste des composants pour tous les projets ou uniquement dans le projet où elle a été créée.

### Création de mesures calculées pour tous les projets

Vous pouvez utiliser le créateur de mesures calculées pour créer des mesures calculées. Une fois créées de cette manière, les mesures calculées sont disponibles dans la liste des composants et peuvent ensuite être utilisées dans des projets à l’échelle de votre organisation.

Pour plus d’informations sur l’accès au créateur de mesures calculées, voir [Création de mesures](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Création de mesures calculées pour un seul projet

Vous pouvez créer des mesures calculées rapides qui ne sont disponibles que pour le projet dans lequel elles ont été créées.

Pour créer une mesure calculée pour un seul projet :

1. Dans Analysis Workspace, ouvrez le projet dans lequel vous souhaitez créer la mesure calculée.

1. Dans un tableau à structure libre, cliquez avec le bouton droit sur une ou plusieurs cellules de colonne d’en-tête, puis sélectionnez **[!UICONTROL Créer une mesure d’après la sélection]**

   ![Panneau Workspace surlignant Créer d’après la sélection](assets/create-metric-from-selection.png)

1. Pour créer une mesure calculée pour ce projet uniquement, choisissez l’une des options suivantes :

   * [!UICONTROL **Diviser**]

   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Ajouter**]

   * [!UICONTROL **Multiplier**]

   Ou, pour ouvrir le créateur de mesures calculées et créer la mesure calculée pour tous les projets, sélectionnez [!UICONTROL **Ouvrir dans le créateur de mesures calculées**], puis continuez avec [Créer des mesures](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

[Mesures calculées : mesures sans implémentation](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=fr) (3:42)

## Comparaison de mesures avec différents modèles d’attribution

Si vous souhaitez comparer rapidement et facilement un modèle d’attribution à un autre, cliquez avec le bouton droit de la souris sur une mesure et sélectionnez **[!UICONTROL Comparer les modèles d’attribution]** :

![ Panneau Workspace surlignant Comparaison des modèles d’attribution](assets/compare-attribution.png)

Ce raccourci vous permet de comparer rapidement et facilement deux modèles d’attribution sans faire glisser une mesure et la configurer deux fois.
