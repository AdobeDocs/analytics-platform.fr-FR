---
title: Table complète d’exportation Customer Journey Analytics
description: Décrit comment utiliser la fonctionnalité Exporter une table complète pour valider vos données ou utiliser vos données pour l'IA/ML.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: ee004948-3025-434b-a90b-8aa185800820
autotag-review: '2026-05-19T09:39:35.989Z'
TQID: 'https://experienceleague.adobe.com/5lP3PKpCpxkeyH34327gieZ48KFkEai4DF2SC0H4E2U'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 4%
---
# Exporter le tableau complet

Cet article décrit comment la fonctionnalité [!DNL Export full table] peut être utilisée pour implémenter le cas d’utilisation d’exportation de données [ suivant ](overview.md) :

* Validation des données
* Préparation à l’IA/ML

## Introduction

L’exportation de données à l’aide de [!DNL Customer Journey Analytics Full Table Export] vous permet d’exporter des données de vos tableaux à structure libre dans Customer Journey Analytics Analysis Workspace.

Extension ![BI](../assets/export-full-table.png)

## Informations supplémentaires

Pour exporter le contenu complet d’un tableau à structure libre que vous créez dans Analysis Workspace directement vers des destinations cloud désignées, utilisez la fonctionnalité Exporter le tableau complet .

L’exportation du tableau complet prend en charge jusqu’à 10 dimensions et 10 mesures par rapport, et inclut des mesures calculées et la segmentation. Selon le niveau de licence, vous pouvez exporter 3 millions, 30 millions, 150 millions ou 300 millions de lignes par exportation, dépassant la limite de 50 000 lignes des autres méthodes d’exportation. Les destinations prises en charge comprennent la zone d’atterrissage de données Adobe Experience Platform, Google Cloud Platform, Microsoft Azure, Amazon S3 et Snowflake. Voir [Avantages de l’exportation complète des tables](/help/analysis-workspace/export/export-cloud.md#advantages) pour plus d’informations.

Pour plus d’informations, consultez la documentation détaillée sur la [Exporter des rapports Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md).
