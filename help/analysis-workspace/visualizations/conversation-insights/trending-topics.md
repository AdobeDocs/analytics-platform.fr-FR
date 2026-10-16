---
description: Utilisez la visualisation des sujets en tendance pour explorer les sujets en tendance dans les conversations.
title: Sujets tendance
feature: Visualizations
role: User
hide: true
source-git-commit: 65d4115d4c292cff7e074d37a91563d369072ba5
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%
---
# Sujets tendance

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

## Création et configuration

Pour créer et configurer une visualisation des rubriques de tendance :

1. Ajoutez une visualisation ![Flux](/help/assets/icons/Feed.svg) **[!UICONTROL Rubriques de tendance]** . Voir [Ajouter une visualisation à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Dans la **[!UICONTROL Rubriques de tendance]** configuration de la visualisation :

   1. Sélectionnez une **[!UICONTROL mesure de classement]**. Par exemple : **[!UICONTROL Conversations]**.
   1. Vous pouvez également sélectionner **[!UICONTROL Définir l’attribution]**, puis **[!UICONTROL Modèle]**, **[!UICONTROL Conteneur]** et **[!UICONTROL Intervalle de recherche en amont]**.
   1. Sélectionnez un niveau pour **[!UICONTROL Limiter les niveaux de sous-rubrique]**. La valeur par défaut est **[!UICONTROL niveau 5]**.

      >[!NOTE]
      >
      >Le **[!UICONTROL Limiter le niveau de sous-rubrique]** définit le nombre maximal de niveaux à analyser en profondeur pour les rubriques de la visualisation. Si aucune autre rubrique n’est disponible à un niveau dans la limite de ce nombre maximal défini, ![DataUnavailable](/help/assets/icons/DataUnavailable.svg) **[!UICONTROL Aucune rubrique trouvée]** s’affiche.

1. Sélectionnez **[!UICONTROL Créer]** pour créer la visualisation. Sélectionnez **[!UICONTROL Réinitialiser]** pour réinitialiser les valeurs de configuration aux valeurs par défaut.

Pour reconfigurer la visualisation des rubriques de tendance, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) en regard de **[!UICONTROL Mesure de classement : _mesure de classement_ | Niveaux de sous-rubrique : _x_]**.

## Utilisation

Pour utiliser la visualisation :

* Pour analyser et afficher les sous-rubriques de tendance pour une rubrique à un niveau inférieur, sélectionnez une rubrique à un niveau spécifique.

* Pour comparer des rubriques par rapport à une autre période, sélectionnez une période dans Comparer avec. Pour utiliser une période personnalisée :
  * Sélectionnez Période personnalisée dans le menu déroulant, puis, dans la boîte de dialogue Nouvelle période , définissez et enregistrez une période personnalisée.
  * Sélectionnez cette période personnalisée.

* Pour afficher un graphique linéaire pour la sélection actuelle de rubriques, déposez une visualisation [Ligne](/help/analysis-workspace/visualizations/line.md) sur la visualisation **[!UICONTROL Rubriques en tendance]**. La visualisation **[!UICONTROL Ligne]** est automatiquement liée à la visualisation **[!UICONTROL Rubriques de tendance]**.

## Paramètres

Les [paramètres de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings) spécifiques suivants sont disponibles.

| Paramètre | Description |
|---|---|
| **[!UICONTROL Afficher la valeur réelle]** | Affiche la valeur réelle d’une rubrique. |
| **[!UICONTROL Afficher le pourcentage]** | Affiche le pourcentage d’une rubrique. |



