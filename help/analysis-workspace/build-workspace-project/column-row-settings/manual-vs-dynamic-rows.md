---
description: Comment interagir avec des lignes statiques dans des tableaux.
title: Lignes statiques et dynamiques
uuid: caf033ef-d252-4f8a-802e-7edbbac5c8c0
translation-type: tm+mt
source-git-commit: 05bc0b378c962f4513ab292d518e32f5f70f7dfd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 91%

---


# Lignes statiques et dynamiques

>[!NOTE] Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

Quand vous faites glisser une dimension sur un tableau d’Analysis Workspace, des lignes « dynamiques » sont générées, ce qui signifie que tous les éléments qui correspondent à la dimension, pour une mesure donnée, sont reportés dans le tableau.

Par exemple, si vous faites glisser la dimension Navigateur dans le tableau, tous les éléments de dimension (navigateur Android, Safari mobile, Firefox, etc.) sont reportés dans le tableau de manière dynamique.

En comparaison, chaque fois que vous sélectionnez et faites glisser manuellement une mesure, un segment, une classe de données ou une dimension individuelle dans un tableau, il en résulte une ligne ou une liste codée en dur ou « statique ». Vous pouvez maintenant interagir sur une ligne statique de différentes façons :

* Cliquez sur l’icône Aperçu dans une ligne statique pour prévisualiser les segments, les mesures et les plages de dates.
* Cliquez sur l’icône X pour supprimer cette ligne du tableau.
* Limitez le nombre de lignes affichées et activez la pagination.
* Ajoutez des éléments de dimension mixtes. Par exemple, ajoutez un élément issu d’une dimension de navigateur et un autre élément issu d’une dimension de produit.

   En voici une illustration :

   ![](assets/static_rows.png)

En outre, (seulement) lorsque vous êtes en mode de ligne statique, vous pouvez maintenant changer le mode de calcul du nombre total de colonnes. Il vous suffit de cliquer sur l’icône d’engrenage et de permuter entre ces deux options :

![](assets/column-totals.png)

| Option | Description |
|---|---|
| (Par défaut) Calculer les totaux en totalisant les valeurs actuellement dans chaque colonne. | Cette option calcule seulement les lignes figurant actuellement dans le tableau. (Calcul côté client) |
| Calculez les totaux d’après toutes les lignes pour chaque mesure. | Cette option comprend tous les éléments de cette dimension, même ceux qui ne sont pas répertoriés dans le tableau. (Calcul côté serveur) |

