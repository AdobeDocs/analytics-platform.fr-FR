---
description: Découvrez comment afficher les prévisions dans un tableau ou un graphique en courbes.
title: Affichage des prévisions dans Analysis Workspace
feature: Visualizations
role: User
exl-id: 4a8b602c-e6aa-4a46-bba9-642387e6af88
source-git-commit: fea1b12a594a820ab2e55f850ca95c5a373184f0
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 1%

---

# Affichage des prévisions dans Analysis Workspace

Vous pouvez afficher les prévisions dans un tableau à structure libre ou sous forme de graphique en courbes.

## Affichage des prévisions dans un tableau

Vous pouvez afficher les prévisions dans un tableau à structure libre de série chronologique. When [!UICONTROL Afficher la prévision] est activé pour le tableau à structure libre dans [préférences utilisateur](../user-preferences.md), la prévision s’affiche automatiquement pour la première colonne de mesures ajoutée au tableau. Pour toute colonne supplémentaire :

1. Icône Sélectionner les paramètres de colonne ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) dans l’en-tête de colonne, assurez-vous que **[!UICONTROL Afficher la prévision]** est sélectionné dans la liste des options. Pour plus d’informations, consultez [Paramètres de colonne](../visualizations/freeform-table/column-row-settings/column-settings.md).

1. Cliquez en dehors du **[!UICONTROL Paramètres des colonnes]** pour enregistrer le paramètre et afficher le tableau mis à jour.

Les prévisions sont présentées dans le tableau ci-dessous :

![Afficher les prévisions dans le tableau](assets/show-forecast-table.png)

* La valeur et le pourcentage de la prévision pour chaque cellule sont affichés dans **gris foncé**.
* Pour indiquer une valeur de prévision, un symbole de prévision <img src="./assets/forecast.svg" alt="Symbole des prévisions" width="20" /> s’affiche dans le coin supérieur droit de la cellule.


## Affichage des prévisions dans un graphique en courbes

Un graphique en courbes est la seule visualisation qui vous permet d’afficher des prévisions.

1. Icône Sélectionner les paramètres ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) dans l’en-tête de visualisation, assurez-vous que **[!UICONTROL Afficher la prévision]** est sélectionné dans la liste des options.

1. (Facultatif) Pour permettre aux prévisions de mettre correctement le graphique à l’échelle, sélectionnez **[!UICONTROL Autoriser la prévision à l’échelle de l’axe Y]**. Cette option n’est pas sélectionnée par défaut, car elle peut parfois rendre un graphique moins lisible.

1. Cliquez en dehors du **[!UICONTROL Paramètres]** pour afficher le graphique en courbes mis à jour.

Les prévisions sont présentées dans le graphique en courbes comme suit :

![Afficher les prévisions dans le graphique en courbes](assets/show-forecast-linechart.png)

* Les valeurs actuelles des mesures du graphique en courbes sont indiquées par une barre verticale. Si vous passez la souris sur cette ligne verticale, une fenêtre contextuelle s’affiche avec la date actuelle la plus récente.
* Les valeurs prédites d’une ou de plusieurs mesures s’affichent directement dans la barre verticale à l’aide de lignes en pointillés. Vous pouvez placer le pointeur de la souris sur un point de données pour une mesure. Une fenêtre contextuelle s’affiche avec :
   * date de la prévision
   * valeur prévue pour la mesure
   * limite supérieure de la valeur prévue pour la mesure
   * limite inférieure de la valeur prévue pour la mesure
* La zone ombrée indique la marge de confiance de la prévision.
