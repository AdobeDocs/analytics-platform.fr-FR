---
title: Guide de transition
description: Découvrez comment passer de Customer Journey Analytics à Customer Journey Analytics B2B edition
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
autotag-review: '2026-05-19T08:06:36.475Z'
TQID: 'https://experienceleague.adobe.com/vkf6272OwRu9B4ZgpiXKhc4J3WAqUAm8r-3iQLUgOKg'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
  - id: d3f42e9e-bb51-4077-a732-358b801d8b29
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 9c87ce4fb30c7d1d66ce88174443369ef44a7377
workflow-type: tm+mt
source-wordcount: 623
ht-degree: 3%

---

# Guide de transition

Ce guide explique comment passer de Customer Journey Analytics à B2B edition de Customer Journey Analytics.

L’article suppose que vous utilisez déjà Customer Journey Analytics dans une certaine mesure :

* Vous disposez de [connexions](/help/connections/overview.md) qui ingèrent des données dans Customer Journey Analytics.
* Vous disposez de [vues de données](/help/data-views/data-views.md) qui utilisent les données de ces connexions.
* Vous disposez de [projets](/help/analysis-workspace/home.md) avec des rapports et des visualisations qui utilisent ces vues de données.

Si vous n’avez encore jamais utilisé Customer Journey Analytics, consultez le guide de démarrage rapide de [B2B edition](cja-b2b-quick-start-guide.md).

Si vous êtes un utilisateur d’Adobe Analytics et envisagez d’utiliser Customer Journey Analytics B2B edition, reportez-vous d’abord à la documentation [mise à niveau d’Adobe Analytics vers Customer Journey Analytics](cja-upgrade/cja-upgrade-recommendations.md).


## Implémentation existante

L’implémentation actuelle de Customer Journey Analytics ne change pas du tout une fois que vous disposez d’une licence et que vous disposez des privilèges d’accès pour Customer Journey Analytics B2B edition.

Toutes les connexions existantes sont considérées [connexions basées sur la personne](cja-b2b-concepts-features.md#connections-and-identifiers) et continuent à fonctionner sans mise à jour. Tout ce qui repose sur les données de ces connexions basées sur la personne, comme les vues de données, les projets d’espace de travail, les segments, les exportations planifiées, les alertes, etc., continue de fonctionner comme prévu et prévu à l’origine.

>[!IMPORTANT]
>
>Vous ne pouvez pas remplacer les connexions existantes basées sur une personne par une connexion basée sur un compte. Une nouvelle connexion basée sur un compte est requise pour utiliser les fonctionnalités de B2B edition.
>


## Mise en œuvre des fonctionnalités B2B

Pour implémenter des fonctionnalités B2B dans votre implémentation existante, procédez comme suit :

1. Modélisez vos données B2B. Vous pouvez utiliser le [modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) d’Adobe pour normaliser les données B2B et définir des schémas pour vos données B2B.<br/>Vous pouvez baser vos schémas sur les [classes standard fournies dans Real-time CDP B2B edition](https://experienceleague.adobe.com/fr/docs/experience-platform/rtcdp/schemas/b2b) ou utiliser vos propres classes et schémas personnalisés. Les articles [cas d’utilisation](/help/use-cases/b2b/b2b-edition/use-cases-overview.md) utilisent des classes et des schémas de B2B edition Real-time CDP. Toutefois, une licence Real-time CDP B2B edition n’est pas nécessaire pour utiliser les classes et schémas standard. <br/>Customer Journey Analytics B2B edition suppose au moins des données d’événement de série temporelle basées sur le compte et bénéficie de données d’enregistrement de profil ou de recherche supplémentaires. Telles que les données de compte, les données de groupe d’achats, les données d’opportunité, les données de membre de la liste marketing, etc.

   * Définissez l’identifiant que vous souhaitez utiliser comme identifiant de compte principal (Identifiant de compte). Souvent, un CRM existant ou un autre outil (par exemple : Demandbase) vous aide à déterminer cet identifiant.
   * Identifiez des identifiants supplémentaires pour les autres données B2B que vous prévoyez d’utiliser : identifiant de compte global, identifiant d’opportunité, identifiant de groupe d’achats et identifiant de personne.

1. Préparez vos données B2B. Veillez à ajouter et à collecter des identifiants de compte sur toutes les données d’événement de série temporelle et les données d’enregistrement pertinentes. De même, assurez-vous que les données d’événement de série temporelle et l’enregistrement de recherche contiennent d’autres identifiants pour les événements pertinents. Par exemple : un événement qui signale le passage à une autre étape de vente doit avoir un identifiant d’opportunité. Cet identifiant doit faire partie de vos données de recherche d’opportunité.

1. [Créez une connexion basée sur un compte](/help/connections/create-connection.md#account-based-connection). Sélectionnez les conteneurs facultatifs à inclure, [ajoutez des jeux de données](/help/connections/create-connection.md#add-datasets) et définissez les [paramètres de chaque jeu de données](/help/connections/create-connection.md#dataset-settings). Utilisez [correspondance par conteneur](cja-b2b-concepts-features.md#match-by-container) pour les jeux de données d’enregistrement de recherche chaque fois que cela est possible.

1. [Créer des vues de données](/help/data-views/create-dataview.md) en fonction de votre nouvelle connexion.

   * Veillez à ajouter tous les champs pertinents en tant que mesures ou dimensions à partir des données que vous avez ingérées.
   * Appliquez les paramètres des composants (tels que la persistance, l’attribution, etc.) si nécessaire.
   * Ajoutez d’autres champs dérivés, le cas échéant.

1. [Créer des projets Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md) pour créer des rapports et obtenir des informations sur vos données B2B. Utilisez des fonctionnalités B2B spécifiques, telles que [conteneurs](cja-b2b-concepts-features.md#containers), pour obtenir des informations détaillées.

   Vous pouvez combiner des rapports et des informations B2B (basés sur la personne) et B2B (basé sur le compte), à l’aide de plusieurs [panneaux](/help/analysis-workspace/c-panels/panels.md), dans un seul projet d’espace de travail.
