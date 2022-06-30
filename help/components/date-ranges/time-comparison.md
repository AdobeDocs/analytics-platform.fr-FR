---
description: 'Dans Analysis Workspace, appliquez une comparaison des dates commune à partir de n’importe quelle colonne contenant une période, par exemple : année par année, trimestre par trimestre, mois par mois, etc.'
title: Comparaison des dates
feature: Calendar
exl-id: 08113536-658f-486b-ac56-6c531240c3c2
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: ht
source-wordcount: '638'
ht-degree: 100%

---

# Comparaison des dates

Dans Analysis Workspace, appliquez une comparaison des dates commune à partir de n’importe quelle colonne contenant une période, par exemple : année par année, trimestre par trimestre, mois par mois, etc.

## Comparaison de périodes

Une analyse ne peut pas avoir lieu sans contexte. Il arrive souvent que ce contexte découle d’une période précédente. Par exemple, la question « Où nous situons-nous par rapport à la même date l’an dernier ? Mieux ou pire ? » est essentielle pour bien comprendre vos activités. La comparaison des dates inclut automatiquement une colonne « différence », qui présente le pourcentage de changement par rapport à une période donnée.

1. Créez un tableau à structure libre, avec les dimensions et mesures à comparer sur une certaine période.
1. Cliquez avec le bouton droit de la souris dans une ligne de tableau, puis sélectionnez **[!UICONTROL Comparer des périodes]**.

   ![](assets/compare-time.png)

   >[!IMPORTANT]
   >
   >Cette option contextuelle est désactivée pour les lignes de mesures, de périodes et de dimension temporelle.

1. Selon la façon dont sont définies les périodes du tableau, les options de comparaison suivantes sont disponibles :

   | Option | Description |
   |---|---|
   | **[!UICONTROL Semaine/Mois/Trimestre/Année précédent(e) à cette période]** | Compare les données à la semaine/au mois/etc. précédant immédiatement cette plage de dates. |
   | **[!UICONTROL Cette semaine/ce mois/ce trimestre/cette année l’an dernier]** | Compare les données à la même période il y a un an. |
   | **[!UICONTROL Sélectionner une plage]** | Permet de sélectionner une période personnalisée. |

   >[!NOTE]
   >
   >Lorsque vous sélectionnez un nombre de jours personnalisé (par exemple, du 7 au 20 octobre, soit 14 jours), seules deux options sont proposées : **[!UICONTROL 14 jours précédant cette période]** et **[!UICONTROL Sélectionner une plage]**.

1. La comparaison qui en résulte ressemble à ceci :

   ![](assets/compare-time-result.png)

   Les lignes dans la colonne Pourcentage de changement sont en rouge pour les valeurs négatives et en vert pour les valeurs positives.

1. (Facultatif) Comme dans n’importe quel autre projet Analysis Workspace, vous pouvez créer des visualisations en fonction de ces comparaisons temporelles. Voici par exemple un graphique en barres :

   ![](assets/compare-time-barchart.png)

   Pour afficher le pourcentage de changement dans ce graphique à barres, le paramètre [!UICONTROL Pourcentages] doit être activé dans les [!UICONTROL Paramètres de visualisation].

## Ajout d’une colonne de période à la comparaison

Vous pouvez désormais ajouter une période à chaque colonne d’un tableau, ce qui permet d’ajouter une période différente de celle configurée pour votre calendrier. Cette fonctionnalité offre un autre moyen de comparer les dates.

1. Cliquez avec le bouton droit de la souris dans le tableau, puis sélectionnez **[!UICONTROL Ajouter une colonne de périodes]** ![](assets/add-time-period-column.png).

1. Selon la façon dont sont définies les périodes du tableau, les options de comparaison suivantes sont disponibles :

   | Option | Description |
   |---|---|
   | **[!UICONTROL Semaine/Mois/Trimestre/Année précédent(e) à cette période]** | Ajoute une colonne avec la semaine/le mois/etc. précédant immédiatement cette plage de dates. |
   | **[!UICONTROL Cette semaine/ce mois/ce trimestre/cette année l’an dernier]** | Ajoute la même période il y a un an. |
   | **[!UICONTROL Sélectionner une plage]** | Permet de sélectionner une période personnalisée. |

   >[!NOTE]
   >
   >Lorsque vous sélectionnez un nombre de jours personnalisé (par exemple, du 7 au 20 octobre, soit 14 jours), seules deux options sont proposées : **[!UICONTROL 14 jours précédant cette période]** et **[!UICONTROL Sélectionner une plage]**.

1. La période sera insérée en haut de la colonne sélectionnée :

   ![](assets/add-time-period-column2.png)

1. Vous pouvez ajouter autant de colonnes que vous le souhaitez, et mélanger et associer différentes périodes :

   ![](assets/add-time-period-column4.png)

1. Vous pouvez également trier chaque colonne, ce qui change l’ordre des jours selon la colonne utilisée pour le tri.

## Harmonisation des dates de colonnes pour qu’elles commencent sur la même ligne {#section_5085E200082048CB899C3F355062A733}

Un nouveau paramètre disponible pour tous les tableaux permet d’**[!UICONTROL Aligner les dates de chaque colonne afin qu’elles commencent toutes sur la même ligne (s’applique à l’ensemble du tableau)]**. « S’applique à l’ensemble du tableau » signifie que si, par exemple, vous définissez ce paramètre pour la ventilation des données d’un tableau, il s’applique également au reste du tableau.

![](assets/date-comparison-setting.png)

>[!IMPORTANT]
>
>Ce paramètre est **désactivé** (décoché) pour tous les projets existants et **activé** (coché) pour tous les nouveaux projets.

Exemple : si vous harmonisez les dates dans le cadre d’une comparaison d’un mois à l’autre entre octobre et septembre 2016, la colonne de gauche commence au 1er octobre et la colonne de droite au 1er septembre :

![](assets/add-time-period-column3.png)

<!-- 

<p>See Jonny Moon's email from November 3. </p>

 -->
