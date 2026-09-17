---
title: Extension BI de Customer Journey Analytics
description: Décrit comment utiliser l’extension BI pour importer des données numériques dans vos propres outils BI ou dans le lac de données en vue de les utiliser avec des jeux de données supplémentaires.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 669a1305-3e37-4ca2-8178-a89a27958e5d
autotag-review: '2026-05-19T08:00:39.048Z'
TQID: 'https://experienceleague.adobe.com/BgO7hQlR2J3o-nD38ZIg2ILUTwDKGfSXu-i-bEo5SJs'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 25%
---
# Extension BI

Cet article décrit comment le [!DNL Customer Journey Analytics BI extension] peut être utilisé pour implémenter le cas d’utilisation d’exportation de données [ suivant ](overview.md) :

* Lac de données, Data Warehouse ou outils de BI

## Introduction

L’exportation de données à l’aide de l’[!DNL Customer Journey Analytics BI extension] vous permet d’exporter des données de vos vues de données Customer Journey Analytics.

Extension ![BI](../assets/bi-extension.png)

## Informations supplémentaires

Le [!DNL Customer Journey Analytics BI extension] permet à SQL d’accéder aux [vues de données](/help/data-views/data-views.md) que vous avez définies dans Customer Journey Analytics. Vos ingénieurs et analystes de données connaissent mieux Power BI, Tableau ou d’autres outils de Business Intelligence et de visualisation (également appelés outils de BI). Elles peuvent désormais créer des rapports et des tableaux de bord en fonction des vues de données des utilisateurs et utilisatrices de Customer Journey Analytics lors de la création de leurs projets Analysis Workspace.

L’extension BI renvoie des données agrégées, et non des lignes brutes au niveau de l’événement. Par défaut, chaque requête renvoie 50 lignes pour une période de 30 jours, mais vous pouvez remplacer la limite de lignes par un maximum de 50 000 lignes et la période par votre propre période personnalisée. Voir [Valeurs par défaut et limites](../../data-views/bi-extension.md#defaults-and-limitations) pour plus d’informations.

Pour plus d’informations, consultez la documentation détaillée sur l’extension [BI](../../data-views/bi-extension.md).
