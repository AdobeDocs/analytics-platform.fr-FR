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
source-wordcount: '318'
ht-degree: 30%

---

# Ajout de Platform en tant que service à votre flux de données

>[!NOTE]
>
>Cette documentation doit être utilisée après avoir rempli le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes précédentes qui ont été générées dynamiquement pour votre organisation.
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau générées dynamiquement pour votre organisation à partir du [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Il doit déjà exister un flux de données avant de suivre les étapes de cette section. Le moment et la manière dont le flux de données a été créé dépendent de votre mise en oeuvre Adobe Analytics, comme suit :

* Si votre mise en oeuvre Adobe Analytics utilise le SDK Web ou l’extension SDK Web, la banque de données était disponible pour votre environnement Adobe Analytics, avant le processus de mise à niveau.

* Pour les autres implémentations d’Adobe Analytics, la création d’un flux de données fait partie du processus de mise à niveau, comme décrit dans la section [Création d’un flux de données à utiliser avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

Avec le flux de données disponible, vous devez ajouter Platform en tant que service :

1. Dans l’interface utilisateur d’Adobe Experience Platform, sélectionnez **[!UICONTROL Flux de données]** sous [!UICONTROL COLLECTE DE DONNÉES] dans le rail de gauche.

1. Sélectionnez le flux de données qui a été précédemment configuré. <!--true?-->

1. Sélectionnez **[!UICONTROL Ajouter un service]**.

1. Sur l’[!UICONTROL écran Ajouter un service] :

   1. Sélectionnez **[!UICONTROL Adobe Experience Platform]** dans la liste [!UICONTROL Service].

   1. Assurez-vous que l’option **[!UICONTROL Activé]** est sélectionnée.

   1. Sélectionnez le jeu de données dans la liste [!UICONTROL Jeu de données d’événement].

      ![Service AEP de flux de données](./assets/datastream-aep-service.png)

   1. Gardez les autres paramètres et sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer le flux de données.

   Le flux de données est maintenant configuré pour transférer les données collectées depuis le site Web vers le jeu de données dans Adobe Experience Platform.

   Consultez [Présentation des flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=fr) pour plus d’informations sur la configuration d’un flux de données et la gestion des données sensibles.

1. Continuez à suivre les étapes de mise à niveau générées dynamiquement pour votre organisation à partir du [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
