---
description: Découvrez comment comparer les fonctionnalités des flux de données dans Customer Journey Analytics et Adobe Analytics
keywords: flux de clics;flux de données;flux des données;Flux de données
title: Fonctionnalité Comparaison des flux de données dans Customer Journey Analytics et Adobe Analytics
feature: Components
hide: true
source-git-commit: a72ed21bdea40e2441443d7218d9fd7c906adc3e
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 0%

---

# Comprendre les écarts de données entre les flux de données et Analysis Workspace

{{release-limited-testing}}

Les données d’une exportation de flux de données ne correspondent pas toujours exactement aux données affichées dans Analysis Workspace. Les informations de cette page en expliquent quelques-unes des principales raisons.

## Période de recherche en amont (flux de données) et période de création de rapports (Analysis Workspace)

La période de recherche en amont dans les flux de données détermine l’historique de Customer Journey Analytics lors de la recherche d’événements qui remplissent les critères d’une diffusion de flux de données. En ce sens, la période de recherche en amont est similaire à la période de création de rapports dans Analysis Workspace. Cependant, il existe des différences majeures.

| Principales différences | Période de création des rapports (Analysis Workspace) | Période de recherche en amont (flux de données) |
|---------|---------|----------|
| **Limite des données**<br/> si les données sont incluses dans un rapport ou un flux | Flexible<p>Les événements qui se situent en dehors de la période de création des rapports peuvent toujours être inclus dans un rapport Workspace si les événements sont influencés par l’un des facteurs suivants :</p><ul><li>**Persistance de Dimension** : peut persister au-delà de la période de création des rapports. Les données sont agrégées</li><li>**Qualification du segment** : par défaut, les segments peuvent s’étendre au-delà de la période du rapport.<p>Les utilisateurs peuvent choisir de limiter le segment à la période du rapport lorsqu’ils créent le segment.<!--add link to new docs--></p></li><li>**Calcul de session** : les sessions peuvent s’étendre au-delà de la période de création de rapports. </li><li>**Transformations de champ dérivées**</li></ul> | Fixe<p>Les événements qui se situent en dehors de la période de recherche en amont ne sont jamais inclus dans un flux de données, qu’ils soient influencés ou non par les facteurs suivants :</p></p><ul><li>**Persistance Dimension** : impossible de persister au-delà de la période de recherche en amont. Les données ne sont pas agrégées.</li><li>**Qualification du segment** : toujours limitée à la période de recherche en amont.</li><li>**Calcul de session** : toujours limité à la période de recherche en amont.</li><li>**Transformations de champ dérivé** : toutes les fonctions de champ dérivé qui font référence à des conteneurs utilisent la période de recherche en amont dans les exportations de flux de données.</li></ul><p>Pour plus d’informations sur la configuration de la période de recherche en amont, voir [Création d’un flux de données](/help/components/exports/cja-data-feeds/create-feed.md#create-and-configure-a-data-feed).</p> |
| **Créneau de rapport**<br/> Période sur laquelle portera le rapport | Le même que la fenêtre de création de rapports (la période sur laquelle vous souhaitez créer des rapports). | Pas la même que la période sur laquelle vous souhaitez créer un rapport. <p>La période sur laquelle portera le rapport est la fenêtre Fréquence, qui peut être d’une heure ou d’un jour.</p> |

>[!BEGINSHADEBOX]

**Exemple**

L’exemple ci-dessous illustre comment les différences entre la période de création de rapports et la période de recherche en amont peuvent entraîner des incohérences de données entre les rapports Workspace et les diffusions de flux de données.

L’événement A s’est produit il y a 85 jours et se trouve sur une dimension avec un paramètre de persistance de 90 jours (par exemple, une fenêtre d’attribution de clic de campagne). L’événement est inclus dans le rapport Analysis Workspace et non dans la diffusion du flux de données.

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

  Les événements qui arrivent après la fermeture de la fenêtre peuvent ne pas être inclus dans l’exportation. Cela est influencé par la [période de recherche en amont](#lookback-date-range-data-feeds-vs-reporting-date-range-analysis-workspace) que vous choisissez.

* **** : traite les données au moment du rapport, de sorte que les événements soient inclus dans les rapports, quelle que soit la date de réception.

## Traitement par lots de données

Parfois, les données sont envoyées dans un lot qui s’étend sur une période prolongée.

Les flux de données et Analysis Workspace fonctionnent différemment concernant les données par lots, comme suit :

* **Flux de données** : distribue des données par lots sur chaque jour ou heure en fonction des horodatages d’origine. Par exemple, un lot contenant 30 jours de données est réparti sur 30 jours d’exportations. Par conséquent, une seule petite tranche apparaît dans une exportation unique.

* **** : affiche toutes les données d&#39;un lot dès qu&#39;elles sont entièrement traitées, quelle que soit la période incluse dans le lot.

