---
title: Création d’un schéma pour Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 60%

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

Un jeu de données est la structure qui stocke et gère les données que vous collectez dans Adobe Experience Platform.

Pour créer un jeu de données :

1. Dans Adobe Experience Platform, dans le rail de gauche, sélectionnez **[!UICONTROL Jeux de données]** sous [!UICONTROL GESTION DES DONNÉES].

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

   Consultez [ Guide de l’interface utilisateur des jeux de données ](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=fr) pour plus d’informations sur l’affichage, la prévisualisation, la création et la suppression d’un jeu de données. Vous pouvez également apprendre à activer un jeu de données pour le profil client en temps réel.

{{upgrade-final-step}}
