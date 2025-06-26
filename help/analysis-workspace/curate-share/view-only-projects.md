---
description: Projets en lecture seule dans Workspace
keywords: Projets en lecture seule
title: Projets en lecture seule
feature: Curate and Share
exl-id: 2bc26444-aeea-4695-92a5-a2b45ac18e0d
role: User
source-git-commit: a462e736ddcdf1a5ea84a85eea2c2ce0b8a34fb0
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 37%

---

# Projets en lecture seule

Vous pouvez partager des projets en lecture seule avec les destinataires via la fonctionnalité [partager](/help/analysis-workspace/curate-share/share-projects.md). Les destinataires dont le rôle est **[!UICONTROL Lecture seule]** bénéficieront d&#39;une expérience de projet plus limitée.

Cela peut être souhaitable si vous partagez un projet avec des utilisateurs qui sont moins familiers avec la structure de données de votre organisation, Analysis Workspace ou Customer Journey Analytics en général, mais que vous souhaitez tout de même qu’ils puissent consommer des données et des informations dans un environnement sûr.

![Partager en lecture seule](assets/read-only-project-sender.png)

Les interactions pour les destinataires en lecture seule sont limitées.

![Partager en lecture seule reçu](assets/read-only-project-receiver.png)

## Interactions désactivées

Les interactions désactivées dans un projet en lecture seule sont les suivantes :

* Panneau de gauche masqué
* Période du calendrier du panneau. Remarque : si vous souhaitez accorder le contrôle de calendrier aux destinataires, ajoutez un [segment déroulant avec des périodes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=fr).
* Segmentation à structure libre
* Nombre de lignes visibles de la structure libre
* Paramètres de ligne, de colonne ou de visualisation à structure libre
* Segments de panneau
* Menus Modifier, Insérer et Composant
* Conseils relatifs à Workspace

## Interactions activées

Voici quelques-unes des interactions activées les plus intéressantes dans un projet en lecture seule :

| Zone | Interactions activées |
| --- | --- |
| Tableaux à structure libre | <ul><li>Pagination et tri</li><li>Survol</li><li>Sélections de cellules qui mettent à jour les visualisations liées</li><li>À partir du menu contextuel > Obtenir le lien de la visualisation</li><li>À partir du menu contextuel > Copier dans le presse-papiers</li></ul> |
| Visualisations | <ul><li>Clic pour activer/désactiver la légende</li><li>Survol</li><li>À partir du menu contextuel > Obtenir le lien de la visualisation</li><li>Réduire/Développer</li><li>Flux - développer les nœuds de flux</li><li>Carte - zoom</li></ul> |
| Panneaux | <ul><li>Segments déroulants interactifs</li><li>À partir du menu contextuel > Obtenir le lien du panneau</li><li>Réduire/Développer</li></ul> |
| Projet | <ul><li>Inspection de toutes les icônes d’informations</li><li>Menu Projet - Nouveau, Ouvrir, Définir comme page de destination, Actualiser, Télécharger CSV/PDF, Informations et paramètres limités du projet</li><li>Menu Partager - Obtenir le lien du projet, Envoyer le fichier maintenant</li><li>Menu Aide - Toutes les actions à l’exception des options Conseils et Débogueur</li></ul> |


## Partager avec tout le monde l’expérience

Si vous avez sélectionné un projet à l’aide de l’option [Partager avec tout le monde](share-projects.md#share-a-project-with-anyone-no-login-required) le destinataire du lien peut uniquement afficher le projet et ne pas interagir avec celui-ci.

![Partagez votre expérience avec tout le monde](assets/share-with-anyone-receiver.png)
