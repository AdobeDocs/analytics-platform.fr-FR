---
title: Transition du connecteur source Analytics vers le SDK web pour Customer Journey Analytics
description: Découvrez comment effectuer une transition vers le SDK Web à partir du connecteur source Analytics lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 30%

---

# Transition du connecteur source Analytics vers le SDK web pour Customer Journey Analytics {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Mise en œuvre du connecteur source Analytics"
>abstract="Le connecteur source Analytics vous permet de tirer plus facilement parti de Customer Journey Analytics. Vous devez toutefois payer pour Adobe Analytics et Customer Journey Analytics. Ce guide peut vous aider à passer à une mise en œuvre indépendante du SDK web."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-delete"
>title="Supprimer le connecteur source Analytics existant"
>abstract="Le connecteur source Analytics dont vous disposez actuellement n’est pas compatible avec le schéma personnalisé de votre organisation. Toutefois, les données sont conservées dans la suite de rapports Analytics. Cette étape supprime le connecteur source Analytics actuel afin que vous puissiez le recréer à l’aide du schéma approprié lors d’une étape ultérieure.<br><br>Avant de supprimer le connecteur source, vous pouvez contacter d’autres membres de votre organisation pour vous assurer que cette suppression n’a pas d’incidence sur la création de rapports au sein de votre organisation. Ces échanges peuvent prendre plusieurs semaines."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

L’utilisation du connecteur source Analytics comme seule implémentation pour Customer Journey Analytics présente des inconvénients inhérents.

Si votre organisation a déjà effectué la mise à niveau vers Customer Journey Analytics à l’aide de l’implémentation du connecteur source Analytics uniquement, Adobe recommande de passer à une nouvelle implémentation de Web SDK pour la collecte de données en cours, et d’utiliser le connecteur source Analytics uniquement pour les données historiques.

## Comprendre les avantages et les inconvénients de l’utilisation exclusive du connecteur source Analytics

Pour plus d’informations sur les avantages et les inconvénients de l’utilisation du connecteur source Analytics, voir [ Utiliser le connecteur source Analytics exclusivement pour effectuer la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md).

## Transition du connecteur source Analytics vers Web SDK

Voici le processus de haut niveau pour passer de l’utilisation exclusive du connecteur source Analytics à une implémentation composée du connecteur source Analytics et d’une implémentation de Web SDK :

1. Créez une implémentation de Web SDK, comme décrit dans [Étapes de mise à niveau recommandées détaillées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) dans l’article [Mise à niveau d’Adobe Analytics vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Une fois l’implémentation de Web SDK configurée, procédez comme suit.

1. [Créez un schéma XDM pour le connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Mappez chaque dimension Adobe Analytics de votre connecteur source Analytics à la dimension dans le schéma Web SDK.

   1. 
      <!-- how do you get here -->

   1. Dans la section **[!UICONTROL Mapper les champs standard]**, sélectionnez l’onglet **[!UICONTROL Personnalisé]**.

   1. Sélectionnez **[!UICONTROL Ajouter un nouveau mappage]**.

      ![mapper les champs de schéma](assets/schema-mapping.png)

   1. Dans le champ **[!UICONTROL Source]** sélectionnez un champ Adobe Analytics dans le groupe de champs Modèle Adobe Analytics ExperienceEvent . Ensuite, dans le **[!UICONTROL Champ cible]**, sélectionnez le champ XDM vers lequel vous souhaitez le mapper.

   1. Répétez cette procédure pour chaque champ du groupe de champs Modèle ExperienceEvent Adobe Analytics que vous utilisez pour collecter des données dans Adobe Analytics.

1. Ajoutez le jeu de données automatiquement créé avec le connecteur source Analytics d’origine à votre connexion Customer Journey Analytics.

   Pour plus d’informations, voir [Ajouter le jeu de données de votre connecteur source Analytics actuel à la connexion](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Conditionnel) Si vous utilisez des jeux de données de recherche, vous devez créer le jeu de données de recherche et l’ajouter à votre connexion. Pour plus d’informations, voir [Création de jeux de données de recherche pour classer les données dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Supprimez le connecteur source Analytics d’origine. <!-- need to add steps somewhere about how to do this -->

1. [Créer un connecteur source Analytics et mapper les champs](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

{{upgrade-final-step}}
