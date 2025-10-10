---
description: Découvrez les fonctionnalités de prise en charge de l’accessibilité dans Analysis Workspace.
title: Accessibilité dans Analysis Workspace
feature: Workspace Basics
exl-id: 1616c625-8914-4ede-815d-e8d62e796ea5
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 100%

---

# Accessibilité dans Analysis Workspace

Découvrez la prise en charge de l’accessibilité dans [!UICONTROL Analysis Workspace], le principal outil d’analyse de Customer Journey Analytics.

L’accessibilité consiste à rendre les produits utilisables pour les personnes souffrant de déficiences visuelles, auditives, cognitives, motrices et autres. Voici quelques exemples de fonctionnalités d’accessibilité pour les produits logiciels :

* prise en charge des lecteurs d’écran,
* équivalents textuels pour les images,
* raccourcis clavier,
* contraste élevé pour les couleurs d’affichage,
* etc.

[!UICONTROL Analysis Workspace] fournit quelques outils qui le rendent accessible, notamment :

## Navigation au clavier

La navigation dans [!UICONTROL Analysis Workspace] s’effectue de haut en bas et de gauche à droite. Les éléments de navigation suivants facilitent l’accessibilité :

* La touche **[!UICONTROL Tab]** active des raccourcis de repère, pour se déplacer entre des sections plus grandes dans Workspace. Dans le panneau de gauche, la touche **[!UICONTROL Tab]** vous permet également de passer d’une option déplaçable à la suivante.
* Les touches ◀ et ▶ permettent de se déplacer entre les éléments individuels après que la touche **[!UICONTROL Tab]** a mis en surbrillance un élément.
* La touche **[!UICONTROL F6]** permet d’accéder au premier panneau du projet et de se déplacer parmi les visualisations de ce panneau. Puis, il passe au panneau suivant du projet et répète la même opération.
* Des indicateurs d’élément actif sont présents afin que les utilisateurs et les utilisatrices malvoyants disposent d’une indication claire mettant en évidence l’élément de l’interface utilisateur actuellement actif. L’indicateur est une bordure bleue pour le panneau actif. Et un arrière-plan gris pour la fonctionnalité sélectionnée récemment et la sélection dans la fonctionnalité. Dans cet exemple, [!UICONTROL Composants] et la dimension Page ont été récemment sélectionnés.

  ![Tableau à structure libre affichant un indicateur de mise au point d’une bordure bleue autour du tableau à structure libre.](assets/focus-indicator.png)

### Navigation au clavier pour la barre de menu

1. Appuyez sur la touche de tabulation jusqu’à ce que vous ayez atteint la barre de menu.
1. Utilisez les touches directionnelles pour naviguer entre les menus et les éléments de menu.
1. Appuyez sur **[!UICONTROL Entrée]** pour ouvrir un menu ou sélectionner un élément de menu.
1. Utilisez la touche **[!UICONTROL Echap]** pour fermer un menu.

### Navigation au clavier pour les interactions de glisser-déposer

[!UICONTROL Analysis Workspace] est une interface utilisateur avec glisser-déposer. Cependant, les utilisateurs et les utilisatrices peuvent également ajouter des composants à l’aide du clavier :

1. Appuyez sur la touche de tabulation pour atteindre un composant dans le panneau de gauche.
1. Appuyez sur **[!UICONTROL Entrée]** pour le sélectionner.
1. Utilisez les touches de direction pour accéder à la zone où vous souhaitez déposer le composant.
1. Appuyez sur **[!UICONTROL Entrée]** pour déposer le composant.

### Raccourcis clavier (touches de raccourci)

[!UICONTROL Analysis Workspace] offre un vaste ensemble de [raccourcis clavier (touches de raccourci)](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) pour un workflow plus fluide.

## Prise en charge des lecteurs d’écran et des loupes

Un lecteur d’écran lit le texte qui s’affiche sur l’écran de l’ordinateur. Il lit également les informations non textuelles, telles que les libellés des boutons ou les descriptions d’image dans l’application.

## Palettes et contraste des couleurs

[!UICONTROL Analysis Workspace] s’efforce de respecter la norme WCAG 2.1 AA, y compris les exigences en matière de contraste des couleurs.

En outre, les utilisateurs peuvent définir leur propre palette de couleurs préférée pour un projet sous **[!UICONTROL Projet]** > **[!UICONTROL Paramètres du projet]** > [Palette de couleurs du projet](/help/analysis-workspace/build-workspace-project/color-palettes.md).

## Validation requise

Lors de la création d’un composant, d’une visualisation ou d’un panneau, les champs obligatoires sont validés lors de l’enregistrement. Si un champ obligatoire n’est pas validé, il est entouré en rouge avec une icône d’erreur. Une description écrite explique ce qui doit être corrigé.

![Créateur de segments et indicateur de validation des erreurs.](assets/error-validation.png)

## Prise en charge des fonctionnalités d’accessibilité du système d’exploitation

Analysis Workspace prend en charge les fonctionnalités d’accessibilité intégrées à Windows et macOS, telles que le mode de contraste élevé, les touches rémanentes et les touches lentes/filtres. Il fournit également des informations sur l’interface utilisateur du système d’exploitation pour permettre l’interaction avec les technologies d’assistance, y compris les lecteurs d’écran tels que VoiceOver pour macOS et NVDA sous Windows.
