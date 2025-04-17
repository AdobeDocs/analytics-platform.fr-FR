---
title: Créer un schéma pour Customer Journey Analytics
description: En savoir plus sur le chemin recommandé lors de la mise à niveau à partir d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '219'
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
