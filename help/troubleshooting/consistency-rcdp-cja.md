---
description: Explique les facteurs qui influencent la cohérence des mesures et du nombre d’adhésions à l’audience entre Real-time Customer Data Platform (plateforme de données clients en temps réel) et Customer Journey Analytics.
title: Cohérence des mesures et du nombre d’adhésions à l’audience entre la plateforme des données clients en temps réel et le Customer Journey Analytics
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: cf6da1f126933f17e05fb458f52dff93c1601891
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 25%

---


# Cohérence des mesures et du nombre d’adhérents à l’audience entre la plateforme de données clients en temps réel et Adobe Customer Journey Analytics

Dans les scénarios réels, la cohérence des mesures et du nombre d’adhésions à l’audience dans Real-time Customer Data Platform (plateforme de données clients en temps réel) et Customer Journey Analytics ne peut pas être garantie. Ce document en explique la raison.

Lors de la comparaison du nombre d’adhésions à l’audience entre la plateforme de données clients en temps réel et le Customer Journey Analytics, il est important de garder à l’esprit les différents objectifs de ces deux outils. La plateforme des données clients en temps réel utilise les données de profil client pour cibler les expériences numériques sur les clients individuels, tandis que Customer Journey Analytics est conçu pour aider les utilisateurs à comprendre les schémas des mesures et segments commerciaux clés. Bien que la publication d’audiences depuis Customer Journey Analytics vers la plateforme de données clients en temps réel permette à un utilisateur de ces outils d’&quot;activer&quot; facilement et nativement une information, en tirant parti des enseignements obtenus en Customer Journey Analytics, ces outils ont néanmoins des objectifs fondamentalement différents.

## Différences dans les configurations d’identité

La plateforme de données clients en temps réel et le Customer Journey Analytics ne partagent pas la même définition d’une personne aujourd’hui. Real-Time CDP repose entièrement sur les informations figurant dans le [graphique d’identités](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=fr) pour créer un profil fusionné.

Customer Journey Analytics peut être configuré pour utiliser [Assemblage](../stitching/overview.md) qui extrait les identifiants des jeux de données du lac de données et applique une logique personnalisée pour les lier.

À l’avenir, Customer Journey Analytics pourra utiliser le graphique d’identités.

## Différences dans la configuration des jeux de données

Vous pouvez choisir de placer certaines données dans la plateforme de données clients en temps réel et d’autres en Customer Journey Analytics ; souvent, les clients choisissent de placer plus de données historiques en Customer Journey Analytics que ce qui est pertinent pour la plateforme de données clients en temps réel. D’autres jeux de données peuvent être plus pertinents pour la plateforme des données clients en temps réel que pour le Customer Journey Analytics.

## Différences dans la configuration du traitement

Customer Journey Analytics permet des modifications de données importantes au moment de la requête, telles que la combinaison de champs, la division des champs entre eux et d’autres manipulations telles que les inclusions/exclusions, les sous-chaînes, la déduplication des valeurs, la mise en session et le filtrage au niveau des lignes.

Real-Time CDP offre un ensemble différent d’outils de manipulation des données. Il applique des [politiques de fusion](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=fr) pour déterminer quelles données seront prioritaires et quelles données seront combinées afin de créer une vue unifiée d’une personne.

## Différences entre le TTL (Time to Live, ou durée de vie) et l’ingestion des données

Même si les jeux de données de la plateforme de données clients en temps réel et du Customer Journey Analytics sont identiques, la plateforme de données clients en temps réel ne peut que garder une fenêtre d’historique très limitée. En revanche, le Customer Journey Analytics a probablement des années de données. En outre :

* Les clients CDP Customer Journey Analytics et en temps réel peuvent définir des fenêtres de conservation personnalisées pour les données, indépendamment les uns des autres.

* La plateforme des données clients en temps réel et le Customer Journey Analytics ont une logique différente pour l’ingestion de données. Customer Journey Analytics ignore les enregistrements sans ID de personne ou horodatage et limite strictement le nombre d’enregistrements qu’un seul profil/personne peut avoir.

* Les clients de Real-Time CDP disposent de 7 jours d’accès aux données du lac. Cela a pour but principal de faciliter l’intégration des données dans leur profil et pour les requêtes ad hoc.

* Il n’existe pas de TTL pour les données du lac pour les clients Customer Journey Analytics. Toutefois, les utilisateurs Customer Journey Analytics peuvent eux-mêmes définir une période de conservation personnalisée dans Customer Journey Analytics lors de la création d’une connexion.

* Le magasin de profils de Real-Time CDP permet aux clients de configurer des TTL. Les clients peuvent modifier ce TTL pour qu’il reste dans la limite de leurs droits de licence.

## Différences dans la latence d’ingestion des données

Customer Journey Analytics ne dispose pas encore des fonctionnalités en temps réel de la plateforme de données clients en temps réel. Par conséquent, la création de rapports de Customer Journey Analytics inclut une certaine latence avant que les données ne soient disponibles pour la création de rapports ou d’audiences. Real-Time CDP traite les données par le biais de différents systèmes, chacun présentant une latence différente.
