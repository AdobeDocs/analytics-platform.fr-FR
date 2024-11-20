---
title: Vue d’ensemble des connexions Customer Journey Analytics
description: Découvrez les connexions dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 2f78905c2a1e94174a52269becc15474baf59f71
workflow-type: ht
source-wordcount: '224'
ht-degree: 100%

---

# Présentation des connexions

Les connexions permettent aux administrateurs et administratrices de produits Customer Journey Analytics d’établir des connexions avec différentes sources de données [!DNL Adobe Experience Platform], telles que les jeux de données d’événement, de recherche et de profil. Ces connexions permettent l’intégration de données d’une connexion à une vue de données dérivée. Les connexions sont la base de CJA et sont créées à partir de jeux de données source [!DNL Experience Platform]. L’accès aux connexions vous permet également d’afficher le gestionnaire de connexions pour afficher les jeux de données sous-jacents qui constituent la connexion, ainsi que d’effectuer des sélections de configuration et de modification critiques.

Nous recommandons de limiter l’accès à la gestion des connexions à un groupe de gestion principal. Les configurations au niveau de la connexion ont des implications contractuelles concernant les attributions de volume pour les données importées dans Customer Journey Analytics.

Voici une présentation vidéo :

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Autorisations nécessaires

Pour créer une connexion Customer Journey Analytics, vous devez disposer des autorisations suivantes : Pour plus d’informations sur les autorisations, consultez la documentation d’[Adobe Admin Console](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) et des [autorisations Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/home).

### Dans Adobe Admin Console :

* Customer Journey Analytics : administration de produit
* Adobe Experience Platform : ajouté au profil de produit nommé *AEP-Default-All-Users*

### Dans les autorisations Adobe Experience Platform :

* Modélisation des données : Afficher les schémas, Gérer les schémas
* Gestion des données : Afficher les jeux de données, Gérer les jeux de données
* Ingestion des données : Gérer les sources
* Identity Management : afficher les espaces de noms d’identité
* Sandbox : sandbox utilisés dans les connexions de Customer Journey Analytics associées

>[!IMPORTANT]
>
>Vous pouvez combiner plusieurs jeux de données [!DNL Experience Platform] en une seule connexion.
