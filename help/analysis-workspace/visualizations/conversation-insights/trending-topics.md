---
description: Utilisez la visualisation des sujets en tendance pour explorer les sujets en tendance dans les conversations.
title: Sujets tendance
feature: Visualizations
role: User
hide: true
source-git-commit: 85311bf19368560ef54a3361edf2e7c13590929c
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 8%
---
# Sujets tendance {#trending-topics}

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="Sujets tendance"
>abstract="Créez une visualisation qui affiche une répartition hiérarchique des sujets de tendance avec des occurrences et des pourcentages, pour vous aider à identifier les thèmes importants dans les conversations."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="Sujets tendance"
>abstract="Analysez les rubriques de tendance en fonction de la mesure de classement sélectionnée. Sélectionnez des rubriques pour effectuer une analyse jusqu&#39;à cinq niveaux de profondeur. Recherchez des rubriques spécifiques et comparez les rubriques à d’autres périodes."

La visualisation ![Flux](/help/assets/icons/Feed.svg) **[!UICONTROL Sujets de tendance]** vous permet d’explorer et d’analyser les sujets de tendance dans le cadre des informations sur les conversations.

Vous pouvez rechercher des rubriques spécifiques et comparer le nombre et le pourcentage de chaque rubrique à chaque niveau avec d’autres plages de données.

## Création et configuration {#trendimg-topics-create-and-configure}

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_usenondefaultattributionmodel"
>title="Utilisation d’un modèle d’attribution différent du modèle par défaut"
>abstract="Activez un modèle d’attribution autre que celui par défaut pour cette mesure."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_usenondefaultattributionmodel_disabled"
>title="Utilisation d’un modèle d’attribution différent du modèle par défaut"
>abstract="Les modèles d’attribution non par défaut ne sont pas disponibles pour cette mesure."

Pour créer et configurer une visualisation **[!UICONTROL Rubriques de tendance]** :

1. Ajoutez une visualisation ![Flux](/help/assets/icons/Feed.svg) **[!UICONTROL Rubriques de tendance]** . Voir [Ajouter une visualisation à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Dans la **[!UICONTROL Rubriques de tendance]** configuration de la visualisation :

   1. Sélectionnez une **[!UICONTROL mesure de classement]**. Par exemple : **[!UICONTROL Conversations]**.
   1. Si vous souhaitez utiliser un modèle [attribution](/help/analysis-workspace/attribution/models.md) autre que celui par défaut pour la mesure, sélectionnez **[!UICONTROL Utiliser un modèle d’attribution autre que celui par défaut]**, puis sélectionnez **[!UICONTROL Modèle]**, **[!UICONTROL Conteneur]** et **[!UICONTROL Intervalle de recherche en amont]**.
1. Sélectionnez **[!UICONTROL Créer]** pour créer la visualisation. Sélectionnez **[!UICONTROL Réinitialiser]** pour réinitialiser les valeurs de configuration aux valeurs par défaut.

Pour reconfigurer la visualisation des rubriques de tendance, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) en regard de **[!UICONTROL Mesure de classement : _mesure de classement_ | Niveaux de sous-rubrique : _x_]**.

## Utilisation

Pour utiliser la visualisation :

![Utilisation de la visualisation des rubriques de tendances](assets/trending-topics.png)

* Pointez sur une rubrique pour afficher une fenêtre contextuelle contenant plus de détails. ➊

* Pour afficher les sous-rubriques de tendance pour une rubrique à un niveau inférieur, sélectionnez une rubrique à un niveau spécifique. Si aucune rubrique n&#39;est disponible à un sous-niveau, ![DataRemove](/help/assets/icons/DataRemove.svg) **[!UICONTROL Aucune sous-rubrique trouvée pour _topic > sous-rubrique > ...]**.

* Utilisez ![Rechercher](/help/assets/icons/Search.svg) **[!UICONTROL _Rechercher des rubriques_]** pour rechercher rapidement des rubriques. ➋

* Pour comparer des rubriques par rapport à une autre période, sélectionnez une période dans **[!UICONTROL Comparer avec]**. ➌

  Pour utiliser une période personnalisée :

  * Sélectionnez **[!UICONTROL Période personnalisée]** dans le menu déroulant, puis dans la boîte de dialogue **[!UICONTROL Nouvelle période]** définissez et enregistrez une période personnalisée.
  * Sélectionnez cette période personnalisée.

* Pour afficher un graphique linéaire pour la sélection actuelle de rubriques, déposez une visualisation [Ligne](/help/analysis-workspace/visualizations/line.md) sur la visualisation **[!UICONTROL Rubriques en tendance]**. La visualisation **[!UICONTROL Ligne]** est automatiquement liée à la visualisation **[!UICONTROL Rubriques de tendance]** et affiche une ligne pour la rubrique sélectionnée.

  ![Visualisation des tendances des lignes de rubrique](assets/trending-topics-line-viz.png)

## Paramètres

Les [paramètres de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings) spécifiques suivants sont disponibles.

| Paramètre | Description |
|---|---|
| **[!UICONTROL Afficher la valeur réelle]** | Affiche la valeur réelle d’une rubrique. |
| **[!UICONTROL Afficher le pourcentage]** | Affiche le pourcentage pour une rubrique. |
