---
title: Création d’un schéma pour Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 55%

---

# Ajouter Platform en tant que service à votre flux de données {#upgrade-addplatform-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-addplatform-datastream"
>title="Ajouter Adobe Experience Platform en tant que service au flux de données"
>abstract="Un flux de données nécessite un ou plusieurs services auxquels envoyer des données. Configurez Adobe Experience Platform en tant que service dans votre flux de données.<br><br>L’ajout de services à un flux de données est un processus simple qui ne prend que quelques minutes."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un flux de données doit déjà exister avant la réalisation des étapes de cette section. La date de création du flux de données et la manière dont il a été créé dépendent de votre implémentation Adobe Analytics, comme suit :

* Si votre implémentation d’Adobe Analytics utilise Web SDK ou l’extension Web SDK, le flux de données était disponible pour votre environnement Adobe Analytics avant le processus de mise à niveau.

* Pour les autres implémentations d’Adobe Analytics, la création d’un flux de données fait partie du processus de mise à niveau, comme décrit dans la section [Créer un flux de données à utiliser avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

Une fois le flux de données disponible, vous devez ajouter Platform as a service :

1. Dans l’interface utilisateur d’Adobe Experience Platform, sélectionnez **[!UICONTROL Flux de données]** sous [!UICONTROL COLLECTE DE DONNÉES] dans le rail de gauche.

1. Sélectionnez le flux de données précédemment configuré. <!--true?-->

1. Sélectionnez **[!UICONTROL Ajouter un service]**.

1. Sur l’[!UICONTROL écran Ajouter un service] :

   1. Sélectionnez **[!UICONTROL Adobe Experience Platform]** dans la liste [!UICONTROL Service].

   1. Assurez-vous que l’option **[!UICONTROL Activé]** est sélectionnée.

   1. Sélectionnez le jeu de données dans la liste [!UICONTROL Jeu de données d’événement].

      ![Service AEP de flux de données](./assets/datastream-aep-service.png)

   1. Gardez les autres paramètres et sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer le flux de données.

   Le flux de données est maintenant configuré pour transférer les données collectées depuis le site Web vers le jeu de données dans Adobe Experience Platform.

   Consultez [Présentation des flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=fr) pour plus d’informations sur la configuration d’un flux de données et la gestion des données sensibles.

{{upgrade-final-step}}
