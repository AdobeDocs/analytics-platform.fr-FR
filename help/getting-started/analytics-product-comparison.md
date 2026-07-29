---
title: Comparaison des produits Customer Journey Analytics
description: Comparez les attributs du client des outils de création de rapports et d’exportation de Parcours Analytics, tels qu’Analysis Workspace, Report Builder, l’exportation de tables complètes, les flux de données, les API et MCP.
keywords: parcours de navigation;flux de données;flux de données;comparaison de produits;Analysis Workspace;Report Builder;Exportation de tableau complet
feature: Components
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: e686fca2c77a8f9739298ece01ccf0fa2fe87b3b
workflow-type: tm+mt
source-wordcount: 464
ht-degree: 44%

---


# Comparaison des produits Analytics

Utilisez cette page pour comparer les outils de création de rapports et d’exportation de Customer Journey Analytics sur des attributs clés afin de vous aider à choisir l’outil approprié à vos besoins d’analyse ou d’exportation de données.

| Nom du produit et lien d’aide | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [Export du tableau complet](/help/analysis-workspace/export/export-cloud.md) | [Flux de données](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [API](https://developer.adobe.com/cja-apis/docs/?lang=fr) | MCP | Extension BI | Collègue |
|---|---|---|---|---|---|---|---|---|
| **Méthode d’accès** | Navigateur | Microsoft Excel | Navigateur | Configuration via le navigateur | Outils d’API RESTful | Outils compatibles avec MCP | Outils de BI | Outils compatibles avec MCP |
| **Granularité des données** | Agrégé | Agrégé | Agrégé | Événement | Agrégé | Agrégé | Agrégé | Agrégé |
| **Experience Cloud ID (ECID) disponible** | Non | Non | Non | Oui | Non | Non | Non | Non |
| **Horodatage disponible** | Non | Non | Non | Oui | Non | Non | Non | Non |
| **Niveau de traitement** | Traitement complet | Traitement complet, avec rapport en temps réel distinct | Traitement complet | Traitement complet | Traitement complet | Traitement complet | Traitement complet | Traitement complet |
| **Où le filtrage des robots est appliqué** | Dans le [flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/bot-detection) et/ou dans [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | Dans le [flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/bot-detection) et/ou dans [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | Dans le [flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/bot-detection) et/ou dans [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | Dans le [flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/bot-detection) et/ou dans [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) |  |  | Dans le [flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/bot-detection) et/ou dans [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | |
| **Limite des lignes visibles (avant pagination)** | 400 | 50,000 | Limite de 3 millions, 30 millions, 150 millions ou 300 millions, selon le niveau | Dépendance du niveau | 50,000 | 50,000 | 50,000 | 50,000 |
| **Vues de données multiples** | Oui, un projet peut contenir des données provenant de plusieurs vues de données | Oui, un projet peut contenir des données provenant de plusieurs vues de données | Non, une exportation ne peut contenir que des données d’une seule vue de données | Non, une exportation ne peut contenir que des données d’une seule vue de données | Non, chaque requête ne peut référencer qu’une seule vue de données | Non, chaque requête ne peut référencer qu’une seule vue de données | Non, chaque requête ne peut référencer qu’une seule vue de données | Oui, si l’utilisateur ou l’utilisatrice le demande |
| **Nombre de colonnes de dimension** | Jusqu’à 5 | ? | Jusqu’à 10 | Illimitées | Jusqu’à 5 | ? | ? | ? |
| **Nombre de colonnes de mesures** | ? | ? | Jusqu’à 10 | Illimitées | ? | ? | ? | ? |
| **Segmentation** <br> [En savoir plus](/help/components/segments/seg-overview.md) | Oui | Oui | Oui | Oui, avec des [limites](/help/components/exports/cja-data-feeds/df-segmentation.md) | Oui | Oui | Oui | Oui |
| **Mesures calculées** <br> [En savoir plus](/help/components/calc-metrics/calc-metr-overview.md) | Oui | Oui | Oui, avec des [limites](/help/analysis-workspace/export/export-cloud.md#calculated-metric-functions-support) | Non | Oui | Oui | Oui | Oui |
| **Champs dérivés** <br> [En savoir plus](/help/data-views/derived-fields/derived-fields.md) | Oui | Oui | Oui | Oui | Oui | Oui | Oui | Oui |
| **Attribution** <br> [En savoir plus](/help/analysis-workspace/attribution/overview.md) | Oui | Limitées | Oui, avec des [limites](/help/analysis-workspace/export/export-cloud.md#attribution-behavior) | Non | Oui | Oui | Oui | Oui |
| **Livraison planifiée** | Oui | Oui | Oui | Oui | — | — | — | — |
| **Destinations des diffusions** | Courriel | E-mail | Amazon S3, Azure RBAC, Azure SAS, GCP | Amazon S3, Azure RBAC, Azure SAS, GCP | — | — | — | — |

{style="table-layout:auto"}
