---
description: Découvrez les mesures et comment les utiliser dans Adobe Analytics.
title: Mesures
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: f3c9a000ae5baa19cb5a6cf0e0343de3a9685b56
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 8%

---

# Mesures

Les mesures vous permettent de quantifier les points de données dans Analysis Workspace. Elles sont généralement utilisées comme colonnes dans une visualisation et liées aux dimensions.

## Utiliser des mesures dans Analysis Workspace

Les mesures sont flexibles dans leur utilisation dans Analysis Workspace. Faire glisser une mesure vers un tableau à structure libre vide pour afficher les tendances de cette mesure sur la période du projet. Vous pouvez également faire glisser une mesure lorsqu’une dimension est présente pour comparer cette mesure à chaque élément de dimension. Faire glisser une mesure au-dessus d’un en-tête de mesure existant remplace la mesure existante, et faire glisser une mesure près d’un en-tête vous permet d’afficher les deux côte à côte.

Pour plus d’informations sur l’ajout de mesures et d’autres types de composants à Analysis Workspace, voir [Utiliser des composants dans Analysis Workspace](/help/components/use-components-in-workspace.md).


## Types de mesures

Adobe propose plusieurs types de mesures à utiliser dans Analysis Workspace :


* **Mesures standard** : les exemples de mesures standard sont Personnes, Sessions, Événements, [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Comptes.

  Contrairement à Adobe Analytics, Customer Journey Analytics vous permet de définir des mesures standard de manière flexible dans le cadre d’une connexion et d’une vue de données.  Voir [Mesures standard](#standard-metrics) pour obtenir la liste complète des mesures standard.

* **Mesures calculées** ![Calculateur](/help/assets/icons/Calculator.svg) : [mesures définies par l’utilisateur](/help/components/calc-metrics/calc-metr-overview.md) qui sont basées sur des mesures standard, des nombres statiques ou des fonctions algorithmiques.

* **Modèles de mesures calculées** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : mesures définies par Adobe qui se comportent de la même manière que les mesures calculées. Vous pouvez les utiliser tels quels dans les projets Workspace ou enregistrer une copie pour personnaliser la logique. Voir [ Mesures calculées par défaut ](calc-metrics/cm-workflow/../default-calcmetrics.md).

Vous pouvez voir si une mesure est approuvée ![icône Approuvée](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) ou non. Si vous souhaitez plus de détails sur une mesure, pointez sur la mesure, puis sélectionnez ![Icône Infos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Voir [Informations sur les composants](use-components-in-workspace.md#component-info) pour plus d’informations.


## Mesures standard

Liste complète des mesures standard dans Customer Journey Analytics :
{{standard-metrics}}


## Créer des mesures calculées

Les mesures calculées vous permettent de configurer la manière dont les mesures sont liées les unes aux autres, à l’aide d’opérateurs simples ou de fonctions statistiques. Consultez [ Présentation des mesures calculées ](/help/components/calc-metrics/calc-metr-overview.md) pour plus d’informations.

Il existe plusieurs façons de créer des mesures calculées. La méthode que vous choisissez détermine si la mesure calculée est disponible dans la liste des composants de tous les projets ou uniquement dans le projet dans lequel elle a été créée.

### Création de mesures calculées pour tous les projets

Vous pouvez utiliser le [créateur de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) pour [créer des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-workflow.md). Une fois créées de cette manière, les mesures calculées sont disponibles dans la liste des composants et peuvent ensuite être utilisées dans les projets de l’ensemble de votre organisation.

### Création de mesures calculées pour un seul projet

Vous pouvez rapidement créer une mesure de calcul qui n’est disponible que pour le projet dans lequel elle a été créée.

Pour créer une mesure calculée pour un seul projet :

1. Dans Analysis Workspace, ouvrez le projet dans lequel vous souhaitez créer la mesure calculée.

1. Dans un tableau à structure libre, cliquez avec le bouton droit sur l’en-tête d’une colonne unique.

   Ou

   Sélectionnez deux colonnes tout en maintenant la touche Maj enfoncée, puis cliquez avec le bouton droit sur l’une des colonnes sélectionnées.

1. Sélectionnez **[!UICONTROL Créer une mesure à partir de la sélection]**

   Panneau ![Workspace mettant en surbrillance Créer à partir de la sélection](assets/create-metric-from-selection.png)

1. Pour créer une mesure calculée pour ce projet uniquement, choisissez l’une des options disponibles.

   Lorsqu’une seule colonne est sélectionnée, les options suivantes sont disponibles :

   * [!UICONTROL **Moyenne**] : crée une colonne qui affiche la valeur moyenne dans l’ensemble des éléments de dimension de la colonne. Cette valeur de colonne utilise la fonction [Mean](/help/components/calc-metrics/cm-functions.md#mean).

   * [!UICONTROL **Médiane**] : crée une colonne qui affiche la valeur médiane dans le jeu d’éléments de dimension de la colonne. Cette valeur de colonne utilise la fonction [Médiane](/help/components/calc-metrics/cm-functions.md#median).

   * [!UICONTROL **Colonne max**] : crée une colonne qui affiche la plus grande valeur de l’ensemble des éléments de dimension de la colonne. Cette valeur de colonne utilise la fonction [Max. colonne](/help/components/calc-metrics/cm-functions.md#column-maximum).

   * [!UICONTROL **Colonne min**] : crée une colonne qui affiche la plus petite valeur du jeu d’éléments de dimension pour la colonne. Cette valeur de colonne utilise la fonction [Column Minimum](/help/components/calc-metrics/cm-functions.md#column-minimum).

   * [!UICONTROL **Somme des colonnes**] : crée une colonne qui ajoute toutes les valeurs numériques d’une mesure dans une colonne (sur l’ensemble des éléments d’une dimension). Cette valeur de colonne utilise la fonction [Column Sum](/help/components/calc-metrics/cm-functions.md#column-sum).

   Lorsque deux colonnes sont sélectionnées, les options suivantes sont disponibles :

   * [!UICONTROL **Diviser**] : crée une colonne qui divise les valeurs des deux colonnes sélectionnées.

   * [!UICONTROL **Soustraire**] : crée une colonne qui soustrait les valeurs des deux colonnes sélectionnées.

   * [!UICONTROL **Ajouter**] : crée une colonne qui ajoute les valeurs des deux colonnes sélectionnées.

   * [!UICONTROL **Multiplier**] : crée une colonne qui multiplie les valeurs des deux colonnes sélectionnées.

   * [!UICONTROL **Changement en pourcentage**] : crée une colonne qui affiche le changement en pourcentage entre les deux colonnes sélectionnées.


## Comparaison de mesures avec différents modèles d’attribution

Pour comparer rapidement un modèle d’attribution à un autre pour une mesure, sélectionnez **[!UICONTROL Comparer les modèles d’attribution]** dans le menu contextuel d’une mesure.

Panneau ![Workspace mettant en surbrillance Comparer les modèles d’attribution](assets/compare-attribution.png)

Ce raccourci vous permet de comparer un modèle d’attribution à un autre sans faire glisser une mesure et la configurer deux fois.


