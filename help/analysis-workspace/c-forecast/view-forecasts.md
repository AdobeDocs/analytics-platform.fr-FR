---
description: Découvrez comment afficher des prévisions dans un tableau ou un graphique en courbes.
title: Affichage des prévisions dans Analysis Workspace
feature: Visualizations
role: User
exl-id: 4a8b602c-e6aa-4a46-bba9-642387e6af88
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 3%

---

# Afficher des prévisions dans Analysis Workspace

Vous pouvez afficher des prévisions dans un tableau à structure libre ou dans un graphique en courbes.

## Afficher les prévisions dans un tableau

Vous pouvez afficher des prévisions dans un tableau à structure libre de série temporelle. Lorsque l’option [!UICONTROL Afficher la prévision] est activée pour le tableau à structure libre dans [Préférences utilisateur](../user-preferences.md), la prévision s’affiche automatiquement pour la première colonne de mesures ajoutée au tableau. Pour toute colonne supplémentaire :

1. Sélectionnez l’icône des paramètres de colonne ![Paramètres de colonne](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) dans l’en-tête de colonne, puis assurez-vous que **[!UICONTROL Afficher la prévision]** est sélectionné dans la liste des options. Pour plus d’informations, consultez [Paramètres de colonne](../visualizations/freeform-table/column-row-settings/column-settings.md).

1. Cliquez en dehors du menu **[!UICONTROL Paramètres de colonne]** pour enregistrer le paramètre et afficher le tableau mis à jour.

Les prévisions sont présentées dans le tableau comme suit :

![Afficher la prévision dans le tableau](assets/show-forecast-table.png)

* La valeur de prévision et le pourcentage pour chaque cellule s’affichent en **gris foncé**.
* Pour indiquer une valeur de prévision, un symbole de prévision ![ForecastAnalytics](/help/assets/icons/ForecastAnalytics.svg) s’affiche dans le coin supérieur droit de la cellule.


## Afficher les prévisions dans un graphique linéaire

Un graphique en courbes est la seule visualisation qui vous permet d’afficher des prévisions.

1. Sélectionnez l’icône des paramètres ![Paramètres de colonne](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) dans l’en-tête de visualisation, puis assurez-vous que **[!UICONTROL Afficher la prévision]** est sélectionné dans la liste des options.

1. (Facultatif) Pour permettre aux prévisions de mettre correctement à l’échelle le graphique, sélectionnez **[!UICONTROL Autoriser la prévision à mettre à l’échelle l’axe Y]**. Cette option n’est pas sélectionnée par défaut, car elle peut parfois rendre un graphique moins lisible.

1. Cliquez en dehors du menu **[!UICONTROL Paramètres]** pour afficher le graphique en courbes mis à jour.

Les prévisions sont représentées dans le graphique linéaire comme suit :

![Afficher la prévision dans le graphique linéaire](assets/show-forecast-linechart.png)

* Les valeurs actuelles des mesures du graphique en courbes sont indiquées par une barre verticale. Si vous pointez sur cette ligne verticale, une fenêtre contextuelle s’affiche avec la dernière date actuelle.
* Les valeurs prévues pour une ou plusieurs mesures sont affichées à droite de la barre verticale à l’aide de lignes pointillées. Vous pouvez pointer sur n’importe quel point de données pour une mesure. Une fenêtre contextuelle s’affiche avec :
   * date de la prévision
   * valeur prévue pour la mesure
   * limite supérieure de la valeur prévue pour la mesure
   * limite inférieure de la valeur prévue pour la mesure
* La zone ombrée affiche la marge de confiance de la prévision.
