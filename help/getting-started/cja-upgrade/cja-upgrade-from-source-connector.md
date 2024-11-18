---
title: Passage du connecteur source Analytics au SDK Web pour Customer Journey Analytics
description: Découvrez comment passer au SDK Web à partir du connecteur source Analytics lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Passage du connecteur source Analytics au SDK Web pour Customer Journey Analytics

>[!NOTE]
> 
>Utilisez les informations de cette page pour répondre aux questions de la [liste de contrôle de mise à niveau des Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

L’utilisation du connecteur source Analytics comme seule implémentation pour Customer Journey Analytics présente des inconvénients. Si votre entreprise a déjà effectué la mise à niveau vers Customer Journey Analytics à l’aide de l’implémentation du connecteur source Analytics uniquement, envisagez de passer à une implémentation du SDK Web.

Adobe recommande d’utiliser le connecteur source Analytics (pour la récupération des données historiques), conjointement avec une nouvelle implémentation du SDK web (pour la collecte de données en cours).

## Comprendre les avantages et les inconvénients de l’utilisation exclusive du connecteur source Analytics

Pour plus d’informations sur les avantages et les inconvénients de l’utilisation du connecteur source Analytics, voir [Utilisation du connecteur source Analytics exclusivement pour la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Passage du connecteur source Analytics au SDK Web

Voici le processus de haut niveau permettant de passer du connecteur source Analytics à une implémentation composée à la fois du connecteur source Analytics et d’une implémentation du SDK Web :

1. Créez une implémentation du SDK Web, comme décrit dans la section [Étapes de mise à niveau recommandées détaillées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) de l’article [Mise à niveau d’Adobe Analytics vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Une fois l’implémentation du SDK Web configurée, passez à l’étape suivante.

1. Décidez si vous utiliserez le schéma Adobe Analytics ou un schéma XDM dans votre mise en oeuvre du SDK Web.

   Pour plus d’informations, voir [Choix de votre schéma pour Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

1. (Conditionnel) Si vous prévoyez d’utiliser le schéma Adobe Analytics, ajoutez le jeu de données automatiquement créé par le connecteur source Analytics à votre connexion de Customer Journey Analytics.

   Pour plus d’informations, voir [Ajout du jeu de données du connecteur source Analytics à la connexion](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Conditionnel) Si vous prévoyez de créer un schéma XDM :

   1. [Créez un schéma XDM pour le connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

   1. Ajoutez le jeu de données qui a été automatiquement créé avec votre connecteur source Analytics d’origine à votre connexion de Customer Journey Analytics.

      Pour plus d’informations, voir [Ajout du jeu de données de votre connecteur source Analytics actuel à la connexion](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

   1. Supprimez votre connecteur source Analytics d’origine. <!-- need to add steps somewhere about how to do this -->

   1. [Créez un connecteur source Analytics et mappez des champs](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).








