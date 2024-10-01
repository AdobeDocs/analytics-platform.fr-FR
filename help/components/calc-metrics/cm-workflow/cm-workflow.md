---
description: Découvrez comment créer des mesures calculées.
title: Création de mesures calculées
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Création de mesures calculées

Par défaut, seuls les administrateurs peuvent créer des mesures calculées. Les utilisateurs ont les droits d’afficher les mesures calculées, de la même manière que les utilisateurs voient d’autres composants (filtres, annotations, etc.).

Cependant, les administrateurs peuvent accorder aux utilisateurs l’autorisation **[!UICONTROL Création de mesure calculée]** pour les **[!UICONTROL outils de création de rapports]** dans **[!UICONTROL Modifier les autorisations d’accès CJA Workspace]** via l’ [Admin Console](/help/technotes/access-control.md#user-level-access).


Vous pouvez créer une mesure calculée de la manière suivante :

![Méthodes pour créer un filtre](assets/create-metric.png)

* ?? Dans l’interface principale, sélectionnez **[!UICONTROL Composants]** et **[!UICONTROL Mesures calculées]**. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL ****] dans le [[!UICONTROL  gestionnaire de ] mesures calculées ](/help/components/calc-metrics/cm-workflow/cm-manager.md).
* ?? Dans un projet Workspace, dans le panneau de gauche Composants, sélectionnez ![Ajouter](/help/assets/icons/Add.svg) à l’emplacement ![Événement](/help/assets/icons/Event.svg) **Mesures**.
* ?? Dans un projet Workspace, dans le menu contextuel de l’en-tête de colonne des mesures, sélectionnez **[!UICONTROL Créer une mesure d’après la sélection]**. Dans le sous-menu, vous pouvez sélectionner une fonction ou **[!UICONTROL Ouvrir dans le créateur de mesures calculées]**. <br/>Si vous sélectionnez une fonction, la mesure calculée est définie comme une mesure de projet uniquement. Lorsque vous modifiez cette mesure par la suite, par le biais de la fenêtre contextuelle [Informations sur le composant](/help/components/use-components-in-workspace.md#component-info), vous recevez une notification dans le [créateur de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
* ?? Dans un projet Workspace, sélectionnez **[!UICONTROL Composants]** dans le menu, puis **[!UICONTROL Créer une mesure]**.
* ?? Dans un projet Workspace, utilisez le raccourci **[!UICONTROL shift+cmd+c]** (macOS) ou **[!UICONTROL shift+ctrl+c]** (Windows).

Pour définir la nouvelle mesure calculée, vous utilisez le [créateur de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

<!--

Learn about the steps to take for creating calculated metrics.

| Workflow Task | Description |
| --- | --- |
| Plan Calculated Metrics | Especially for metrics that are going to be officially "approved", it makes sense to outline which calculated metrics will be widely used and how they will be defined. |
| [Build](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) Calculated Metrics | Build and edit calculated and advanced calculated metrics for use in [!DNL Customer Journey Analytics] components. |
| [Tag](cm-tagging.md) Calculated Metrics | Tag calculated metrics for ease of organization and sharing. See how to plan and assign tags for simple and advanced searches and organization. |
| [Approve](cm-approving.md) Calculated Metrics | Approve calculated metrics to make them canonical. |
| Apply Calculated Metrics | You can apply metrics directly from a report, from the Metric Selector (to access it, click [!UICONTROL Show Metrics]). |
| Filter Calculated Metrics | In the Metric Selector, click [!UICONTROL Advanced Selection] and filter by tags, owners, and other filters (Show All, Mine, Shared With me, Favorites, and Approved.) |
| Mark Calculated Metrics as [Favorites](cm-finding.md) | Marking metrics as favorites is another way to organize them for ease of use.|

-->
