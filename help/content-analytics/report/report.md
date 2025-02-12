---
title: Rapports Content Analytics
description: Comment créer des rapports sur Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: 7542e7a402c8e2f8d6e4c1e624f04ceb752cc27e
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Rapports Content Analytics - Aperçu

>[!WARNING]
>
>Cet article est un avant-projet non officiel d’une version finale à venir et fait partie de la documentation de Content Analytics. Tout le contenu est sujet à modification et aucune obligation légale quelle qu&#39;elle soit ne peut être dérivée de la version actuelle de cet article.
>

{{release-limited-testing}}

La création de rapports sur les analyses de contenu s’effectue dans Analysis Workspace. Un modèle Workspace [template](#template) spécifique est disponible afin que vous puissiez immédiatement accéder à un projet Workspace prérempli avec des informations pertinentes sur le contenu.

Pour créer entièrement des rapports sur Content Analytics :

1. [Créez un projet](/help/analysis-workspace/build-workspace-project/create-projects.md) ou [ouvrez un projet existant](/help/analysis-workspace/build-workspace-project/open-projects.md) dans Workspace.
1. Faites glisser une visualisation ![Tableau](/help/assets/icons/Table.svg) [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) sur la zone de travail.
1. Utilisez des dimensions et des mesures Content Analytics spécifiques, ainsi que d’autres [composants](/help/components/overview.md) génériques (tels que des filtres, des périodes, des annotations) pour créer vos informations d’analyse de contenu.

## Miniatures

En fonction des dimensions spécifiques à Content Analytics que vous utilisez dans votre projet, des miniatures s’affichent pour les ressources et les dimensions.

![Miniatures Content Analytics](../assets/aca-thumbnails.png)

## Prévisualisations

Pour les dimensions qui comportent des miniatures (comme le nom de la ressource, le nom de l’expérience, etc.), vous pouvez ouvrir une fenêtre contextuelle d’aperçu.

Pour ouvrir l’aperçu avec les détails suivants :

* Sélectionnez ![ InfoOutline ](/help/assets/icons/InfoOutline.svg). Les détails suivants s’affichent.

  | Aperçu de l’expérience | Aperçu des ressources |
  |---|---|
  | ![Aperçu de l’expérience Content Analytics](../assets/aca-experience-preview.png) | ![Aperçu de la ressource Content Analytics](../assets/aca-asset-preview.png) |
  | **[!UICONTROL Nom de l’expérience]** | **[!UICONTROL Nom de la ressource]** |
  | **[!UICONTROL Impressions (toutes les heures)]** : nombre d’impressions pour l’expérience. | **[!UICONTROL Impressions (toutes les fois)]** : nombre d’impressions de la ressource. |
  | **[!UICONTROL Assets]** : nombre de ressources que contient cette expérience. Sélectionnez ![Répartition](/help/assets/icons/Breakdown.svg) Répartition pour examiner les ressources. | **[!UICONTROL Expériences]** : nombre d’expériences dans lesquelles cette ressource est affichée. [Répartition](/help/assets/icons/Breakdown.svg) Répartition pour inspecter les ressources. |
  | **[!UICONTROL Première impression]** : date de la première impression de l’expérience. | **[!UICONTROL Première impression]** : date de la première impression de la ressource. |
  | **[!UICONTROL Dernière impression]** : date de la dernière impression de l’expérience. | **[!UICONTROL Impression la plus récente]** : date de l’impression la plus récente de la ressource. |
  | **[!UICONTROL Attributs d’expérience]** : attributs de l’expérience. | **[!UICONTROL Attributs de ressource]** : les attributs de la ressource. |


## Modèle

Détails sur les modèles...
