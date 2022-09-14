---
description: Permet de visualiser facilement les données de comparaison dans Analysis Workspace, par exemple en créant des comparaisons avec le mois dernier, l’année dernière, etc.
title: Visualisation des diagrammes en courbes
feature: Visualizations
role: User, Admin
exl-id: 08e49857-aa58-4527-bdfd-b1663a75a02b
source-git-commit: 5aee0fcc0ec241d946da4ce97dc01eb6274648aa
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 33%

---

# Graphique combo

Le [!UICONTROL Graphique en courbes] la visualisation facilite la création rapide d’une visualisation de comparaison sans avoir à créer d’abord un tableau. Vous pouvez facilement afficher les tendances de vos données dans une combinaison ligne/barre.

Utilisez une [!UICONTROL Graphique en courbes] à :

* Comparez les commandes de cette semaine aux commandes en même temps le mois dernier (et l’année dernière), le tout en quelques clics.
* Analysez et comparez rapidement plusieurs mesures (comme [!UICONTROL Visiteurs uniques] et [!UICONTROL Recettes]) les uns par rapport aux autres sur le même graphique.
* Analyse d’une mesure par rapport à une fonction (telle que [!UICONTROL Moyenne cumulée]) sur un horizon temporel.

Gardez à l’esprit que vous pouvez :

* Ajout de plusieurs comparaisons en une seule [!UICONTROL Graphique en courbes].
* Si vous ajoutez une ou plusieurs comparaisons, celles-ci doivent être du même type, par exemple : [!UICONTROL Comparaison des heures].
* Vous pouvez ajouter jusqu’à 5 comparaisons.
* Vous pouvez appliquer jusqu’à 3 filtres (segments) à une mesure.

## Création d’un diagramme Combo

1. Dans la liste déroulante Visualisations du rail de gauche, faites glisser le [!UICONTROL Graphique en courbes] visualisation dans un panneau vierge.

   ![Build](assets/combo-chart-build.png)

1. Dans les listes déroulantes, sélectionnez une dimension pour l’axe X et une mesure pour l’axe Y.

1. Sélectionnez le type de [!UICONTROL Comparaison des lignes] vous voulez utiliser.

   | Type de comparaison de lignes | Définition |
   | --- | --- |
   | **[!UICONTROL Comparaison de temps]** | Type de comparaison le plus courant : comparaison de cette période à il y a 4 semaines, par exemple. Si vous avez sélectionné [!UICONTROL Comparaison des heures], effectuez une sélection secondaire pour connaître la période à comparer.<p>![Période](assets/combo-time-period.png) |
   | **[!UICONTROL Fonction]** | Vous pouvez introduire une fonction telle que [!UICONTROL Moyenne] dans la comparaison. Consultez la liste des fonctions prises en charge ci-dessous.<p>![Fonctions](assets/combo-functions.png) |
   | **[!UICONTROL Mesure secondaire]** | Vous pouvez, par exemple, comparer des [!UICONTROL Recettes] à une autre mesure.<p>![Deux mesures](assets/combo-2metrics.png) |

   {style=&quot;table-layout:auto&quot;}

1. Cliquez sur **[!UICONTROL Créer]**.

   La sortie ressemblera à ceci :

   ![Sortie](assets/combo-output.png)

   La période en cours s’affiche dans le graphique à barres et la période de comparaison est représentée par le graphique en courbes. Les points sur le graphique en courbes sont appelés &quot;barres&quot;.

## Fonctions prises en charge

Si vous choisissez **[!UICONTROL Fonction]** comme la propriété [!UICONTROL Type de comparaison de lignes], une fonction de la mesure choisie est renvoyée.

| Fonction | Définition |
| --- | --- |
| **[!UICONTROL Somme de la colonne]** | Ajoute toutes les valeurs numériques pour une mesure dans une colonne (sur l’ensemble des éléments d’une dimension) |
| **[!UICONTROL Moyenne cumulée]** | Renvoie la moyenne des N dernières lignes. |
| **[!UICONTROL Médiane]** | Renvoie la médiane pour une mesure dans une colonne. La médiane est le nombre au milieu d’un ensemble de nombres, c’est-à-dire que la moitié des nombres ont une valeur supérieure ou égale à la médiane et la moitié une valeur inférieure ou égale à la médiane. |
| **[!UICONTROL Cumulé]** | Somme cumulée de N lignes. |
| **[!UICONTROL Max. colonne]** | Renvoie la valeur la plus grande d’un ensemble d’éléments de dimension pour une colonne de mesures. |
| **[!UICONTROL Moyenne]** | Renvoie la moyenne arithmétique, ou moyenne, pour une mesure. |
| **[!UICONTROL Min. colonne]** | Renvoie la valeur la plus petite d’un ensemble d’éléments de dimension pour une colonne de mesures. |

{style=&quot;table-layout:auto&quot;}

Voici un exemple de la moyenne cumulée de la mesure Recettes :

![Moyenne cumulée](assets/combo-cumul-avg.png)

Voici un exemple de graphique combiné avec les fonctions Moyenne cumulée et Moyenne cumulée :

![Deux fonctions](assets/combo-two-functions.png)

## Paramètres des graphiques combinés

Cliquez sur l’icône d’engrenage en haut à droite d’un graphique combiné pour en modifier les paramètres.

![Paramètres](assets/combo-settings.png)

| Paramètre | Définition |
| --- | --- |
| **[!UICONTROL Type de visualisation]** | Permet de passer à un autre type de visualisation. |
| **[!UICONTROL Granularité]** | Pour les visualisations de tendances, vous pouvez modifier la granularité temporelle (jour, semaine, mois, etc.) à partir de cette liste déroulante. |
| **[!UICONTROL Général]** |  |
| **[!UICONTROL Pourcentages]** | Affiche les valeurs en pourcentages. |
| **[!UICONTROL Légende visible]** | Permet de masquer le texte de légende détaillé pour la visualisation des graphiques en courbes. |
| **[!UICONTROL Limiter le nombre maximal d’éléments]** | Réduit le nombre d’éléments sur l’axe X. Si vous disposez d’un jeu de données volumineux, vous pouvez uniquement afficher les 10 premiers éléments (ou toute valeur choisie). |
| **[!UICONTROL Recouvrements]** | Afficher ou masquer les barres sur les lignes. |
| **[!UICONTROL Axe]** |  |
| **[!UICONTROL Afficher l’axe double]** | S’applique seulement s’il existe deux mesures : vous pouvez afficher un axe des ordonnées sur la gauche (pour une mesure) et un sur la droite (pour l’autre mesure). Cela sʼavère utile lorsque les mesures tracées présentent des dimensions très différentes. La couleur de l’axe double correspond à la couleur du tableau, sauf s’il existe plusieurs comparaisons. Dans ce cas, la couleur de toutes les comparaisons est grise. |
| **[!UICONTROL Normalisation]** | Force les mesures en proportions égales. Cela sʼavère utile lorsque les mesures tracées présentent des dimensions très différentes. |
| **[!UICONTROL Afficher l’axe X]** | Affichez l’axe X ou masquez-le. |
| **[!UICONTROL Afficher l’axe Y]** | Affichez l’axe des ordonnées ou masquez-le. |
| **[!UICONTROL Axe Y de l’ancre à zéro]** | Si toutes les valeurs mappées dans le graphique sont considérablement supérieures à zéro, le seuil de l’axe des ordonnées est par défaut NON NUL. Si cette option est activée, l’axe des ordonnées est obligatoirement ancré à zéro (et le graphique est retracé). |

{style=&quot;table-layout:auto&quot;}
