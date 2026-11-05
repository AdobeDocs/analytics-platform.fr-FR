---
description: Découvrez comment comparer les fonctionnalités des flux de données dans Customer Journey Analytics et Adobe Analytics
keywords: flux de clics;flux de données;flux des données;Flux de données
title: Fonctionnalité Comparaison des flux de données dans Customer Journey Analytics et Adobe Analytics
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 03beb4bd52769a5428ca084beacefd8996d4c810
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%
---
# Comprendre les écarts de données entre les flux de données et Analysis Workspace

{{release-limited-testing}}

Les données d’une exportation de flux de données ne correspondent pas toujours exactement aux données affichées dans Analysis Workspace. Les informations de cette page en expliquent quelques-unes des principales raisons.

## Fenêtre de traitement (Flux de données) ou fenêtre de création de rapports (Analysis Workspace) {#processing-window}

Chaque diffusion de flux de données utilise une fenêtre dynamique de traitement de 30 jours. La fenêtre de traitement fournit le contexte historique nécessaire pour classer les événements dans une diffusion de flux de données. Pour plus d’informations sur la fenêtre de traitement, y compris des exemples, voir [Présentation de la fenêtre de traitement](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window).

En ce sens, la fenêtre de traitement est similaire à la fenêtre de création de rapports dans Analysis Workspace (la période que vous choisissez pour un rapport). Cependant, il existe des différences majeures.

| Principales différences | Créneau de reporting (Analysis Workspace) | Fenêtre de traitement (Flux de données) |
|---------|---------|----------|
| **Limite des données**<br/> si les données sont incluses dans un rapport ou un flux | Flexible<p>Les événements qui se produisent en dehors de la fenêtre de création de rapports peuvent toujours être inclus dans un rapport Workspace si les événements sont influencés par l’un des facteurs suivants :</p><ul><li>**Persistance Dimension** : peut persister au-delà de la fenêtre de création de rapports lors de l’utilisation de l’expiration Session, Heure personnalisée ou Mesure [expiration](/help/data-views/component-settings/persistence.md#expiration-settings). Identique à la fenêtre de compte rendu des performances lorsque vous utilisez la fenêtre Compte rendu des performances des personnes [expiration](/help/data-views/component-settings/persistence.md#expiration-settings). Les données sont agrégées</li><li>**Qualification du segment** : par défaut, les segments peuvent s’étendre au-delà de la fenêtre de création de rapports.<p>Les utilisateurs peuvent choisir de limiter le segment à la fenêtre de création de rapports lorsqu’ils créent le segment.<!--add link to new docs--></p></li><li>**Calcul de session** : les sessions peuvent s’étendre au-delà de la fenêtre de compte rendu des performances. </li><li>**Transformations de champ dérivées**</li></ul> | Fixe<p>Les événements qui se trouvent en dehors de la fenêtre de traitement n’influencent généralement pas un flux de données. La fenêtre de traitement s’applique aux facteurs suivants :</p><ul><li>**Persistance de Dimension** : peut persister au-delà de la fenêtre de traitement (jusqu’à 90 jours) lors de l’utilisation de l’heure personnalisée [expiration](/help/data-views/component-settings/persistence.md#expiration-settings), de la même manière que dans Workspace. La persistance ne peut pas dépasser la fenêtre de traitement lors de l’utilisation de la fenêtre Rapport sur les personnes [expiration](/help/data-views/component-settings/persistence.md#expiration-settings). Les données ne sont pas agrégées.</li><li>**Qualification du segment** : toujours limitée à la fenêtre de traitement.</li><li>**Calcul de session** : toujours limité à la fenêtre de traitement.</li><li>**Transformations de champ dérivé** : toutes les fonctions de champ dérivé qui font référence à des conteneurs utilisent la fenêtre de traitement dans les exportations de flux de données.</li></ul> |
| **Période pour la création de rapports**<br/> Quels événements sont inclus dans un rapport ou un flux ? | Identique à la fenêtre de création de rapports. | Différent de la fenêtre de traitement. <p>La période pour laquelle créer des rapports est la fenêtre de fréquence, qui peut être une heure ou un jour à la fin de la fenêtre de traitement.</p> |

>[!BEGINSHADEBOX]

**Exemple**

L’exemple ci-dessous illustre comment les différences entre la fenêtre de création de rapports et la fenêtre de traitement peuvent entraîner des incohérences de données entre les rapports Workspace et les diffusions de flux de données.

Un utilisateur s’est qualifié pour un segment avec un conteneur Personne il y a 45 jours et a un événement aujourd’hui. Un rapport Workspace avec une fenêtre de création de rapports de 30 jours inclut l’événement de l’utilisateur ou de l’utilisatrice, car les segments peuvent s’étendre au-delà de la fenêtre de création de rapports par défaut. La diffusion des flux de données pour aujourd’hui n’inclut pas l’événement, car la qualification du segment est limitée à la fenêtre de traitement de 30 jours.

<!-- update the following graphic -->

![Différences de données entre Workspace et les flux de données](assets/data-feed-data-differences.png)


>[!ENDSHADEBOX]

## Assemblage de relectures

Chaque fois qu’une relecture d’assemblage s’exécute, les données d’identité historiques sont mises à jour rétroactivement.

Les flux de données et Analysis Workspace traitent différemment l’assemblage des relectures, comme suit :

* **Flux de données** : reflète uniquement l’identité regroupée au moment de l’exportation. Les résultats de la relecture ne sont pas appliqués rétroactivement aux fichiers exportés.

* **** : affiche les données regroupées les plus récentes, mises à jour rétroactivement chaque fois qu’une relecture s’exécute. Les données historiques changent après chaque relecture, de sorte que Workspace reflète toujours la dernière résolution d’identité.

## Evénements en retard

Dans un flux de données, les événements peuvent arriver après la fermeture de la fenêtre d’exportation du flux de données.

Les flux de données et Analysis Workspace fonctionnent différemment concernant les événements passés, comme suit :

* **Flux de données** : exporte les données dans une fenêtre temporelle fixe en fonction du moment de réception des événements.

  Les événements qui arrivent après la fermeture de la fenêtre peuvent ne pas être inclus dans l’exportation. Cela est influencé par le [ délai de traitement ](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay) vous choisissez.

* **** : traite les données au moment du rapport, de sorte que les événements soient inclus dans les rapports, quelle que soit la date de réception.

## Traitement par lots de données

Parfois, les données sont envoyées dans un lot qui s’étend sur une période prolongée.

Les flux de données et Analysis Workspace fonctionnent différemment concernant les données par lots, comme suit :

* **Flux de données** : distribue des données par lots sur chaque jour ou heure en fonction des horodatages d’origine. Par exemple, un lot contenant 30 jours de données est réparti sur 30 jours d’exportations. Par conséquent, une seule petite tranche apparaît dans une exportation unique.

* **** : affiche toutes les données d&#39;un lot dès qu&#39;elles sont entièrement traitées, quelle que soit la période incluse dans le lot.

