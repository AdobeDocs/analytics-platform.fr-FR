---
title: Affichage des annotations
description: Comment afficher les annotations dans l’espace de travail.
role: User, Admin
feature: Components
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
source-git-commit: 7164c90fe50434a07db8154de173c3c7d8e5cb14
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Affichage des annotations

Les annotations se présentent de manière légèrement différente, selon qu’elles s’étendent sur un seul jour ou sur une période.

## Affichage des annotations dans les graphiques linéaires ou les tableaux

| Date | Apparence |
| --- | --- |
| **Un seul jour** | ![](assets/single-day.png)<p>Lorsque vous pointez sur l’annotation, des options permettant dʼafficher les détails, de la modifier (via lʼicône de stylo) ou de la supprimer apparaissent :<p> ![](assets/hover.png) |
| **Période** | L’icône change et lorsque vous pointez dessus, la période s’affiche.<p>![](assets/multi-day.png)<p>Lorsque vous la sélectionnez dans le graphique linéaire, les métadonnées de l’annotation apparaissent et vous pouvez les modifier ou les supprimer :![](assets/multi-hover.png)<p>Dans un tableau, une icône s’affiche pour chaque date de la période.<p>![](assets/multi-day-table.png) |
| **Annotations qui se chevauchent** | Les jours auxquels plusieurs annotations sont liées comportent une icône de couleur grise.<p>![](assets/grey.png)<p>Lorsque vous pointez sur l’icône grise, toutes les annotations qui se chevauchent s’affichent :<p>![](assets/overlap.png) |

{style=&quot;table-layout:auto&quot;}

## Affichage des annotations dans un fichier .pdf

Puisque vous ne pouvez pas pointer sur les icônes dans un fichier .pdf, ce fichier (après l’exportation) fournit des notes d’explication au bas d’un panneau. Voici un exemple :

![](assets/ann-pdf.png)

## Afficher les annotations avec des données qui ne représentent pas de tendance

Parfois, les annotations s’affichent avec des données qui ne représentent pas de tendances, mais qui sont liées à une dimension spécifique. Ces annotations sont affichées sous la forme dʼune annotation sommaire, dans le coin inférieur droit. Voici un exemple :

![](assets/non-date.png)

Le graphique de synthèse s’affiche dans tous les types de visualisation dans le coin, et pas seulement dans les tableaux à structure libre et les nombres de synthèse ne représentant pas de tendance. Il apparaît également dans les visualisations telles que [!UICONTROL Anneau], [!UICONTROL Flux], [!UICONTROL Abandon], [!UICONTROL Cohorte], etc.

![](assets/ann-summary.png)