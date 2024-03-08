---
title: Vue d’ensemble des connexions Customer Journey Analytics
description: Découvrez les connexions dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 14cdc7bd8817dbf1d7a9950fa6ff62aedff82640
workflow-type: ht
source-wordcount: '188'
ht-degree: 100%

---

# Présentation des connexions

Les connexions permettent aux administrateurs et administratrices de produits Customer Journey Analytics d’établir des connexions avec différentes sources de données AEP, telles que les jeux de données d’événement, de recherche et de profil. Ces connexions permettent l’intégration de données d’une connexion à une vue de données dérivée. Nous recommandons de limiter l’accès à la gestion des connexions à un groupe de gestion principal. Les configurations au niveau de la connexion ont des implications contractuelles concernant les attributions de volume pour les données importées dans Customer Journey Analytics.
Les connexions sont la base de CJA et sont créées à partir de jeux de données source AEP. L’accès aux connexions permet également d’afficher le gestionnaire de connexions, qui vous permet d’afficher les jeux de données sous-jacents qui constituent la connexion, ainsi que d’effectuer des sélections de configuration et de modification critiques.

Voici une présentation vidéo :

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Autorisations nécessaires

Afin de créer une connexion Customer Journey Analytics,vous avez besoin des autorisations suivantes dans [Adobe Admin Console](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) :

Adobe Experience Platform :
* Modélisation des données : Afficher les schémas, Gérer les schémas
* Gestion des données : Afficher les jeux de données, Gérer les jeux de données
* Ingestion des données : Gérer les sources
* Afficher des espaces de noms d’identités

Customer Journey Analytics
* Accès administrateur de produit

>[!IMPORTANT]
>
>Vous pouvez combiner plusieurs jeux de données [!DNL Experience Platform] en une seule connexion.
