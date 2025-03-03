---
title: Création d’un schéma pour Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 48%

---

# Créer un flux de données à utiliser avec Customer Journey Analytics {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Créer un flux de données dans Adobe Experience Platform"
>abstract="Un flux de données est un emplacement intermédiaire qui transmet vos données à tous les services configurés. Créez cet emplacement dans Adobe Experience Platform.<br><br>La création initiale d’un flux de données dans l’interface de Platform ne prend que quelques minutes."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un flux de données représente la configuration côté serveur lors de la mise en œuvre des SDK Web et Mobile Adobe Experience Platform. Lors de la collecte de données avec les SDK Adobe Experience Platform, les données sont envoyées à Adobe Experience Platform Edge Network. Il s’agit du flux de données qui détermine les services vers lesquels ces données sont transférées.

Dans votre configuration, vous souhaitez configurer le flux de données pour envoyer les données collectées à votre jeu de données dans Adobe Experience Platform.

>[!NOTE]
>
>Les étapes suivantes ne sont requises que pour les implémentations d’Adobe Analytics utilisant AppMeasurement ou l’extension Analytics (balises).
>
>Si votre mise en œuvre Adobe Analytics utilise le SDK Web ou l’extension Web SDK, le flux de données existe déjà dans votre environnement Adobe Analytics.

Configurer le flux de données :

1. Dans Adobe Experience Platform, sélectionnez **[!UICONTROL Flux de données]** sous [!UICONTROL COLLECTE DE DONNÉES] dans le rail de gauche.

1. Sélectionnez **[!UICONTROL Nouveau flux de données]**.

1. Nommez et décrivez le flux de données. Sélectionnez le schéma dans la liste [!UICONTROL Schéma d’événement].

   ![Nouveau flux de données](assets/new-datastream.png)

1. Sélectionnez **[!UICONTROL Enregistrer]**.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
