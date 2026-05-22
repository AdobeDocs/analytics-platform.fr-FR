---
description: Explique les facteurs qui influencent la cohérence des mesures et du nombre d’appartenances à une audience entre Real-time Customer Data Platform (Real-Time CDP) et Customer Journey Analytics.
title: Cohérence des mesures et des appartenances à une audience
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
TQID: https://experienceleague.adobe.com/IYlFUArrqejRjs5uDJ0MNGixQG4IP6ly4qLQBMALCjA
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 671
ht-degree: 100%

---

# Cohérence des mesures et des appartenances à une audience

Dans des scénarios réels, la cohérence des mesures et du nombre d’appartenances à une audience dans Real-time Customer Data Platform (Real-Time CDP) et Customer Journey Analytics ne peut pas être garantie. Ce document en explique la raison.

Lors de la comparaison du nombre d’appartenances à une audience entre Real-Time CDP et Customer Journey Analytics, il est important de garder à l’esprit les différentes fonctions de ces deux outils. Real-Time CDP utilise les données de profil client pour cibler les expériences numériques des clientes et clients individuels, tandis que Customer Journey Analytics est conçu pour aider les utilisateurs et utilisatrices à comprendre les modèles dans les mesures et segments commerciaux clés. Bien que la publication d’audiences de Customer Journey Analytics vers Real-Time CDP permette à l’utilisateur ou à l’utilisatrice de ces outils d’« activer » facilement et nativement une information, en tirant parti des enseignements obtenus dans Customer Journey Analytics, les fonctions de ces deux outils restent fondamentalement différentes.

## Différences dans les configurations d’identité

Real-Time CDP et Customer Journey Analytics ne partagent pas actuellement la même définition d’une personne. Real-Time CDP repose entièrement sur les informations figurant dans le [graphique d’identité](https://experienceleague.adobe.com/fr/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs) pour créer un profil fusionné.

Customer Journey Analytics peut être configuré pour utiliser le [groupement](../stitching/overview.md). Si vous utilisez le [rapprochement basé sur les champs](/help/stitching/fbs.md) comme mécanisme de rapprochement, vous spécifiez l’identifiant d’un jeu de données du lac de données afin de rapprocher les données dans ce jeu dans le but de l’améliorer avec des profils fusionnés optimisés. Si vous utilisez le [rapprochement basé sur les graphiques](/help/stitching/gbs.md) comme mécanisme de rapprochement, un processus similaire utilise le graphique d’identité basé sur un espace de noms d’identité spécifié.


## Différences dans la configuration des jeux de données

Vous pouvez choisir de placer certaines données dans Real-Time CDP et d’autres dans Customer Journey Analytics. Les clientes et clients choisissent souvent de placer plus de données historiques dans Customer Journey Analytics que nécessaire pour Real-Time CDP. D’autres jeux de données peuvent être plus pertinents pour Real-Time CDP que pour Customer Journey Analytics.

## Différences dans la configuration du traitement

Customer Journey Analytics permet une modification complète des données au moment de la requête, comme la combinaison ou la division de champs, ainsi que d’autres manipulations telles que les inclusions/exclusions, les sous-chaînes, la déduplication des valeurs, la sessionnalisation et le filtrage au niveau des lignes.

Real-Time CDP offre un ensemble différent d’outils de manipulation des données. Il applique des [politiques de fusion](https://experienceleague.adobe.com/fr/docs/experience-platform/profile/merge-policies/overview) pour déterminer quelles données seront prioritaires et quelles données seront combinées afin de créer une vue unifiée d’une personne.

## Différences entre le TTL (Time to Live, ou durée de vie) et l’ingestion des données

Même si les jeux de données dans Real-Time CDP et Customer Journey Analytics sont identiques, Real-Time CDP ne peut conserver qu’une fenêtre d’historique très limitée. En revanche, Customer Journey Analytics contient probablement des années de données. En outre :

* Les clientes et clients de Customer Journey Analytics et de Real-Time CDP peuvent définir des fenêtres de rétention personnalisées pour les données, indépendantes les unes des autres.

* Real-Time CDP et Customer Journey Analytics ont une logique différente pour l’ingestion de données. Customer Journey Analytics ignore les enregistrements sans ID de personne ou horodatage et limite strictement le nombre d’enregistrements qu’un seul profil ou une seule personne peut avoir.

* Les clientes et clients de Real-Time CDP disposent de 7 jours d’accès aux données du lac. Cela a pour but principal de faciliter l’intégration des données dans leur profil et pour les requêtes ad hoc.

* Il n’existe pas de TTL (durée de vue) pour les données du lac pour les clientes et clients de Customer Journey Analytics. Toutefois, les utilisateurs et utilisatrices de Customer Journey Analytics peuvent définir une fenêtre de rétention personnalisée dans Customer Journey Analytics lors de la création d’une connexion.

* Le magasin de profils de Real-Time CDP permet aux clients de configurer des TTL. Les clients peuvent modifier ce TTL pour qu’il reste dans la limite de leurs droits de licence.

## Différences dans la latence d’ingestion des données

Customer Journey Analytics ne dispose pas encore des fonctionnalités en temps réel de Real-Time CDP. Par conséquent, la création de rapports Customer Journey Analytics comprend une certaine latence avant que les données ne soient disponibles pour la création de rapports ou d’audiences. Real-Time CDP traite les données par le biais de différents systèmes, chacun présentant une latence différente.
