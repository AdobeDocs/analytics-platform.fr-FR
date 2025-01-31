---
title: Vue d’ensemble de l’utilisation du produit
description: Affichez des informations et des rapports sur l’utilisation de Customer Journey Analytics par votre organisation.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 13%

---

# Vue d’ensemble de l’utilisation du produit

L’utilisation des produits permet à votre entreprise d’afficher des données d’analyse sur la manière dont votre entreprise utilise Customer Journey Analytics. Elle est disponible pour toutes les organisations qui utilisent Customer Journey Analytics. Une fois activés, les composants Adobe Experience Platform suivants sont automatiquement créés et connectés. Ces composants sont tous détenus par le système, en lecture seule et ne peuvent pas être modifiés.

* Un schéma dans Adobe Experience Platform
* Un jeu de données dans Adobe Experience Platform
* Une connexion dans Customer Journey Analytics
* Une vue de données dans Customer Journey Analytics

Une fois activées, toutes les opérations de collecte et de configuration des données sont automatiquement configurées. Chaque fois qu’un utilisateur effectue une action dans Analysis Workspace, cette action est suivie et disponible pour la création de rapports.

>[!IMPORTANT]
>
>Cette fonctionnalité est prise en compte dans les limites de lignes contractuelles de Adobe Experience Platform. Assurez-vous que votre entreprise peut prendre en charge les données générées par cette fonctionnalité avant de l’activer.

## Activer l’utilisation du produit

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Outils]** > **[!UICONTROL Utilisation du produit]**

En accédant à cette section de l’interface dans le Customer Journey Analytics, vous accédez à [Paramètres des données](data-settings.md) où vous pouvez activer cette fonctionnalité.

## Dimensions disponibles

Lorsque vous activez l’utilisation du produit, les dimensions suivantes sont disponibles. Si vous souhaitez modifier des paramètres de dimension, créez une copie de la vue de données appartenant au système et utilisez la vue de données copiée dans Analysis Workspace.

* **[!UICONTROL Nom de l’action]** : type d’action entreprise par l’utilisateur. Vous pouvez utiliser cette dimension comme toute mesure souhaitée en créant une copie dans les paramètres de la vue de données. Les éléments de Dimension sont les suivants :
   * [!UICONTROL Ajouter une attribution]
   * [!UICONTROL Ajouter un composant]
   * [!UICONTROL Ajouter un panneau]
   * [!UICONTROL Ajouter une visualisation]
   * [!UICONTROL Créer une analyse guidée]
   * [!UICONTROL Créer un projet]
   * [!UICONTROL Traitement des composants]
   * [!UICONTROL Téléchargement de fichier CSV]
   * [!UICONTROL Télécharger le PDF]
   * [!UICONTROL Charger l’analyse guidée]
   * [!UICONTROL Charger le projet]
   * [!UICONTROL Nouvelle carte de performance chargée]
   * [!UICONTROL Ouvrir le dictionnaire de données]
   * [!UICONTROL Ouvrir les légendes intelligentes]
   * [!UICONTROL Partage de projet]
   * [!UICONTROL Exécuter le panneau Expérimentation]
   * [!UICONTROL Enregistrer le projet]
   * [!UICONTROL  Carte de score enregistrée ]
   * [!UICONTROL Envoyer un fichier]
   * [!UICONTROL Envoyer le fichier selon le calendrier]
   * [!UICONTROL Partager le projet avec tout le monde]
   * [!UICONTROL Partager le projet avec des utilisateurs de Workspace]
* **[!UICONTROL Modèle d’attribution utilisé]** : type de modèle d’attribution utilisé par le composant. Les éléments de Dimension sont les suivants :
   * [!UICONTROL Dernière touche]
   * [!UICONTROL Première touche]
   * [!UICONTROL Linéaire]
   * [!UICONTROL Participation]
   * [!UICONTROL Même touche]
   * [!UICONTROL en U]
   * [!UICONTROL courbe J]
   * [!UICONTROL Inverse J]
   * [!UICONTROL Atténuation temporelle]
   * [!UICONTROL Personnalisé]
   * [!UICONTROL Algorithmique]
* **[!UICONTROL Nom du composant]** : le nom du composant qui a été ajouté, supprimé ou modifié.
* **[!UICONTROL Type de composant]** : le type de composant qui a été ajouté, supprimé ou modifié. Les éléments de Dimension sont les suivants :
   * [!UICONTROL Dimension]
   * [!UICONTROL Mesure]
   * [!UICONTROL Filtrer]
   * [!UICONTROL Mesure calculée]
   * [!UICONTROL Période]
   * [!UICONTROL Annotation]
   * [!UICONTROL Alerte]
* **[!UICONTROL Utilisateur de connexion]** : utilisateur qui a effectué l’action.
* **[!UICONTROL Panneau utilisé]** : panneau dans lequel le composant a été ajouté, supprimé ou modifié. Les éléments de Dimension sont les suivants :
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
* **[!UICONTROL Nom du projet]** : nom convivial du projet.
* **[!UICONTROL Type de projet]** : le type de projet. Les éléments de Dimension sont les suivants :
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL Visualisation utilisée]** : la visualisation qui a été ajoutée, supprimée ou modifiée. Les éléments de Dimension sont les suivants :
   * [!UICONTROL Tableau à structure libre]
   * [!UICONTROL Table de cohorte]
   * [!UICONTROL Abandon]
   * [!UICONTROL Flux]
   * [!UICONTROL Parcours du petit rapport sur la zone de travail]
   * [!UICONTROL Surface]
   * [!UICONTROL Aires empilées]
   * [!UICONTROL Barre]
   * [!UICONTROL Barres empilées]
   * [!UICONTROL Puces]
   * [!UICONTROL Combo]
   * [!UICONTROL Anneau]
   * [!UICONTROL Histogramme]
   * [!UICONTROL Barre horizontale]
   * [!UICONTROL Barres empilées horizontales]
   * [!UICONTROL Résumé des mesures clés ]
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
