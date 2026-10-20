---
description: Découvrez les fonctionnalités de prise en charge de l’accessibilité dans Analysis Workspace.
title: Accessibilité dans Analysis Workspace
feature: Workspace Basics
exl-id: 1616c625-8914-4ede-815d-e8d62e796ea5
role: User
TQID: https://experienceleague.adobe.com/555a8gxm8jBGyatt1Vp6e40Wj2gqgRl95oFiHC4NMhQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
    internal-label: Accessibility
source-git-commit: 0932da0728fd386c366b3c9b3cec45115f4e7e4b
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 60%
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
* Des indicateurs de focus sont appliqués afin que les personnes voyantes utilisant le clavier disposent d’une indication claire de l’élément de l’interface utilisateur qui possède actuellement le focus. L’indicateur est une bordure bleue entourant le panneau qui a le focus. Et un arrière-plan gris pour la fonctionnalité sélectionnée récemment et la sélection dans la fonctionnalité. Dans cet exemple, [!UICONTROL Composants] et la dimension Page ont été récemment sélectionnés.

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

### Navigation au clavier pour les colonnes du tableau {#table-columns}

Vous pouvez redimensionner et réorganiser les colonnes d’un tableau à l’aide du clavier. Les mêmes touches fonctionnent sous macOS et Windows.

#### Redimensionner les colonnes {#resize-columns}

Vous pouvez redimensionner les colonnes des tableaux à structure libre et des tableaux de cohortes à l’aide du séparateur de redimensionnement des colonnes, qui est la limite entre deux en-têtes de colonne.

1. Appuyez sur la touche de **[!UICONTROL Tab]** jusqu’à ce qu’un séparateur de redimensionnement de colonne ait le focus.

   Instructions pour redimensionner l’affichage lorsque le séparateur a le focus. Les lecteurs d’écran annoncent ces instructions et la largeur actuelle de la colonne en pourcentage.

1. Utilisez les clés suivantes pour redimensionner la colonne. Une colonne ne peut pas être redimensionnée au-delà de sa largeur minimale ou maximale.

   | Clé | Action |
   | --- | --- |
   | **[!UICONTROL Flèche Gauche]** | Réduisez la colonne à gauche du séparateur de 10 pixels. |
   | **[!UICONTROL Flèche Droite]** | Élargissez de 10 pixels la colonne située à gauche du séparateur. |
   | **[!UICONTROL Enter]** | Réinitialise la largeur de la colonne. |

#### Réorganiser les colonnes {#rearrange-columns}

Dans un tableau à structure libre que vous pouvez modifier, vous pouvez déplacer une colonne vers la gauche ou la droite à l’aide du menu **[!UICONTROL Réorganiser]** dans l’en-tête de colonne.

1. Appuyez sur **[!UICONTROL Tab]** jusqu’à ce que le bouton **[!UICONTROL Réorganiser]** de l’en-tête de colonne ait le focus.
1. Appuyez sur **[!UICONTROL Entrée]**, **[!UICONTROL Espace]** ou **[!UICONTROL Flèche vers le bas]** pour ouvrir le menu.
1. Sélectionnez **[!UICONTROL Déplacer la colonne vers la gauche]** ou **[!UICONTROL Déplacer la colonne vers la droite]**.

   Pour fermer le menu sans déplacer la colonne, appuyez sur **[!UICONTROL Échap]**. Le focus revient au bouton **[!UICONTROL Réorganiser]**.

   Après avoir déplacé une colonne, les lecteurs d’écran annoncent le nom de la colonne et sa nouvelle position au sein de son groupe.

Tenez compte des points suivants lors de la réorganisation des colonnes à l’aide du clavier :

* Une colonne ne se déplace qu’au sein de son groupe de colonnes frères, qui sont les colonnes au même niveau sous le même en-tête parent. Vous ne pouvez pas utiliser le clavier pour déplacer une colonne dans un autre groupe ou pour copier une colonne.
* Lorsque vous déplacez un en-tête parent, ses colonnes et filtres imbriqués se déplacent avec lui.
* L’option **[!UICONTROL Déplacer la colonne vers la gauche]** est désactivée pour la première colonne d’un groupe. L’option **[!UICONTROL Déplacer la colonne vers la droite]** est désactivée pour la dernière colonne d’un groupe.
* Le bouton **[!UICONTROL Réorganiser]** n’est disponible que pour les colonnes que vous pouvez également réorganiser en les faisant glisser. Il n’est pas disponible pour :
  * Tables en lecture seule ou tables avec interactions désactivées.
  * Tableaux à structure libre avec [plusieurs colonnes de dimension](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md), où vous ne pouvez pas faire glisser les colonnes.
  * Colonnes de dates dans les tableaux de cohortes.

### Raccourcis clavier (touches de raccourci)

[!UICONTROL Analysis Workspace] offre un vaste ensemble de [raccourcis clavier (touches de raccourci)](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) pour un workflow plus fluide.

## Prise en charge des lecteurs d’écran et des loupes

Un lecteur d’écran lit le texte qui s’affiche sur l’écran de l’ordinateur. Il lit également les informations non textuelles, telles que les libellés des boutons ou les descriptions d’images dans l’application.

## Palettes et contraste des couleurs

[!UICONTROL Analysis Workspace] s’efforce de respecter la norme WCAG 2.1 AA, y compris les exigences en matière de contraste des couleurs.

En outre, les utilisateurs peuvent définir leur propre palette de couleurs préférée pour un projet sous **[!UICONTROL Projet]** > **[!UICONTROL Paramètres du projet]** > [Palette de couleurs du projet](/help/analysis-workspace/build-workspace-project/color-palettes.md).

## Validation requise

Lors de la création d’un composant, d’une visualisation ou d’un panneau, les champs obligatoires sont validés lors de l’enregistrement. Si un champ obligatoire ne passe pas la validation, il est encadré en rouge et accompagné d’une icône d’erreur. Une description écrite explique ce qui doit être corrigé.

![Créateur de segments et indicateur de validation des erreurs.](assets/error-validation.png)

## Prise en charge des fonctionnalités d’accessibilité du système d’exploitation

Analysis Workspace prend en charge les fonctionnalités d’accessibilité intégrées de Windows et macOS, telles que le mode de contraste élevé, les touches rémanentes et les touches lentes/touches de filtrage. Il fournit également des informations sur l’interface utilisateur du système d’exploitation pour permettre l’interaction avec les technologies d’assistance, y compris les lecteurs d’écran tels que VoiceOver pour macOS et NVDA sous Windows.
