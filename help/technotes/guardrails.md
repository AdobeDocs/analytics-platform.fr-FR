---
title: Barrières de sécurité du Customer Journey Analytics
description: En savoir plus sur les barrières de sécurité pour Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: a0124ee6c4534cbaf607367ee3ae79f1cbfc239c
workflow-type: tm+mt
source-wordcount: '1747'
ht-degree: 10%

---

# Barrières de sécurité du Customer Journey Analytics

Ce document fournit des limites pour divers composants de Customer Journey Analytics. Pour les garde-fous, les paramètres de plage et les droits, voir la [description du produit pour le Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=fr) ou le [descriptif du produit pour le module complémentaire Adobe Analytics : Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html?lang=fr).

## Types de limite

Ce document comprend deux types de limites par défaut :

| Type de protection | Description |
|----------|---------|
| **Barrières de sécurité des performances (limite logicielle)** | Les garde-performances sont des limites d’utilisation liées à la portée de vos cas d’utilisation. Lorsque vous dépassez les barrières de performance, vous pouvez subir une dégradation des performances et une latence. Adobe n’est pas responsable d’une telle dégradation des performances. Les clients qui dépassent systématiquement une barrière de performance peuvent choisir de posséder une capacité supplémentaire pour éviter une dégradation des performances. |
| **Barrières de sécurité système (limite stricte)** | Les protections appliquées par le système sont appliquées par l’interface utilisateur ou l’API du Customer Journey Analytics. Il s’agit de limites que vous ne pouvez pas dépasser, car l’interface utilisateur et l’API vous empêchent de le faire ou renvoient une erreur. |

{style="table-layout:auto"}

Certaines des fonctionnalités et leur valeur associée pour la limite dépendent du package de Customer Journey Analytics auquel vous avez droit.

>[!NOTE]
>
>Les valeurs décrites dans ce document peuvent être modifiées en fonction des améliorations continues apportées au produit. Consultez régulièrement les mises à jour. Si vous souhaitez en savoir plus sur les limites personnalisées, contactez votre représentant de l’assistance clientèle.

## Requêtes SQL ad hoc

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Réessayer Délai d’expiration | 90 | Barrière de sécurité imposée par le système | Nombre maximum de secondes avant que le moteur de reporting ne réponde : la requête prend trop de temps pour renvoyer des résultats (peut-être en raison d’autres requêtes simultanées) ; il est possible de demander à nouveau. |
| Ne plus essayer le délai d’expiration | 600 | Barrière de sécurité imposée par le système | Nombre maximal de secondes avant le délai d’expiration des requêtes Ad Hoc SQL. Dans le cas contraire, le nombre maximal de secondes avant que les moteurs de reporting ne signalent que la requête a pris trop de temps pour renvoyer les résultats et ne doit pas être tentée à nouveau. La requête ne renvoie probablement jamais de résultats en raison de problèmes dans le processus en arrière-plan. |
| Mesures | 150 | Barrière de sécurité imposée par le système | Nombre maximal de mesures dans une requête. |
| Lignes de sortie de requête interactive | 50 000 | Barrière de sécurité imposée par le système | Nombre de lignes par défaut renvoyé, sauf indication contraire. |

{style="table-layout:auto"}

## Projets Analysis Workspace

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Lignes visibles par tableau | 400 | Barrière de sécurité imposée par le système | Nombre maximal de lignes visibles dans tout tableau à structure libre d’un projet Analysis Workspace. |
| Lignes exportables par tableau | 50 000 | Barrière de sécurité imposée par le système | Nombre maximal de lignes pouvant être exportées par dimension unique. |
| Panneaux par projet | 15 | Barrière de sécurité imposée par le système | Nombre maximal de [panneaux](../analysis-workspace/home.md#panels) par projet. |
| Visualisations par panneau | 25 | Barrière de sécurité imposée par le système | Nombre maximal de [visualisations](../analysis-workspace/home.md#visualizations) par panneau. |
| Champs dérivés par tableau à structure libre | 5 | Barrière de sécurité imposée par le système | Nombre maximal de champs dérivés différents dans un seul tableau à structure libre. |

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
| Filtres d’audiences | 20 | Barrière de sécurité imposée par le système | Nombre maximal de [filtres](../components/filters/filters-overview.md) par audience. |
| Nombre d’identités d’audience | 20 million | Barrière de sécurité imposée par le système | Nombre maximal d’identités par audience. |
| Fréquence d’actualisation de l’audience | 4 | Barrière de sécurité imposée par le système | La fréquence maximale en heures d&#39;actualisation d&#39;une [audience](../components/audiences/audiences-overview.md). |
| Période de recherche en amont de l’actualisation de l’audience | 90 | Barrière de sécurité imposée par le système | Nombre maximal de jours pour l’intervalle de recherche en amont d’actualisation. |
| Actualisation de la date d’expiration de l’audience | 13 | Barrière de sécurité imposée par le système | Nombre maximum de mois pendant lesquels l’audience cesse de s’actualiser à partir de la date de création. Les clients peuvent prolonger cette période de 13 mois supplémentaires. |
| Nombre d’audiences actualisées | 75 150 | Barrière de sécurité imposée par le système | Nombre maximal d’audiences d’actualisation, la valeur varie en fonction du package du Customer Journey Analytics (voir Description du produit). |

{style="table-layout:auto"}

Voir aussi [Barrières de sécurité Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=fr) Experience Platform.


## Expiration automatisée du jeu de données

| Nom | Valeur | Type de limite | Description |
|---|--:|---|:---:|
| Commandes | 20 | Barrière de sécurité imposée par le système | Nombre maximal de commandes de travail d’expiration de jeu de données automatisées par mois. |

{style="table-layout:auto"}



## Connexions, Vues de données, Projets

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Projets | 50 000 | Barrière de sécurité imposée par le système | Nombre maximal de projets pour une organisation. |
| Vues des données | 2 000 | Barrière de sécurité imposée par le système | Nombre maximal de [vues de données](../data-views/data-views.md) pour une organisation. |
| Vues des données | 50 | Barrière de sécurité imposée par le système | Nombre maximal de vues de données pour une connexion |
| Jeux de données | 100 | Barrière de sécurité imposée par le système | Nombre maximal de [jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=fr) par connexion. |
| Connexions | 1000 | Barrière de sécurité imposée par le système | Nombre maximal de [connexions](../connections/overview.md) pour une organisation. |
| Titre de la connexion | 500 | Barrière de sécurité imposée par le système | Nombre maximal de caractères pour un titre de connexion. |
| Mesures | 5 000 | Barrière de sécurité imposée par le système | Nombre maximal de mesures dans une vue de données. |
| Dimensions | 5 000 | Barrière de sécurité imposée par le système | Nombre maximal de dimensions dans une vue de données. |
| Titre de l’annotation | 100 | Barrière de sécurité imposée par le système | Nombre maximal de caractères pour un titre d’annotation. |
| Description de l’annotation | 250 | Barrière de sécurité imposée par le système | Nombre maximal de caractères pour une description d’annotation. |
| Champs de schéma | 10 | Barrière de sécurité imposée par le système | Nombre maximum de champs de schéma (ne comprenant pas les champs standard) lors de la définition de règles pour un [champ dérivé](../data-views/derived-fields/derived-fields.md). |
| Recherche / Champs de profil | 3 | Barrière de sécurité imposée par le système | Nombre maximum de champs de schéma de recherche ou de profil dans le nombre maximum de champs de schéma (non compris les champs standard) lors de la définition de règles pour un champ dérivé. |
| Champs dérivés | 100 à 500 | Barrière de sécurité imposée par le système | Nombre maximal de champs dérivés par connexion ; la valeur varie en fonction du package du Customer Journey Analytics (voir Description du produit). |

{style="table-layout:auto"}


## Limites de transfert de données

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Champs | 10 000 | Barrière de sécurité imposée par le système | Nombre maximal de propriétés ou de champs par ligne dans un jeu de données. |
| Chaînes uniques | 10 million | Barrière de sécurité imposée par le système | Nombre maximal de clés uniques par jeu de données de recherche. |
| Lignes | 1 million | Barrière de sécurité imposée par le système | Nombre maximal de lignes par identifiant de personne unique au cours d’un mois donné au sein d’une connexion. |
| Taille de ligne | 2 | Barrière de sécurité des performances / barrière de sécurité appliquée au système | Taille moyenne en kilo-octets par ligne de données ingérées dans Customer Journey Analytics (limite soft). Une limite statique pour la taille des lignes est déterminée par les barrières de sécurité pour l’ingestion de données dans Experience Platform. |

{style="table-layout:auto"}

Voir aussi [Barrières de sécurité pour l’ingestion de données ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html) Experience Platform.


## Exportation des données de destinations

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Exportation de données | Stockage total autorisé du lac de données | Protection des performances | Le client peut utiliser l’exportation de jeux de données de destination pour exporter les données clients dans le lac de données jusqu’au stockage total autorisé de lac de données. |
| Jeux de données disponibles | Profil et événement | Protection forcée du système | Jeux de données d’événement, de profil ou de recherche créés dans l’interface utilisateur de l’Experience Platform après ingestion ou collecte de données par le biais de sources, SDK web, SDK mobile, Analytics Data Connector et Audience Manager. |

{style="table-layout:auto"}

Voir aussi [Barrières de sécurité de l’exportation des jeux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/guardrails#dataset-exports) Experience Platform


## Zone d&#39;entrée des données

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Zone d’entrée de données par sandbox | 1 | Barrière de sécurité imposée par le système | Nombre maximal de zones d’entrée de données par environnement de test. |
| Stockage des données | 7 | Barrière de sécurité imposée par le système | Nombre maximum de jours pendant lesquels les données sont stockées dans la zone d&#39;entrée des données avant d&#39;être supprimées. |

{style="table-layout:auto"}


## Groupement basé sur les champs

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Jeux de données groupés | 5 à 50 | Barrière de sécurité imposée par le système | Nombre maximal de jeux de données assemblés par client ; la valeur varie en fonction du package du Customer Journey Analytics (voir Description du produit). |
| Longueur de renvoi | 6 à 25 | Barrière de sécurité imposée par le système | Nombre maximal de mois de données de renvoi ; la valeur varie en fonction du package du Customer Journey Analytics (voir Description du produit). |
| Intervalle de recherche en amont/fréquence de relecture | 1/1 - 30/7 | Barrière de sécurité imposée par le système | Intervalle de recherche en amont maximal en jours / Fréquence de relecture ; la valeur varie en fonction du package du Customer Journey Analytics (voir Description du produit). |

{style="table-layout:auto"}


## Groupement basé sur les graphiques

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Jeux de données groupés | 10 à 50 | Barrière de sécurité imposée par le système | Nombre maximal de jeux de données assemblés par client ; la valeur varie en fonction du package du Customer Journey Analytics (voir Description du produit). |
| Longueur de renvoi | 13 à 25 | Barrière de sécurité imposée par le système | Nombre maximal de mois de données de renvoi ; la valeur varie en fonction du package du Customer Journey Analytics (voir Description du produit). |
| Intervalle de recherche en amont/fréquence de relecture | 1/1 - 30/7 | Barrière de sécurité imposée par le système | Intervalle de recherche en amont maximal en jours / Fréquence de relecture ; la valeur varie en fonction du package du Customer Journey Analytics (voir Description du produit). |


## Filtres et mesures calculées

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Conteneurs par filtre | 50 | Barrière de sécurité imposée par le système | Nombre maximal de conteneurs par filtre. |
| Mesures par mesure calculée | 25 | Barrière de sécurité imposée par le système | Nombre maximal de mesures par mesure calculée. |
| Mesures et Dimensions par filtre | 25 | Barrière de sécurité imposée par le système | Nombre maximal de mesures et de dimensions uniques par filtre. |
| Conteneurs imbriqués par filtre | 10 | Barrière de sécurité imposée par le système | Nombre maximal de conteneurs imbriqués par filtre. |
| Règles par filtre | 100 | Barrière de sécurité imposée par le système | Nombre maximal de règles par filtre. |
| Comparaisons des chaînes par Dimension et par filtre | 100 | Barrière de sécurité imposée par le système | Nombre maximum de comparaisons de chaînes par dimension et par filtre. |
| Mesures calculées | 6 000 | Barrière de sécurité imposée par le système | Nombre maximal de mesures calculées pour une organisation. |
| Filtres | 50 000 | Barrière de sécurité imposée par le système | Nombre maximal de filtres que vous pouvez définir pour une organisation. |
| Appels API | 120 | Barrière de sécurité imposée par le système | Demandes d’API par minute (12 demandes toutes les 6 secondes). |

{style="table-layout:auto"}


## Application mobile

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Carreaux | 16 | Barrière de sécurité imposée par le système | Nombre maximal de mosaïques par fiche d’évaluation. |
| Filtres | 10 | Barrière de sécurité imposée par le système | Nombre maximal de filtres par fiche d’évaluation. |
| Dimensions | 10 | Barrière de sécurité imposée par le système | Nombre maximal de dimensions par fiche d’évaluation. |

{style="table-layout:auto"}

## Report Builder

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Taille du fichier du classeur | 5 | Barrière de sécurité imposée par le système | Taille maximale du fichier en Mo d’un classeur planifié. |
| Blocs de données | 1000 | Barrière de sécurité imposée par le système | Nombre maximal de [blocs de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=fr) par classeur. |
| Mesures | 20 | Barrière de sécurité imposée par le système | Nombre maximal de mesures par bloc de données. |
| Période | 13 | Barrière de sécurité imposée par le système | Nombre maximal de mois qu’une période peut couvrir par bloc de données. |
| Lignes | 50 000 | Barrière de sécurité imposée par le système | Nombre maximal de lignes par bloc de données. |

{style="table-layout:auto"}


## Export du tableau complet

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Lignes par rapport | 3 millions - 300 millions | Barrière de sécurité imposée par le système | Nombre maximal de lignes de rapport par rapport ; la valeur varie en fonction du package du Customer Journey Analytics (voir Description du produit). |
| Ventilations par tableau | 5 | Barrière de sécurité imposée par le système | Nombre maximum de ventilations par table. |
| Mesures par tableau | 5 | Barrière de sécurité imposée par le système | Nombre maximal de mesures par tableau. |
| Fréquence des planifications | 1 | Barrière de sécurité imposée par le système | Les exportations peuvent être planifiées une fois (1) par jour ou selon une planification plus longue (par exemple : une fois tous les 2 jours ou une fois par semaine). |

{style="table-layout:auto"}

## Latences

>[!NOTE]
>
>Les temps de traitement ci-dessous sont des protections, et non des contrats de niveau de service (SLA) contractuels. La latence varie en fonction de la configuration client, des volumes de données et des applications client. Les temps de traitement réels sont souvent plus rapides. Consultez votre contrat de Customer Journey Analytics pour connaître vos termes contractuels et contrats de niveau de service spécifiques. Pour plus d’informations, voir Barrières de sécurité Experience Platform pour Data Ingestion ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html) .[

| Flux de données | Latence attendue |
|---|---|
| Adobe Analytics vers Adobe Analytics Source Connector (A4T activé) | &lt; 30 minutes |
| Connecteur Source Adobe Analytics vers Real-time Customer Profile (A4T non activé) | &lt; 2 minutes |
| Connecteur Source Adobe Analytics vers Real-time Customer Profile (A4T activé) | &lt; 30 minutes |
| Ingestion de données dans le lac de données à partir d’une ingestion par flux ou Edge Network | &lt; 60 minutes |
| Ingestion de données dans le lac de données à partir d’Adobe Analytics Source Connector | &lt; 2,25 heures |
| Ingestion de données dans Customer Journey Analytics à partir du lac de données | &lt; 90 minutes |
| Assemblage (fonctionnalité facultative ; voir [Présentation de l’assemblage](../stitching/overview.md) pour plus d’informations) | &lt; 3,25 heures |
| Renvoi Adobe Analytics Source Connector de moins de 10 milliards d’événements (maximum 13 mois de données historiques) | &lt; 4 semaines |
| Publication d’audiences sur Real-time Customer Profile, y compris la création automatique du segment de diffusion en continu et la possibilité pour le segment d’être prêt à recevoir les données. | ≈ 60 minutes |
| Actualisation de la fréquence des audiences | Actualisation unique : latence inférieure à 5 minutes.<br/> Actualisez toutes les 4 heures, tous les jours, toutes les semaines, tous les mois (la latence va de pair avec le taux d’actualisation). |

{style="table-layout:auto"}
