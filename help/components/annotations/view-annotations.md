---
title: Affichage des annotations
description: Comment afficher les annotations dans l’espace de travail.
role: User, Admin
feature: Components
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
source-git-commit: 998cc9e5f8d2ffd3964078dc389f55bb573063b9
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 43%

---

# Affichage des annotations

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de tests limités.

Les annotations se présentent de manière légèrement différente, selon qu’elles s’étendent sur un seul jour ou sur une période.

## Affichage des annotations dans les graphiques linéaires ou les tableaux

| Date | Apparence |
| --- | --- |
| **Un seul jour** | ![](assets/single-day.png)<p>Lorsque vous placez le pointeur de la souris sur l’annotation, vous pouvez en afficher les détails, la modifier en sélectionnant l’icône de stylo ou la supprimer :<p> ![](assets/hover.png) |
| **Période** | L’icône change et lorsque vous pointez dessus, la période s’affiche.<p>![](assets/multi-day.png)<p>Lorsque vous la sélectionnez dans le graphique en courbes, les métadonnées d’annotation s’affichent et vous pouvez les modifier ou les supprimer :![](assets/multi-hover.png)<p>Dans un tableau, une icône s’affiche pour chaque date de la période.<p>![](assets/multi-day-table.png) |
| **Chevauchement des annotations** | Les jours auxquels plusieurs annotations sont liées, l’icône s’affiche en gris.<p>![](assets/grey.png)<p>Lorsque vous passez la souris sur l’icône grise, toutes les annotations qui se chevauchent s’affichent :<p>![](assets/overlap.png) |

## Affichage des annotations dans un fichier .pdf

Puisque vous ne pouvez pas pointer sur les icônes dans un fichier .pdf, ce fichier (après l’exportation) fournit des notes d’explication au bas d’un panneau. Voici un exemple :

![](assets/ann-pdf.png)

## Affichage des annotations avec des données non de tendance

Parfois, les annotations s’affichent avec des données qui ne correspondent pas à des tendances, mais qui sont liées à une dimension spécifique. Dans ce cas, elles apparaissent uniquement dans une annotation récapitulative dans le coin inférieur droit. Voici un exemple :

![](assets/non-date.png)

Le graphique de synthèse s’affiche dans tous les types de visualisation dans le coin, et pas seulement dans les tableaux à structure libre et les nombres de synthèse de tendances. Il apparaît également dans les visualisations telles que [!UICONTROL Anneau], [!UICONTROL Flux],[!UICONTROL Abandon],[!UICONTROL Cohorte], etc.

![](assets/ann-summary.png)