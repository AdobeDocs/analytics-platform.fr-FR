---
title: Créer des segments
description: Comprendre l’interface utilisateur de création de segments.
exl-id: b6a921d5-7dd3-4230-88b8-5f1cd313b791
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# Créer des segments

Vous pouvez créer différents types de segments dans Customer Journey Analytics.  Le type que vous sélectionnez dépend de la complexité des segments et du fait qu’ils doivent s’appliquer au projet Workspace actuel uniquement ou à tous les projets. Vous pouvez créer des segments directement dans l’interface principale de Customer Journey Analytics ou lorsque vous travaillez dans un projet Workspace.

Par défaut, seuls les administrateurs peuvent créer des segments. Les utilisateurs et utilisatrices disposent de droits d’affichage des segments, de la même manière que les utilisateurs et utilisatrices voient d’autres composants (tels que les annotations, les mesures calculées, etc.).

Cependant, les administrateurs peuvent accorder aux utilisateurs l’autorisation **[!UICONTROL Création de segments]** pour **[!UICONTROL Outils de création de rapports]** dans **[!UICONTROL Autorisations de modification pour l’accès à CJA Workspace]** via [Admin Console](/help/technotes/access-control.md#user-level-access).

Vous pouvez créer un segment des manières suivantes :

![Comment créer un segment ](assets/create-filter.png)

* **A**. Dans l’interface principale, sélectionnez **[!UICONTROL Composants]** puis **[!UICONTROL Segments]**. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] dans le gestionnaire [[!UICONTROL Segment]](/help/components/segments/seg-manage.md).
* **B**. Dans un projet Workspace, dans le panneau de gauche Composants , sélectionnez ![Ajouter](/help/assets/icons/Add.svg) sous ![Segment](/help/assets/icons/Segmentation.svg) **Segments**.
* **C**. Dans un projet Workspace, dans le menu contextuel d’une visualisation, sélectionnez **[!UICONTROL Créer un segment à partir de la sélection]**.
* **D**. Dans un projet Workspace, sélectionnez **[!UICONTROL Composants]** dans le menu, puis sélectionnez **[!UICONTROL Créer un segment]**.
* ****. Dans un projet Workspace, utilisez le raccourci **[!UICONTROL maj+cmd+e]** (macOS) ou **[!UICONTROL maj+ctrl+e]** (Windows).
* **F**. Sélectionnez ![Ajouter](/help/assets/icons/Add.svg) dans ***Déposez un segment ici (ou tout autre composant)*** zone de dépôt. Cette action crée un segment Projet uniquement.

Pour définir le nouveau segment, utilisez le [créateur de segments](/help/components/segments/seg-builder.md).

Lorsque vous vous trouvez dans un projet Workspace, vous pouvez également créer un segment rapidement à l’aide de [Segment rapide](/help/components/segments/seg-quick.md).
