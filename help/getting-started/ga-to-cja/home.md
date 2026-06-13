---
title: Transition de Google Analytics 4 vers Customer Journey Analytics
description: Découvrez les concepts clés pour obtenir des rapports dans Customer Journey Analytics, en les orientant vers les analystes qui connaissent Google Analytics 4.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 3d7c8b91-f2a4-4e6b-9c1d-5f8e3a720469
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 3%

---


# Transition de Google Analytics 4 vers Customer Journey Analytics

Ce guide permet aux analystes qui connaissent Google Analytics 4 d’apprendre les concepts et rapports équivalents dans Adobe Customer Journey Analytics. Si vous êtes responsable de la mise en œuvre technique plutôt que de la création de rapports, consultez [Mise à niveau d’une solution d’analyse tierce vers Customer Journey Analytics](../cja-upgrade/cja-upgrade-third-party-solution.md) pour obtenir des conseils sur la configuration de Web SDK et l’ingestion des données. Si votre organisation doit encore migrer les données Google Analytics existantes vers Adobe Experience Platform, voir [Migrer les données depuis Google Analytics](/help/use-cases/third-party/ga/overview.md).

## Principales différences entre GA4 et Customer Journey Analytics

GA4 et Customer Journey Analytics partagent la même philosophie de base : chaque interaction utilisateur est un événement, et l’analyse est effectuée dans un outil en zone de travail vierge dans lequel vous faites glisser et déposez des dimensions et des mesures pour créer des vues personnalisées. Si vous connaissez GA4 Explorer, il est probable qu’Analysis Workspace soit immédiatement reconnaissable.

Les différences les plus importantes concernent les domaines dans lesquels Customer Journey Analytics s’étend au-delà de GA4 :

* **Données cross-canal** : Customer Journey Analytics peut combiner des analyses web à des sources de données hors ligne (telles que les enregistrements de centre d’appel, l’activité CRM, les programmes de fidélité ou l’engagement des e-mails) dans la même analyse. GA4 se limite aux interactions numériques collectées via son SDK.
* **Traitement de la période de rapport** : Customer Journey Analytics applique une logique telle que des modèles d’attribution, des définitions de session et des règles de segment au moment de la requête, et non au moment de la collecte. Les modifications apportées aux définitions de session ou aux modèles d’attribution s’appliquent rétroactivement à toutes les données historiques sans retraitement.
* **Définitions de session flexibles** : le délai d’expiration de la session, les événements de début et de fin de session sont configurables par vue de données dans Customer Journey Analytics. Le délai d’expiration de la session GA4 est ajustable (30 minutes par défaut, jusqu’à 7 heures 55 minutes), mais s’applique à l’ensemble des propriétés. De plus, son comportement de début et de fin de session est fixe.
* **Combinaison d’identités** : la fonctionnalité de combinaison de Customer Journey Analytics peut lier des interactions entre appareils et cross-canal à la même personne, produisant ainsi un nombre de personnes plus précis que le modèle d’identité mixte de GA4.

## Compte et structure des données

GA4 et Customer Journey Analytics organisent les données différemment au niveau de la plateforme.

| GA4 | Customer Journey Analytics |
|---|---|
| Compte Google | Organisation Adobe IMS |
| Propriété | Connexion + vue de données |
| Flux de données | [!UICONTROL Jeu de données d’événement] dans Platform |
| Filtres de données | Filtres des composants de la vue de données |
| Sous-propriété | Vue de données distincte avec filtres appliqués |
| Propriété de cumul | Connexion combinant plusieurs jeux de données |

La différence structurelle la plus importante est qu&#39;une propriété GA4 gère le câblage des données et la création de rapports comme un seul objet. Customer Journey Analytics sépare ces concepts en deux couches distinctes :

* Une **connexion** lie un ou plusieurs jeux de données Adobe Experience Platform à Customer Journey Analytics. Cette étape ingère des données dans Customer Journey Analytics dans un format optimisé pour la création de rapports.
* Une **vue de données** repose sur une connexion et définit les dimensions, mesures et paramètres disponibles pour la création de rapports. Il s’agit de la couche de configuration des rapports.

Les deux doivent exister avant de pouvoir analyser les données dans Customer Journey Analytics. Il n’existe aucune suite de rapports dans Customer Journey Analytics.

## Prise en main dans Analysis Workspace

GA4 Explorer et Analysis Workspace sont deux outils d’analyse par glisser-déposer de la zone de travail vierge. Le modèle d’interaction est le même ; la terminologie diffère légèrement.

| Exploration GA4 | Analysis Workspace |
|---|---|
| Zone de travail d’exploration | Panneau |
| Type de graphique ou de visualisation | Visualisation |
| Dimension | Dimension |
| Mesure | Mesure |
| Segment ou filtre | Segment |
| Nombre d’événements | [!UICONTROL Événements] |
| Utilisateurs et utilisatrices | [!UICONTROL Personnes] |
| Sessions | [!UICONTROL Sessions] |

>[!TIP]
>
>Les conteneurs de segments GA4 sont nommés Utilisateurs, Sessions et Événements. Dans Customer Journey Analytics, les conteneurs équivalents sont **[!UICONTROL Personne]**, **[!UICONTROL Session]** et **[!UICONTROL Événement]**. La logique de définition de la portée est la même.

>[!MORELIKETHIS]
>
>* [Migration des données depuis Google Analytics](/help/use-cases/third-party/ga/overview.md)
