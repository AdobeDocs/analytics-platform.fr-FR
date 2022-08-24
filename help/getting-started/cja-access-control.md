---
title: Contrôle d’accès CJA
description: Découvrez les exigences en matière de contrôle d’accès pour la création de connexions, l’ajout de jeux de données, la création de vues de données, etc.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: e5ae592c6765638e26ee5252f458e82af9d24e44
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Contrôle d’accès CJA

Pour accéder et exécuter des tâches dans Customer Journey Analytics, vous devez être ajouté(e) en tant qu’administrateur au **profil de produit Customer Journey Analytics** dans [Admin Console](https://adminconsole.adobe.com/enterprise/). Les autorisations suivantes sont accordées aux administrateurs de produits :

* Créer/mettre à jour/supprimer des connexions ou des vues de données.
* Mettre à jour/supprimer des projets, des filtres, des mesures calculées ou des filtres créés par dʼautres utilisateurs.
* Partager des projets de l’espace de travail avec tous les utilisateurs.

## Autorisations Adobe Experience Platform requises

Le statut d’administrateur de produit dans Customer Journey Analytics ne suffit pas pour pouvoir créer, mettre à jour ou supprimer une connexion. Pour créer une connexion à un jeu de données Experience Platform, vous avez également besoin d’autorisations Experience Platform. En particulier, vous devez faire partie d’un **profil de produit Experience Platform** qui vous donne les autorisations suivantes :

* Afficher des schémas
* Gérer des schémas
* Afficher des espaces de noms d’identités
* Afficher des jeux de données

Pour plus d’informations sur les autorisations Experience Platform, voir [Contrôle d’accès dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=fr).

## Accorder l’accès à des mesures ou dimensions individuelles

Vous ne pouvez pas accorder ni refuser des autorisations concernant des mesures ou des dimensions individuelles dans Customer Journey Analytics comme le permet la version standard d’Adobe Analytics. Les mesures et dimensions peuvent être modifiées dans les [vues de données](/help/data-views/data-views.md), et donc dans CJA, ce qui impacte rétroactivement la création de rapports.

## Accès utilisateur

Les non-administrateurs de produit (utilisateurs) de Customer Journey Analytics ne peuvent pas afficher de vues de données ou de connexions, mais peuvent créer des filtres, des projets et des mesures calculées.

## Traitement du projet Workspace

Pour plus d’informations sur la façon de limiter les composants (dimensions, mesures, segments, plages de dates) au niveau du projet, voir [Traitement des projets](/help/analysis-workspace/curate-share/curate.md).



