---
title: Créer un schéma pour Customer Journey Analytics
description: En savoir plus sur le chemin recommandé lors de la mise à niveau à partir d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 100%

---

# Créer un train de données à utiliser avec Customer Journey Analytics {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Créer un flux de données dans Adobe Experience Platform"
>abstract="Un train de données est un emplacement intermédiaire qui transmet vos données à tous les services configurés. Créez cet emplacement dans Adobe Experience Platform.<br><br>La création initiale d’un train de données dans l’interface de Platform ne prend que quelques minutes."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un flux de données représente la configuration côté serveur lors de la mise en œuvre des SDK Web et Mobile Adobe Experience Platform. Lors de la collecte de données avec les SDK Adobe Experience Platform, les données sont envoyées à Adobe Experience Platform Edge Network. Il s’agit du train de données qui détermine les services vers lesquels les données sont transférées.

Dans votre configuration, vous souhaitez configurer le train de données pour envoyer les données collectées à votre jeu de données dans Adobe Experience Platform.

>[!NOTE]
>
>Les étapes suivantes ne sont requises que pour les implémentations d’Adobe Analytics utilisant AppMeasurement ou l’extension Analytics (balises).
>
>Si votre implémentation Adobe Analytics utilise le SDK web ou l’extension SDK wev, le train de données existe déjà dans votre environnement Adobe Analytics.

Configurer le flux de données :

1. Dans Adobe Experience Platform, sélectionnez **[!UICONTROL Trains de données]** sous [!UICONTROL COLLECTE DE DONNÉES] dans le rail de gauche.

1. Sélectionnez **[!UICONTROL Nouveau flux de données]**.

1. Nommez et décrivez le flux de données. Sélectionnez le schéma dans la liste [!UICONTROL Schéma d’événement].

   ![Nouveau flux de données](assets/new-datastream.png)

1. Sélectionnez **[!UICONTROL Enregistrer]**.

{{upgrade-final-step}}
