---
title: Contrôle d’accès CJA
description: Découvrez les exigences de contrôle d’accès pour la création de connexions, l’ajout de jeux de données, la création de vues de données, etc.
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 13513561ec288c1f4ab69128769cd0e7c059e44b
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 91%

---


# Contrôle d’accès CJA

Pour créer des connexions, ajouter des jeux de données, etc., vous avez besoin des autorisations suivantes dans l’[Admin Console](https://adminconsole.adobe.com/enterprise/) :

* Pour accéder à Customer Journey Analytics ou établir une connexion, vous devez être ajouté en tant quʼadministrateur au **produit Customer Journey Analytics** dans lʼ[Admin Console](https://adminconsole.adobe.com/enterprise/). Les autorisations suivantes sont accordées aux administrateurs de produits :
   * Créer/mettre à jour/supprimer des connexions ou des vues de données
   * Mettre à jour/supprimer des projets, des filtres, des mesures calculées ou des filtres créés par dʼautres utilisateurs
   * Partager un projet d’espace de travail avec tous les utilisateurs
* Le simple fait de devenir administrateur de produit dans Customer Journey Analytics ne suffit pas à créer, mettre à jour ou supprimer une connexion. Pour créer une connexion à un jeu de données Experience Platform, vous avez également besoin d’autorisations Experience Platform. En particulier, vous devez faire partie d’un **profil de produit Experience Platform** qui vous donne les autorisations suivantes :
   * Afficher des schémas
   * Gérer des schémas
   * Afficher des espaces de noms d’identités
   * Afficher des jeux de données

Pour plus d’informations sur les autorisations Experience Platform, voir [Contrôle d’accès dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=fr).

>[!NOTE]
>
>Vous ne pouvez pas accorder ni refuser des autorisations concernant des mesures ou des dimensions individuelles dans Customer Journey Analytics comme le permet la version standard d’Adobe Analytics. Les mesures et dimensions peuvent être modifiées dans les [vues de données](/help/data-views/data-views.md), et donc dans CJA, ce qui impacte rétroactivement la création de rapports.

## Accès utilisateur

Les non-administrateurs de produit (utilisateurs) de Customer Journey Analytics ne peuvent pas afficher de vues de données ou de connexions, mais peuvent créer des filtres, des projets et des mesures calculées.