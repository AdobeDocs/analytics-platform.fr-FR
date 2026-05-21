---
description: Découvrez comment utiliser la comparaison des dates dans Analysis Workspace, qui permet de prendre n’importe quelle colonne contenant une période et de créer une comparaison de dates commune.
title: Comparaison des dates
feature: Calendar
exl-id: 08113536-658f-486b-ac56-6c531240c3c2
role: User
TQID: https://experienceleague.adobe.com/LhPSvchJbDMPV-HmGSA2JaBZxoPQ7UyEKd7GMS-33UU
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: cb6c7d24-631f-46e5-9e39-3a2705f73962
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 770
ht-degree: 90%

---

# Comparaison des dates

Dans Analysis Workspace, la comparaison de dates vous permet de prendre n’importe quelle colonne contenant une période et de créer une comparaison de dates commune, par exemple : année par année, trimestre par trimestre, mois par mois, etc.

## Comparer des périodes

Une analyse ne peut pas avoir lieu sans contexte. Il arrive souvent que ce contexte découle d’une période précédente. Par exemple, la question *Dans quelle mesure votre situation s’est-elle améliorée ou détériorée par rapport à la même période l’an dernier ?* est essentiel à la compréhension de votre entreprise. La comparaison des dates inclut automatiquement une colonne *différence*, qui présente le pourcentage de changement par rapport à une période donnée.

1. Créez un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), avec les dimensions et mesures à comparer sur une certaine période.
1. Définissez la période sur le panneau ou la colonne pour déterminer la période de comparaison, et s’il s’agit d’une comparaison de temps fixe ou flottante.

   Pour créer une comparaison de temps flottante, définissez la période du panneau ou de la colonne sur une période flottante (par exemple, **[!UICONTROL 7 derniers jours]**, **[!UICONTROL 30 derniers jours]**, etc.).

   Pour créer une comparaison de temps fixe, définissez la période du panneau ou de la colonne sur une période personnalisée.

1. Ouvrez le menu contextuel d’une ligne de tableau et sélectionnez **[!UICONTROL Comparer des périodes]**.

   ![Ligne de tableau avec l’option Comparer des périodes sélectionnée](assets/compare-time.png)

   >[!NOTE]
   >
   >Cette option de menu contextuelle est désactivée pour les lignes de mesures, de périodes et de dimension temporelle.

1. Selon la façon dont sont définies les périodes du tableau, les options de comparaison suivantes sont disponibles :

   | Option | Description |
   |---|---|
   | **[!UICONTROL *x* semaines/mois/trimestres/années précédant cette période]** | Compare à la période sélectionnée immédiatement avant cette période. |
   | **[!UICONTROL Ces x semaines/mois/trimestres/années l’an dernier à cette période]** | Compare les données à la même période il y a un an. |
   | **[!UICONTROL Période personnalisée à cette période]** | Permet de définir une période personnalisée. |

   >[!NOTE]
   >
   >Lorsque vous sélectionnez un nombre de jours personnalisé (par exemple, du 7 au 20 octobre, soit 14 jours), seules deux options sont proposées : **[!UICONTROL 14 jours précédant cette période]** et **[!UICONTROL Période personnalisée à cette période]**.

1. La comparaison qui en résulte ressemble à ceci :

   ![Tableau à structure libre présentant une comparaison des périodes et le pourcentage de modification.](assets/compare-time-result.png)

   Les lignes dans la colonne Pourcentage de modification sont en rouge pour les valeurs négatives et en vert pour les valeurs positives.

## Ajouter une colonne de périodes à la comparaison

Vous pouvez désormais ajouter une période à chaque colonne d’un tableau, ce qui permet d’ajouter une période différente de celle configurée pour votre calendrier.

1. Cliquez avec le bouton droit de la souris dans le tableau, puis sélectionnez **[!UICONTROL Ajouter une colonne de périodes]**.

   ![](assets/add-time-period-column.png)

1. Selon la façon dont sont définies les périodes du tableau, les options de comparaison suivantes sont disponibles :

   | Option | Description |
   |---|---|
   | **[!UICONTROL *x* semaines/mois/trimestres/années précédant cette période]** | Ajoutez une colonne avec la semaine/le mois/etc. juste avant cette période. |
   | **[!UICONTROL Ces *x* semaines/mois/trimestres/années l’année dernière à cette période]** | Ajoute la même période il y a un an. |
   | **[!UICONTROL Période personnalisée à cette période]** | Permet de créer une période personnalisée. |

   >[!NOTE]
   >
   >Lorsque vous sélectionnez un nombre de jours personnalisé (par exemple, du 7 au 20 octobre, soit 14 jours), seules deux options sont proposées : **[!UICONTROL 14 jours précédant cette période]** et **[!UICONTROL Période personnalisée à cette période]**.

1. La période est insérée en haut de la colonne sélectionnée :

   ![Tableau à structure libre présentant les occurrences de la période calendaire en cours et du mois calendaire précédent.](assets/add-time-period-column2.png)

1. Vous pouvez ajouter autant de colonnes que vous le souhaitez, et mélanger et associer différentes périodes :

1. Vous pouvez également trier chaque colonne, ce qui change l’ordre des jours selon la colonne utilisée pour le tri.

## Aligner les dates de colonnes pour commencer sur la même ligne

Vous pouvez également aligner les dates de chaque colonne afin qu’elles commencent à partir de la même ligne.

Par exemple, vous effectuez une comparaison jour par jour pour la dernière semaine (se terminant le 5 octobre 2024) et la semaine précédente. Par défaut, la colonne de gauche commence par le 22 septembre et la colonne de droite par le 29 septembre.

![Dates non alignées](assets/not-align-dates.png)

Vous pouvez activer l’option **[!UICONTROL Aligner les dates de chaque colonne pour qu’elles commencent toutes sur la même ligne]** dans [Paramètres](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1) pour que la visualisation du tableau à structure libre aligne les dates des colonnes pour qu’elles commencent sur la même ligne.

![](assets/align-dates.png)

Tenez compte des points suivants lorsque vous utilisez cette option :

* Ce paramètre est activé par défaut pour tous les nouveaux projets.

* Ce paramètre s’applique à l’ensemble du tableau. Par exemple, si vous modifiez ce paramètre pour une répartition au sein du tableau, le paramètre est appliqué pour l’ensemble du tableau.

