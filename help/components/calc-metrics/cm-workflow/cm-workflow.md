---
description: Découvrez comment créer des mesures calculées.
title: Créer des mesures calculées
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 18%

---

# Créer des mesures calculées

Par défaut, seuls les administrateurs peuvent créer des mesures calculées. Les utilisateurs et utilisatrices disposent de droits pour afficher les mesures calculées, de la même manière que les utilisateurs et utilisatrices affichent d’autres composants (tels que les segments, les annotations, etc.).

Cependant, les administrateurs peuvent accorder aux utilisateurs l’autorisation **[!UICONTROL Création de mesures calculées]** pour **[!UICONTROL Outils de création de rapports]** dans **[!UICONTROL Autorisations de modification de l’accès à CJA Workspace]** via l’[Admin Console](/help/technotes/access-control.md#user-level-access).


Vous pouvez créer une mesure calculée des manières suivantes :

![Comment créer une mesure ](assets/create-metric.png)

* **A**. Dans l’interface principale, sélectionnez **[!UICONTROL Composants]** puis **[!UICONTROL Mesures calculées]**. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] dans le gestionnaire [[!UICONTROL Mesures calculées]](/help/components/calc-metrics/cm-workflow/cm-manager.md).
* **B**. Dans un projet Workspace, dans le panneau de gauche Composants , sélectionnez ![Ajouter](/help/assets/icons/Add.svg) à ![Événement](/help/assets/icons/Event.svg) **Mesures**.
* **C**. Dans un projet Workspace, dans le menu contextuel de l’en-tête de colonne des mesures, sélectionnez **[!UICONTROL Créer une mesure à partir de la sélection]**. Dans le sous-menu, vous pouvez sélectionner une fonction ou sélectionner **[!UICONTROL Ouvrir dans le créateur de mesures calculées]**. <br/>Si vous sélectionnez une fonction, la mesure calculée est définie comme mesure de projet uniquement. Lorsque vous modifiez cette mesure par la suite, dans la fenêtre contextuelle [Informations sur le composant](/help/components/use-components-in-workspace.md#component-info), une notification s’affiche dans le [Créateur de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
* **D**. Dans un projet Workspace, sélectionnez **[!UICONTROL Composants]** dans le menu, puis sélectionnez **[!UICONTROL Créer une mesure]**.
* **&#x200B;**. Dans un projet Workspace, utilisez le raccourci **[!UICONTROL maj+cmd+c]** (macOS) ou **[!UICONTROL maj+ctrl+c]** (Windows).

Pour définir la nouvelle mesure calculée, utilisez le [créateur de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).


## Processus

Avant de créer des mesures calculées, prenez soigneusement en compte le workflow suivant :

| Tâche du processus | Description |
| --- | --- |
| Planifier les mesures calculées | En particulier pour les mesures qui vont être officiellement approuvées, il est logique de planifier pour souligner les mesures calculées qui seront largement utilisées et comment elles seront définies. |
| [Créer](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) mesures calculées | Créez et modifiez des mesures calculées et des mesures calculées avancées en vue de les utiliser dans les composants d’[!DNL Customer Journey Analytics].   |
| [Balise](cm-tagging.md) mesures calculées | Balisez les mesures calculées pour faciliter l’organisation et le partage. Apprenez à planifier et affecter des balises pour des recherches simples et avancées et pour l’entreprise. |
| [Approuver](cm-approving.md) les mesures calculées | Approuvez des mesures calculées pour les rendre canoniques. |
| Utilisation des mesures calculées | Utilisez les mesures calculées dans vos projets. |
| [Partage](cm-sharing.md) mesures calculées | Partagez vos mesures calculées avec d’autres personnes, groupes ou organisations. |
| [Filtrer](cm-filter.md) mesures calculées | Filtrez les mesures calculées par balises, propriétaires et autres filtres (Afficher tout, À moi, Partagé avec moi, Favoris et Approuvé). |
| Marquer les mesures calculées comme [favoris](cm-finding.md) | Le marquage des mesures en tant que favoris est une autre manière de les organiser pour en faciliter l’utilisation. |

