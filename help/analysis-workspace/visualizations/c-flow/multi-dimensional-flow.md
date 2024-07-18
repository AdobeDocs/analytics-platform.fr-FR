---
description: Dans un flux interdimensionnel, vous pouvez examiner le cheminement des utilisateurs dans plusieurs dimensions.
title: Flux interdimensionnels
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 73%

---

# Flux interdimensionnels

Dans un flux interdimensionnel, vous pouvez examiner le cheminement des utilisateurs dans plusieurs dimensions.

Un libellé de dimension dans la partie supérieure de chaque colonne Flux rend l’utilisation de plusieurs dimensions dans une visualisation de flux plus intuitive :

![ Flux interdimensionnel mettant en évidence plusieurs dimensions, notamment le produit, la page, la version du système d’exploitation et la durée de la visite.](assets/flow.png)

Nous allons étudier deux exemples d’utilisation : sur le web et dans une application.

## 1er exemple d’utilisation : Application

La dimension [!UICONTROL Nom de l’action] a été ajoutée au flux, le premier élément renvoyé étant [!UICONTROL ItemAdded] :

![Flux montrant l’élément ajouté.](assets/multi-dimensional-flow.png)

Afin d’explorer l’interaction entre les écrans et pages et les actions dans cette application, faites glisser la dimension de page à plusieurs emplacements, selon ce que vous souhaitez savoir :

* Faites-la glisser à l’une des extrémités de la zone de dépôt (dans la zone rectangulaire bordée de noir qui apparaît) pour **remplacer** les principaux résultats correspondants :

  ![Flux montrant la dimension Page glissée-déposée vers plusieurs zones.](assets/multi-dimensional-flow2.png) ![Diagramme de flux montrant les éléments déplacés.](assets/multi-dimensional-flow3.png)

* Faites-la glisser sur l’espace blanc à l’extrémité (remarquez la parenthèse noire) pour **l’ajouter** à la visualisation :

  ![Flux montrant la dimension Page glissée vers l’espace blanc à la fin.](assets/multi-dimensional-flow4.png)

Voici le résultat si vous décidez de remplacer l’élément ItemScaled dans la colonne de droite avec la dimension Page. Le premier résultat correspond maintenant au premier résultat de la dimension Page :

![A fLow indiquant les résultats de la dimension Page en haut de la liste.](assets/multi-dimensional-flow5.png)

Vous pouvez maintenant voir de quelle façon vos clients se déplacent dans les actions et les pages. Pour explorer le flux plus en détail, cliquez sur les différents nœuds :

![ Flux montrant les éléments ajoutés, les éléments déplacés et la vue principale.](assets/multi-dimensional-flow6.png)

Voici ce qui se passe si vous faites glisser une autre dimension Nom de l’action sur la fin de la visualisation :

![Flux montrant le nom de l’action ajouté.](assets/multi-dimensional-flow7.png)

Vous avez ainsi accès à des informations plus détaillées et aux changements possibles à apporter à l’application que vous analysez.

## 2e exemple d’utilisation : Web

Cet exemple d’utilisation illustre la façon de déterminer quelles campagnes génèrent le plus d’entrées sur un site web.

Faites glisser la dimension Nom de la campagne dans un nouveau flux :

![Flux montrant la dimension Nom de campagne glissée vers un nouveau flux.](assets/multi-dimensional-flow8.png)

Je souhaite maintenant savoir quelles pages de ces campagnes attirent le plus de trafic ; je fais donc glisser la dimension Page sur la droite des résultats du flux pour l’ajouter à la visualisation :

![Flux montrant la dimension Page glissée à droite des résultats du flux.](assets/multi-dimensional-flow9.png)
