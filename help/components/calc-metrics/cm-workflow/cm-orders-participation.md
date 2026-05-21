---
description: Explique comment créer une mesure qui indique quels canaux marketing aident à générer des commandes.
title: Création D’Une Mesure Calculée Plus Complexe
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
TQID: https://experienceleague.adobe.com/T5hA3-IeRUfDR53RL6TnJUslUI7XxRSZN2KpPKAz7k0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 9%

---

# Créer une mesure calculée plus complexe

Cet article explique un exemple plus complexe de mesure calculée. Ces mesures calculées indiquent les canaux marketing qui aident à générer des commandes. Ce type de mesure calculée peut être adapté à n’importe quelle dimension ou événement de succès.

1. Commencez à créer une mesure calculée, comme décrit dans la section [Créer des mesures](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

1. Dans le créateur de Mesures calculées, nommez la mesure `Assisted Online Orders` ou une autre mesure similaire.

1. Sélectionnez la mesure **[!UICONTROL Commandes en ligne]** parmi les composants **[!UICONTROL Mesures]** et faites-la glisser dans la zone **[!UICONTROL Définition]**.

   1. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) pour la mesure.
   1. Sélectionnez **[!UICONTROL Utiliser le modèle d’attribution différent du modèle par défaut]**.
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
