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
source-git-commit: c7fc5df2a0fd7393b48bfe6bdfa7dccdfffde46c
workflow-type: tm+mt
source-wordcount: 390
ht-degree: 53%

---


# Comparaison des produits Analytics

Utilisez cette page pour comparer les outils de création de rapports et d’exportation de Customer Journey Analytics sur des attributs clés afin de vous aider à choisir l’outil approprié à vos besoins d’analyse ou d’exportation de données.

| Nom du produit et lien d’aide | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [Export du tableau complet](/help/analysis-workspace/export/export-cloud.md) | [Flux de données](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [API](https://developer.adobe.com/cja-apis/docs/?lang=fr) | MCP |
|---|---|---|---|---|---|---|
| **Méthode d’accès** | Navigateur | Microsoft Excel | Navigateur | Configuration via le navigateur | Outils d’API RESTful | Outils compatibles avec MCP |
| **Granularité des données** | Agrégé | Agrégé | Agrégé | Événement | Agrégé | Agrégé |
| **Experience Cloud ID (ECID) disponible** | Non | Non | Non | Oui | Non | Non |
| **Horodatage disponible** | Non | Non | Non | Oui | Non | Non |
| **Niveau de traitement** | Traitement complet | Traitement complet | Traitement complet | Traitement complet | Traitement complet | Traitement complet |
| **Données de filtre de robots incluses** | Non | Non | Non | Non | Non | Non |
| **Limite des lignes visibles (avant pagination)** | 400 | 50,000 | Limite de 3 millions, 30 millions, 150 millions ou 300 millions, selon le niveau | Limite de 3 millions, 30 millions, 150 millions ou 300 millions, selon le niveau | 50,000 | 50,000 |
| **Vues de données multiples** | Oui, un projet peut contenir des données provenant de plusieurs vues de données | Oui, un projet peut contenir des données provenant de plusieurs vues de données | Non, une exportation ne peut contenir que des données d’une seule vue de données | Non, une exportation ne peut contenir que des données d’une seule vue de données | Oui | Oui |
| **Nombre de répartitions** | Illimitées | Jusqu’à 2 | Illimitées | Illimitées | Illimitées, appliquées à plusieurs requêtes | Illimitées |
| **Segmentation** <br> [En savoir plus](/help/components/segments/seg-overview.md) | Oui | Oui | Oui | Oui, avec des [limites](/help/components/exports/cja-data-feeds/df-segmentation.md) | Oui | Oui |
| **Mesures calculées** <br> [En savoir plus](/help/components/calc-metrics/calc-metr-overview.md) | Oui | Oui | Oui, avec des [limites](/help/analysis-workspace/export/export-cloud.md#calculated-metric-functions-support) | Non | Oui | Oui |
| **Champs dérivés** <br> [En savoir plus](/help/data-views/derived-fields/derived-fields.md) | Oui | Oui | Oui | Oui | Oui | Oui |
| **Analyse des cohortes** | [Oui](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Non | Non | Non | Non | Non |
| **Attribution** <br> [En savoir plus](/help/analysis-workspace/attribution/overview.md) | Oui | Limitées | Non | Non | Oui | Oui |
| **Traitement** <br> [En savoir plus](/help/analysis-workspace/curate-share/curate.md) | Oui, avec dans les projets et les vues de données | Non | Non | Oui, dans la vue de données | Oui, dans la vue de données | Oui, dans la vue de données |
| **Partage des projets** <br> [En savoir plus](/help/analysis-workspace/curate-share/share-projects.md) | Oui, avec des rôles de projet | Non | Non | Non | Non | Non |
| **Livraison planifiée** | Oui | Oui | Oui | Oui | Non | Non |
| **Destinations des diffusions** | Courriel | E-mail | Amazon S3, Azure RBAC, Azure SAS, GCP | Amazon S3, Azure RBAC, Azure SAS, GCP | — | — |
| **Traitement de la période de rapport de la vue de données** <br> [En savoir plus](/help/data-views/data-views.md) | Oui | Oui | Non | Non | Oui | Oui |

{style="table-layout:auto"}
