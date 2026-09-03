---
title: Surveiller l’ingestion des jeux de données lors de la mise à niveau vers Customer Journey Analytics
description: Découvrez comment surveiller l’ingestion des jeux de données lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
autotag-review: '2026-05-19T08:10:42.746Z'
TQID: 'https://experienceleague.adobe.com/tAPQiUUPilyH50PlqwefoZjw14QDN9ER1D6EKsMAR9w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 224
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

