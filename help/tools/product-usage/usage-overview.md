---
title: Vue d’ensemble de l’utilisation du produit
description: Affichez des informations et des rapports sur la manière dont votre organisation utilise Customer Journey Analytics.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: a4615907f61b4d63393a9481fdd7b45b7b9b6262
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 100%

---

# Vue d’ensemble de l’utilisation du produit

L’utilisation des produits permet à votre entreprise d’afficher des données d’analyse sur la manière dont elle utilise Customer Journey Analytics. Elle est disponible pour toutes les organisations qui utilisent Customer Journey Analytics. Une fois activés, les composants Adobe Experience Platform suivants sont automatiquement créés et connectés. Ces composants sont tous détenus par le système, en lecture seule et ne peuvent pas être modifiés.

* Schéma dans Adobe Experience Platform
* Jeu de données dans Adobe Experience Platform
* Connexion dans Customer Journey Analytics
* Vue de données dans Customer Journey Analytics

Une fois activées, toutes les opérations de collecte et de configuration des données sont automatiquement configurées. Chaque fois qu’une personne effectue une action dans Analysis Workspace, cette action est suivie et disponible pour la création de rapports.

>[!IMPORTANT]
>
>Cette fonctionnalité est prise en compte dans les limites de lignes contractuelles de Adobe Experience Platform. Assurez-vous que votre entreprise peut prendre en charge les données générées par cette fonctionnalité avant de l’activer.

## Activer l’utilisation du produit

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Outils]** > **[!UICONTROL Utilisation du produit]**

En accédant à cette section de l’interface dans Customer Journey Analytics, vous accédez à [Paramètres des données](data-settings.md) où vous pouvez activer cette fonctionnalité.

## Dimensions disponibles

Lorsque vous activez Utilisation du produit, les dimensions suivantes sont disponibles. Si vous souhaitez modifier des paramètres de dimension, créez une copie de la vue de données appartenant au système et utilisez la vue de données copiée dans Analysis Workspace.

* **[!UICONTROL Nom de l’action]** : type d’action entreprise par la personne. Vous pouvez utiliser cette dimension comme toute mesure souhaitée en créant une copie dans les paramètres de la vue de données. Les éléments de dimension comprennent ce qui suit :
   * [!UICONTROL Ajouter une attribution]
   * [!UICONTROL Ajouter un composant]
   * [!UICONTROL Ajouter le panneau]
   * [!UICONTROL Ajouter une visualisation]
   * [!UICONTROL Créer une analyse guidée]
   * [!UICONTROL Créer un projet]
   * [!UICONTROL Traiter les composants]
   * [!UICONTROL Téléchargement de fichier CSV]
   * [!UICONTROL Télécharger le PDF]
   * [!UICONTROL Charger l’analyse guidée]
   * [!UICONTROL Charger le projet]
   * [!UICONTROL Nouvelle carte de performance chargée]
   * [!UICONTROL Ouvrir le dictionnaire de données]
   * [!UICONTROL Ouvrir des légendes intelligentes]
   * [!UICONTROL Partage de projet]
   * [!UICONTROL Exécuter le panneau Expérimentation]
   * [!UICONTROL Enregistrer le projet]
   * [!UICONTROL Carte de performance enregistrée ]
   * [!UICONTROL Envoyer un fichier]
   * [!UICONTROL Envoyer le fichier selon le planning]
   * [!UICONTROL Partager le projet avec tout le monde]
   * [!UICONTROL Partager le projet avec les utilisateurs et utilisatrices de Workspace]
* **[!UICONTROL Modèle d’attribution utilisé]** : type de modèle d’attribution utilisé par le composant. Les éléments de dimension comprennent ce qui suit :
   * [!UICONTROL Dernière touche]
   * [!UICONTROL Première touche]
   * [!UICONTROL Linéaire]
   * [!UICONTROL Participation]
   * [!UICONTROL Même touche]
   * [!UICONTROL En forme de U]
   * [!UICONTROL Courbe en J]
   * [!UICONTROL Inverse J]
   * [!UICONTROL Atténuation temporelle]
   * [!UICONTROL Personnalisé]
   * [!UICONTROL Algorithmique]
* **[!UICONTROL Nom du composant]** : nom du composant qui a été ajouté, supprimé ou modifié.
* **[!UICONTROL Type de composant]** : type de composant qui a été ajouté, supprimé ou modifié. Les éléments de dimension comprennent ce qui suit :
   * [!UICONTROL Dimension]
   * [!UICONTROL Mesure]
   * [!UICONTROL Segment]
   * [!UICONTROL Mesure calculée]
   * [!UICONTROL Période]
   * [!UICONTROL Annotation]
   * [!UICONTROL Alerte]
* **[!UICONTROL Utilisateur ou utilisatrice de connexion]** : utilisateur ou utilisatrice qui a effectué l’action.
* **[!UICONTROL Panneau utilisé]** : panneau dans lequel le composant a été ajouté, supprimé ou modifié. Les éléments de dimension comprennent ce qui suit :
   * [!UICONTROL Attribution]
   * [!UICONTROL Panneau vierge]
   * [!UICONTROL Expérimentation]
   * [!UICONTROL Structure libre]
   * [!UICONTROL Élément suivant ou précédent]
   * [!UICONTROL Aperçu rapide]
   * [!UICONTROL Tendances]
   * [!UICONTROL Entonnoir]
   * [!UICONTROL Croissance des utilisateurs et des utilisatrices]
   * [!UICONTROL Impact]
   * [!UICONTROL Flux d’utilisateur ou d’utilisatrice]
   * [!UICONTROL Rétention]
   * [!UICONTROL Matrice des fonctionnalités]
* **[!UICONTROL Nom du projet]** : nom convivial du projet.
* **[!UICONTROL Type de projet]** : type de projet. Les éléments de dimension comprennent ce qui suit :
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL Visualisation utilisée]** : visualisation qui a été ajoutée, supprimée ou modifiée. Les éléments de dimension comprennent ce qui suit :
   * [!UICONTROL Tableau à structure libre]
   * [!UICONTROL Table de cohorte]
   * [!UICONTROL Abandon]
   * [!UICONTROL Flux]
   * [!UICONTROL Petit rapport de Zone de travail de parcours]
   * [!UICONTROL Surface]
   * [!UICONTROL Aires empilées]
   * [!UICONTROL Barre]
   * [!UICONTROL Barres empilées]
   * [!UICONTROL Puces]
   * [!UICONTROL Combo]
   * [!UICONTROL Anneau]
   * [!UICONTROL Histogramme]
   * [!UICONTROL Barre horizontale]
   * [!UICONTROL Barres horizontales empilées]
   * [!UICONTROL Synthèse des mesures clés]
   * [!UICONTROL Ligne]
   * [!UICONTROL Carte]
   * [!UICONTROL Dispersion]
   * [!UICONTROL En-tête de section]
   * [!UICONTROL Résumé des changements]
   * [!UICONTROL Numéro de résumé]
   * [!UICONTROL Texte]
   * [!UICONTROL Treemap]
   * [!UICONTROL Venn]

L’utilisation du produit ne suit pas les composants individuels d’un projet lorsqu’un projet est simplement ouvert ou affiché. L’action de l’utilisateur ou de l’utilisatrice lors de l’ouverture d’un projet est toutefois suivie.

## Modèle disponible

Un [modèle Adobe](/help/analysis-workspace/templates/use-templates.md) qui utilise les composants générés automatiquement à partir de cette fonctionnalité, est disponible.

**[!UICONTROL Modèles Adobe]** > **[!UICONTROL Autre]** > **[!UICONTROL Vue d’ensemble de l’utilisation du produit]**

Sélectionnez la vue de données que l’utilisation du produit a automatiquement créée dans le sélecteur de vue de données, puis sélectionnez le modèle **[!UICONTROL Vue d’ensemble de l’utilisation du produit]**. Sélectionnez **[!UICONTROL Aperçu]** pour voir quels panneaux le modèle utilise et en savoir plus sur les cas d’utilisation pertinents, ou sélectionnez **[!UICONTROL Utiliser le modèle]** à ouvrir dans Analysis Workspace.
