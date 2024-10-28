---
title: Création d’un schéma pour Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 35%

---

# Création d’un flux de données à utiliser avec Customer Journey Analytics

>[!NOTE]
>
>Cette documentation doit être utilisée après avoir rempli le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes précédentes qui ont été générées dynamiquement pour votre organisation.
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau générées dynamiquement pour votre organisation à partir du [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un flux de données représente la configuration côté serveur lors de la mise en œuvre des SDK Web et Mobile Adobe Experience Platform. Lors de la collecte de données avec les SDK Adobe Experience Platform, les données sont envoyées à Adobe Experience Platform Edge Network. Il s’agit du flux de données qui détermine les services vers lesquels les données sont transférées.

Dans votre configuration, vous devez envoyer les données collectées sur le site Web au jeu de données dans Adobe Experience Platform.

Configurer le flux de données :

1. Dans Adobe Experience Platform, sélectionnez **[!UICONTROL Datastreams]** depuis [!UICONTROL DATA COLLECTION] dans le rail de gauche.

1. Sélectionnez **[!UICONTROL Nouveau flux de données]**.

1. Nommez et décrivez le flux de données. Sélectionnez le schéma dans la liste [!UICONTROL Schéma d’événement].

   ![Nouveau flux de données](assets/new-datastream.png)

1. Sélectionnez **[!UICONTROL Enregistrer]**.

1. Continuez à suivre les étapes de mise à niveau générées dynamiquement pour votre organisation à partir du [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

