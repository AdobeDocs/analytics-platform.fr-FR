---
title: Création d’un schéma pour Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 33%

---

# Création d’un jeu de données à utiliser avec Customer Journey Analytics

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes de mise à niveau précédentes effectuées. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement pour votre organisation avec le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un jeu de données est le concept qui stocke et gère les données que vous collectez dans Adobe Experience Platform.

Pour créer un jeu de données :

1. Dans Adobe Experience Platform, dans le rail de gauche, sélectionnez **[!UICONTROL Jeux de données]** dans [!UICONTROL  DATA MANAGEMENT].

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

   Pour plus d’informations sur l’affichage, la prévisualisation, la création et la suppression d’un jeu de données, reportez-vous au [guide de l’interface utilisateur des jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=fr) . Vous pouvez également apprendre à activer un jeu de données pour Real-time Customer Profile.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [ étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).

