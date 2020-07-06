---
description: valeur nulle
title: Panneaux - Aperçu
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 80%

---


# Panneaux - Aperçu

>[!NOTE]
>
>Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

Un panneau est un ensemble de tableaux et de visualisations. Vous pouvez accéder aux panneaux à partir de l’icône supérieure gauche dans Workspace. Les panneaux vous permettent d’organiser vos projets selon les périodes, les unités opérationnelles, la géographie, etc. Ces quatre types de panneaux sont disponibles dans Analysis Workspace pour Customer Journey Analytics :

* [Panneau vierge](blank-panel.md)
* [Panneau Quick Insights](quickinsight.md)
* [Panneau Attribution](attribution.md)
* [Panneau à structure libre](freeform-panel.md)

Les panneaux d’informations rapides, à structure vierge et à structure libre sont des endroits idéaux pour début votre analyse, tandis que le panneau QI d’attribution se prête à des analyses plus avancées. Un `"+"` bouton est disponible dans les projets afin que vous puissiez ajouter des panneaux vides à tout moment.

The default starting panel is the Freeform panel, but you can make the [blank panel](/help/analysis-workspace/c-panels/blank-panel.md) your default as well.

## filtres déroulants dans les panneaux

La zone de liste du panneau propose désormais une fonction de filtrage déroulante. Ces filtres vous permettent d’interagir avec les données du projet de manière contrôlée, afin de réaliser des analyses approfondies, simplifier vos projets et/ou partager des connaissances.

Voici un exemple de projet simplifié : supposons que vous disposiez de plusieurs versions d’un projet/panneau afin d’effectuer du reporting spécifique à chaque pays. Vous pouvez désormais réduire ces projets/panneaux dans un panneau unique et ajouter une liste déroulante des pays à la place pour filtrer les différents jeux de données.

![](assets/dropdowns.png)

N’oubliez pas ce qui suit :

* Vous pouvez dérouler plusieurs composants (ou éléments de dimension), puis passer de l’un à l’autre dans une liste déroulante pour filtrer le contenu du panneau.
* Vous pouvez également créer plusieurs listes déroulantes sur le même panneau.
* Vous pouvez personnaliser le titre de la liste déroulante en cliquant sur le titre et en le modifiant, ou supprimer complètement le titre en cliquant sur le x à côté de ce dernier.
* Vous pouvez créer des filtres déroulants avec n’importe quel type de composant : dimensions, périodes, segments et mesures. Notez que les périodes déroulantes écrasent toujours les périodes du panneau.
* Nous maintenons les couleurs des composants du rail de gauche : jaune pour les listes déroulantes d’éléments de dimension, vert pour les mesures, bleu pour les segments et violet pour les périodes.
* La zone de dépôt créé toujours des segments de niveau d’accès pour les éléments déplacés en tant que segments. Vous pouvez les modifier normalement en cliquant d’abord sur l’icône d’informations (i) à côté du segment, puis sur l’icône de modification en forme de crayon et en les modifiant dans le créateur de segments.

**Pour créer et utiliser des filtres déroulants :**

1. Sélectionnez n’importe quel élément dans le rail de gauche puis, **tout en maintenant la touche enfoncée**, déposez-le dans la zone de dépôt du panneau.

   ![](assets/create_dropdown.png)

   Cela permet de transformer les composants en liste déroulante plutôt qu’en segment. (Vous pouvez toujours ajouter des segments en ne maintenant pas enfoncée la touche.)

   ![](assets/dropdown.png)

1. Sélectionnez l’une des options de la liste déroulante ci-dessous pour modifier les données du panneau. (Vous pouvez également choisir de ne pas filtrer les données du panneau en sélectionnant **[!UICONTROL Pas de filtre]**.)
1. Par exemple, si vous souhaitez également répartir les données par canal marketing, vous pouvez ajouter une autre liste déroulante appelée « Canal marketing » :

   ![](assets/mc_dropdown.png)

