---
description: Comment poser des questions à la documentation du Customer Journey Analytics
title: Assistant IA pour Adobe Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
source-git-commit: 20b578a6269aeaf54f6296b1f4337937887ecf05
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 2%

---


# Assistant IA pour Adobe Customer Journey Analytics

L’assistant d’IA est une expérience conversationnelle qui permet aux utilisateurs d’effectuer rapidement des tâches. Il s’agit de comprendre les concepts, de résoudre les problèmes ou de rechercher des informations. L’assistant d’IA permet également aux non-experts d’effectuer des tâches d’expert et d’améliorer la qualité générale du travail.

L’assistant d’IA en Customer Journey Analytics est formé à la documentation de Adobe Experience League. Lorsqu’une question est posée, l’assistant d’IA répond avec une réponse utile qui permet un apprentissage rapide.

En tant qu’utilisateur novice, vous pouvez utiliser l’assistant d’IA pour découvrir les concepts de Customer Journey Analytics et vous inscrire à des produits et fonctionnalités que vous ne connaissez pas. En tant qu’utilisateur expérimenté, vous pouvez utiliser l’assistant d’IA pour présenter des cas d’utilisation plus avancés ou des conseils et astuces.

Voici quelques exemples de questions conceptuelles :

* Quelle est la différence entre l’ingestion par lots et l’ingestion par flux ?
* À quoi Customer Journey Analytics est-il le mieux utilisé ?
* Comment configurer une vue de données ?

Il n’est pas possible de répondre à des questions en dehors de la portée de Customer Journey Analytics, telles que des questions sur d’autres produits Adobe tels qu’Adobe Target et Adobe Creative Cloud Suite.

L’assistant d’IA pour les Customer Journey Analytics est disponible pour tous les niveaux de produit.

## Connaissances produit {#knowledge}

Le modèle de récupération des connaissances du produit est formé sur Customer Journey Analytics. D’autres fonctionnalités, telles que l’analyse des données, seront déployées ultérieurement.

| Connaissances produit | Exemples |
| --- | --- |
| Apprentissage pointé | <ul><li>Quelle est la différence entre Adobe Analytics et Customer Journey Analytics ?</li><li>Comment créer une mesure calculée ?</li></ul> |
| Découverte ouverte | <ul><li>Comment exporter un projet Workspace ?</li><li>Comment puis-je trouver des composants Workspace en double ?</li></ul> |
| Résolution des problèmes | <ul><li>Combien de temps faut-il pour que les données entrent dans CJA ?</li><li>Combien de champs dérivés puis-je avoir dans une connexion de Customer Journey Analytics ?</li></ul> |

## Accès aux fonctionnalités

Les paramètres suivants régissent l’accès à la fonctionnalité de l’assistant d’IA :

* **Accès aux solutions** : l’assistant d’IA est disponible en Customer Journey Analytics, mais pas dans Adobe Analytics. Il est également disponible dans Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP et d’autres applications Experience Platform.

* **Accès contractuel** : si vous ne pouvez pas utiliser l’assistant d’IA, contactez l’administrateur ou le représentant du compte d’Adobe de votre entreprise. Avant de pouvoir utiliser l’assistant d’IA, votre entreprise doit accepter certaines dispositions légales relatives à l’IA dédiée à Gen.

* **Autorisations** : dans le [!UICONTROL Adobe Admin Console], l’autorisation [!UICONTROL Outils de création de rapports] **[!UICONTROL Assistant d’IA : connaissance du produit]** détermine l’accès à cet outil. Un [ administrateur de profil de produit ](https://helpx.adobe.com/fr/enterprise/using/manage-product-profiles.html) doit suivre les étapes suivantes dans l’ [!UICONTROL Admin Console] :
   1. Accédez à **[!UICONTROL Admin Console]** > **[!UICONTROL Produits et services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Profils de produit]**
   1. Sélectionnez le titre du profil de produit pour lequel vous souhaitez donner accès à [!UICONTROL Assistant IA : connaissance du produit].
   1. Dans le profil de produit spécifique, sélectionnez **[!UICONTROL Autorisations]**.
   1. Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) pour modifier les **[!UICONTROL outils de création de rapports]**.
   1. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) pour ajouter **Assistant IA : connaissance du produit** à **[!UICONTROL Éléments d’autorisation inclus]**.

      ![Ajouter une autorisation](assets/ai-assistant-permissions.png).

   1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les autorisations.

Voir [Contrôle d’accès](/help/technotes/access-control.md#access-control) pour plus d’informations.

## Accès à l’assistant d’IA dans l’interface utilisateur de Customer Journey Analytics

1. Pour lancer l’assistant d’IA, sélectionnez l’icône de l’assistant dans l’en-tête supérieur d’une page de l’interface utilisateur du Customer Journey Analytics.

   ![Icône de l’assistant d’IA](assets/ai-asst1.png)

   Lors de l’utilisation initiale de l’assistant d’IA, une clause de non-responsabilité s’affiche avec certaines conditions d’utilisation de l’assistant.

1. Dans la boîte de dialogue fournie, posez une question spécifique en langage naturel à l’assistant d’IA.

   ![Zone de question](assets/ai-asst2.png)

1. (Facultatif) Pour afficher les sources, cliquez sur **[!UICONTROL Afficher les sources]** et la ou les sources de documentation qui ont fourni la réponse s’affichent.

1. (Facultatif) Vous pouvez également fournir un vote par pouce ou par pouce sur l’utilité d’une réponse donnée.

1. (Facultatif) Vous pouvez marquer la réponse pour du contenu inapproprié ou nocif.
