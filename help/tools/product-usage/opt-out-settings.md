---
title: Paramètres d’exclusion de l’utilisation du produit
description: Gérez les paramètres d’exclusion pour les utilisateurs individuels de votre entreprise.
hide: true
hidefromtoc: true
source-git-commit: f337dfbd780aab4ae40534c5c1151dba35681b21
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# Paramètres d’exclusion de l’utilisation du produit {#product-usage-opt-out-settings}

{{release-limited-testing}}

La page _Paramètres d’exclusion_ vous permet d’exclure ou de réinclure des utilisateurs de votre organisation du suivi de l’utilisation des produits. Elle n’est visible que par les administrateurs de produit.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Outils]** > **[!UICONTROL Utilisation du produit]** > **[!UICONTROL Paramètres d’exclusion]**

Les paramètres suivants sont disponibles sur cette page :

* **[!UICONTROL Utilisateur d’exclusion]** : liste déroulante contenant tous les utilisateurs Customer Journey Analytics de votre entreprise. Sélectionnez un utilisateur dans cette liste déroulante et sélectionnez **[!UICONTROL Opt-out]** pour exclure cet utilisateur du suivi de l’utilisation des produits. Cet utilisateur est ajouté au tableau [!UICONTROL Liste des utilisateurs exclus] ci-dessous.
* **[!UICONTROL Liste des utilisateurs exclus]** : tableau qui présente tous les utilisateurs qui sont actuellement désinscrits du suivi de l’utilisation des produits. Pour réactiver le suivi de l’utilisation des produits par un utilisateur, cochez la case en regard d’un utilisateur donné, puis cliquez sur le bouton **[!UICONTROL Opt-in]** .

Adobe utilise une combinaison de suivi côté client et côté serveur pour collecter les données d’utilisation des produits pour votre entreprise. Lorsqu’un utilisateur est initialement exclu, il peut toujours voir les données de suivi côté client dans son débogueur jusqu’à ce qu’il se déconnecte et se reconnecte à Customer Journey Analytics. La validation côté serveur d’Adobe garantit que les données de suivi côté client sont ignorées pour les utilisateurs désinscrits.

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="Exclusion des utilisateurs"
>abstract="Excluez les utilisateurs du suivi de l’utilisation des produits."
