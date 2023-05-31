---
description: Permet de visualiser facilement les données de comparaison dans Analysis Workspace, par exemple en créant des comparaisons avec le mois dernier, l’année dernière, etc.
title: Visualisation des graphiques combinés
feature: Visualizations
role: User, Admin
exl-id: 06faa997-3a4e-4c41-b64e-64a15ada6552
source-git-commit: 82ba31eec1455bf3d0c746cf5eebc81ce6162a00
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 95%

---

# Graphique combo

La visualisation sous forme de [!UICONTROL graphique combiné] facilite la création rapide d’une visualisation de comparaison sans qu’il soit nécessaire de créer un tableau au préalable. Vous pouvez facilement afficher les tendances de vos données dans une combinaison ligne/barre.

Utilisez un [!UICONTROL Graphique combiné] pour:

* Comparez les commandes de cette semaine à celles de la même période du mois dernier (et de l’année dernière), le tout en quelques clics.
* Analysez et comparez rapidement plusieurs mesures (comme [!UICONTROL Visiteurs uniques] et [!UICONTROL Revenus]) les uns par rapport aux autres sur le même graphique.
* Analysez une mesure par rapport à une fonction (telle que la [!UICONTROL Moyenne cumulée]) sur un horizon temporel.

Gardez ceci à l’esprit :

* Vous pouvez ajouter plusieurs comparaisons dans un seul [!UICONTROL graphique combiné].
* Si vous ajoutez une ou plusieurs comparaisons, celles-ci doivent être du même type, par exemple : [!UICONTROL Comparaison de temps].
* Vous pouvez ajouter jusqu’à 5 comparaisons.
* Vous pouvez appliquer jusqu’à 3 filtres à une mesure.
* Les mesures calculées ne sont pas prises en charge dans les graphiques combinés.

## Créer un graphique combiné

1. Dans la liste déroulante Visualisations du rail de gauche, faites glisser la visualisation du [!UICONTROL graphique combiné] dans un panneau vide.

   ![Build](assets/combo-chart-build.png)

1. Dans les listes déroulantes, sélectionnez une dimension pour l’axe X et une mesure pour l’axe Y.

1. Sélectionnez le type de [!UICONTROL comparaison des lignes] que vous voulez utiliser.

   | Type de comparaison de lignes | Définition |
   | --- | --- |
   | **[!UICONTROL Comparaison de temps]** | Type de comparaison le plus courant : comparaison de cette période avec celle d’il y a 4 semaines, par exemple. Si vous avez sélectionné [!UICONTROL Comparaison des heures], effectuez une deuxième sélection pour indiquer la période à comparer.<p>![Période](assets/combo-time-period.png) |
   | **[!UICONTROL Fonction]** | Vous pouvez introduire une fonction telle que [!UICONTROL Moyenne] dans la comparaison. Consultez la liste des fonctions prises en charge ci-dessous.<p>![Fonctions](assets/combo-functions.png) |
   | **[!UICONTROL Deuxième mesure]** | Vous pouvez, par exemple, comparer des [!UICONTROL revenus] à une autre mesure.<p>![Deux mesures](assets/combo-2metrics.png) |

   {style="table-layout:auto"}

1. Cliquez sur **[!UICONTROL Créer]**.

   La sortie ressemblera à ceci :

   ![Sortie](assets/combo-output.png)

   La période en cours s’affiche dans le graphique à barres et la période de comparaison est représentée par le graphique à lignes. Les points sur le graphique linéaire sont appelés « haltères ».

## Fonctions prises en charge

Si vous choisissez la **[!UICONTROL Fonction]** comme [!UICONTROL type de comparaison linéaire], une fonction de la mesure que vous avez choisie est renvoyée.

| Fonction | Définition |
| --- | --- |
| **[!UICONTROL Somme de la colonne]** | Ajoute toutes les valeurs numériques pour une mesure dans une colonne (sur l’ensemble des éléments d’une dimension) |
| **[!UICONTROL Moyenne cumulée]** | Renvoie la moyenne des N dernières lignes. |
| **[!UICONTROL Médiane]** | Renvoie la médiane pour une mesure dans une colonne. La médiane est le nombre au milieu d’un ensemble de nombres, c’est-à-dire que la moitié des nombres ont une valeur supérieure ou égale à la médiane et la moitié une valeur inférieure ou égale à la médiane. |
| **[!UICONTROL Cumulé]** | Somme cumulée de N lignes. |
| **[!UICONTROL Max. colonne]** | Renvoie la valeur la plus grande d’un ensemble d’éléments de dimension pour une colonne de mesures. |
| **[!UICONTROL Moyenne]** | Renvoie la moyenne arithmétique, ou moyenne, pour une mesure. |
| **[!UICONTROL Min. colonne]** | Renvoie la valeur la plus petite d’un ensemble d’éléments de dimension pour une colonne de mesures. |

{style="table-layout:auto"}

Voici un exemple de la moyenne cumulée de la mesure Revenus :

![Moyenne cumulée](assets/combo-cumul-avg.png)

Voici un exemple de graphique combiné avec les fonctions Moyenne cumulée et Moyenne :

![Deux fonctions](assets/combo-two-functions.png)

## Paramètres des graphiques combinés

Cliquez sur l’icône d’engrenage qui se trouve en haut à droite d’un graphique combiné pour en modifier les paramètres.

![Paramètres](assets/combo-settings.png)

| Paramètre | Définition |
| --- | --- |
| **[!UICONTROL Type de visualisation]** | Permet de passer à un autre type de visualisation. |
| **[!UICONTROL Granularité]** | Pour les visualisations de tendances, vous pouvez modifier la granularité temporelle (jour, semaine, mois, etc.) dans cette liste déroulante. |
| **[!UICONTROL Général]** |  |
| **[!UICONTROL Pourcentages]** | Affiche les valeurs en pourcentages. |
| **[!UICONTROL Légende visible]** | Permet de masquer le texte de légende détaillé pour la visualisation des graphiques combinés. |
| **[!UICONTROL Nombre max d’éléments]** | Réduit le nombre d’éléments sur l’axe X. Si vous disposez d’un jeu de données volumineux, vous pouvez uniquement afficher les 10 premiers éléments (ou toute valeur choisie). |
| **[!UICONTROL Superpositions]** | Afficher ou masquer les haltères sur les lignes. |
| **[!UICONTROL Axe]** |  |
| **[!UICONTROL Afficher l’axe double]** | S’applique seulement s’il existe deux mesures : vous pouvez afficher un axe des y sur la gauche (pour une mesure) et un sur la droite (pour l’autre mesure). Cela sʼavère utile lorsque les mesures tracées présentent des dimensions très différentes. La couleur de l’axe double correspond à celle du tableau, sauf s’il existe plusieurs comparaisons. Dans ce cas, toutes les comparaisons sont grises. |
| **[!UICONTROL Normalisation]** | Force les mesures en proportions égales. Cela sʼavère utile lorsque les mesures tracées présentent des dimensions très différentes. |
| **[!UICONTROL Afficher l’axe X]** | Affichez l’axe X ou masquez-le. |
| **[!UICONTROL Afficher l’axe Y]** | Affichez l’axe Y ou masquez-le. |
| **[!UICONTROL Faire commencer l’axe Y sur zéro]** | Si toutes les valeurs mappées dans le graphique sont considérablement supérieures à zéro, le seuil de l’axe des ordonnées est par défaut NON NUL. Si cette option est activée, l’axe des ordonnées est obligatoirement ancré à zéro (et le graphique est retracé). |

{style="table-layout:auto"}
