---
title: Paramètres des données d’utilisation du produit
description: Activez, désactivez ou configurez les paramètres d’utilisation du produit.
hide: true
hidefromtoc: true
source-git-commit: 8f2a340f59d8cdf97a5309ec20dc36f49b8f1129
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---

# Paramètres des données d’utilisation du produit {#product-usage-data-settings}

{{release-limited-testing}}

La page _Paramètres des données_ traite votre configuration d’utilisation du produit. Vous pouvez utiliser cette page pour activer ou désactiver l’utilisation du produit pour votre entreprise. Vous pouvez également configurer l’environnement de test Adobe Experience Platform sous lequel le jeu de données est créé et remplacer la fenêtre de rétention des données si vous le souhaitez. Elle n’est visible que par les administrateurs de produit.

**Customer Journey Analytics** > **Outils** > **Utilisation du produit** > **Paramètres des données**

>[!IMPORTANT]
>
>Lorsque vous activez cette fonction, vous devez accepter les conditions générales avant de l’utiliser. Lorsque vous acceptez ces conditions générales, vous le faites au nom de l’ensemble de votre organisation.

Les paramètres suivants sont disponibles sur cette page :

* **Activer l’utilisation du produit** : active la disponibilité de la collecte de données d’utilisation du produit. Si vous activez l’utilisation du produit, puis le désactivez ultérieurement, le jeu de données, la connexion et la vue de données ne sont pas supprimés. Le suivi est désactivé globalement pour votre organisation lorsqu’il est désactivé.
* **Sandbox** : détermine l’environnement de test Adobe Experience Platform sous lequel le schéma et le jeu de données sont créés. L’environnement de test que vous choisissez n’a aucune incidence sur la collecte de données d’utilisation du produit. Si vous modifiez ce paramètre d’environnement de test, un jeu de données, une connexion et une vue de données distincts sont créés. Les données historiques restent dans l’environnement de test précédent.
* **Remplacer la fenêtre de rétention des données** : chaque jeu de données comporte une fenêtre de rétention des données par défaut. Si ce paramètre est désactivé, l’utilisation du produit suit cette période par défaut. Vous pouvez activer ce paramètre si vous souhaitez raccourcir la durée de conservation des données. Vous ne pouvez pas étendre la rétention des données au-delà de la fenêtre de rétention des données par défaut du jeu de données.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Environnement de test Adobe Experience Platform"
>abstract="Détermine l’environnement de test Adobe Experience Platform sous lequel le schéma et le jeu de données sont créés."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Remplacer la période de conservation des données"
>abstract="Raccourcissez la disponibilité des données d’utilisation du produit pour réduire les coûts."
