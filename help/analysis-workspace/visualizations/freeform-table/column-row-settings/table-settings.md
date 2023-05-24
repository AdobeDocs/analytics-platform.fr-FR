---
description: Les configurations des lignes varient selon le composant déposé dans le tableau.
title: Paramètres des lignes
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 93%

---

# Paramètres des lignes

Regardez une vidéo sur les paramètres des lignes et des colonnes ici :

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

Les configurations des lignes varient selon le composant déposé dans le tableau. Pour accéder aux paramètres de ligne dʼun tableau, cliquez sur lʼicône [!UICONTROL Paramètres] en regard dʼune dimension, dʼun filtre, dʼune mesure, dʼune période ou dʼune répartition :

![](assets/row-settings.png)

| Paramètre | Description |
| --- | --- |
| Alignement des dates | Il s’agit d’un paramètre au niveau du tableau qui aligne les dates de chaque colonne afin qu’elles commencent toutes à partir de la même ligne. L’alignement des dates est activé par défaut lorsqu’une dimension temporelle est utilisée dans les lignes du tableau et que différentes périodes sont appliquées dans les colonnes. Par exemple, dans un tableau quotidien auquel les colonnes d’octobre et de septembre sont appliquées, la colonne de gauche commence au 1er octobre et la colonne de droite au 1er septembre. |
| Répartition par position | Par défaut, ce paramètre est désactivé et les répartitions sont fixées aux éléments de la ligne statique. Par exemple, imaginons que vous répartissiez les éléments de dimension des 3 premières pages (page d’accueil, résultats de recherche et passage en caisse) par canal marketing. Ensuite, vous quittez le projet et revenez deux semaines plus tard. Lors de la réouverture du projet, les 3 premières pages ont changé. Désormais, la page d’accueil, les résultats de recherche et le passage en caisse figurent sur les 4 à 6 premières pages. Par défaut, les répartitions des canaux marketing apparaîtront toujours sous la page d’accueil, les résultats de recherche et le passage en caisse, même si elles se trouvent maintenant dans les lignes 4 à 6. <br>En revanche, la **répartition par position** répartit toujours les 3 premiers éléments, quelle que soit leur nature. Pour revenir à notre exemple, lorsque vous rouvrez votre projet, les répartitions des canaux marketing sont liées aux 3 premières pages du tableau, et non à la page d’accueil, aux résultats de recherche et au passage en caisse qui se trouvent maintenant dans les lignes 4 à 6. |
| Pourcentages | **Calculer les pourcentages par colonne** est le paramètre par défaut. Les pourcentages visibles dans une colonne sont calculés en fonction du total de la colonne. <br>**Calcul des pourcentages par ligne** oblige le tableau à structure libre à calculer les pourcentages des cellules par ligne, et non pas par colonne, avec le total général comme dénominateur. Cette fonctionnalité est particulièrement utile pour les pourcentages de tendance. Ce paramètre est activé par défaut lors de l’utilisation de l’icône Visualiser. |
| Totaux des colonnes | Ces paramètres sont uniquement disponibles pour les lignes [statiques](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Afficher comme somme des lignes actuelles** affiche une somme des lignes du tableau côté client, ce qui signifie que le total *not* dédupliquez les mesures telles que les visites ou les personnes. <br> **Afficher le total général** indique une somme côté serveur, ce qui signifie que le total dédupliquera les mesures. |

## Modification du nombre de lignes

Pour modifier le nombre de lignes affichées, procédez comme suit :

1. Cliquez sur le nombre en regard de [!UICONTROL Lignes] en haut du tableau.

   ![](assets/row-number.png)

1. Dans la liste déroulante, sélectionnez le nombre de lignes à afficher dans le tableau.