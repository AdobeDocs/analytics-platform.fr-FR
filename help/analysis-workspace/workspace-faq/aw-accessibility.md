---
description: Fonctionnalités de prise en charge de l’accessibilité dans Analysis Workspace
title: Accessibilité dans Analysis Workspace
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 100%

---


# Accessibilité dans Analysis Workspace

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

Découvrez la prise en charge de l’accessibilité dans [!UICONTROL Analysis Workspace], le principal outil d’analyse d’Adobe Analytics.

L’accessibilité consiste à rendre les produits utilisables pour les personnes souffrant de déficiences visuelles, auditives, cognitives, motrices et autres. Parmi les exemples de fonctionnalités d’accessibilité pour les logiciels, citons la prise en charge des lecteurs d’écran, les équivalents textuels pour les illustrations, les raccourcis clavier, le changement des couleurs d’affichage pour obtenir un contraste élevé, etc.

[!UICONTROL Analysis Workspace] fournit quelques outils qui le rendent accessible, notamment :

## Navigation dans [!UICONTROL Workspace] à l’aide du clavier

La navigation dans [!UICONTROL Analysis Workspace] fonctionne du haut vers le bas et de gauche à droite. Les éléments de navigation suivants facilitent l’accessibilité :

* La touche `F6` active des raccourcis de repère.
* La touche `Tab` permet de se déplacer entre les éléments individuels.
* Nous appliquons des indicateurs de ciblage afin que les utilisateurs de clavier à vue normale aient une indication claire de l’élément de l’interface utilisateur actuellement ciblé. L’indicateur correspond à une bordure bleue autour de l’élément sélectionné.

   ![Indicateur de ciblage](assets/focus-indicator.png)

### Navigation au clavier pour les interactions de glisser-déposer

[!UICONTROL Analysis Workspace] est une interface utilisateur de glisser-déposer. Cependant, les utilisateurs peuvent également ajouter des composants à l’aide du clavier :

1. Appuyez sur la touche de tabulation pour atteindre un composant dans le rail de gauche.
1. Appuyez sur `Enter` pour le sélectionner.
1. Utilisez les touches de direction pour accéder à la zone où vous souhaitez déposer le composant.
1. Appuyez sur `Enter` pour déposer le composant.

### Raccourcis clavier (touches de raccourci)

[!UICONTROL Analysis Workspace] offre un vaste ensemble de [raccourcis clavier](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) pour accélérer le processus. Voici quelques raccourcis courants pour la navigation, la création d’analyses et la démocratisation des informations.

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
| Maintenir la touche Maj enfoncée (dans la zone de dépôt des segments du panneau) | Créer un [filtre déroulant](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html) |

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

En outre, les utilisateurs peuvent définir leur propre palette de couleurs préférée pour un projet sous **[!UICONTROL Projet]** > **[!UICONTROL Paramètres du projet]** > [Palette de couleurs du projet](/help/analysis-workspace/build-workspace-project/color-palettes.md).

## Validation des champs obligatoires dans les créateurs de composants

Lorsque vous créez un composant, les champs obligatoires sont validés lors de l’enregistrement. Si un champ obligatoire n’est pas validé, il est signalé en rouge avec une icône d’erreur. Une description écrite du problème à résoudre apparaît.

Une fois qu’un composant est entièrement validé, appuyez sur `Save` pour fermer le créateur.

![Validation d’erreur](assets/error-validation.png)

## Prise en charge des fonctionnalités d’accessibilité du système d’exploitation

Analysis Workspace prend en charge les fonctionnalités d’accessibilité intégrées à MS Windows et macOS, telles que le mode contraste élevé, les touches rémanentes et les touches lentes/filtres. Il fournit également des informations sur l’interface utilisateur du système d’exploitation pour permettre l’interaction avec les technologies d’assistance, y compris les lecteurs d’écran tels que VoiceOver pour macOS et NVDA sous Windows.