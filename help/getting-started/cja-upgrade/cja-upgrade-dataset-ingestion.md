---
title: Surveiller l’ingestion des jeux de données lors de la mise à niveau vers Customer Journey Analytics
description: Découvrir comment conserver les données historiques lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 100%

---

# Surveiller l’ingestion des jeux de données lors de la mise à niveau vers Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Valider des données dans le jeu de données"
>abstract="Maintenant que vous avez configuré votre implémentation, vous pouvez utiliser le gestionnaire d’activités du jeu de données pour afficher les lots ingérés et en échec. Si vous voyez principalement des lots ingérés, cette étape est terminée. Si vous voyez principalement des lots ayant échoué ou aucun lot, vérifiez votre implémentation pour vous assurer qu’elle envoie correctement des données à Adobe."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Après avoir configuré l’implémentation du SDK web ou de l’API, vous devez vérifier le statut de chaque lot pour vous assurer que les données sont ingérées dans le jeu de données.

1. Dans l’interface d’utilisation d’Experience Platform, sélectionnez **[!UICONTROL Surveillance]** dans le volet de navigation de gauche.

   Le tableau de bord Surveillance s’affiche. Le tableau de bord vous permet de consulter les statuts des données entrantes soit depuis le lot soit depuis l’ingestion en flux continu.

   <!-- insert screenshot -->

1. Sélectionnez **[!UICONTROL Lot de bout en bout]** pour afficher une liste de lots.

   Si aucun lot ne s’affiche, vérifiez l’implémentation pour vous assurer qu’elle envoie correctement des données à Adobe.

   <!-- insert screenshot -->

1. Sélectionnez l’ID de lot d’un jeu de données donné, puis vérifiez que **[!UICONTROL Succès]** s’affiche dans le champ **[!UICONTROL Statut]**.

   Si **[!UICONTROL Échec]** s’affiche dans le champ **[!UICONTROL Statut]**, vérifiez l’implémentation pour vous assurer qu’elle envoie correctement des données à Adobe.

   Répétez cette étape pour vérifier le statut de chaque lot.

{{upgrade-final-step}}

