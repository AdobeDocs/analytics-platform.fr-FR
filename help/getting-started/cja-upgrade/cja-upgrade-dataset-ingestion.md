---
title: Surveiller l’ingestion des jeux de données lors de la mise à niveau vers Customer Journey Analytics
description: Découvrez comment surveiller l’ingestion des jeux de données lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# Surveiller l’ingestion des jeux de données lors de la mise à niveau vers Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Valider des données dans le jeu de données"
>abstract="Maintenant que vous avez configuré votre implémentation de Web SDK, vous pouvez utiliser le gestionnaire d’activités du jeu de données pour afficher les lots ingérés et en échec. Si vous voyez principalement des lots ingérés, cette étape est terminée. Si vous voyez principalement des lots ayant échoué ou aucun lot, vérifiez votre implémentation de Web SDK pour vous assurer qu’elle envoie correctement des données à Adobe.<br><br>Si tout a été fait correctement et parfaitement, cette étape peut être réalisée en moins d’une journée. S’il existe plusieurs problèmes de collecte de données, leur résolution peut prendre beaucoup plus de temps."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Après avoir configuré votre implémentation de Web SDK, vous devez vérifier les statuts des lots individuels pour vérifier que les données sont ingérées dans le jeu de données.

1. Dans l’interface utilisateur d’Experience Platform, sélectionnez **[!UICONTROL Surveillance]** dans le volet de navigation de gauche.

   Le tableau de bord Surveillance s’affiche. Ce tableau de bord vous permet d’afficher les états des données entrantes à partir de l’ingestion par lots ou par flux.

   <!-- insert screenshot -->

1. Sélectionnez **[!UICONTROL Lot de bout en bout]** pour afficher une liste de lots.

   Si aucun lot ne s’affiche, vérifiez votre implémentation de Web SDK pour vous assurer qu’elle envoie correctement des données à Adobe.

   <!-- insert screenshot -->

1. Sélectionnez l’ID de lot d’un jeu de données donné, puis vérifiez que **[!UICONTROL Succès]** s’affiche dans le champ **[!UICONTROL Statut]**.

   **[!UICONTROL Si le champ**[!UICONTROL &#x200B;Échec ]**s’affiche]** vérifiez votre implémentation de Web SDK pour vous assurer qu’elle envoie correctement des données à Adobe.

   Répétez cette étape pour vérifier l’état de chaque lot.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).

