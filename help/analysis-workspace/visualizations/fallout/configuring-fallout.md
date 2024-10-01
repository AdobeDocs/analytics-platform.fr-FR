---
description: Découvrez comment spécifier les points de contact pour créer une séquence d’abandons multidimensionnelle.
title: Configuration d’une visualisation Abandons
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 664756b796e8915a701ccabfb5f250e777701b60
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 36%

---

# Configuration d’une visualisation Abandons

Vous pouvez spécifier les points de contact d’après lesquels créer une séquence d’abandons multidimensionnelle. En général, un point de contact est une page sur votre site. Ils ne se limitent toutefois pas à cela. Vous pouvez par exemple ajouter des événements, tels que des unités, ainsi que des personnes uniques et des visites récurrentes. Vous pouvez aussi ajouter des dimensions, telles qu’une catégorie, un type de navigateur ou un terme de recherche interne.

Il est possible en outre d’ajouter des filtres dans un point de contact. Par exemple, vous pouvez comparer des filtres tels que des utilisateurs iOS et Android™. Faites glisser les filtres souhaités en haut de l’abandon pour ajouter des informations sur ces filtres au rapport sur les abandons. Si vous souhaitez n’afficher que ces filtres, vous pouvez supprimer la ligne de base Toutes les visites .

Le nombre d’étapes que vous pouvez ajouter ou le nombre de dimensions utilisées ne sont pas limités.

Vous pouvez effectuer un cheminement sur les dimensions, les mesures et les filtres. Par exemple, supposons que quelqu’un regarde des chaussures, des chemises sur une page, et sur la page suivante, il regarde des chemises, des chaussettes. Le prochain rapport de flux de produits généré à partir des chaussures portera sur chemise et chaussettes, SAUF chemise.

## Sélectionnez l’option  

1. Ajoutez une visualisation ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Abandon]**. Voir [Ajout d’une visualisation à un panneau](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Faites glisser une page, par exemple la page d’accueil, de la dimension Page vers le menu déroulant *Ajouter un point de contact* .

   ![Page d’accueil de la dimension Page d’accueil glissée vers le champ Ajouter un point de contact.](assets/fallout-drag.png)

   Pointez sur un point de contact pour afficher les abandons et d’autres informations sur ce niveau, telles que le nom du point de contact, ainsi que le nombre de personnes à ce stade. Consultez le taux de succès de ce point de contact (et comparez-le à d’autres points de contact).

   Les nombres encadrés dans la partie grise de la barre correspondent aux abandons entre les points de contact (et non à l’ensemble des abandons à ce point). Le **[!UICONTROL point de contact %]** indique la réussite de la transition de l’étape précédente à l’étape actuelle dans le rapport d’abandons.

   Vous pouvez également ajouter une seule page au rapport des abandons, plutôt que la dimension entière. Cliquez sur la flèche de droite ![ChevronRight](/help/assets/icons/ChevronRight.svg) sur la dimension de page pour sélectionner une page spécifique à ajouter au rapport sur les abandons.

1. Continuez à ajouter des points de contact jusqu’à ce que votre séquence soit complète.

   Vous pouvez **combiner plusieurs points de contact** en faisant glisser un ou plusieurs composants supplémentaires sur un point de contact.

   >[!NOTE]
   >
   >Plusieurs filtres sont reliés par l’opérateur AND, mais plusieurs éléments, tels que des éléments de dimension et des mesures, sont reliés par l’opérateur OR.

   ![Page:CamerRoll ou Page : points de contact de l’appareil photo surlignés.](assets/fallout-or.png)

1. Vous pouvez également **limiter les points de contact individuels à l’événement suivant** (par opposition à *finalement*) dans le chemin. Sous chaque point de contact, il existe un sélecteur avec les options **[!UICONTROL Chemin d’accès éventuel]** et **[!UICONTROL Événement suivant]**, comme illustré ici :

   ![La vue Toutes les visites affiche l’option Chemin d’accès éventuel mise en surbrillance. ](assets/fallout-nexthit.png)

   | Option | Description |
   |---|---|
   | **[!UICONTROL Chemin d’accès éventuel]** (par défaut) | Les personnes sont comptabilisées et qui finiront *par* sur la page suivante du chemin, mais pas nécessairement sur l’événement suivant. |
   | **[!UICONTROL Prochain événement]** | sont comptabilisés et accèdent à la page suivante du chemin d’accès à l’événement suivant. |


## Paramètres

Dans le cadre de la visualisation, des paramètres spécifiques sont disponibles.

| Conteneur d’abandons | Description |
|--- |--- |
| **[!UICONTROL Session]** ou **[!UICONTROL Personne]** | Passez de [!UICONTROL Session] à [!UICONTROL Personne] pour analyser le cheminement de la personne. La valeur par défaut est [!UICONTROL Person]. Ces paramètres permettent de comprendre l’engagement des personnes au niveau des personnes (sur les sessions) ou de contraindre l’analyse à une seule session. |


## Menu contextuel

Des options de menu contextuel spécifiques sont disponibles dans la visualisation.

![Options d’abandon](assets/fallout-options.png)

| Option | Description |
|--- |--- |
| **[!UICONTROL Point de contact de tendance]** | Consultez dans un graphique linéaire les données sur les tendances d’un point de contact, avec quelques données de détection des anomalies prédéfinies. |
| **[!UICONTROL Point de contact de tendance (%)]** | Calcule la tendance du pourcentage total d’abandons. |
| **[!UICONTROL Tendance de tous les points de contact (%)]** | Calcule la tendance de tous les pourcentages des points de contact de l’abandon (sauf **[!UICONTROL Toutes les personnes]**, s’ils sont inclus) sur le même graphique. |
| **[!UICONTROL Ventiler les abandons à ce point de contact]** | Vérifiez ce que les personnes ont fait entre deux points de contact (ce point de contact et le point de contact suivant) si elles ont continué jusqu’au point de contact suivant. Un tableau à structure libre présentant les dimensions est ainsi créé. Vous pouvez y remplacer les dimensions et d’autres éléments qui le composent. |
| **[!UICONTROL Ventiler les abandons à ce point de contact]** | Vérifiez quelles personnes qui n’ont pas franchi l’entonnoir l’ont fait immédiatement après l’étape sélectionnée. |
| **[!UICONTROL Créer un filtre à partir du point de contact]** | Créez un nouveau filtre à partir du point de contact sélectionné. |

>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Paramètres de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu contextuel de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

