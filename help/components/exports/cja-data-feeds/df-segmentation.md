---
title: Segmentation dans les flux de données Customer Journey Analytics
description: Découvrez comment appliquer des segments aux flux de données Customer Journey Analytics et comment les segments de période interagissent avec la fenêtre de création de rapports du flux.
keywords: parcours de navigation;flux de données;flux de données;segmentation;segments;période
feature: Components
hide: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: f36723dab5500f728dd9ec267d97305aff604149
workflow-type: tm+mt
source-wordcount: 659
ht-degree: 2%

---


# Segmentation dans les flux de données

{{release-limited-testing}}

Les flux de données de Customer Journey Analytics prennent en charge la segmentation, ce qui vous permet de filtrer les lignes incluses dans chaque diffusion de flux. Vous pouvez appliquer des segments au niveau de la vue de données, du flux ou des deux.

## Où les segments sont appliqués

Vous pouvez appliquer des segments à un flux de données à deux endroits :

- **Vue de données** : segment configuré dans la vue de données qui s’applique à tous les flux utilisant cette vue de données.
- **Flux de données** : segment appliqué directement à un flux individuel, en plus de tout segment de vue de données.

Lorsque les deux sont configurés, Customer Journey Analytics les combine. Seules les lignes qui répondent aux deux segments sont incluses dans la sortie de flux.

## Segments de période

Les segments qui référencent des périodes sont pris en charge dans les flux de données. Cependant, le comportement diffère d’Analysis Workspace sur un point important : **les conditions de période dans un segment ne remplacent pas la période de création des rapports du flux.**

Dans Analysis Workspace, l’application d’un segment de période modifie la fenêtre de création de rapports active pour correspondre à la période du segment. Dans les flux de données, la fenêtre de création de rapports est toujours définie par la diffusion planifiée du flux (horaire ou quotidienne). Un segment avec une condition de période filtre les lignes dans cette fenêtre ; il ne déplace ni ne développe la fenêtre elle-même.

Cette conception est intentionnelle. Si les segments de période remplacent la fenêtre de création de rapports, un flux horaire peut fournir une fenêtre de données beaucoup plus grande que prévu, ce qui entraîne une duplication des données ou un volume de sortie excessif.

### Exemples

**Exemple 1 — Segment qui inclut des événements à partir d’une date spécifique**

Supposons que vous appliquiez un segment qui renvoie uniquement les événements du 1er juillet et que vous exécutiez le flux pour le 22 juillet :

- La fenêtre de diffusion des flux reste le 22 juillet.
- Le segment filtre toutes les lignes, car aucun événement de la fenêtre du 22 juillet ne correspond aux critères du 1er juillet. Le flux s’exécute mais ne diffuse aucune ligne.
- Si vous exécutez un renvoi pour le 1er juillet, le segment se comporte comme prévu : seuls les événements correspondant aux critères du 1er juillet sont inclus.

**Exemple 2 : segment qui exclut les événements d’une date spécifique**

Supposons que vous appliquiez un segment qui exclut tous les événements avec une commande le 1er juillet et que vous exécutiez le flux pour le 22 juillet :

- Le segment s’applique aux données du 22 juillet. Comme il n’existe aucun événement du 1er juillet dans la fenêtre du 22 juillet, rien n’est exclu et toutes les lignes sont diffusées.
- Si vous exécutez un renvoi pour le 1er juillet, le segment exclut les lignes pertinentes comme prévu.

## Segments avec plusieurs conditions

Pour les segments qui combinent des conditions de période avec d’autres critères, Customer Journey Analytics évalue la partie de période sous la forme d’un filtre de ligne uniquement et non d’un remplacement de fenêtre de création de rapports. Toutes les conditions du segment sont respectées dans la fenêtre de diffusion du flux.

## Qualification du segment et période de recherche en amont

Pour les segments qui utilisent un conteneur Personne ou Session , la qualification est déterminée par le paramètre **Période de recherche en amont** et pas seulement par la fenêtre de diffusion. Si une personne répond aux critères de la période de recherche arrière, tous les événements de cette personne dans la fenêtre de diffusion sont inclus. Le paramètre de conteneur détermine la portée :

- **Conteneur d’événements** : seuls les événements correspondant aux critères de segment dans la fenêtre de diffusion sont inclus.
- **Conteneur de sessions** : tous les événements des sessions de qualification dans la fenêtre de diffusion sont inclus, où la qualification de la session est évaluée sur la période de recherche en amont.
- **Conteneur de personnes** : tous les événements de la fenêtre de diffusion sont inclus pour toute personne qualifiée pendant la période de recherche en amont.

Pour plus d’informations sur la période de recherche en amont et son impact sur la qualification des segments, voir [Création d’un flux de données](/help/components/exports/cja-data-feeds/create-feed.md).

## Comparaison avec Analysis Workspace

| Comportement | Analysis Workspace | Flux de données |
|---|---|---|
| Fenêtre de rapport de remplacement du segment de période | Oui | Non |
| Filtre de segments sur les lignes dans la fenêtre de rapport | Oui | Oui |
| Application du segment de la vue de données | Oui | Oui |
| Segment additionnel appliqué directement à la diffusion | Non | Oui |

{style="table-layout:auto"}
