---
title: Éléments De Dimension Dynamiques Et Statiques
description: Découvrez comment utiliser des éléments de dimension dynamiques ou statiques dans les tableaux à structure libre d’Analysis Workspace.
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
role: User
TQID: https://experienceleague.adobe.com/q9X-MNr4r3Xrs16gAgH6-F3yrRDJP73xfXdd8BcFg84
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 549
ht-degree: 77%

---

# Éléments de dimension dynamiques et statiques

Dans les tableaux à structure libre, les lignes et les colonnes peuvent contenir différentes valeurs de composant. Ces valeurs peuvent être dynamiques (changent avec le temps) ou statiques (ne changent pas avec le temps), selon l’analyse que vous souhaitez créer.

## Éléments de dimension dynamiques

Les éléments de dimension dynamiques changent avec le temps et dépendent de la mesure de tri dans le tableau à structure libre. Les éléments de dimension dynamiques sont recommandés lorsque vous souhaitez analyser les éléments principaux d’une période donnée.

Lorsque vous déposez une dimension dans un tableau à structure libre, des lignes dynamiques sont renvoyées. Elles représentent les éléments principaux qui correspondent à la dimension pour une mesure et une période données. Vous pouvez également déposer une dimension dans des colonnes de tableau à structure libre et la dimension se développe automatiquement dans les 5 premiers éléments de dimension.

Par exemple, lorsque vous faites glisser la dimension Type de navigateur dans le tableau, les principaux éléments de dimension Type de navigateur (par exemple, Microsoft, Apple, Google, etc.) revenir dynamiquement aux lignes du tableau. Si vous les déposez dans une colonne, les 5 premiers éléments de la dimension Type de navigateur sont dynamiquement renvoyés.

Les éléments de dimension dynamiques comportent l’option de filtre de ligne ![Filtrer](/help/assets/icons/Filter.svg) et un ![Fermer](/help/assets/icons/Close.svg), et ne comportent **pas** de verrou ![LockClosed](/help/assets/icons/LockClosed.svg). <!--do they have the lock icon? --> Lorsque vous cliquez sur ![Fermer](/help/assets/icons/Close.svg) en regard d’un élément de dimension dynamique, un filtre est automatiquement appliqué. Pour plus d’informations sur l’application de filtres aux tableaux, voir [Filtrer et trier des tableaux](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![Tableau à structure libre mettant en surbrillance l’icône de filtre.](assets/dynamic-items.png)

## Éléments de dimension statiques

Les éléments de dimension statiques ne changent pas avec le temps. Il s’agit de composants fixes toujours renvoyés dans un tableau à structure libre. Les éléments de dimension statiques sont recommandés lorsque vous souhaitez toujours analyser le même élément, qu’il s’agisse de campagnes spécifiques ou de jours précis de la semaine.

Chaque fois que vous sélectionnez et déposez manuellement des valeurs de composant spécifiques (dimension, mesure, segment, période) dans un tableau, le résultat est une liste statique de lignes ou de colonnes.

Par exemple, lorsque vous faites glisser des éléments Type de navigateur spécifiques tels que Microsoft et Apple, ces deux éléments spécifiques sont toujours extraits dans le tableau.

Les éléments de dimension statiques peuvent également être créés si vous choisissez de sélectionner **[!UICONTROL Afficher uniquement les lignes sélectionnées]** dans le menu contextuel des lignes sélectionnées.

Les éléments de dimension statiques **ne disposent pas** de l’option de filtre de ligne. Au lieu de cela, des éléments ![LockClosed](/help/assets/icons/LockClosed.svg) et ![Fermer](/help/assets/icons/Close.svg) sont présents sur chaque élément. Sélectionnez ![Fermer](/help/assets/icons/Close.svg) pour supprimer cet élément de dimension du tableau.

![Tableau à structure libre présentant le type de navigateur et la ligne Microsoft avec une icône de verrouillage. Remarque : cet élément de dimension est statique et ne change pas avec le temps.](assets/static-items.png)

## Éléments de dimension mixtes

Vous pouvez ajouter des éléments de dimension de différentes dimensions au même tableau. Dans ces cas, l’en-tête de ligne indique **[!UICONTROL Dimensions mixtes]**. Ces éléments de dimension sont statiques. Par exemple, l’ajout d’éléments de dimension spécifiques de la dimension du groupe Navigateur et d’autres éléments de dimension de la dimension du nom Navigateur.

![Tableau à structure libre mettant en surbrillance la colonne Dimensions mixtes.](assets/mixed-dimensions.png)

## Lignes totales à structure libre

Les lignes dynamiques et statiques se comportent différemment dans la ligne de total à structure libre. Par défaut :

* Les lignes dynamiques sont additionnées côté serveur et dédupliquent les mesures, telles que les visites ou les personnes.
* Les lignes statiques sont additionnées côté client et ne dédupliquent **pas** les mesures. Pour calculer la ligne de total côté serveur, définissez le paramètre des lignes sur **Afficher le total général**. [En savoir plus](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)
