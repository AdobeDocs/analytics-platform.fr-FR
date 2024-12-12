---
title: Surveiller l’ingestion du jeu de données lors de la mise à niveau vers Customer Journey Analytics
description: Découvrez comment surveiller l’ingestion des jeux de données lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: f71f5b863a024d882a116a5fd3bf0fc433e5fe99
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# Surveiller l’ingestion du jeu de données lors de la mise à niveau vers Customer Journey Analytics

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement après avoir effectué toutes les étapes de mise à niveau précédentes. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou suivre les étapes de mise à niveau qui ont été générées dynamiquement pour votre organisation à l’aide du questionnaire de mise à niveau d’[Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois les étapes de cette page terminées, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Après avoir configuré votre implémentation de Web SDK, vous devez vérifier les statuts des lots individuels pour vérifier que les données sont ingérées dans le jeu de données.

1. Dans l’interface utilisateur de l’Experience Platform, sélectionnez **[!UICONTROL Surveillance]** dans le volet de navigation de gauche.

   Le tableau de bord Surveillance s’affiche. Ce tableau de bord vous permet d’afficher les états des données entrantes à partir de l’ingestion par lots ou par flux.

   <!-- insert screenshot -->

1. Sélectionnez **[!UICONTROL Lot de bout en bout]** pour afficher une liste de lots.

   Si aucun lot ne s’affiche, vérifiez votre implémentation de Web SDK pour vous assurer qu’elle envoie correctement les données vers l’Adobe.

   <!-- insert screenshot -->

1. Sélectionnez l’ID de lot d’un jeu de données donné, puis vérifiez que **[!UICONTROL Succès]** s’affiche dans le champ **[!UICONTROL Statut]**.

   **[!UICONTROL Si le champ**[!UICONTROL &#x200B;Échec ]**s’affiche]** vérifiez votre implémentation de Web SDK pour vous assurer qu’elle envoie correctement des données vers l’Adobe.

   Répétez cette étape pour vérifier l’état de chaque lot.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).

