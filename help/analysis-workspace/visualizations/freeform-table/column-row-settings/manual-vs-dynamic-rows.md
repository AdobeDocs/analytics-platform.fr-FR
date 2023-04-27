---
title: Éléments de dimension dynamiques ou statiques dans les tableaux à structure libre
description: Interaction avec des éléments de dimension dynamiques et statiques dans des tableaux
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
source-git-commit: 67435cdfcb23e3c6e9a04ecb4a0b0e854473387c
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 97%

---

# Éléments de dimension dynamiques ou statiques dans les tableaux à structure libre

Dans les tableaux à structure libre, les lignes et les colonnes peuvent contenir diverses valeurs de composant. Ces valeurs peuvent être dynamiques (changent avec le temps) ou statiques (ne changent pas avec le temps), selon l’analyse que vous souhaitez créer.

## Éléments de dimension dynamiques

Les éléments de dimension dynamiques changent avec le temps et dépendent de la mesure de tri dans le tableau à structure libre. Les éléments de dimension dynamiques sont recommandés lorsque vous souhaitez analyser les éléments principaux d’une période donnée.

Lorsque vous déposez une dimension dans un tableau à structure libre, des lignes dynamiques sont renvoyées. Elles représentent les éléments principaux qui correspondent à la dimension pour une mesure et une période données. Vous pouvez également déposer une dimension dans des colonnes de tableau à structure libre et la dimension se développe automatiquement dans les 5 premiers éléments de dimension.

Par exemple, lorsque vous faites glisser la dimension Type de navigateur dans le tableau, les premiers éléments de dimension Type de navigateur (par exemple, Microsoft, Apple, Google, etc.) sont dynamiquement renvoyés aux lignes du tableau. Si vous les déposez dans une colonne, les 5 premiers éléments de dimension Type de navigateur sont dynamiquement renvoyés.

Les éléments de dimension dynamiques disposent de l’option de filtre de ligne, mais ne disposent **pas** de l’icône en forme de verrou et de l’icône X. Pour plus d’informations sur l’application de filtres aux tableaux, voir [Filtrage et tri des tableaux](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![](assets/dynamic-items.png)

## Éléments de dimension statiques

Les éléments de dimension statiques ne changent pas avec le temps. Il s’agit de composants fixes toujours renvoyés dans un tableau à structure libre. Les éléments de dimension statiques sont recommandés lorsque vous souhaitez toujours analyser le même élément, qu’il s’agisse de campagnes spécifiques ou de jours précis de la semaine.

Chaque fois que vous sélectionnez et déposez manuellement des valeurs de composant spécifiques (dimension, mesure, filtre, période) dans un tableau, le résultat se présente sous la forme dʼune liste statique de lignes ou de colonnes. Vous pouvez également créer des éléments de dimension statiques si vous le souhaitez, en procédant comme suit :

* Dans les lignes, cliquez avec le bouton droit de la souris sur > [!UICONTROL Afficher uniquement les lignes sélectionnées]
* Dans les colonnes, cliquez avec le bouton droit de la souris sur [!UICONTROL Rendre l’élément statique]

Par exemple, lorsque vous faites glisser des éléments Type de navigateur spécifiques tels que Microsoft et Apple, ces deux éléments spécifiques sont toujours extraits dans le tableau.

Les éléments de dimension statiques ne disposent **pas** de l’option de filtre de ligne. En revanche, chaque élément comporte l’icône en forme de verrou et l’icône X. Cliquez sur l’icône X pour supprimer cet élément de dimension du tableau.

![](assets/static-items.png)

## Éléments de dimension mixtes

Vous pouvez ajouter des éléments de dimension de différentes dimensions au même tableau. Dans ces cas, l’en-tête de ligne indique « Dimensions mixtes ». Ces éléments de dimension sont statiques. Par exemple, l’ajout d’éléments de dimension spécifiques de la dimension Type de navigateur et d’autres éléments de dimension de la dimension Navigateur.

![](assets/mixed-dimensions.png)

## Lignes totales à structure libre

Les lignes dynamiques et statiques se comportent différemment dans la ligne de total à structure libre. Par défaut :

* Les lignes dynamiques sont additionnées côté serveur et dédupliquent les mesures, telles que les visites ou les visiteurs.
* Les lignes statiques sont additionnées côté client et ne dédupliquent **pas** les mesures. Pour calculer la ligne de total côté serveur, définissez le paramètre des lignes sur **Afficher le total général**. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=fr)
