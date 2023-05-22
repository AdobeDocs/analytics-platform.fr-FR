---
description: Un histogramme est semblable à un graphique à barres, à ceci près qu’il regroupe les chiffres par classes (intervalles).
title: Histogramme
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 95%

---

# Histogramme

Un histogramme est semblable à un graphique à barres, à ceci près qu’il répartit les chiffres en classes (intervalles). Analytics automatise la classification des chiffres. Vous pouvez toutefois modifier les paramètres dans les [Paramètres avancés](#section_09D774C584864D4CA6B5672DC2927477).

## Création d’un histogramme {#section_74647707CC984A1CB6D3097F43A30B45}

Pour créer un histogramme, procédez comme suit :

1. Cliquez sur **[!UICONTROL Visualisations]** dans le rail de gauche.
1. Faites glisser **[!UICONTROL Histogramme]** sur le panneau.
1. Faites glisser une mesure sur la visualisation Histogramme, puis cliquez sur **[!UICONTROL Créer]**.

![](assets/histogram.png)

>[!NOTE]
>
>Les histogrammes prennent seulement en charge les mesures standard, et non les mesures calculées.

Ici, nous avons utilisé la mesure Pages vues par visiteurs uniques. La première classe (à gauche) correspond à une page vue par visiteur unique, la deuxième à deux pages vues, etc.

![](assets/histogram2.png)

## Paramètres avancés {#section_09D774C584864D4CA6B5672DC2927477}

Pour régler les paramètres de l’histogramme, cliquez sur l’icône d’engrenage Paramètres dans le coin supérieur droit. Voici les paramètres que vous pouvez modifier :

| Paramètres de l’histogramme | Description |
|---|---|
| Intervalle de début | Détermine par quel intervalle commence l’histogramme. « 1 » par défaut. Peut être défini sur 0 à l’infini (aucun nombre négatif). |
| Intervalles de mesures | Permet d’augmenter ou de réduire le nombre de classes de données (intervalles). Il ne peut pas y avoir plus de 50 intervalles. |
| Taille de l’intervalle de mesures | Permet de définir la taille de chaque intervalle. Vous pouvez par exemple modifier la taille de l’intervalle d’une page vue à deux pages vues. |
| Méthode de comptage | Permet de choisir parmi [Visiteur](https://experienceleague.adobe.com/docs/analytics/components/metrics/unique-visitors.html?lang=fr), [Visite](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=fr) ou Type d’accès. Par exemple, pages vues par visite ou pages vues par visiteur ou pages vues par événement. Pour l’accès, la mesure « Occurrences » est utilisée comme mesure de l’axe Y dans un tableau à structure libre. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exemples** :

* Intervalle de début : 1 ; Intervalles de mesures : 5 ; Taille de l’intervalle de mesures : 2 générera cet histogramme : 1-2, 3-4, 5-6, 7-8, 9-10.
* Intervalle de début : 0 ; Intervalles de mesures : 3 ; Taille de l’intervalle de mesures : 5 générera cet histogramme : 0-4, 5-9, 10-14.

## Affichage et modification des données de l’histogramme {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

Pour afficher ou modifier la source de données de l’histogramme, cliquez sur le point en regard de l’en-tête Histogramme pour accéder à **[!UICONTROL Paramètres de source de données]** > **[!UICONTROL Afficher la source de données]**.

![](assets/manage-data-source.png)

Les filtres prédéfinis du tableau sont des filtres internes ; ils n’apparaîtront pas dans le sélecteur de filtres. Cliquez sur l’icône « i » en regard du nom du filtre, puis, pour le rendre public, cliquez sur **[!UICONTROL Rendre public]**.

![](assets/prebuilt_segments.png)

Pour découvrir d’autres façons de générer des tableaux de données à structure libre et d’autres visualisations (répartitions de données, par exemple), cliquez [ici](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=fr).
