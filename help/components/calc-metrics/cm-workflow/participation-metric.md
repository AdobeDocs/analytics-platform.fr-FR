---
description: Avec le créateur de mesures calculées, tout le monde peut créer une mesure de participation.
title: Mesure de participation
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 82ba31eec1455bf3d0c746cf5eebc81ce6162a00
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 32%

---

# Création d’une mesure &quot;Participation&quot;

Les informations suivantes expliquent comment créer une mesure qui indique les pages qui ont contribué (ou participé) aux sessions qui contenaient une commande.

Ce type d’informations peut s’avérer utile pour tout propriétaire de contenu.

>[!NOTE]
>
>Vous pouvez activer les mesures de participation dans les outils d’administration, mais uniquement pour les événements personnalisés 1 à 100.

1. Commencez à créer une mesure, comme décrit dans la section [Créer des mesures](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Dans le créateur de mesures calculées, nommez la mesure &quot;Participation&quot; ou quelque chose du même type.
1. Faites glisser l’événement de succès « Commandes » vers le canevas Définition.
1. Modifiez le [modèle d’attribution](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de cet événement en **[!UICONTROL Participation]** sous l’engrenage **[!UICONTROL Paramètres]**. Sélectionner **[!UICONTROL Session]** recherche en amont. La définition doit ressembler à celle-ci :

   ![](assets/participation.png)

1. Sélectionner [!UICONTROL **Enregistrer**] pour enregistrer la mesure.
1. Utilisez la mesure calculée dans un rapport **[!UICONTROL Pages]**.

   ![](assets/participation-pages.png)

1. (Facultatif) Partagez la mesure avec d’autres utilisateurs de votre entreprise, comme décrit dans la section [Partage des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
