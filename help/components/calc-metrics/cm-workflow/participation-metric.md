---
description: Avec le créateur de mesures calculées, tout le monde peut créer une mesure de participation.
title: Mesure de participation
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---

# Mesure de participation

Voici un cas d’utilisation simple : vous êtes propriétaire de contenu et souhaitez déterminer quelles pages ont contribué aux (participé dans) visites qui contenaient une commande. Procédez comme suit :

>[!NOTE]
>
>Auparavant, vous deviez effectuer cette opération via Outils d’administration. Vous pouvez continuer à activer les mesures de participation dans Outils d’administration, mais uniquement pour les événements personnalisés de 1 à 100.

Voici un cas d’utilisation simple : vous êtes propriétaire de contenu et souhaitez déterminer quelles pages ont contribué aux (participé dans) visites qui contenaient une inscription aux courriers électroniques. Procédez comme suit :

1. Créez une mesure dans le créateur de mesures calculées.
1. Faites glisser l’événement de succès « Commandes » vers le canevas Définition.
1. Modifiez le [modèle d’attribution](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de cet événement en **[!UICONTROL Participation]** sous l’engrenage **[!UICONTROL Paramètres]**. Sélectionnez la recherche en amont **[!UICONTROL Visite]**. La définition doit ressembler à celle-ci :

   ![](assets/participation.png)

1. Enregistrez la mesure.
1. Utilisez la mesure calculée dans un rapport **[!UICONTROL Pages]**.

   ![](assets/participation-pages.png)

1. (Facultatif) Partagez la mesure avec d’autres utilisateurs de votre entreprise.
