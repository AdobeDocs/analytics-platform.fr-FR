---
title: Affichage des annotations
description: Comment afficher les annotations dans l’espace de travail.
role: User
feature: Components
exl-id: c0e4fb37-b20c-463c-b29a-310ca3adb2c7
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 86%

---

# Affichage des annotations

Les annotations se présentent de manière légèrement différente, selon qu’elles s’étendent sur un seul jour ou sur une période.

## Affichage des annotations dans les graphiques linéaires ou les tableaux

| Date | Apparence |
| --- | --- |
| **Un seul jour** | ![Visualisation en graphique linéaire avec annotation mise en surbrillance](assets/single-day.png)<p>Lorsque vous pointez sur l’annotation, des options permettant dʼafficher les détails, de la modifier (via lʼicône de stylo) ou de la supprimer apparaissent :<p> ![Détails des annotations avec la possibilité de modifier ou de supprimer l’annotation.](assets/hover.png) |
| **Période** | L’icône change et lorsque vous pointez dessus, la période s’affiche.<p>![Icône d’annotation de période](assets/multi-day.png)<p>Lorsque vous la sélectionnez dans le graphique linéaire, les métadonnées de l’annotation apparaissent et vous pouvez les modifier ou les supprimer :![](assets/multi-hover.png)<p>Dans un tableau, une icône s’affiche pour chaque date de la période.<p>![](assets/multi-day-table.png) |
| **Annotations qui se chevauchent** | Les jours auxquels plusieurs annotations sont liées comportent une icône de couleur grise.<p>![Détails des annotations qui se chevauchent  ](assets/grey.png)<p>Lorsque vous pointez sur l’icône grise, toutes les annotations qui se chevauchent s’affichent :<p>![](assets/overlap.png) |

{style="table-layout:auto"}

## Affichage des annotations dans un fichier .pdf

Puisque vous ne pouvez pas pointer sur les icônes dans un fichier .pdf, ce fichier (après l’exportation) fournit des notes d’explication au bas d’un panneau. Voici un exemple :

![Affichage en surbrillance d’un fichier .pdf contenant des explications sur les annotations.](assets/ann-pdf.png)

## Afficher les annotations avec des données qui ne représentent pas de tendance

Parfois, les annotations s’affichent avec des données qui ne représentent pas de tendances, mais qui sont liées à une dimension spécifique. Ces annotations sont affichées sous la forme dʼune annotation sommaire, dans le coin inférieur droit. Voici un exemple :

![](assets/non-date.png)

Le graphique de synthèse s’affiche dans tous les types de visualisation dans le coin, et pas seulement dans les tableaux à structure libre et les nombres de synthèse ne représentant pas de tendance. Il apparaît également dans les visualisations telles que [!UICONTROL Anneau], [!UICONTROL Flux], [!UICONTROL Abandon], [!UICONTROL Cohorte], etc.

![Graphique synthétique dans les visualisations](assets/ann-summary.png)
