---
title: Segmentation dans les flux de données
description: Découvrez comment appliquer des segments aux flux de données Customer Journey Analytics et comment les segments de période interagissent avec la fenêtre de création de rapports du flux.
keywords: parcours de navigation;flux de données;flux de données;segmentation;segments;période
feature: Components
hide: true
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
source-wordcount: 357
ht-degree: 0%

---


# Segmentation dans les flux de données

{{release-limited-testing}}

Les flux de données de Customer Journey Analytics prennent en charge la segmentation, ce qui vous permet de filtrer les lignes incluses dans chaque diffusion de flux. Vous pouvez appliquer des segments au niveau de la vue de données, du flux ou des deux.

## Où les segments sont appliqués

Vous pouvez appliquer des segments à un flux de données à deux endroits :

- **Vue de données** : segment configuré dans la vue de données qui s’applique à tous les flux utilisant cette vue de données.
- **Flux de données** : segment appliqué directement à un flux individuel, en plus de tout segment de vue de données.

Lorsque les deux sont configurés, Customer Journey Analytics les combine. Seules les lignes qui répondent aux deux segments sont incluses dans la sortie de flux.

## Segments incluant une période

Vous pouvez utiliser des segments qui incluent des périodes dans un flux de données. Cependant, la fenêtre de création de rapports est toujours définie par la diffusion planifiée du flux (horaire ou quotidienne). Si un segment contient une période, il filtre les lignes dans la fenêtre du flux de données sans modifier ou développer la fenêtre elle-même.

Cette procédure est différente de celle d’Analysis Workspace, où l’application d’un segment qui comprend une période modifie la fenêtre de création de rapports active pour correspondre à la période du segment.

## Qualification du segment et période de recherche en amont

Pour les segments qui utilisent un conteneur Personne ou Session , la qualification est déterminée par le paramètre **Période de recherche en amont** et pas seulement par la fenêtre de diffusion. Si une personne répond aux critères de la période de recherche arrière, tous les événements de cette personne dans la fenêtre de diffusion sont inclus. Le paramètre de conteneur détermine la portée :

- **Conteneur d’événements** : seuls les événements correspondant aux critères de segment dans la fenêtre de diffusion sont inclus.
- **Conteneur de sessions** : tous les événements des sessions de qualification dans la fenêtre de diffusion sont inclus, où la qualification de la session est évaluée sur la période de recherche en amont.
- **Conteneur de personnes** : tous les événements de la fenêtre de diffusion sont inclus pour toute personne qualifiée pendant la période de recherche en amont.

Pour plus d’informations sur la période de recherche en amont et son impact sur la qualification des segments, voir [Création d’un flux de données](/help/components/exports/cja-data-feeds/create-feed.md).

