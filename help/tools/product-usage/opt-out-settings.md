---
title: Paramètres d’exclusion de l’utilisation du produit
description: Gérez les paramètres d’opt-out pour les utilisateurs individuels au sein de votre organisation.
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 11%

---

# Paramètres d’exclusion de l’utilisation du produit {#product-usage-opt-out-settings}

{{release-limited-testing}}

La page _Paramètres d’opt-out_ vous permet d’exclure ou de réinclure des utilisateurs de votre organisation dans le suivi de l’utilisation des produits. Il n’est visible que par les administrateurs du produit.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Outils]** > **[!UICONTROL Utilisation du produit]** > **[!UICONTROL Paramètres d’exclusion]**

Les paramètres suivants sont disponibles sur cette page :

* **[!UICONTROL Utilisateur s’excluant]** : liste déroulante contenant tous les utilisateurs du Customer Journey Analytics de votre organisation. Sélectionnez un utilisateur dans cette liste déroulante, puis sélectionnez **[!UICONTROL Opt-out]** pour l’exclure du suivi de l’utilisation du produit. Cet utilisateur est ajouté au tableau [!UICONTROL Liste des utilisateurs désinscrits] ci-dessous.
* **[!UICONTROL Liste des utilisateurs désinscrits]** : un tableau qui vous indique tous les utilisateurs qui sont actuellement désinscrits du suivi de l’utilisation des produits. Pour réintégrer un utilisateur dans le suivi de l’utilisation des produits, cochez la case en regard d’un utilisateur donné, puis cliquez sur le bouton **[!UICONTROL Souscription]**.

Adobe utilise une combinaison de suivi côté client et côté serveur pour collecter des données d’utilisation des produits pour votre organisation. Lorsqu’un utilisateur est initialement désinscrit, il peut toujours voir les données de suivi côté client dans son débogueur jusqu’à ce qu’il se déconnecte et se reconnecte à Customer Journey Analytics. La validation côté serveur d’Adobe garantit que les données de suivi côté client sont ignorées pour les utilisateurs exclus.

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="Exclusion des utilisateurs et utilisatrices"
>abstract="Excluez les utilisateurs et utilisatrices du suivi de l’utilisation des produits."

>[!CONTEXTUALHELP]
>id="product_usage_opt_out_settings"
>title="Exclusion des utilisateurs et utilisatrices"
>abstract="Excluez les utilisateurs et utilisatrices du suivi de l’utilisation des produits."
