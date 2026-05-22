---
title: Créer un schéma pour Customer Journey Analytics
description: En savoir plus sur le chemin recommandé lors de la mise à niveau à partir d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
autotag-review: '2026-05-19T08:13:03.106Z'
TQID: 'https://experienceleague.adobe.com/vzavQGq0OyhXTpSkqe3nnXQEW0Nax9RXt4SwTRwa4UU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 100%

---

# Créer un train de données à utiliser avec Customer Journey Analytics {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Créer un flux de données dans Adobe Experience Platform"
>abstract="Un train de données est un emplacement intermédiaire qui transmet vos données à tous les services configurés. Créez cet emplacement dans Adobe Experience Platform.<br><br>La création initiale d’un flux de données dans l’interface de Platform ne prend que quelques minutes."

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
