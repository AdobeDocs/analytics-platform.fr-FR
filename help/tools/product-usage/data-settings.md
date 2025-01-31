---
title: Paramètres des données dʼutilisation des produits
description: Activer, désactiver ou configurer les paramètres d’utilisation du produit.
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 23%

---

# Paramètres des données dʼutilisation des produits {#product-usage-data-settings}

La page _Paramètres des données_ gère la configuration de l’utilisation du produit. Vous pouvez utiliser cette page pour activer ou désactiver l’utilisation des produits pour votre organisation. Vous pouvez également configurer le sandbox Adobe Experience Platform sous lequel le jeu de données est créé et remplacer la fenêtre de conservation des données si vous le souhaitez. Il n’est visible que par les administrateurs du produit.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Outils]** > **[!UICONTROL Utilisation du produit]** > **[!UICONTROL Paramètres des données]**

>[!IMPORTANT]
>Lorsque vous activez cette fonctionnalité, vous devez accepter les conditions générales avant de l’utiliser. Lorsque vous acceptez les présentes conditions générales, vous le faites au nom de l’ensemble de votre entreprise.

Les paramètres suivants sont disponibles sur cette page :

* **[!UICONTROL Activer l’utilisation du produit]** : active/désactive la disponibilité de la collecte de données d’utilisation du produit. Si vous activez l’utilisation du produit, puis le désactivez à l’avenir, le jeu de données, la connexion et la vue de données ne sont pas supprimés. Lorsqu’il est désactivé, le suivi est désactivé au niveau mondial pour votre organisation.
* **[!UICONTROL Sandbox]** : détermine le sandbox Adobe Experience Platform sous lequel le schéma et le jeu de données sont créés. Le sandbox que vous choisissez n’a aucune incidence sur la collecte de données d’utilisation des produits. Si vous modifiez ce paramètre de sandbox, toutes les données existantes sont supprimées. Un nouveau jeu de données, une nouvelle connexion et une nouvelle vue de données sont créés dans le sandbox sélectionné.
* **[!UICONTROL Remplacer la fenêtre de conservation des données]** : chaque jeu de données a une fenêtre de conservation des données par défaut. Si ce paramètre est désactivé, l’utilisation du produit suit cette période par défaut. Vous pouvez activer ce paramètre si vous souhaitez réduire la durée de conservation des données. Réduction de la période de conservation des données, réduction des coûts et respect des règles de confidentialité spécifiques aux employés. Vous ne pouvez pas étendre la conservation des données au-delà de la fenêtre de conservation des données par défaut du jeu de données.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Sandbox Adobe Experience Platform"
>abstract="Détermine le sandbox Adobe Experience Platform dans lequel sont créés le schéma et le jeu de données."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Remplacement de la période de conservation des données"
>abstract="Raccourcissez la disponibilité des données d’utilisation du produit afin de réduire les coûts et de respecter les directives en matière de confidentialité."

>[!CONTEXTUALHELP]
>id="product_usage_sandbox"
>title="Sandbox Adobe Experience Platform"
>abstract="Détermine le sandbox Adobe Experience Platform dans lequel sont créés le schéma et le jeu de données."

>[!CONTEXTUALHELP]
>id="product_usage_data_retention"
>title="Remplacement de la période de conservation des données"
>abstract="Raccourcissez la disponibilité des données d’utilisation du produit afin de réduire les coûts et de respecter les directives en matière de confidentialité."
