---
title: Mécanismes de sécurisation de Customer Journey Analytics
description: En savoir plus sur les mécanismes de sécurisation de Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: 2dd215b0fe689c9370e9f5867fd1bd5fdee83d42
workflow-type: tm+mt
source-wordcount: '1760'
ht-degree: 10%

---

# Mécanismes de sécurisation de Customer Journey Analytics

Ce document fournit des limites pour divers composants de Customer Journey Analytics. Pour les mécanismes de sécurisation, les paramètres de définition de la portée et les droits, reportez-vous à la [ Description du produit pour Customer Journey Analytics ](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=fr) ou à la [ Description du produit pour le module complémentaire Adobe Analytics : Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html?lang=fr).

## Types de limite

Ce document comprend deux types de limites par défaut :

| Type de mécanisme de sécurisation | Description |
|----------|---------|
| **Mécanismes de sécurisation des performances (limite soft)** | Les mécanismes de sécurisation de performances sont des limites d’utilisation liées à la portée de vos cas d’utilisation. Si vous dépassez les mécanismes de sécurisation des performances, vous pouvez rencontrer une dégradation des performances et une latence. L’Adobe n’est pas responsable de cette dégradation des performances. Les clients qui dépassent systématiquement un mécanisme de sécurisation des performances peuvent choisir de concéder une licence pour une capacité supplémentaire afin d’éviter une dégradation des performances. |
| **Mécanismes de sécurisation appliqués par le système (limite stricte)** | Les mécanismes de sécurisation appliqués par le système sont appliqués par l’interface utilisateur ou l’API du Customer Journey Analytics. Il s’agit de limites que vous ne pouvez pas dépasser, car l’interface utilisateur et l’API vous en empêchent ou renvoient une erreur. |

{style="table-layout:auto"}

Certaines des fonctionnalités et leur valeur associée pour la limitation dépendent du package de Customer Journey Analytics auquel vous avez droit.

>[!NOTE]
>
>Les valeurs décrites dans ce document peuvent faire l’objet de modifications en fonction des améliorations continues du produit. Consultez régulièrement les mises à jour. Si vous souhaitez en savoir plus sur les limites personnalisées, contactez votre représentant de l’assistance clientèle.

## Requêtes SQL ad hoc

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Délai d’expiration de la réessai | 90 | Mécanisme de sécurisation mis en œuvre par le système | Nombre de secondes maximum avant que le moteur de création de rapports ne réponde que la requête met trop de temps à renvoyer les résultats (peut-être en raison d’autres requêtes simultanées) ; il est possible de faire une nouvelle requête. |
| Ne plus réessayer après la temporisation | 600 | Mécanisme de sécurisation mis en œuvre par le système | Durée maximale en secondes avant expiration des requêtes SQL ad hoc. Dans le cas contraire, le nombre maximal de secondes avant que les moteurs de création de rapports ne renvoient un rapport indiquant que la requête a mis trop de temps à renvoyer des résultats et qu’elle ne doit pas être réexécutée. La requête ne renvoie probablement jamais de résultats en raison de problèmes dans le processus en arrière-plan. |
| Mesures | 150 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures dans une requête. |
| Lignes de sortie de requête interactive | 50 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre par défaut de lignes renvoyées, sauf indication contraire. |

{style="table-layout:auto"}

## Projets Analysis Workspace

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Lignes visibles par tableau | 400 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de lignes visibles dans un tableau à structure libre d’un projet Analysis Workspace. |
| Lignes exportables par tableau | 50 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de lignes exportables par dimension unique. |
| Panneaux par projet | 15 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de [panneaux](../analysis-workspace/home.md#panels) par projet. |
| Visualisations par panneau | 25 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de [visualisations](../analysis-workspace/home.md#visualizations) par panneau. |
| Champs dérivés par tableau à structure libre | 5 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de champs dérivés différents dans un seul tableau à structure libre. |

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
| Filtres d’audience | 20 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de [filtres](../components/filters/filters-overview.md) par audience. |
| Nombre d’identités d’audience | 20 million | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal d’identités par audience. |
| Fréquence d’actualisation de l’audience | 4 | Mécanisme de sécurisation mis en œuvre par le système | Fréquence maximale en heures pendant laquelle une [ audience ](../components/audiences/audiences-overview.md) peut être actualisée. |
| Intervalle De Recherche En Amont De L’Actualisation D’Audience | 90 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de jours pour l’intervalle de recherche en amont de l’actualisation. |
| Actualisation de la date d’expiration de l’audience | 13 | Mécanisme de sécurisation mis en œuvre par le système | Le nombre maximal de mois pendant lesquels l’audience cesse d’être actualisée à partir de la date de création. Les clients peuvent prolonger ce délai de 13 mois supplémentaires. |
| Nombre d’audiences en cours d’actualisation | 75 150 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal d’audiences en cours d’actualisation. La valeur varie en fonction du package de Customer Journey Analytics (voir Description du produit). |

{style="table-layout:auto"}

Consultez également la section Mécanismes de sécurisation Real-time Customer Data Platform [Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=fr).


## Expiration automatisée des jeux de données

| Nom | Valeur | Type de limite | Description |
|---|--:|---|:---:|
| Ordres de travail | 20 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal d’ordres de travail d’expiration automatisée de jeux de données par mois. |

{style="table-layout:auto"}



## Connexions, Vues de données, Projets

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Projets | 50 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de projets pour une organisation. |
| Vues des données | 2 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de [vues de données](../data-views/data-views.md) pour une organisation. |
| Vues des données | 500-1000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de vues de données pour une connexion. La valeur varie en fonction du package de Customer Journey Analytics (voir Description du produit). |
| Jeux de données | 100 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de [jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=fr) par connexion. |
| Connexions | 1000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de [connexions](../connections/overview.md) pour une organisation. |
| Titre de la connexion | 500 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de caractères pour un titre de connexion. |
| Mesures | 5 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures dans une vue de données. |
| Dimensions | 5 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de dimensions dans une vue de données. |
| Titre de l’annotation | 100 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de caractères pour le titre d’une annotation. |
| Description de l’annotation | 250 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de caractères pour la description d’une annotation. |
| Champs de schéma | 10 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de champs de schéma (champs standard non inclus) lors de la définition de règles pour un [champ dérivé](../data-views/derived-fields/derived-fields.md). |
| Champs de recherche/profil | 3 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de champs de schéma de recherche ou de profil dans le nombre maximal de champs de schéma (champs standard non inclus) lors de la définition de règles pour un champ dérivé. |
| Champs dérivés | 100 - 500 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de champs dérivés par connexion. La valeur varie en fonction du package de Customer Journey Analytics (voir Description du produit). |

{style="table-layout:auto"}


## Limites de transfert de données

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Champs | 10 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de propriétés ou de champs par ligne dans un jeu de données. |
| Chaînes uniques | 10 million | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de clés uniques par jeu de données de recherche. |
| Lignes | 1 million | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de lignes par ID de personne unique au cours d’un mois donné dans une connexion. |
| Taille de ligne | 2 | Mécanisme de sécurisation des performances/mécanisme de sécurisation mis en œuvre par le système | Taille moyenne en kilo-octets par ligne de données ingérées dans Customer Journey Analytics (limite conditionnelle). Une limite statique pour la taille des lignes est déterminée par les mécanismes de sécurisation pour l’ingestion de données dans Experience Platform. |

{style="table-layout:auto"}

Consultez également la section Mécanismes de sécurisation Experience Platform [pour l’ingestion de données](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html).


## Exportation des données des destinations

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Exportation de données | Stockage total autorisé dans le lac de données | Mécanisme de sécurisation des performances | Le client peut utiliser l’exportation de jeux de données de destination pour exporter les données client dans le lac de données jusqu’au stockage total autorisé du lac de données. |
| Jeux de données disponibles | Profil et événement | Mécanisme de sécurisation appliqué par le système | Jeux de données d’événements, de profils ou de recherches créés dans l’interface utilisateur de l’Experience Platform après l’ingestion ou la collecte de données par le biais de sources, de Web SDK, de Mobile SDK, du connecteur de données Analytics et de l’Audience Manager. |

{style="table-layout:auto"}

Consultez également la section Mécanismes de sécurisation Experience Platform [Exportation de jeux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/guardrails#dataset-exports)


## Zone d’atterrissage des données

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Zone d’atterrissage des données par sandbox | 1 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de zones d’atterrissage de données par sandbox. |
| Stockage des données | 7 | Mécanisme de sécurisation mis en œuvre par le système | Le nombre maximum de jours pendant lesquels les données sont stockées dans la zone d’atterrissage avant d’être supprimées. |

{style="table-layout:auto"}


## Groupement basé sur les champs

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Jeux de données groupés | 5 - 50 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de jeux de données groupés par client. La valeur varie en fonction du package de Customer Journey Analytics (voir Description du produit). |
| Longueur de renvoi | 6 - 25 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mois de données de renvoi. La valeur varie en fonction du package de Customer Journey Analytics (voir Description du produit). |
| Intervalle de recherche en amont/Fréquence de relecture | 1/1 - 30/7 | Mécanisme de sécurisation mis en œuvre par le système | Intervalle de recherche en amont maximal en jours/fréquence de relecture. La valeur varie en fonction du package de Customer Journey Analytics (voir Description du produit). |

{style="table-layout:auto"}


## Groupement basé sur les graphiques

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Jeux de données groupés | 10 - 50 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de jeux de données groupés par client. La valeur varie en fonction du package de Customer Journey Analytics (voir Description du produit). |
| Longueur de renvoi | 13 - 25 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mois de données de renvoi. La valeur varie en fonction du package de Customer Journey Analytics (voir Description du produit). |
| Intervalle de recherche en amont/Fréquence de relecture | 1/1 - 30/7 | Mécanisme de sécurisation mis en œuvre par le système | Intervalle de recherche en amont maximal en jours/fréquence de relecture. La valeur varie en fonction du package de Customer Journey Analytics (voir Description du produit). |


## Filtres et mesures calculées

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Conteneurs par filtre | 50 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de conteneurs par filtre. |
| Mesures par mesure calculée | 25 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures par mesure calculée. |
| Mesures et Dimensions par filtre | 25 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures et de dimensions uniques par filtre. |
| Conteneurs imbriqués par filtre | 10 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de conteneurs imbriqués par filtre. |
| Règles par filtre | 100 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de règles par filtre. |
| Comparaisons de chaînes par Dimension et par filtre | 100 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de comparaisons de chaînes par dimension et par filtre. |
| Mesures calculées | 6 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures calculées pour une organisation. |
| Filtres | 50 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de filtres que vous pouvez définir pour une organisation. |
| Appels API | 120 | Mécanisme de sécurisation mis en œuvre par le système | Requêtes API par minute (12 requêtes toutes les 6 secondes). |

{style="table-layout:auto"}


## Application mobile

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Mosaïques | 16 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de vignettes par carte de performance. |
| Filtres | 10 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de filtres par carte de performance. |
| Dimensions | 10 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de dimensions par carte de performance. |

{style="table-layout:auto"}

## Report Builder

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Taille de fichier du classeur | 5 | Mécanisme de sécurisation mis en œuvre par le système | Taille maximale de fichier en Mo d’un classeur planifié. |
| Blocs de données | 1000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de [blocs de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=fr) par classeur. |
| Mesures | 20 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures par bloc de données. |
| Période | 13 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mois qu’une période peut couvrir par bloc de données. |
| Lignes | 50 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de lignes par bloc de données. |

{style="table-layout:auto"}


## Export du tableau complet

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Lignes par rapport | 3 millions - 300 millions | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de lignes de rapports par rapport. La valeur varie en fonction du package de Customer Journey Analytics (voir Description du produit). |
| Répartitions par tableau | 5 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de répartitions par tableau. |
| Mesures par tableau | 5 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures par table. |
| Fréquence de planification | 1 | Mécanisme de sécurisation mis en œuvre par le système | Les exportations peuvent être planifiées une fois (1) par jour ou sur une planification plus longue (par exemple : une fois tous les 2 jours ou une fois par semaine). |

{style="table-layout:auto"}

## Latences

>[!NOTE]
>
>Les délais de traitement ci-dessous sont des mécanismes de sécurisation, et non des accords de niveau de service (SLA) contractuels. La latence varie en fonction de la configuration du client, des volumes de données et des applications clientes. Les temps de traitement réels sont souvent plus rapides. Consultez votre contrat de Customer Journey Analytics pour connaître les termes contractuels et les contrats de niveau de service spécifiques. Pour plus d’informations, voir Mécanismes de sécurisation Experience Platform [Data Ingestion](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html).

| Flux de données | Latence attendue |
|---|---|
| Connecteur Adobe Analytics vers Adobe Analytics Source (activé A4T) | &lt; 30 minutes |
| Connecteur Source Adobe Analytics au profil client en temps réel (A4T non activé) | &lt; 2 minutes |
| Connecteur Adobe Analytics Source au profil client en temps réel (activé pour A4T) | &lt; 30 minutes |
| Ingestion de données dans le lac de données à partir de l’ingestion Edge Network ou en flux continu | &lt; 60 minutes |
| Ingestion de données dans le lac de données à partir du connecteur Adobe Analytics Source | &lt; 2,25 heures |
| Ingestion de données dans Customer Journey Analytics à partir du lac de données | &lt; 90 minutes |
| Groupement (fonctionnalité facultative ; voir [présentation du groupement](../stitching/overview.md) pour plus d’informations) | 4 heures |
| Renvoi du connecteur Adobe Analytics Source de moins de 10 milliards d’événements (maximum de 13 mois de données historiques) | &lt; 4 semaines |
| Publication d’audiences dans le profil client en temps réel, y compris la création automatique du segment de diffusion en continu et la possibilité pour le segment d’être prêt à recevoir les données. | ≈ 60 minutes |
| Fréquence d’actualisation des audiences | Actualisation unique : latence inférieure à 5 minutes.<br/>Actualisation toutes les 4 heures, tous les jours, toutes les semaines, tous les mois (la latence va de pair avec le taux d’actualisation). |

{style="table-layout:auto"}
