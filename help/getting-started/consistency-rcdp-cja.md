---
description: Explique les facteurs qui influencent la cohérence des mesures et du nombre d’adhésions à l’audience entre Real-time Customer Data Platform (Real-Time CDP) et CJA.
title: Cohérence des mesures et du nombre d’adhésions à l’audience entre Real-Time CDP et CJA
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 100%

---


# Cohérence des mesures et du nombre d’adhésions à l’audience entre Real-Time CDP et CJA

Dans des scénarios réels, la cohérence des mesures et du nombre d’adhésions à l’audience dans Real-time Customer Data Platform (Real-Time CDP) et Customer Journey Analytics (CJA) ne peut pas être garantie. Ce document en explique la raison.

Lors de la comparaison du nombre d’adhésions à l’audience entre Real-Time CDP et CJA, il est important de garder à l’esprit les différentes fonctions de ces deux outils. Real-Time CDP utilise les données de profil client pour cibler les expériences numériques des clients individuels, tandis que CJA est conçu pour aider les utilisateurs à comprendre les schémas dans les mesures et segments commerciaux clés. Bien que la publication d’audiences de CJA vers Real-Time CDP permette à l’utilisateur de ces outils d’« activer » facilement et nativement une information, en tirant parti des enseignements obtenus dans CJA, les fonctions de ces deux outils restent fondamentalement différentes.

## Différences dans les configurations d’identité

Real-Time CDP et CJA ne partagent pas actuellement la même définition d’une personne. Real-Time CDP repose entièrement sur les informations figurant dans le [graphique d’identités](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=fr) pour créer un profil fusionné.

CJA peut être configuré pour utiliser l’[Cross-Channel Analytics](/help/cca/overview.md) qui extrait les identifiants des jeux de données du lac de données et applique une logique personnalisée pour les lier.

À l’avenir, CJA pourra utiliser le graphique d’identités.

## Différences dans la configuration des jeux de données

Vous pouvez choisir de placer certaines données dans Real-Time CDP et d’autres dans CJA. Les clients choisissent souvent de placer plus de données historiques dans CJA que nécessaire pour Real-Time CDP. D’autres jeux de données peuvent être plus pertinents pour Real-Time CDP que pour CJA.

## Différences dans la configuration du traitement

CJA permet une modification complète des données au moment de la requête, comme la combinaison/division des champs, ainsi que d’autres manipulations telles que les inclusions/exclusions, les sous-chaînes, la déduplication des valeurs, la sessionnalisation et le filtrage au niveau des lignes.

Real-Time CDP offre un ensemble différent d’outils de manipulation des données. Il applique des [stratégies de fusion](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=fr) pour déterminer quelles données seront prioritaires et quelles données seront combinées afin de créer une vue unifiée d’une personne.

## Différences entre le TTL (Time to Live, ou durée de vie) et l’ingestion des données

Même si les jeux de données dans Real-Time CDP et CJA sont identiques, Real-Time CDP ne peut conserver qu’une fenêtre d’historique très limitée. En revanche, CJA contient probablement des années de données. En outre :

* Les clients de CJA et de Real-Time CDP peuvent définir des fenêtres de rétention personnalisées pour les données, indépendantes les unes des autres.

* Real-Time CDP et CJA ont une logique différente pour l’ingestion de données. CJA ignore les enregistrements sans ID de personne ou horodatage et limite strictement le nombre d’enregistrements qu’un seul profil ou une seule personne peut avoir.

* Les clients de Real-Time CDP disposent de 7 jours d’accès aux données du lac. Cela a pour but principal de faciliter l’intégration des données dans leur profil et pour les requêtes ad hoc.

* Il n’existe pas de TTL pour les données du lac pour les clients de CJA. Toutefois, les utilisateurs peuvent définir une fenêtre de rétention personnalisée dans CJA lors de la création d’une connexion.

* Le magasin de profils de Real-Time CDP permet aux clients de configurer des TTL. Les clients peuvent modifier ce TTL pour qu’il reste dans la limite de leurs droits de licence.

## Différences dans la latence d’ingestion des données

CJA ne dispose pas encore des fonctionnalités en temps réel de Real-Time CDP. Par conséquent, la création de rapports CJA inclut une certaine latence avant que les données ne soient disponibles pour la création de rapports ou d’audiences. Real-Time CDP traite les données par le biais de différents systèmes, chacun présentant une latence différente.
