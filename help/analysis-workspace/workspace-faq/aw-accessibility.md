---
description: Fonctionnalités de prise en charge de l’accessibilité dans Analysis Workspace
title: Accessibilité dans Analysis Workspace
feature: FAQ
exl-id: 1616c625-8914-4ede-815d-e8d62e796ea5
source-git-commit: 82ba31eec1455bf3d0c746cf5eebc81ce6162a00
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 99%

---

# Accessibilité dans Analysis Workspace

Découvrez la prise en charge de l’accessibilité dans [!UICONTROL Analysis Workspace], le principal outil d’analyse de Customer Journey Analytics.

L’accessibilité consiste à rendre les produits utilisables pour les personnes souffrant de déficiences visuelles, auditives, cognitives, motrices et autres. Parmi les exemples de fonctionnalités d’accessibilité pour les logiciels, citons la prise en charge des lecteurs d’écran, les équivalents textuels pour les illustrations, les raccourcis clavier, le changement des couleurs d’affichage pour obtenir un contraste élevé, etc.

[!UICONTROL Analysis Workspace] fournit quelques outils qui le rendent accessible, notamment :

## Navigation dans [!UICONTROL Workspace] à l’aide du clavier

La navigation dans [!UICONTROL Analysis Workspace] fonctionne du haut vers le bas et de gauche à droite. Les éléments de navigation suivants facilitent l’accessibilité :

* La touche `Tab` active des raccourcis de repère.Cela s’effectue en passant d’une section à l’autre dans Workspace. Dans le rail de gauche, `Tab` vous permet également de passer d’une option déplaçable à la suivante.
* Les `left/right arrows` vous permettent de vous déplacer entre des éléments individuels après la mise en évidence réalisée par `Tab`.
* La touche `F6` permet d’accéder au premier panneau du projet et de se déplacer parmi les visualisations de ce panneau. Puis, il passe au panneau suivant du projet et répète la même opération.
* Nous appliquons des indicateurs de ciblage afin que les utilisateurs de clavier à vue normale aient une indication claire de l’élément de l’interface utilisateur actuellement ciblé. L’indicateur correspond à une bordure bleue autour de l’élément sélectionné.

   ![Indicateur de ciblage](assets/focus-indicator.png)

### Navigation au clavier pour la barre de menu

1. Appuyez sur la touche de tabulation jusqu’à ce que vous ayez atteint la barre de menu.
1. Utilisez les touches fléchées gauche/droite pour accéder au menu de votre choix.
1. Appuyez sur `Enter` pour sélectionner le menu et afficher ses options.
1. Utilisez les touches fléchées haut/bas pour accéder à l’option de menu de votre choix.
1. Appuyez sur `Enter` pour sélectionner l’option.

### Navigation au clavier pour les interactions de glisser-déposer

[!UICONTROL Analysis Workspace] est une interface utilisateur de glisser-déposer. Cependant, les utilisateurs peuvent également ajouter des composants à l’aide du clavier :

1. Appuyez sur la touche de tabulation pour atteindre un composant dans le rail de gauche.
1. Appuyez sur `Enter` pour le sélectionner.
1. Utilisez les touches de direction pour accéder à la zone où vous souhaitez déposer le composant.
1. Appuyez sur `Enter` pour déposer le composant.

### Raccourcis clavier (touches de raccourci)

[!UICONTROL Analysis Workspace] offre un vaste ensemble de [raccourcis clavier](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=fr) pour accélérer le processus. Voici quelques raccourcis courants pour la navigation, la création d’analyses et la démocratisation des informations.

#### Navigation

| Raccourci | Action |
| --- | --- |
| `[Alt + Shift + 1 / 2 / 3]` | Accéder à différents rails : [!UICONTROL Panneaux], [!UICONTROL Visualisations] ou [!UICONTROL Composants] |
| `[Alt + Left / Right]` | Navigation entre les panneaux |
| `[Alt + M]` | Réduire/Développer tous les panneaux |
| `[Alt + Ctrl + M]` | Réduire/Développer le panneau actif |
| `[Ctrl + /]` | Rechercher dans le rail de gauche |

#### Création d’analyses

| Raccourci | Action |
| --- | --- |
| `[Alt + 1]` | Nouveau tableau à structure libre |
| `[Ctrl + Shift + C]` | Nouvelle mesure calculée |
| `[Ctrl + Shift + D]` | Nouvelle période |
| `[Ctrl + Shift + E]` | Nouveau filtre |
| `[Ctrl + Z]` | Annuler |
| `[Component drag + Shift]` | Création d’un filtre de menu déroulant |

#### Démocratisation

| Raccourci | Action |
| --- | --- |
| `[Ctrl + S]` | Enregistrer |
| `[Ctrl + Shift + G]` | Traiter |
| `[Ctrl + G]` | Partager |
| `[Alt + Shift + S]` | Planifier |
| `[Alt + L]` | Obtenir le lien vers le projet |
| `[Ctrl + Shift + B]` | Télécharger un PDF |

## Prise en charge des lecteurs d’écran et des loupes

Un lecteur d’écran lit le texte qui s’affiche sur l’écran de l’ordinateur. Il lit également les informations non textuelles, telles que les noms des boutons ou les descriptions d’image dans l’application, fournies dans les balises ou attributs d’accessibilité.

## Palettes et contraste des couleurs

[!UICONTROL Analysis Workspace] s’efforce de respecter la norme WCAG 2.1 AA, y compris les exigences en matière de contraste des couleurs.

En outre, les utilisateurs peuvent définir leur propre palette de couleurs préférée pour un projet sous **[!UICONTROL Projet]** > **[!UICONTROL Paramètres du projet]** > [Palette de couleurs du projet](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=fr).

## Validation des champs obligatoires dans les créateurs de composants

Lorsque vous créez un composant, les champs obligatoires sont validés lors de l’enregistrement. Si un champ obligatoire n’est pas validé, il est signalé en rouge avec une icône d’erreur. Une description écrite du problème à résoudre apparaît.

Une fois qu’un composant est entièrement validé, appuyez sur `Save` pour fermer le créateur.

![Validation d’erreur](assets/error-validation.png)

## Prise en charge des fonctionnalités d’accessibilité du système d’exploitation

Analysis Workspace prend en charge les fonctionnalités d’accessibilité intégrées à MS Windows et macOS, telles que le mode contraste élevé, les touches rémanentes et les touches lentes/filtres. Il fournit également des informations sur l’interface utilisateur du système d’exploitation pour permettre l’interaction avec les technologies d’assistance, y compris les lecteurs d’écran tels que VoiceOver pour macOS et NVDA sous Windows.
