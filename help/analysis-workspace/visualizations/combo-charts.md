---
description: Visualisez facilement les données de comparaison dans Analysis Workspace, par exemple en établissant des comparaisons avec le mois dernier, l’année dernière, etc.
title: Visualisation des graphiques combinés
feature: Visualizations
exl-id: 06faa997-3a4e-4c41-b64e-64a15ada6552
role: User
source-git-commit: 590a3ddbe988d27341fe96a3fa866960d1641e24
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 41%

---

# Combo {#combo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_combo_button"
>title="Combo"
>abstract="Créez rapidement une visualisation de graphique combiné sans avoir à créer d’abord un tableau à structure libre."

<!-- markdownlint-enable MD034 -->


La visualisation ![Commentaire](/help/assets/icons/ComboChart.svg) **[!UICONTROL Combo]** facilite la création rapide d’une visualisation de comparaison sans avoir à créer un tableau au préalable. Vous pouvez facilement afficher les tendances de vos données dans une combinaison ligne/barre.

Utilisez un [!UICONTROL Combo] pour :

* Comparez les commandes de la semaine aux commandes de la même semaine le mois dernier (et l’année dernière).
* Analysez et comparez rapidement plusieurs mesures (comme [!UICONTROL Personnes] et [!UICONTROL Recettes]) l’une par rapport à l’autre sur le même graphique.
* Analysez une mesure par rapport à une fonction (telle que la [!UICONTROL Moyenne cumulée]) sur un horizon temporel.

Gardez les éléments suivants à l’esprit :

* Vous pouvez ajouter plusieurs comparaisons dans un seul [!UICONTROL graphique combiné].
* Si vous ajoutez une ou plusieurs comparaisons, celles-ci doivent être du même type, par exemple : [!UICONTROL Comparaison de temps].
* Vous pouvez ajouter jusqu’à 5 comparaisons.
* Vous pouvez appliquer jusqu’à 3 filtres à une mesure.
* Les mesures calculées ne sont pas prises en charge dans les graphiques combinés.

## Sélectionnez l’option  

1. Ajoutez une visualisation ![Commentaire](/help/assets/icons/ComboChart.svg) [!UICONTROL Combo]. Voir [Ajout d’une visualisation à un panneau](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)

1. Dans les listes déroulantes, sélectionnez une dimension pour l’axe X et une mesure pour l’axe Y.

1. Sélectionnez le type de [!UICONTROL comparaison de lignes] que vous souhaitez utiliser.

   | Type de comparaison de lignes | Définition |
   | --- | --- |
   | **[!UICONTROL Comparaison de temps]** | Type de comparaison le plus courant : comparaison de cette période avec celle d’il y a 4 semaines, par exemple. Si vous avez sélectionné [!UICONTROL Comparaison des heures], effectuez une deuxième sélection pour indiquer la période à comparer.<p>![Comparaison des lignes avec la période sélectionnée et le champ de sélection secondaire pour la période.](assets/combo-time-period.png) |
   | **[!UICONTROL Fonction]** | Vous pouvez introduire une fonction telle que [!UICONTROL Moyenne] dans la comparaison. Voir la liste des [fonctions prises en charge](#supported-functions).<p>![Menu déroulant de comparaison des lignes affichant les fonctions sélectionnées et une liste des fonctions prises en charge disponibles.](assets/combo-functions.png) |
   | **[!UICONTROL Deuxième mesure]** | Vous pouvez, par exemple, comparer des [!UICONTROL revenus] à une autre mesure.<p>![Un diagramme en boîte comparant deux mesures.](assets/combo-2metrics-settings.png) |

   {style="table-layout:auto"}

1. Sélectionnez la **[!UICONTROL Version]**.

   La sortie ressemble à :

   ![Graphique en courbes représentant la période actuelle dans un graphique à barres et la période de comparaison dans le graphique en courbes ](assets/combo-output.png)

   La période en cours s’affiche dans le graphique à barres. Le graphique en courbes représente la période de comparaison. Les points sur le graphique en courbes sont appelés *cloches à barres*.

## Fonctions prises en charge

Si vous sélectionnez **[!UICONTROL Fonction]** comme [!UICONTROL  type de comparaison Ligne], une fonction de la mesure choisie est renvoyée.

| Fonction | Définition |
| --- | --- |
| **[!UICONTROL Somme de la colonne]** | Ajoute toutes les valeurs numériques d’une mesure dans une colonne (sur l’ensemble des éléments d’une dimension). |
| **[!UICONTROL Moyenne cumulée]** | Renvoie la moyenne des N dernières lignes. |
| **[!UICONTROL Médiane]** | Renvoie la médiane pour une mesure dans une colonne. La médiane est le nombre situé au milieu d’un ensemble de nombres. La moitié des nombres a des valeurs supérieures ou égales à la médiane et la moitié du nombre a des valeurs inférieures ou égales à la médiane. |
| **[!UICONTROL Cumulé]** | Somme cumulée de N lignes. |
| **[!UICONTROL Max. colonne]** | Renvoie la valeur la plus grande d’un ensemble d’éléments de dimension pour une colonne de mesures. |
| **[!UICONTROL Moyenne]** | Renvoie la moyenne arithmétique, ou moyenne, pour une mesure. |
| **[!UICONTROL Min. colonne]** | Renvoie la valeur la plus petite d’un ensemble d’éléments de dimension pour une colonne de mesures. |

{style="table-layout:auto"}

Voici un exemple de la moyenne cumulée de la mesure Revenus :

![Graphique à virgule montrant la moyenne cumulée](assets/combo-cumul-avg.png)

Voici un exemple de graphique combiné avec les fonctions Moyenne cumulée et Moyenne :

![Graphique à virgules montrant les fonctions moyennes et moyennes cumulées.](assets/combo-three-functions.png)

>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Paramètres de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu contextuel de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>