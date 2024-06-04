---
description: Comment poser des questions à la documentation du Customer Journey Analytics
title: Assistant IA pour Adobe Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
hide: true
hidefromtoc: true
source-git-commit: 7e2a372d6e1fcbcfc26a63ddc804a592d6ee1725
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---


# Assistant IA pour Adobe Customer Journey Analytics

>[!NOTE]
>
>L’assistant d’IA pour le Customer Journey Analytics est actuellement en version bêta. La fonctionnalité et sa documentation peuvent faire l’objet de modifications.

L’assistant d’IA est une expérience conversationnelle qui permet aux utilisateurs d’effectuer rapidement des tâches, que ce soit en termes de compréhension des concepts, de résolution des problèmes ou de recherche d’informations. Il permet également aux non-experts d&#39;effectuer des tâches d&#39;experts et d&#39;améliorer la qualité générale du travail.

L’assistant d’IA en Customer Journey Analytics est formé à la documentation de Adobe Experience League. Lorsqu’une question est posée, l’assistant d’IA répond avec une réponse utile qui permet un apprentissage rapide.

En tant qu’utilisateur novice, vous pouvez utiliser l’assistant d’IA pour découvrir les concepts de Customer Journey Analytics et vous inscrire à des produits et fonctionnalités que vous ne connaissez pas. En tant qu’utilisateur expérimenté, vous pouvez utiliser l’assistant d’IA pour présenter des cas d’utilisation plus avancés ou des conseils et astuces.

Voici quelques exemples de questions conceptuelles :

* Quelle est la différence entre l’ingestion par lots et l’ingestion par flux ?
* À quoi Customer Journey Analytics est-il le mieux utilisé ?
* Comment configurer une vue de données ?

## Connaissances produit {#knowledge}

Le modèle de récupération des connaissances du produit est formé sur Customer Journey Analytics. D’autres fonctionnalités, telles que l’analyse des données, seront déployées ultérieurement.

| Connaissances produit | Exemples |
| --- | --- |
| Apprentissage pointé | <ul><li>Quelle est la différence entre Adobe Analytics et Customer Journey Analytics ?</li><li>Comment créer une mesure calculée ?</li></ul> |
| Découverte ouverte | <ul><li>Comment exporter un projet Workspace ?</li><li>Comment puis-je trouver des composants Workspace en double ?</li></ul> |
| Résolution des problèmes | <ul><li>Combien de temps faut-il pour que les données entrent dans CJA ?</li><li>Combien de champs dérivés puis-je avoir dans une connexion de Customer Journey Analytics ?</li></ul> |

Il n’est pas possible de répondre à des questions en dehors de la portée de Customer Journey Analytics, telles que des questions sur d’autres produits Adobe tels qu’Adobe Target et Adobe Creative Cloud Suite.

L’assistant d’IA pour les Customer Journey Analytics est disponible pour tous les niveaux de produit.

## Accès aux fonctionnalités

Dans cette première version, l’accès à la fonction d’assistant d’IA est régi par les paramètres suivants :

* **Accès aux solutions**: l’assistant d’IA est disponible en Customer Journey Analytics, mais pas dans Adobe Analytics. Il est également disponible dans Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP et d’autres applications Experience Platform.

* **Accès contractuel**: si vous ne pouvez pas utiliser l’assistant d’IA, contactez l’administrateur ou le représentant du compte d’Adobe de votre entreprise. Avant que votre entreprise puisse utiliser l’assistant d’IA, elle doit accepter certaines dispositions légales relatives à GenAI.

* **Autorisations**: dans [!UICONTROL Adobe Admin Console], la variable [!UICONTROL Outils de création de rapports] L’autorisation &quot;Assistant IA : connaissance du produit&quot; détermine l’accès à cet outil.
A [administrateur de profil de produit](https://helpx.adobe.com/fr/enterprise/using/manage-product-profiles.html) doit suivre les étapes suivantes en Admin Console :
   1. Accédez à [!UICONTROL Admin Console] > [!UICONTROL Produits et services] > [!UICONTROL Customer Journey Analytics] > [!UICONTROL Profil de produits] > [!UICONTROL Autorisations] > [!UICONTROL Modifier les outils de création de rapports].
   1. Ajoutez &quot;Assistant IA : Connaissances produit&quot;.

## Accès à l’assistant d’IA dans l’interface utilisateur de Customer Journey Analytics

1. Pour lancer l’assistant d’IA, sélectionnez l’icône de l’assistant dans l’en-tête supérieur d’une page de l’interface utilisateur du Customer Journey Analytics.

   ![Icône Assistant IA](assets/ai-asst1.png)

   Lors de l’utilisation initiale de l’assistant d’IA, une clause de non-responsabilité s’affiche avec certaines conditions d’utilisation de l’assistant.

1. Dans la boîte de dialogue fournie, posez une question spécifique en langage naturel à l’assistant d’IA.

   ![Zone de question](assets/ai-asst2.png)

1. (Facultatif) Pour afficher les sources, cliquez sur **[!UICONTROL Afficher les sources]**, et la ou les sources de documentation qui ont informé la réponse s’affichent.

1. (Facultatif) Vous pouvez également fournir un vote par pouce ou par pouce sur l’utilité d’une réponse donnée.
