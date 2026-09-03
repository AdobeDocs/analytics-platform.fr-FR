---
title: Créer un schéma pour Customer Journey Analytics
description: En savoir plus sur le chemin recommandé lors de la mise à niveau à partir d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
autotag-review: '2026-05-19T08:12:18.647Z'
TQID: 'https://experienceleague.adobe.com/ti9UiQzAa9wBCCH-44dmUxTzojuh5ZHu9YJ9HNC8OHI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 100%

---

# Créer un jeu de données à utiliser avec Customer Journey Analytics {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Créer un jeu de données dans Adobe Experience Platform"
>abstract="Un jeu de données est un emplacement où se trouvent les données collectées. Créez cet emplacement dans Adobe Experience Platform.<br><br>La création d’un jeu de données avec un schéma en tête ne prend que quelques minutes."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un jeu de données est la structure qui stocke et gère les données que vous collectez dans Adobe Experience Platform.

Pour créer un jeu de données, procédez comme suit :

1. Dans le rail de gauche de l’interface d’utilisation d’Adobe Experience Platform, sélectionnez **[!UICONTROL Jeux de données]** dans [!UICONTROL GESTION DES DONNÉES].

1. Sélectionnez **[!UICONTROL Créer un jeu de données]**.

   ![Créer un jeu de données](assets/create-dataset.png)

1. Sélectionnez **[!UICONTROL Créer un jeu de données à partir d’un schéma]**.

   ![Créer un jeu de données à partir d’un schéma](assets/create-dataset-from-schema.png)

1. Sélectionnez le schéma que vous avez créé précédemment et sélectionnez **[!UICONTROL Suivant]**.

1. Nommez le jeu de données et (facultatif) fournissez une description.

   ![Nom du jeu de données](assets/name-your-datatest.png)

1. Sélectionnez **[!UICONTROL Terminer]**.

1. Sélectionnez le sélecteur de **[!UICONTROL Profil]**.

   Vous êtes invité à activer le jeu de données pour le profil. Une fois activé, le jeu de données enrichit les profils clients en temps réel avec ses données ingérées.

   >[!IMPORTANT]
   >
   >    Vous ne pouvez activer un jeu de données pour le profil que si le schéma, auquel le jeu de données adhère, est également activé pour le profil.

   ![Activer un schéma pour le profil](assets/aepwebsdk-dataset-profile.png)

   Consultez [Guide de l’interface d’utilisation des jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=fr) pour plus d’informations sur l’affichage, la prévisualisation, la création et la suppression d’un jeu de données. Vous pouvez également en apprendre davantage sur l’activation d’un jeu de données pour le profil client en temps réel.

{{upgrade-final-step}}
