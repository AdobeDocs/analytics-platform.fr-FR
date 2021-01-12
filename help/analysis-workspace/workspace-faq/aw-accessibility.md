---
description: Fonctionnalités de prise en charge de l’accessibilité dans Analysis Workspace
title: Accessibilité dans Analysis Workspace
translation-type: tm+mt
source-git-commit: e004a2a8ec24113ae8b62a9d30c10fe0eb763460
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 82%

---


# Accessibilité dans Analysis Workspace

Découvrez la prise en charge de l’accessibilité dans [!UICONTROL Analysis Workspace], le principal outil d’analyse d’Adobe Analytics.

L’accessibilité consiste à rendre les produits utilisables pour les personnes souffrant de déficiences visuelles, auditives, cognitives, motrices et autres. Parmi les exemples de fonctionnalités d’accessibilité pour les logiciels, citons la prise en charge des lecteurs d’écran, les équivalents textuels pour les illustrations, les raccourcis clavier, le changement des couleurs d’affichage pour obtenir un contraste élevé, etc.

[!UICONTROL Analysis Workspace] fournit quelques outils qui le rendent accessible, notamment :

## Navigation dans [!UICONTROL Workspace] à l’aide du clavier

La navigation dans [!UICONTROL Analysis Workspace] fonctionne du haut vers le bas et de gauche à droite. Les éléments de navigation suivants facilitent l’accessibilité :

* La touche `Tab` active des raccourcis de repère., en passant d’une section à l’autre dans Workspace. Dans le rail de gauche, `Tab` vous permet également de passer d&#39;une option déplaçable à l&#39;autre.
* Le déplacement de `left/right arrows` entre des éléments individuels après `Tab` l&#39;a mis en évidence.
* `F6` accède au premier panneau du projet et se déplace entre les visualisations dans ce panneau. Ensuite, il passe au panneau suivant du projet et se répète.
* Nous appliquons des indicateurs de ciblage afin que les utilisateurs de clavier à vue normale aient une indication claire de l’élément de l’interface utilisateur actuellement ciblé. L’indicateur correspond à une bordure bleue autour de l’élément sélectionné.

   ![Indicateur de ciblage](assets/focus-indicator.png)

### Navigation au clavier pour la barre de menus

1. Appuyez sur la touche de tabulation jusqu’à ce que vous ayez atteint la barre de menus.
1. Utilisez les touches fléchées gauche/droite pour accéder au menu de votre choix.
1. Appuyez sur `Enter` pour sélectionner le menu et afficher ses options.
1. Utilisez les touches fléchées Haut/Bas pour accéder à l&#39;option de menu de votre choix.
1. Appuyez sur `Enter` pour sélectionner l&#39;option.

### Navigation au clavier pour les interactions de glisser-déposer

[!UICONTROL Analysis Workspace] est une interface utilisateur de glisser-déposer. Cependant, les utilisateurs peuvent également ajouter des composants à l’aide du clavier :

1. Appuyez sur la touche de tabulation pour atteindre un composant dans le rail de gauche.
1. Appuyez sur `Enter` pour le sélectionner.
1. Utilisez les touches de direction pour accéder à la zone où vous souhaitez déposer le composant.
1. Appuyez sur `Enter` pour déposer le composant.

### Raccourcis clavier (touches de raccourci)

[!UICONTROL Analysis Workspace] offre un vaste ensemble de [raccourcis clavier](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=fr-FR) pour accélérer le processus. Voici quelques raccourcis courants pour la navigation, la création d’analyses et la démocratisation des informations.

#### Navigation

| Raccourci | Action |
|---|---|
| Alt+Maj+1/2/3 | Accéder à différents rails : [!UICONTROL Panneaux], [!UICONTROL Visualisations] ou [!UICONTROL Composants] |
| Alt+flèche gauche/droite | Navigation entre les panneaux |
| Alt+M | Réduire/Développer tous les panneaux |
| Alt+Ctrl+M | Réduire/Développer le panneau actif |
| Ctrl+/ | Rechercher dans le rail de gauche |

#### Création d’analyses

| Raccourci | Action |
|---|---|
| Alt+1 | Nouveau tableau à structure libre |
| Ctrl+Maj+C | Nouvelle mesure calculée |
| Ctrl+Maj+D | Nouvelle période |
| Ctrl+Maj+E | Nouveau segment |
| Ctrl+Z | Annuler |
| Maintenir la touche Maj enfoncée (dans la zone de dépôt des segments du panneau) | Créer un [filtre déroulant](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=fr-FR) |

#### Démocratisation

| Raccourci | Action |
|---|---|
| Ctrl+S | Enregistrer |
| Ctrl+Maj+G | Traiter |
| Ctrl+G | Partager |
| Alt+Maj+S | Planifier |
| Alt+L | Obtenir le lien vers le projet |
| Ctrl+Maj+B | Télécharger un PDF |

## Prise en charge des lecteurs d’écran et des loupes

Un lecteur d’écran lit le texte qui s’affiche sur l’écran de l’ordinateur. Il lit également les informations non textuelles, telles que les noms des boutons ou les descriptions d’image dans l’application, fournies dans les balises ou attributs d’accessibilité.

## Palettes et contraste des couleurs

[!UICONTROL Analysis Workspace] s’efforce de respecter la norme WCAG 2.1 AA, y compris les exigences en matière de contraste des couleurs.

En outre, les utilisateurs peuvent définir leur propre palette de couleurs préférée pour un projet sous **[!UICONTROL Projet]** > **[!UICONTROL Paramètres du projet]** > [Palette de couleurs du projet](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=fr-FR).

## Validation des champs obligatoires dans les créateurs de composants

Lorsque vous créez un composant, les champs obligatoires sont validés lors de l’enregistrement. Si un champ obligatoire n’est pas validé, il est signalé en rouge avec une icône d’erreur. Une description écrite du problème à résoudre apparaît.

Une fois qu’un composant est entièrement validé, appuyez sur `Save` pour fermer le créateur.

![Validation d’erreur](assets/error-validation.png)

## Prise en charge des fonctionnalités d’accessibilité du système d’exploitation

Analysis Workspace prend en charge les fonctionnalités d’accessibilité intégrées à MS Windows et macOS, telles que le mode contraste élevé, les touches rémanentes et les touches lentes/filtres. Il fournit également des informations sur l’interface utilisateur du système d’exploitation pour permettre l’interaction avec les technologies d’assistance, y compris les lecteurs d’écran tels que VoiceOver pour macOS et NVDA sous Windows.
