---
title: Créer un schéma pour Customer Journey Analytics
description: En savoir plus sur le chemin recommandé lors de la mise à niveau à partir d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
autotag-review: '2026-05-19T08:12:37.701Z'
TQID: 'https://experienceleague.adobe.com/ncFpZWJRFzOg8eFg6OF7TfAw6fZRhSdKi6W-LxPUAGg'
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 280
ht-degree: 100%

---

# Ajouter Platform en tant que service au train de données {#upgrade-addplatform-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-addplatform-datastream"
>title="Ajouter Adobe Experience Platform en tant que service au flux de données"
>abstract="Un train de données nécessite un ou plusieurs services auxquels envoyer des données. Configurez Adobe Experience Platform en tant que service dans votre train de données.<br><br>L’ajout de services à un train de données est un processus simple qui ne prend que quelques minutes."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un train de données doit déjà exister avant la réalisation des étapes de cette section. La date de création du train de données et la manière dont il a été créé dépendent de votre implémentation Adobe Analytics, comme sui :

* Si votre implémentation d’Adobe Analytics utilise le SDK web ou l’extension SDK web, le train de données était disponible pour votre environnement Adobe Analytics avant le processus de mise à niveau.

* Pour les autres implémentations d’Adobe Analytics, la création d’un train de données fait partie du processus de mise à niveau, comme décrit dans la section [Créer un train de données à utiliser avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

Une fois le train de données disponible, vous devez ajouter Platform en tant que service :

1. Dans l’interface utilisateur d’Adobe Experience Platform, sélectionnez **[!UICONTROL Flux de données]** sous [!UICONTROL COLLECTE DE DONNÉES] dans le rail de gauche.

1. Sélectionnez le train de données précédemment configuré. <!--true?-->

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
