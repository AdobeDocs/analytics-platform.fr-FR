---
title: Contrôle d’accès CJA
description: Découvrez les exigences de contrôle d’accès pour les trois niveaux d’accès dans CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: ed1885b4dd560bdbce66a1fa2bad1bcd822a3ea3
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 46%

---

# Contrôle d’accès CJA

Customer Journey Analytics (CJA) est régi par trois niveaux d’accès ou trois rôles : Rôle d’administrateur de produit, rôle d’administrateur de profil de produit et accès au niveau utilisateur. Cette rubrique explique ces rôles de manière plus détaillée.

## Rôle Administrateur de produit

Les administrateurs de produit sont autorisés à effectuer toute tâche nécessaire dans CJA. Vous devez être ajouté en tant qu’administrateur de produit au **Profil de produit Customer Journey Analytics** dans le [Admin Console](https://adminconsole.adobe.com/enterprise/) sous Customer Journey Analytics > Onglet Admins > Ajouter un administrateur. Les autorisations suivantes sont accordées aux administrateurs de produits :

* Créer/mettre à jour/supprimer des connexions ou des vues de données.
* Mettre à jour/supprimer des projets, des filtres, des mesures calculées ou des filtres créés par dʼautres utilisateurs.
* Partager des projets de l’espace de travail avec tous les utilisateurs.

Le statut d’administrateur de produit dans Customer Journey Analytics ne suffit pas pour pouvoir créer, mettre à jour ou supprimer une connexion. Pour créer une connexion à un jeu de données Experience Platform, vous avez également besoin d’autorisations Experience Platform. En particulier, vous devez faire partie d’un **profil de produit Experience Platform** qui vous donne les autorisations suivantes :

* Modélisation des données : Afficher les schémas, Gérer les schémas
* Gestion des données : Afficher les jeux de données, Gérer les jeux de données
* Ingestion des données : Gérer les sources
* Afficher des espaces de noms d’identités

Pour plus d’informations sur les autorisations Experience Platform, voir [Contrôle d’accès dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=fr).

## Rôle d’administrateur de profil de produit

Ce rôle est similaire à celui de l’administrateur de produit, mais sa portée est plus limitée. Un profil de produit est un ensemble d’autorisations. Par exemple, un administrateur de profil de produit peut donner accès à toutes les vues de données ou à certaines vues de données aux membres d’un profil de produit. Pour les outils de création de rapports, ces administrateurs peuvent ajouter les autorisations suivantes :

![autorisations de la console d’administration](assets/permissions.png)

## Accès au niveau utilisateur

Les administrateurs (utilisateurs) autres que les produits dans Customer Journey Analytics ne peuvent pas créer, modifier ou afficher de vues de données ou de connexions. Les utilisateurs peuvent créer des filtres, des projets, des audiences et des mesures calculées avec des autorisations spéciales dans le Admin Console.

## Traitement du projet Workspace

Pour plus d’informations sur la façon de limiter les composants (dimensions, mesures, segments, plages de dates) au niveau du projet Workspace et sur la manière dont le traitement est lié aux vues de données, voir [Traitement des projets](/help/analysis-workspace/curate-share/curate.md).

## Accorder l’accès à des mesures ou dimensions individuelles

Vous ne pouvez pas accorder ni refuser des autorisations concernant des mesures ou des dimensions individuelles dans Customer Journey Analytics comme le permet la version standard d’Adobe Analytics. Les mesures et dimensions peuvent être modifiées dans les [vues de données](/help/data-views/data-views.md), et donc dans CJA, ce qui impacte rétroactivement la création de rapports.

