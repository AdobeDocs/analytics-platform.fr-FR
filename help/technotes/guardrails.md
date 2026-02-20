---
title: Mécanismes de sécurisation de Customer Journey Analytics
description: En savoir plus sur les mécanismes de sécurisation pour Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: 976170212fb9904a32db93368fbda5f143f4a462
workflow-type: tm+mt
source-wordcount: '2281'
ht-degree: 10%

---

# Mécanismes de sécurisation de Customer Journey Analytics

Ce document fournit des limites pour divers composants de Customer Journey Analytics. Pour les mécanismes de sécurisation, les paramètres de définition de la portée et les droits, reportez-vous aux sections [Description du produit pour Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=fr), [Description du produit pour le module complémentaire Adobe Analytics : Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html?lang=fr) ou [Description du produit pour Customer Journey Analytics B2B edition](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics-b2b.html?lang=fr).

## Types de limite

Ce document comprend deux types de limites par défaut :

| Type de mécanisme de sécurisation | Description |
|----------|---------|
| **Mécanismes de sécurisation des performances (limite soft)** | Les mécanismes de sécurisation de performances sont des limites d’utilisation liées à la portée de vos cas d’utilisation. Si vous dépassez les mécanismes de sécurisation des performances, vous pouvez rencontrer une dégradation des performances et une latence. Adobe n’est pas responsable de cette dégradation des performances. Les clients qui dépassent systématiquement un mécanisme de sécurisation des performances peuvent choisir de concéder une licence pour une capacité supplémentaire afin d’éviter une dégradation des performances. |
| **Mécanismes de sécurisation appliqués par le système (limite stricte)** | Les mécanismes de sécurisation appliqués par le système sont appliqués par l’interface utilisateur ou l’API Customer Journey Analytics. Il s’agit de limites que vous ne pouvez pas dépasser, car l’interface utilisateur et l’API vous en empêchent ou renvoient une erreur. |

{style="table-layout:auto"}

Certaines des fonctionnalités et leur valeur associée pour la limite dépendent du package Customer Journey Analytics auquel vous avez droit.

>[!NOTE]
>
>Les valeurs décrites dans ce document peuvent faire l’objet de modifications en fonction des améliorations continues du produit. Consultez régulièrement les mises à jour. Si vous souhaitez en savoir plus sur les limites personnalisées, contactez votre représentant de l’assistance clientèle.

## Requêtes SQL ad hoc

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Délai d’expiration de la réessai | 90 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximum de secondes avant que le moteur de création de rapports ne réponde que la requête prend trop de temps pour renvoyer les résultats (peut-être en raison d’autres requêtes simultanées). Il est possible de faire une nouvelle requête. |
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
| Commentaires par projet | 1 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de commentaires par projet. |
| Commentaires par projet | 1 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de commentaires par projet. |
| Réponses par commentaire | 100 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximum de réponses par commentaire. |
| Images par commentaire | 5 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal d’images par commentaire. |
| Taille de l’image | 2 | Mécanisme de sécurisation mis en œuvre par le système | Taille maximale de chargement par image en Mo. |
| Réponses par commentaire | 100 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximum de réponses par commentaire. |
| Images par commentaire | 5 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal d’images par commentaire. |
| Taille de l’image | 2 | Mécanisme de sécurisation mis en œuvre par le système | Taille maximale de chargement par image en Mo |

{style="table-layout:auto"}


<!-- at flatview GA, add: - Dimension columns per freeform table - 5 - System-enforced Guardrail - Maximum number of dimensions per freeform table. -->

<!--

## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

-->

## Audiences

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Segments d’audience | 20 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de [segments](../components/segments/seg-overview.md) par audience. |
| Nombre d’identités d’audience | 20 million | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal d’identités par audience. |
| Fréquence d’actualisation de l’audience | 4 | Mécanisme de sécurisation mis en œuvre par le système | Fréquence maximale en heures pendant laquelle une [ audience ](../components/audiences/audiences-overview.md) peut être actualisée. |
| Intervalle De Recherche En Amont De L’Actualisation D’Audience | 90 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de jours pour l’intervalle de recherche en amont de l’actualisation. |
| Actualisation de la date d’expiration de l’audience | 13 | Mécanisme de sécurisation mis en œuvre par le système | Le nombre maximal de mois pendant lesquels l’audience cesse d’être actualisée à partir de la date de création. Les clients peuvent prolonger ce délai de 13 mois supplémentaires. |
| Nombre d’audiences en cours d’actualisation | 75 150 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal d’audiences en cours d’actualisation. La valeur varie en fonction du package Customer Journey Analytics (voir Description du produit). |

{style="table-layout:auto"}

Consultez également la section Experience Platform [Mécanismes de sécurisation de Real-time Customer Data Platform](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/guardrails/overview).


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
| Vues des données | 500-1000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de vues de données pour une connexion. La valeur varie en fonction du package Customer Journey Analytics (voir Description du produit). |
| Jeux de données | 100 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de [jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=fr) par connexion. |
| Connexions | 1 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de [connexions](../connections/overview.md) pour une organisation. |
| Titre de la connexion | 500 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de caractères pour un titre de connexion. |
| Mesures | 5 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures dans une vue de données. |
| Dimensions | 5 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de dimensions dans une vue de données. |
| Titre de l’annotation | 100 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de caractères pour le titre d’une annotation. |
| Description de l’annotation | 250 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de caractères pour la description d’une annotation. |
| Champs de schéma | 10 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de champs de schéma (champs standard non inclus) lors de la définition de règles pour un [champ dérivé](../data-views/derived-fields/derived-fields.md). |
| Champs de recherche/profil | 3 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de champs de schéma de recherche ou de profil dans le nombre maximal de champs de schéma (champs standard non inclus) lors de la définition de règles pour un champ dérivé. |
| Champs dérivés | 100 - 500 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de champs dérivés par connexion. La valeur varie en fonction du package Customer Journey Analytics (voir Description du produit). |

{style="table-layout:auto"}


## Limites de transfert de données

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Champs | 10 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de propriétés ou de champs par ligne dans un jeu de données. |
| Chaînes uniques | 10 millions - 1 milliard | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de clés uniques par jeu de données de recherche. Dépend du package Customer Journey Analytics (voir Description du produit).<ul><li>Fondation : 10 millions.</li><li>Sélectionner : 100 millions.</li><li>Prime : 250 millions.</li><li>Ultimate : 1 milliard</li><ul> |
| Lignes par personne | 1 million | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de lignes par ID de personne unique au cours d’un mois donné dans une connexion. |
| Lignes par jour | 2,5 milliards | Mécanisme de sécurisation des performances | Nombre moyen maximal de lignes par jour dans une connexion. |
| Lignes par connexion par an | Varie selon le centre de données affecté (voir la description pour plus d’informations). | Mécanisme de sécurisation des performances | Limite de lignes par an dans une connexion. Les limites répertoriées ci-dessous sont effectives à compter du 20 janvier 2026 et peuvent augmenter au fil du temps pour autoriser plus de lignes par connexion. <p>La limite des lignes varie comme suit en fonction du centre de données affecté :</p><ul><li>**ÉTATS-UNIS Azure (valeur par défaut pour les clients américains)** : environ 500 milliards (environ 42 milliards par mois)</li><li>**ÉTATS-UNIS AWS (disponible sur demande pour les clients américains)** : environ 30 milliards (environ 2,5 milliards par mois)</li><li>**Amsterdam** : Environ 200 milliards (environ 16,5 milliards par mois)</li><li>**Tous les autres centres de données** : 25 milliards (environ 2 milliards par mois)</li></ul><p>Si vous prévoyez de dépasser ces limites et souhaitez éviter tout problème de dégradation des performances, contactez l’équipe de votre compte Adobe pour discuter des autres configurations.</p><p>Les entreprises peuvent choisir leur centre de données lors de la mise en œuvre initiale d’AEP+Apps. Cette décision est généralement basée sur les propres exigences de résidence des données de chaque client. Tous les cas d’utilisation AEP+Apps (et pas seulement les volumes de lignes dans Customer Journey Analytics) doivent être pris en compte lors du choix d’un centre de données.</p><p>Pour plus d’informations sur l’affichage du centre de données qui vous est affecté, consultez [Emplacements d’hébergement Customer Journey Analytics](/help/technotes/data-centers.md).</p> |
| Taille de ligne | 2 | Mécanisme de sécurisation des performances/mécanisme de sécurisation mis en œuvre par le système | Taille moyenne en kilo-octets par ligne de données ingérées dans Customer Journey Analytics (limite conditionnelle). Une limite statique pour la taille des lignes est déterminée par les mécanismes de sécurisation pour l’ingestion des données dans Experience Platform. |

{style="table-layout:auto"}

Consultez également la section Experience Platform [ Mécanismes de sécurisation pour l’ingestion de données](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html).


## Exportation des données des destinations

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Exportation de données | Stockage total autorisé dans le lac de données | Mécanisme de sécurisation des performances | Le client peut utiliser l’exportation de jeux de données de destination pour exporter les données client dans le lac de données jusqu’au stockage total autorisé du lac de données. |
| Jeux de données disponibles | Profil et événement | Mécanisme de sécurisation appliqué par le système | Jeux de données d’événements, de profils ou de recherches créés dans l’interface utilisateur d’Experience Platform après l’ingestion ou la collecte de données par le biais de sources, de Web SDK, de Mobile SDK, du connecteur de données Analytics et d’Audience Manager. |

{style="table-layout:auto"}

Consultez également la section Experience Platform [ Mécanismes de sécurisation d’exportation de jeux de données ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/guardrails#dataset-exports)


## Zone d’atterrissage des données

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Zone d’atterrissage des données par sandbox | 1 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de zones d’atterrissage de données par sandbox. |
| Stockage des données | 7 | Mécanisme de sécurisation mis en œuvre par le système | Le nombre maximum de jours pendant lesquels les données sont stockées dans la zone d’atterrissage avant d’être supprimées. |

{style="table-layout:auto"}


## Rapprochement basé sur les champs

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Jeux de données groupés | 5 - 50 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de jeux de données groupés par client. La valeur varie en fonction du package Customer Journey Analytics (voir Description du produit). |
| Longueur de renvoi | 6 - 25 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mois de données de renvoi. La valeur varie en fonction du package Customer Journey Analytics (voir Description du produit). |
| Intervalle de recherche en amont/Fréquence de relecture | 1/1 - 30/7 | Mécanisme de sécurisation mis en œuvre par le système | Intervalle de recherche en amont maximal en jours/fréquence de relecture. La valeur varie en fonction du package Customer Journey Analytics (voir Description du produit). |

{style="table-layout:auto"}


## Rapprochement basé sur les graphiques

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Jeux de données groupés | 15 - 50 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de jeux de données groupés par client. La valeur varie en fonction du package Customer Journey Analytics (voir Description du produit). |
| Longueur de renvoi | 6 - 25 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mois de données de renvoi. La valeur varie en fonction du package Customer Journey Analytics (voir Description du produit). |
| Intervalle de recherche en amont/Fréquence de relecture | 1/1 - 30/7 | Mécanisme de sécurisation mis en œuvre par le système | Intervalle de recherche en amont maximal en jours/fréquence de relecture. La valeur varie en fonction du package Customer Journey Analytics (voir Description du produit). |


## Segments et mesures calculées

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Conteneurs par segment | 50 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de conteneurs par segment. |
| Mesures par mesure calculée | 25 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures par mesure calculée. |
| Mesures et dimensions par segment | 25 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures et de dimensions uniques par segment. |
| Conteneurs imbriqués par segment | 10 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de conteneurs imbriqués par segment. |
| Règles par segment | 100 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de règles par segment. |
| Comparaisons de chaînes par Dimension et par segment | 100 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de comparaisons de chaînes par dimension et par segment. |
| Mesures calculées | 50 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures calculées pour une organisation. |
| Segments | 50 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de segments que vous pouvez définir pour une organisation. |
| Appels API | 120 | Mécanisme de sécurisation mis en œuvre par le système | Requêtes API par minute (12 requêtes toutes les 6 secondes). |

{style="table-layout:auto"}


## Application mobile

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Mosaïques | 16 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de vignettes par carte de performance. |
| Segments | 10 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de segments par carte de performance. |
| Dimensions | 10 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de dimensions par carte de performance. |

{style="table-layout:auto"}

## Report Builder

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Taille de fichier du classeur | 5 | Mécanisme de sécurisation mis en œuvre par le système | Taille maximale de fichier en Mo d’un classeur planifié. |
| Blocs de données | 1 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de [blocs de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=fr) par classeur. |
| Mesures | 20 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures par bloc de données. |
| Période | 13 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mois qu’une période peut couvrir par bloc de données. |
| Lignes | 50 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de lignes par bloc de données. |

{style="table-layout:auto"}


## Export du tableau complet

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Lignes par rapport | 3 millions - 300 millions | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de lignes de rapports par rapport. La valeur varie en fonction du package Customer Journey Analytics (voir Description du produit). |
| Répartitions par tableau | 5 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de répartitions par tableau. |
| Mesures par tableau | 5 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures par table. |
| Fréquence de planification | 1 | Mécanisme de sécurisation mis en œuvre par le système | Les exportations peuvent être planifiées une fois (1) par jour ou sur une planification plus longue (par exemple : une fois tous les 2 jours ou une fois par semaine). |

{style="table-layout:auto"}


## Mesures et dimensions partagées

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Bibliothèque partagée | 1 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de bibliothèques partagées pour une connexion. |
| Mesures partagées | 10 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de mesures partagées par bibliothèque partagée. |
| Dimensions communes | 10 000 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de dimensions partagées par bibliothèque partagée. |

{style="table-layout:auto"}


## Agent Data Insights

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Vues des données | 50 | Mécanisme de sécurisation mis en œuvre par le système | Nombre maximal de vues de données activables pour le Data Insights Agent. Lorsque d’autres vues de données sont activées, seules les vues de données les plus utilisées sont disponibles pour le Data Insights Agent. Ce mécanisme de sécurisation n’a aucune incidence sur les [mécanismes de sécurisation définissant le nombre maximal de vues de données que vous pouvez définir pour une connexion ou au sein de votre organisation](#connections-data-views-projects). |


## Customer Journey Analytics B2B Edition

| Nom | Valeur | Type de limite | Description |
|---|--:|---|---|
| Lignes à déclarer du profil professionnel (BPP) | 1 million | Mécanisme de sécurisation des performances | Nombre moyen de lignes à déclarer pour 1 000 profils professionnels à déclarer |




## Latences

>[!NOTE]
>
>Les délais de traitement ci-dessous sont des mécanismes de sécurisation, et non des accords de niveau de service (SLA) contractuels. La latence varie en fonction de la configuration du client, des volumes de données et des applications clientes. Les temps de traitement réels sont souvent plus rapides. Consultez votre contrat Customer Journey Analytics pour connaître les conditions contractuelles et les contrats de niveau de service spécifiques. Voir Experience Platform [Mécanismes de sécurisation pour l’ingestion de données](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html) pour plus d’informations.

| Flux de données | Latence attendue |
|---|---|
| Connecteur Adobe Analytics vers Adobe Analytics Source (activé A4T) | &lt; 30 minutes |
| Connecteur Source Adobe Analytics au profil client en temps réel (A4T non activé) | &lt; 2 minutes |
| Connecteur Adobe Analytics Source au profil client en temps réel (activé pour A4T) | &lt; 30 minutes |
| Ingestion de données dans le lac de données à partir d’Edge Network ou ingestion par flux | &lt; 60 minutes |
| Ingestion de données dans le lac de données à partir du connecteur Adobe Analytics Source | &lt; 2,25 heures |
| Ingestion de données dans Customer Journey Analytics à partir du lac de données | &lt; 90 minutes |
| Groupement (fonctionnalité facultative ; voir [présentation du groupement](../stitching/overview.md) pour plus d’informations) | &lt; 4 heures |
| Renvoi du connecteur Adobe Analytics Source de moins de 10 milliards d’événements (maximum de 13 mois de données historiques) | &lt; 4 semaines |
| Publication d’audiences dans le profil client en temps réel, y compris la création automatique du segment de diffusion en continu et la possibilité pour le segment d’être prêt à recevoir les données. | ≈ 60 minutes |
| Fréquence d’actualisation des audiences | Actualisation unique : latence inférieure à 5 minutes.<br/>Actualisation toutes les 4 heures, tous les jours, toutes les semaines, tous les mois (la latence va de pair avec le taux d’actualisation). |

| Latences de création de rapports en temps réel | Latence attendue |
|---|---|
| SDK/API d’Edge Network dans Edge Network | &lt; 7 minutes |
| Connecteurs de diffusion en continu | &lt; 17 minutes |
| Connecteur source Adobe Analytics | &lt; 17 minutes |
| Autres connecteurs source (y compris les données par lots) | &lt; 25 heures |

{style="table-layout:auto"}
