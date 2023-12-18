---
title: Barrières de sécurité du Customer Journey Analytics
description: En savoir plus sur les barrières de sécurité pour Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
source-git-commit: affe7fe57ba59a15458263afabe2715d4c5da5fe
workflow-type: tm+mt
source-wordcount: '1467'
ht-degree: 14%

---


# Barrières de sécurité du Customer Journey Analytics

Ce document fournit des limites pour divers composants de Customer Journey Analytics. Pour les garde-fous, les paramètres de portée et les droits, voir la section [Description du produit pour Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html) ou le [Description du produit pour le module complémentaire Adobe Analytics : Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

## Types de limite

Ce document comprend deux types de limites par défaut :

| Type de protection | Description |
|----------|---------|
| **Barrières de sécurité des performances (limite logicielle)** | Les barrières de performance sont des limites d’utilisation liées à la portée de vos cas d’utilisation. Lorsque vous dépassez les barrières de performance, vous pouvez rencontrer une dégradation des performances et une latence. Adobe n’est pas responsable d’une telle dégradation des performances. Les clients qui dépassent systématiquement une barrière de performance peuvent choisir d’acquérir une capacité supplémentaire afin d’éviter une dégradation des performances. |
| **Barrières de sécurité appliquées par le système (limite stricte)** | Les barrières de sécurité appliquées par le système sont appliquées par l’interface utilisateur ou l’API du Customer Journey Analytics. Il s’agit de limites que vous ne pouvez pas dépasser, car l’interface utilisateur et l’API vous empêchent de le faire ou renvoient une erreur. |

{style="table-layout:auto"}

Certaines fonctionnalités et leur valeur associée pour la limite dépendent du package de Customer Journey Analytics auquel vous avez droit.

>[!NOTE]
>
>Les valeurs décrites dans ce document peuvent être modifiées en fonction des améliorations continues apportées au produit. Consultez régulièrement les mises à jour. Si vous souhaitez en savoir plus sur les limites personnalisées, contactez votre représentant de l’assistance clientèle.

## Requêtes SQL ad hoc

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Réessayer le délai | 90 | Barrière de sécurité mise en place par le système | Nombre maximum de secondes avant que le moteur de reporting ne réponde : la requête prend trop de temps pour renvoyer des résultats (peut-être en raison d’autres requêtes simultanées) ; il est possible de demander à nouveau. | |
| Ne réessayez pas le délai d’expiration | 600 | Barrière de sécurité mise en place par le système | Nombre maximal de secondes avant le délai d’expiration des requêtes Ad Hoc SQL. Dans le cas contraire, le nombre maximal de secondes avant que les moteurs de reporting ne signalent que la requête a pris trop de temps pour renvoyer les résultats et ne doit pas être tentée à nouveau. La requête ne renvoie probablement jamais de résultats en raison de problèmes dans le processus en arrière-plan. |
| Mesures | 150 | Barrière de sécurité mise en place par le système | Nombre maximal de mesures dans une requête. | | |
| Lignes de sortie de requête interactive | 50 000 | Barrière de sécurité mise en place par le système | Nombre de lignes par défaut renvoyé, sauf indication contraire. | |

{style="table-layout:auto"}

## Projets Analysis Workspace

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Lignes visibles par tableau | 400 | Barrière de sécurité mise en place par le système | Nombre maximal de lignes visibles dans tout tableau à structure libre d’un projet Analysis Workspace. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Lignes exportables par table | 50 000 | Barrière de sécurité mise en place par le système | Nombre maximal de lignes pouvant être exportées par dimension unique. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Panneaux par projet | 15 | Barrière de sécurité mise en place par le système | Nombre maximal de [panneaux](../analysis-workspace/home.md#panels) par projet. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Visualisations par panneau | 25 | Barrière de sécurité mise en place par le système | Nombre maximal de [visualisations](../analysis-workspace/home.md#visualizations) par panneau. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

{style="table-layout:auto"}

<!--
## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}
-->

## Audiences

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Filtres d’audiences | 20 | Barrière de sécurité mise en place par le système | Nombre maximal de [filtres](../components/filters/filters-overview.md) par audience. |
| Nombre d’identités d’audience | 20 million | Barrière de sécurité mise en place par le système | Nombre maximal d’identités par audience. |
| Fréquence d’actualisation de l’audience | 4 | Barrière de sécurité mise en place par le système | Fréquence maximale en heures et [audience](../components/audiences/audiences-overview.md) peut être actualisée. | |
| Intervalle de recherche en amont de l’actualisation de l’audience | 90 | Barrière de sécurité mise en place par le système | Nombre maximal de jours pour l’intervalle de recherche en amont d’actualisation. |
| Actualisation de la date d’expiration de l’audience | 13 | Barrière de sécurité mise en place par le système | Nombre maximum de mois pendant lesquels l’audience cesse de s’actualiser à partir de la date de création. Les clients peuvent prolonger cette période de 13 mois supplémentaires. |
| Nombre d’audiences actualisées | 75, 100, 150 | Barrière de sécurité mise en place par le système | Nombre maximal d’audiences d’actualisation, la valeur varie en fonction du package. |

{style="table-layout:auto"}

Voir aussi Experience Platform [Barrières de sécurité Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=en).


## Expiration automatisée du jeu de données

| Nom | Valeur | Type de limite | Description |
|---|--:|---|:---:|
| Ordres de travail | 20 | Barrière de sécurité mise en place par le système | Nombre maximal de commandes de travail d’expiration de jeu de données automatisées par mois. |

{style="table-layout:auto"}



## Connexions, Vues de données, Projets

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Projets | 2 000 | Barrière de sécurité mise en place par le système | Nombre maximal de projets pour une organisation. |
| Vues des données | 2 000 | Barrière de sécurité mise en place par le système | Nombre maximal de [vues de données](../data-views/data-views.md) pour une organisation. |
| Vues des données | 50 | Barrière de sécurité mise en place par le système | Nombre maximal de vues de données pour une connexion |
| Jeux de données | 100 | Barrière de sécurité mise en place par le système | Nombre maximal de [jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=en) par connexion. |
| Connexions | 1000 | Barrière de sécurité mise en place par le système | Nombre maximal de [connexions](../connections/overview.md) pour une organisation. |
| Titre de la connexion | 500 | Barrière de sécurité mise en place par le système | Nombre maximal de caractères pour un titre de connexion. |
| Mesures | 5 000 | Barrière de sécurité mise en place par le système | Nombre maximal de mesures dans une vue de données. |
| Dimensions | 5 000 | Barrière de sécurité mise en place par le système | Nombre maximal de dimensions dans une vue de données. | |
| Titre de l’annotation | 100 | Barrière de sécurité mise en place par le système | Nombre maximal de caractères pour un titre d’annotation. |
| Description de l’annotation | 250 | Barrière de sécurité mise en place par le système | Nombre maximal de caractères pour une description d’annotation. | |
| Champs de schéma | 10 | Barrière de sécurité mise en place par le système | Nombre maximum de champs de schéma (non compris les champs standard) lors de la définition de règles pour un [champ dérivé](../data-views/derived-fields/derived-fields.md). |
| Champs de recherche/profil | 3 | Barrière de sécurité mise en place par le système | Nombre maximum de champs de schéma de recherche ou de profil dans le nombre maximum de champs de schéma (non compris les champs standard) lors de la définition de règles pour un champ dérivé. |
| Champs dérivés | 100 | Barrière de sécurité mise en place par le système | Nombre maximum de champs dérivés par connexion. |

{style="table-layout:auto"}


## Limites de transfert de données

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Champs | 10 000 | Barrière de sécurité mise en place par le système | Nombre maximal de propriétés ou de champs par ligne dans un jeu de données. | | |
| Chaînes uniques | 10 million | Barrière de sécurité mise en place par le système | Nombre maximal de clés uniques par jeu de données de recherche. |
| Lignes | 1 million | Barrière de sécurité mise en place par le système | Nombre maximal de lignes par identifiant de personne unique au sein d’une connexion. |
| Taille de ligne | 2 | Barrière de sécurité des performances / barrière de sécurité appliquée par le système | Taille moyenne en kilo-octets par ligne de données ingérées dans Customer Journey Analytics (limite soft). Une limite statique pour la taille des lignes est déterminée par des barrières de sécurité pour l’ingestion de données dans Experience Platform. |

{style="table-layout:auto"}

Voir aussi Experience Platform [Barrières de sécurité pour l’ingestion des données](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=en).


## Zone d&#39;entrée des données

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Zone d’entrée de données par environnement de test | 1 | Barrière de sécurité mise en place par le système | Nombre maximal de zones d’entrée de données par environnement de test. |
| Stockage des données | 7 | Barrière de sécurité mise en place par le système | Nombre maximum de jours pendant lesquels les données sont stockées dans la zone d&#39;entrée des données avant d&#39;être supprimées. |

{style="table-layout:auto"}


## Groupement basé sur les champs

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Jeux de données groupés | 10 | Barrière de sécurité mise en place par le système | Nombre maximal de jeux de données assemblés par client, selon le package. |
| Renvoyer les données | 60 | Barrière de sécurité mise en place par le système | Nombre maximal de jours de données de renvoi. |

{style="table-layout:auto"}


## Filtres et mesures calculées

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Conteneurs par filtre | 50 | Barrière de sécurité mise en place par le système | Nombre maximal de conteneurs par filtre. |
| Mesures par mesure calculée | 25 | Barrière de sécurité mise en place par le système | Nombre maximal de mesures par mesure calculée. |
| Mesures et dimensions par filtre | 25 | Barrière de sécurité mise en place par le système | Nombre maximal de mesures et de dimensions uniques par filtre. |
| Conteneurs imbriqués par filtre | 10 | Barrière de sécurité mise en place par le système | Nombre maximal de conteneurs imbriqués par filtre. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Règles par filtre | 100 | Barrière de sécurité mise en place par le système | Nombre maximal de règles par filtre. |
| Chaîne comparée par dimension et par filtre | 100 | Barrière de sécurité mise en place par le système | Nombre maximum de comparaisons de chaînes par dimension et par filtre. |
| Mesures calculées | 6 000 | Barrière de sécurité mise en place par le système | Nombre maximal de mesures calculées pour une organisation. | |
| Filtres | 50 000 | Barrière de sécurité mise en place par le système | Nombre maximal de filtres que vous pouvez définir pour une organisation. |

{style="table-layout:auto"}


## Application mobile

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Carreaux | 16 | Barrière de sécurité mise en place par le système | Nombre maximal de mosaïques par fiche d’évaluation. |
| Filtres | 10 | Barrière de sécurité mise en place par le système | Nombre maximal de filtres par fiche d’évaluation. |
| Dimensions | 10 | Barrière de sécurité mise en place par le système | Nombre maximal de dimensions par fiche d’évaluation. |

{style="table-layout:auto"}

## Report Builder

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Taille du fichier classeur | 5 | Barrière de sécurité mise en place par le système | Taille maximale du fichier en Mo d’un classeur planifié. |
| Blocs de données | 1000 | Barrière de sécurité mise en place par le système | Nombre maximal de [blocs de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=en) par classeur. |
| Mesures | 20 | Barrière de sécurité mise en place par le système | Nombre maximal de mesures par bloc de données. |
| Période | 13 | Barrière de sécurité mise en place par le système | Nombre maximal de mois qu’une période peut couvrir par bloc de données. |  |
| Lignes | 50 000 | Barrière de sécurité mise en place par le système | Nombre maximal de lignes par bloc de données. |

{style="table-layout:auto"}


## Export table complète

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Lignes par rapport | 3 millions - 300 millions | Barrière de sécurité mise en place par le système | Nombre maximal de lignes de rapport par rapport ; valeur basée sur le package sous licence. |
| Ventilations par tableau | 5 | Barrière de sécurité mise en place par le système | Nombre maximum de ventilations par table. |
| Mesures par tableau | 5 | Barrière de sécurité mise en place par le système | Nombre maximal de mesures par tableau. |
| Fréquence des planifications | 1 | Barrière de sécurité mise en place par le système | Les exportations peuvent être planifiées une fois (1) par jour ou selon une planification plus longue (par exemple : une fois tous les 2 jours ou une fois par semaine). |

{style="table-layout:auto"}

## Latences

>[!NOTE]
>
>Les temps de traitement ci-dessous sont des barrières de sécurité, et non des contrats de niveau de service (SLA) contractuels. La latence varie en fonction de la configuration client, des volumes de données et des applications client. Les temps de traitement réels sont souvent plus rapides. Consultez votre contrat de Customer Journey Analytics pour connaître vos termes contractuels et contrats de niveau de service spécifiques. Voir Experience Platform [Barrières de sécurité pour l’ingestion des données](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=en) pour plus d’informations.

| Flux de données | Latence attendue |
|---|---|
| Connecteur source Adobe Analytics vers Adobe Analytics (A4T activé) | &lt; 30 minutes |
| Connecteur source Adobe Analytics vers Real-time Customer Profile (A4T non activé) | &lt; 2 minutes |
| Connecteur source Adobe Analytics vers Real-time Customer Profile (A4T activé) | &lt; 30 minutes |
| Ingestion de données dans le lac de données à partir d’Edge Network ou ingestion par flux | &lt; 60 minutes |
| Ingestion de données dans le lac de données à partir du connecteur source Adobe Analytics | &lt; 90 minutes |
| Ingestion de données dans Customer Journey Analytics à partir du lac de données | &lt; 90 minutes |
| Renvoi du connecteur source Adobe Analytics de moins de 10 milliards d’événements (maximum 13 mois de données historiques) | &lt; 4 semaines |
| Publication d’audiences dans Real-time Customer Profile, y compris la création automatique du segment de diffusion en continu et la possibilité pour le segment d’être prêt à recevoir les données. | ≈ 60 minutes |
| Fréquence d’actualisation des audiences | Actualisation unique : latence inférieure à 5 minutes.<br/>Actualisez toutes les 4 heures, tous les jours, toutes les semaines, tous les mois (la latence va de pair avec le taux d’actualisation). |

{style="table-layout:auto"}

