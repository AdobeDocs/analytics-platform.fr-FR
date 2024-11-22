---
title: Transition du connecteur source Analytics vers le SDK Web pour Customer Journey Analytics
description: Découvrez comment passer au SDK Web à partir du connecteur source Analytics lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Transition du connecteur source Analytics vers le SDK Web pour Customer Journey Analytics

>[!NOTE]
> 
>Utilisez les informations de cette page pour répondre aux questions de la [liste de contrôle de mise à niveau des Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

L’utilisation du connecteur source Analytics comme seule implémentation pour Customer Journey Analytics présente des inconvénients.

Si votre entreprise a déjà effectué la mise à niveau vers Customer Journey Analytics à l’aide de l’implémentation du connecteur source Analytics uniquement, vous devez envisager de passer à une implémentation qui utilise le connecteur source Analytics (pour transférer des données historiques), conjointement avec une nouvelle implémentation du SDK web (pour la collecte de données en cours).

## Comprendre les avantages et les inconvénients de l’utilisation exclusive du connecteur source Analytics

Pour plus d’informations sur les avantages et les inconvénients de l’utilisation du connecteur source Analytics, voir [Utilisation du connecteur source Analytics exclusivement pour la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Transition du connecteur source Analytics vers le SDK Web

Vous trouverez ci-dessous le processus de haut niveau pour passer de l’utilisation exclusive du connecteur source Analytics à une implémentation composée à la fois du connecteur source Analytics et d’une implémentation du SDK Web :

1. Créez une implémentation du SDK Web, comme décrit dans la section [Étapes de mise à niveau recommandées détaillées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) de l’article [Mise à niveau d’Adobe Analytics vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Une fois l’implémentation du SDK Web configurée, procédez comme suit.

1. [Créez un schéma XDM pour le connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Mappez chaque dimension Adobe Analytics de votre connecteur source Analytics à la dimension dans le schéma SDK Web.

   1. 
      <!-- how do you get here -->

   1. Dans la section **[!UICONTROL Mapper les champs standard]** , sélectionnez l’onglet **[!UICONTROL Personnalisé]** .

   1. Sélectionnez **[!UICONTROL Ajouter un nouveau mapping]**.

      ![Champs de schéma de carte](assets/schema-mapping.png)

   1. Dans le **[!UICONTROL champ Source]**, sélectionnez un champ Adobe Analytics dans le groupe de champs Modèle Adobe Analytics ExperienceEvent. Ensuite, dans le **[!UICONTROL champ cible]**, sélectionnez le champ XDM vers lequel vous souhaitez le mapper.

   1. Répétez cette procédure pour chaque champ du groupe de champs Modèle ExperienceEvent Adobe Analytics que vous utilisez pour collecter des données dans Adobe Analytics.

1. Ajoutez le jeu de données qui a été automatiquement créé avec votre connecteur source Analytics d’origine à votre connexion de Customer Journey Analytics.

   Pour plus d’informations, voir [Ajout du jeu de données de votre connecteur source Analytics actuel à la connexion](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Conditionnel) Si vous utilisez des jeux de données de recherche, vous devez créer le jeu de données de recherche et l’ajouter à votre connexion. Pour plus d’informations, voir [Création de jeux de données de recherche pour classer les données dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Supprimez votre connecteur source Analytics d’origine. <!-- need to add steps somewhere about how to do this -->

1. [Créez un connecteur source Analytics et mappez des champs](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).
