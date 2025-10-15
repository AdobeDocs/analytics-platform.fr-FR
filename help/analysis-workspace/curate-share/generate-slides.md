---
description: Découvrez comment générer des présentations au format pptx à partir de rapports Workspace.
keywords: Analysis Workspace
title: Génération de présentations à partir de rapports Workspace
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 680799fdf18703acbd0569e25b41e6ecbc154d62
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 3%

---

# Storytelling de données : génération de présentations de diapositives à partir de rapports Workspace {#generate-powerpoint}

Vous pouvez générer automatiquement des présentations .pptx à partir de projets Analysis Workspace. Lors de la génération de présentations, Customer Journey Analytics identifie automatiquement les informations clés et les convertit en diapositives prêtes à l’emploi des parties prenantes.

Cette fonctionnalité réduit le temps et les efforts requis pour rechercher des résultats dans vos projets Workspace. Elle vous permet également de créer rapidement des récits à l’intention des dirigeants et de communiquer l’impact commercial.

## Générer une présentation .pptx basée sur un projet Workspace

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-powerpoint-include-visualizations"
>title="Panneaux et visualisations inclus"
>abstract="Choisissez les panneaux et les visualisations que vous souhaitez inclure dans la présentation. Vous pouvez inclure jusqu’à 50 visualisations."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-presentation-emphasized-components"
>title="Composants mis en évidence"
>abstract="Sélectionnez jusqu’à 5 mesures et 5 dimensions dans vos visualisations, sur lesquelles vous souhaitez mettre l’accent dans la présentation. Les mesures que vous choisissez s’affichent en italique, les dimensions en gras et les éléments de dimension en contraste de couleur."

<!-- markdownlint-enable MD034 -->

1. Accédez au projet Workspace contenant les données que vous souhaitez utiliser comme base de votre présentation.

1. Sélectionnez **[!UICONTROL Générer des diapositives]** dans le coin supérieur droit de la page.

1. Indiquez les informations suivantes :

   | Option | Description |
   |---------|----------|
   | **[!UICONTROL Titre de la couverture]** | Indiquez un titre pour la présentation. Ce titre s&#39;affiche sur la diapositive de titre de la présentation. |
   | **[!UICONTROL Inclure le nom du présentateur]** | Spécifiez le nom du présentateur. Ce nom apparaît sur la diapositive de titre de la présentation, sous le titre de couverture. |
   | **[!UICONTROL Panneaux et visualisations à inclure]** | Choisissez les panneaux et la visualisation à inclure dans la présentation. Vous pouvez inclure jusqu’à 50 visualisations.<p>La plupart des panneaux et des visualisations sont pris en charge. Pour plus d’informations sur les panneaux et les visualisations non pris en charge, voir [Éléments et fonctionnalités de projet non pris en charge](#unsupported-project-elements-and-features).</p> |
   | **[!UICONTROL Descriptions des panneaux et des visualisations]** | |
   | **[!UICONTROL Annotations]** | |
   | **[!UICONTROL Mettre en gras les composants]** | Sélectionnez jusqu’à 5 mesures et 5 dimensions dans vos visualisations, sur lesquelles vous souhaitez mettre l’accent dans la présentation.<p>Lorsque aucun accent n’est mis, les composants s’affichent dans les présentations comme suit :<ul><li>**Mesures et dimensions :** italique</li><li>**Éléments Dimension :** guillemets</li></ul></p><p>Lorsque l’accent est mis, les composants s’affichent dans les présentations comme suit :</p><ul><li>**Mesures et dimensions :** italiques et gras</li><li>**Éléments Dimension :** gras lorsque la dimension correspondante est mise en évidence<p>Une couleur est également appliquée à l’élément de dimension lorsque celui-ci est mis en surbrillance dans le graphique.</p></li></ul> |

(Conditionnel) Sélectionnez **[!UICONTROL Thème par défaut]** si vous souhaitez que vos diapositives soient générées avec le thème par défaut.

1. Choisissez d’utiliser un thème par défaut ou de charger un modèle personnalisé :

   * **[!UICONTROL Thème par défaut]** :

   * **[!UICONTROL Charger le modèle]** :





## Modifier les diapositives d&#39;une présentation générée précédemment


## Télécharger une présentation .pptx générée

## Éléments et fonctionnalités de projet non pris en charge {#unsupported}

Les éléments et fonctionnalités Analysis Workspace suivants utilisés dans un projet ne sont pas pris en charge lors de la génération de diapositives :

* Panneau d’attribution

  Ce panneau s’affiche en grisé lorsque les options de configuration s’affichent.

  Tous les autres panneaux peuvent être inclus dans les diapositives générées à partir d’un projet Workspace.

* Quelques visualisations

  La plupart des visualisations peuvent être incluses dans les diapositives générées à partir d’un projet Workspace. Toutefois, les visualisations suivantes ne peuvent pas être incluses et s’affichent en grisé lorsque les options de configuration sont affichées :

   * Table de cohorte

   * Zone de travail de parcours

   * Puces

   * Combo

   * Nuage de points

   * Plan en arborescence

* Répartitions

* Analyses guidées


