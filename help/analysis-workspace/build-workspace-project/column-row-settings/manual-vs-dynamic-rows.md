---
title: Valeurs de dimension dynamiques ou statiques
description: Comment interagir avec des valeurs de dimension dynamiques et statiques dans des tableaux.
translation-type: tm+mt
source-git-commit: 0477302df92ccab30d9f3a45cc7b22f2112a0c70
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 9%

---


# Valeurs de dimension dynamique ou statique dans les tableaux à structure libre

>[!NOTE] Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

Dans les tableaux à structure libre, les rangées et les colonnes peuvent contenir diverses valeurs de composant. Ces valeurs peuvent être dynamiques (changer avec le temps) ou statiques (ne pas changer avec le temps), selon l’analyse que vous souhaitez construire.

## Valeurs de dimension dynamiques

Les valeurs de dimension dynamique changent avec le temps et dépendent de la mesure triée par dans le tableau à structure libre. Les valeurs de dimension dynamique sont préférées lorsque vous souhaitez analyser les principaux éléments pour une période donnée.

Lorsque vous déposez une dimension dans un tableau à structure libre, des lignes dynamiques sont renvoyées. Ils représentent les principaux éléments qui correspondent à la dimension pour une mesure et une période données. Vous pouvez également déposer une dimension dans des colonnes de tableau à structure libre et la dimension se développe automatiquement dans les 5 premières valeurs de dimension.

Par exemple, lorsque vous faites glisser la dimension Type de navigateur dans le tableau, les principales valeurs de dimension Type de navigateur (par exemple Microsoft, Apple, Google, etc.) revient dynamiquement aux rangées du tableau. Si vous les insérez dans une colonne, les 5 premières valeurs de dimension Type de navigateur renvoient dynamiquement.

Les valeurs de dimension dynamique disposent de l’option de filtre de ligne et n’ont **pas** d’icône de verrouillage et de X.

## Valeurs de dimension statique

Les valeurs de dimension statique ne changent pas avec le temps ; il s’agit de composants fixes qui sont toujours renvoyés dans un tableau à structure libre. Les valeurs de dimension statique sont préférées lorsque vous souhaitez toujours analyser le même élément, qu’il s’agisse de campagnes spécifiques ou de jours spécifiques dans la semaine.

Chaque fois que vous sélectionnez et déposez manuellement des valeurs de composant spécifiques (dimension, mesure, segment, plage de dates) dans un tableau, le résultat est une liste statique de lignes ou de colonnes. Vous pouvez également créer des valeurs de dimension statique si vous choisissez :

* Dans les lignes, cliquez avec le bouton droit de la souris > [!UICONTROL Afficher uniquement les lignes sélectionnées.]
* Dans les colonnes, cliquez avec le bouton droit de la souris > [!UICONTROL Rendre l’élément statique]

Par exemple, lorsque vous faites glisser des éléments de type navigateur spécifiques tels que Microsoft et Apple, ces deux éléments spécifiques sont toujours extraits dans le tableau.

Les valeurs de dimension statique **ne disposent pas** de l’option de filtre de ligne. A la place, des icônes de verrouillage et X sont présentes sur chaque élément. Cliquez sur l’icône X pour supprimer cette valeur de dimension du tableau.

## Valeurs de dimension mixtes

Les valeurs de dimension de différentes dimensions peuvent être ajoutées à la même table. Dans ces cas, l’en-tête de ligne indique &quot;Dimensions mixtes&quot;. Ces valeurs de dimension sont statiques. Par exemple, l’ajout de valeurs de dimension spécifiques de la dimension Type de navigateur et d’autres valeurs de dimension de la dimension Navigateur.

## Lignes totales de forme libre

Les lignes dynamiques et statiques se comportent différemment dans la ligne de total à structure libre. Par défaut:

* Les lignes dynamiques sont additionnées de mesures côté serveur et de duplicata, telles que les visites ou les visiteurs.
* Les lignes statiques sont additionnées côté client et **ne déduisent pas** les mesures de duplicata.

[En savoir plus sur les options totales](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html) de Workspace pour les lignes dynamiques et statiques.
