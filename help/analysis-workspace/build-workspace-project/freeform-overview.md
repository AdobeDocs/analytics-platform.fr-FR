---
description: Présentation des projets Workspace avec la barre de menus et les paramètres
keywords: Analysis Workspace
title: Présentation des projets
feature: CJA Workspace Basics
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '1165'
ht-degree: 91%

---

# Présentation des projets

Les projets Workspace vous permettent de combiner des composants de données, des tableaux et des visualisations afin d’élaborer votre analyse et de la partager avec qui vous le souhaitez au sein de votre entreprise. Avant de démarrer votre premier projet, découvrez comment accéder à vos projets, les parcourir et les gérer.

## Liste de projets {#project-list}

Quand vous sélectionnez **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** pour la première fois, la page répertorie tous les projets dont vous êtes propriétaire ou qui ont été partagés avec vous. Il s’agit également de la landing page d’Adobe Analytics, sauf si vous avez précédemment défini une landing page personnalisée.

![](assets/sample-project.png)

La page de liste de projets Workspace présente les informations suivantes :

| Élément | Description |
|---|---|
| [Créer un projet](/help/analysis-workspace/home.md) | Cliquez sur ce lien pour démarrer un projet entièrement nouveau. |
| Gérer les projets | Cliquez sur ce lien pour accéder au Gestionnaire de composants des projets (**[!UICONTROL Analytics]** > **[!UICONTROL Composants]** > **[!UICONTROL Projets]**), où sont répertoriés tous les projets et où vous pouvez baliser, partager, supprimer, renommer, approuver ou copier les projets et les exporter au format CSV. |
| Définir comme page d’entrée | Transforme cette page en page de destination Workspace. |
| [Afficher les tutoriels](/help/analysis-workspace/home.md) | Permet d’accéder aux tutoriels vidéos Analysis Workspace. |
| Nom | Nom du projet de Workspace. |
| Propriétaire | Personne qui a créé ce projet (vous ou quelqu’un qui a partagé le projet avec vous). |
| Type | Indique s’il s’agit d’un projet Workspace ou d’une [fiche d’évaluation mobile](/help/mobile-app/home.md). |
| [Rôle de projet](/help/analysis-workspace/curate-share/share-projects.md) | Indique votre rôle pour ce projet : propriétaires, modifier, dupliquer, afficher. |
| Balises | Balises appliquées au projet. |
| Dernière modification | Date et heure de dernière modification du projet. |
| Mes projets favoris | Pour marquer un projet comme favori, ouvrez le projet et cliquez sur l’étoile en regard de son nom. Il s’affichera dans cette liste la prochaine fois que vous ouvrirez Workspace. |
| Projets fréquemment consultés | Répertorie tous les projets que vous ouvrez fréquemment, pour en faciliter l’accès. |

## Barre de menus {#menu-bar}

Dans un projet, le menu fournit des options relatives à la gestion du projet, à l’ajout de composants, à la recherche d’aide et bien plus. Chaque option de menu est également accessible à partir des [raccourcis](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) clavier.

![](assets/menu.png)

| Élément de menu | Description |
|---|---|
| Projet   | Inclut des actions courantes pour la gestion de projet, notamment Nouveau, Ouvrir, Enregistrer, Enregistrer sous et Enregistrer comme modèle. Vous pouvez également actualiser l’intégralité du projet pour récupérer les données et définitions les plus récentes en cliquant sur Actualiser le projet. Les options de [téléchargement CSV et PDF](/help/analysis-workspace/curate-share/download-send.md) vous permettent d’exporter des données à partir de Workspace. **Informations et paramètres du projet** (voir ci-dessous) offre de nombreuses options pour gérer votre projet. |
| Modifier | Annulez ou rétablissez votre dernière action. L’option Effacer tout réinitialise le point de départ de votre projet. |
| Insérer | Insérez de nouveaux panneaux ou de nouvelles visualisations à partir de ce menu. Vous pouvez également insérer de nouveaux panneaux et de nouvelles visualisations à partir du rail de gauche. |
| [Composants](/help/components/overview.md) | Créez de nouveaux filtres, mesures calculées, périodes ou composants d’alerte à partir de votre projet. Vous pouvez également créer des composants à partir du rail de gauche. Si vos définitions de composants ont été récemment modifiées, l’option Actualiser les composants récupère les dernières définitions. |
| [Partager](/help/analysis-workspace/curate-share/send-schedule-files.md) | Traitez, partagez et planifiez des projets PDF/CSV pour les destinataires de votre entreprise. |
| Aide | Accédez à la documentation d’aide, aux vidéos et à la [communauté Experience League](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=fr) d’Analytics. Gérez la visibilité des conseils relatifs à Workspace ainsi que le [débogueur](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md). Recherchez des informations détaillées sur Workspace et sur les facteurs qui affectent les [performances](/help/analysis-workspace/workspace-faq/optimizing-performance.md) du projet. |
| Bouton Partager ou Propriétaire | Si vous disposez du rôle Propriétaire ou Modifier pour le projet, le bouton Partager situé dans le coin supérieur droit vous permet d’accéder en un clic à la gestion des destinataires de votre projet. Si vous disposez d’un rôle Dupliquer ou Afficher pour ce projet, le nom du propriétaire du projet s’affiche. |

### Informations et paramètres du projet {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Projet]** > **[!UICONTROL Informations et paramètres du projet]**   fournit des informations au niveau du projet sur le projet actuellement actif.

![](assets/projectinfo.png)

Les paramètres incluent :

| Paramètre | Description |
|---|---|
| Projet   Nom | Nom donné au projet. Double-cliquez dessus pour le modifier. |
| Créée par | Nom du titulaire du projet. |
| Dernière modification | Date de la dernière modification du projet. |
| Balises | Répertorie les balises appliquées à un projet afin de faciliter la catégorisation. |
| Description | Une description est utile pour clarifier l’objet d’un projet. Double-cliquez dessus pour la modifier. |
| Compter les instances répétées | Ce paramètre indique si les instances répétées sont comptabilisées dans les rapports. Remarque : ce paramètre ne s’applique pas aux visualisations de flux ou d’abandons. |
| [Palette de couleurs du projet](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Vous pouvez modifier la palette de couleurs catégoriques utilisée dans Workspace en choisissant parmi les palettes prêtes à l’emploi qui ont été optimisées pour le daltonisme ou en spécifiant votre palette personnalisée. Cette fonction affecte de nombreux éléments dans Workspace, y compris la plupart des visualisations. |
| [Densité d’affichage](/help/analysis-workspace/build-workspace-project/view-density.md) | Permet de voir plus de données sur l’écran en réduisant l’espacement vertical du rail gauche, dans les tableaux à structure libre et dans les tableaux de cohortes. |

## Rail de gauche {#left-rail}

Dans un projet, les [panneaux](/help/analysis-workspace/c-panels/panels.md), les tableaux, les [visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) et les [composants] sont accessibles à partir du rail de gauche. Ce sont les blocs de construction de votre projet.

Vous pouvez également accéder aux visualisations et aux panneaux à partir du [panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md).

Les composants (Dimensions, Mesures, Filtres, Périodes) du rail de gauche sont associés à la principale vue de données du panneau. Le panneau principal comporte une bordure bleue et la principale vue de données est répertoriée en haut du rail du composant.

![](assets/left-rail.png)

## Canevas de projet {#canvas}

Le canevas du projet est l’emplacement où vous rassemblez des panneaux, des tableaux, des visualisations et des composants pour créer votre analyse. Un projet peut contenir de nombreux panneaux et chaque panneau peut contenir de nombreux tableaux et visualisations.

Les panneaux sont utiles pour organiser vos projets en fonction des périodes, des vues de données ou des cas pratiques dʼanalyses. Le panneau principal comporte une bordure bleue et détermine les composants disponibles dans le rail de gauche.

Selon le point de départ choisi pour vos projets, le canevas comporte soit un [panneau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), soit un [panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md) au démarrage. Le moyen le plus rapide de démarrer une analyse consiste à sélectionner un ou plusieurs composants, puis tout simplement à les faire glisser et les déposer dans le canevas du projet. Un tableau de données est alors automatiquement rendu. [En savoir plus](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) sur les différentes options de création d’un tableau ou sur la manière de tirer parti de notre [tutoriel de formation](/help/analysis-workspace/home.md) pour apprendre à créer votre premier projet.

![](assets/canvas.png)

## Chef de projets {#manager}

Les projets Analysis Workspace peuvent être gérés sous **Analytics > Composants > Projets**. Le Gestionnaire de projets affiche les éléments créés par un utilisateur spécifique. La propriété du projet peut être transférée à un nouvel utilisateur sous Admin > Utilisateurs et ressources Analytics > Transférer les ressources.

Le Gestionnaire de projets vous permet d’ajouter, baliser, partager, dupliquer/copier et bien plus encore. Utilisez la barre de recherche ou les options de filtre dans le rail de gauche pour rechercher un projet. Vous pouvez filtrer par balise, propriétaires, type de projet et bien d’autres.

![](assets/project-manager.png)

Voici les actions courantes du Gestionnaire de projets, qui peuvent être exécutées simultanément sur un ou plusieurs projets :

| Action | Description |
|---|---|
| Ajouter | Créez un projet à partir de zéro. |
| Baliser ou approuver | Choisissez « Baliser » ou « Approuver » pour organiser vos projets et en faciliter la recherche. |
| [Partager](/help/analysis-workspace/curate-share/share-projects.md) | Rend un projet disponible pour d’autres utilisateurs d’Analysis Workspace de votre entreprise. |
| Supprimer | Supprimez votre projet. |
| Renommer | Modifiez le nom de votre projet. |
| Copier | Créez un doublon du projet. Cela crée un projet ainsi qu’un identifiant de projet. Les partages ou les planifications liés au projet d’origine ne sont pas copiés. |
| Exporter dans un fichier CSV | Téléchargez votre projet sous forme de fichier CSV, qui inclut les données en texte brut. |
