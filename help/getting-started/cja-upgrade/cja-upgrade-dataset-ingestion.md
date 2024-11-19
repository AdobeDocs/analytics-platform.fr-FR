---
title: Surveiller l’ingestion des jeux de données lors de la mise à niveau vers Customer Journey Analytics
description: Découvrez comment surveiller l’ingestion des jeux de données lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a5425eccff643cd45fd630172b0113e646b2a9cc
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Surveiller l’ingestion des jeux de données lors de la mise à niveau vers Customer Journey Analytics

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes de mise à niveau précédentes effectuées. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement pour votre organisation avec le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Une fois que vous avez configuré l’implémentation de votre SDK Web, vous devez vérifier les états des lots individuels pour vérifier que les données sont ingérées dans le jeu de données.

1. Dans l’interface utilisateur de l’Experience Platform, sélectionnez **[!UICONTROL Surveillance]** dans le volet de navigation de gauche.

   Le tableau de bord Surveillance s’affiche. Ce tableau de bord vous permet de consulter les états des données entrantes à partir de l’ingestion par lots ou par flux.

   <!-- insert screenshot -->

1. Sélectionnez **[!UICONTROL Batch end-to-end]** pour afficher une liste de lots.

   Si aucun lot n’est affiché, vérifiez l’implémentation de votre SDK Web pour vous assurer qu’il envoie correctement les données à Adobe.

   <!-- insert screenshot -->

1. Sélectionnez l’identifiant de lot d’un jeu de données donné, puis validez que **[!UICONTROL Success]** s’affiche dans le champ **[!UICONTROL Status]** .

   Si **[!UICONTROL Failed]** est affiché dans le champ **[!UICONTROL Status]**, vérifiez l’implémentation de votre SDK Web pour vous assurer qu’il envoie correctement des données à Adobe.

   Répétez cette étape pour vérifier l’état de chaque lot.




