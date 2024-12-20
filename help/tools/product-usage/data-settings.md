---
title: Paramètres des données dʼutilisation des produits
description: Activez, désactivez ou configurez les paramètres d’utilisation du produit.
source-git-commit: 7d22c512e8e96963b288567704d2245e64411b10
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 14%

---

# Paramètres des données dʼutilisation des produits {#product-usage-data-settings}

{{release-limited-testing}}

La page _Paramètres des données_ traite votre configuration d’utilisation du produit. Vous pouvez utiliser cette page pour activer ou désactiver l’utilisation du produit pour votre entreprise. Vous pouvez également configurer l’environnement de test Adobe Experience Platform sous lequel le jeu de données est créé et remplacer la fenêtre de rétention des données si vous le souhaitez. Elle n’est visible que par les administrateurs de produit.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Outils]** > **[!UICONTROL Utilisation du produit]** > **[!UICONTROL Paramètres des données]**

>[!IMPORTANT]
>Lorsque vous activez cette fonction, vous devez accepter les conditions générales avant de l’utiliser. Lorsque vous acceptez ces conditions générales, vous le faites au nom de l’ensemble de votre organisation.

Les paramètres suivants sont disponibles sur cette page :

* **[!UICONTROL Activer l’utilisation du produit]** : active la disponibilité de la collecte de données d’utilisation du produit. Si vous activez l’utilisation du produit, puis le désactivez ultérieurement, le jeu de données, la connexion et la vue de données ne sont pas supprimés. Le suivi est désactivé globalement pour votre organisation lorsqu’il est désactivé.
* **[!UICONTROL Sandbox]** : détermine l’environnement de test Adobe Experience Platform sous lequel le schéma et le jeu de données sont créés. L’environnement de test que vous choisissez n’a aucune incidence sur la collecte de données d’utilisation du produit. Si vous modifiez ce paramètre d’environnement de test, toutes les données existantes sont supprimées. Un nouveau jeu de données, une nouvelle connexion et une nouvelle vue de données sont créés dans l’environnement de test sélectionné.
* **[!UICONTROL Remplacer la fenêtre de rétention des données]** : chaque jeu de données comporte une fenêtre de rétention des données par défaut. Si ce paramètre est désactivé, l’utilisation du produit suit cette période par défaut. Vous pouvez activer ce paramètre si vous souhaitez raccourcir la durée de conservation des données. Réduire la période de rétention des données et réduire les coûts afin de vous permettre de respecter les directives de confidentialité spécifiques aux employés. Vous ne pouvez pas étendre la rétention des données au-delà de la fenêtre de rétention des données par défaut du jeu de données.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Sandbox Adobe Experience Platform"
>abstract="Détermine le sandbox Adobe Experience Platform dans lequel sont créés le schéma et le jeu de données."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Remplacement de la période de conservation des données"
>abstract="Raccourcissez la disponibilité des données d’utilisation du produit afin de réduire les coûts et de respecter les directives en matière de confidentialité."
