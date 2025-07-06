---
description: Explique comment créer une mesure qui indique quels canaux marketing aident à générer des commandes.
title: Création D’Une Mesure Calculée Plus Complexe
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: 1b6e1d432bfe4b0574b8ee68bcfa940941f3c36f
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 6%

---

# Créer une mesure calculée plus complexe

Cet article explique un exemple plus complexe de mesure calculée. Ces mesures calculées indiquent les canaux marketing qui aident à générer des commandes. Ce type de mesure calculée peut être adapté à n’importe quelle dimension ou événement de succès.

1. Commencez à créer une mesure calculée, comme décrit dans la section [Créer des mesures](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

1. Dans le créateur de Mesures calculées, nommez la mesure `Assisted Online Orders` ou une autre mesure similaire.

1. Sélectionnez la mesure **[!UICONTROL Commandes en ligne]** parmi les composants **[!UICONTROL Mesures]** et faites-la glisser dans la zone **[!UICONTROL Définition]**.

   1. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) pour la mesure.
   1. Sélectionnez **[!UICONTROL Utiliser un modèle d’attribution autre que celui par défaut]**.
   1. Ajustez le modèle d’attribution dans le **[!UICONTROL Modèle d’attribution de colonne]**.
      1. Sélectionnez **[!UICONTROL Personnalisé]** pour **[!UICONTROL Modèle]**. Définissez **[!UICONTROL Starter]** sur `0`, **[!UICONTROL Player]** sur `100` et **[!UICONTROL Closer]** sur `0`.
      1. Sélectionnez **[!UICONTROL Visiteur]** pour **[!UICONTROL Conteneur]**.
      1. Sélectionnez **[!UICONTROL 30 jours]** pour **[!UICONTROL Intervalle de recherche en amont]**.

      1. Sélectionnez **[!UICONTROL Appliquer]**.

      ![ Modèle d’attribution de colonne ](assets/complex-calculated-metric.png)

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer la mesure calculée.

Pour utiliser la mesure calculée :

1. Dans Analysis Workspace, créez un tableau à structure libre avec la dimension **[!UICONTROL Canal marketing]**, **[!UICONTROL Commandes en ligne]** et votre nouvelle mesure **[!UICONTROL Commandes en ligne assistées]**.

   ![Commandes en ligne assistées par canal marketing](assets/marketing-channel-assists.png)

1. (Facultatif) Partagez la mesure avec d’autres utilisateurs de votre organisation, comme décrit dans la section [Partage de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-sharing.md).

C’est un moyen facile d’indiquer les canaux marketing qui ont aidé au pilotage des commandes. Vous pouvez également sélectionner n’importe quelle mesure dans un tableau à structure libre et, à partir du menu contextuel, ajuster directement le modèle d’attribution à partir du tableau.
