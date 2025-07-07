---
description: Découvrez comment traiter les projets dans Analysis Workspace. Le traitement limite l’accès aux composants avant le partage d’un projet.
keywords: Traitement d’Analysis Workspace
title: Traiter des projets
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
source-git-commit: 084c995658a5cf698d253f1c15229f621a8c55d5
workflow-type: ht
source-wordcount: '500'
ht-degree: 100%

---

# Traitement des projets

Le traitement vous permet de limiter les composants (dimensions, mesures, segments, périodes) avant de partager un projet. Lorsqu’une personne destinataire ouvre le projet, elle voit un ensemble limité de composants que vous avez traités à sa place. Le traitement est une étape facultative mais recommandée avant de partager un projet.

>[!NOTE]
> Les profils de produit constituent le principal mécanisme contrôlant ce que voit un utilisateur. Ils sont gérés via l’[Admin Console pour Adobe Experience Cloud](https://experienceleague.adobe.com/fr/docs/core-services/interface/administration/admin-tool-experience-cloud). Le traitement est un segment secondaire.

## Appliquer le traitement du projet

1. Sélectionnez **[!UICONTROL Partager]** > **[!UICONTROL Traiter les données du projet]**.
Les composants utilisés dans le projet sont automatiquement ajoutés.
Si un projet comporte plusieurs vues de données, une cible de dépôt de traitement s’affiche pour chaque vue de données du projet.
1. (Facultatif) Pour ajouter d’autres composants, faites glisser ceux que vous souhaitez partager du panneau de gauche vers la zone de dépôt **[!UICONTROL Traiter les composants]** pour la vue de données.
1. Sélectionnez **[!UICONTROL Terminé]**.

<!--
Curation can also be applied from the [!UICONTROL Share] menu by selecting **[!UICONTROL Curate and Share]**. This option automatically curates the project to the components in use in the project. You can add additional components following the steps above.
-->

![Fenêtre Traiter les composants présentant les composants utilisés dans le projet.](assets/curation-field.png)

Lorsqu’une personne destinataire ouvre un projet traité, elle ne voit que l’ensemble de composants traités que vous avez définis :


## Suppression du traitement du projet

Pour supprimer le traitement du projet et restaurer l’ensemble complet des composants dans le panneau de gauche, procédez comme suit :

1. Sélectionnez **[!UICONTROL Partager]** > **[!UICONTROL Traiter les données du projet]**.
1. Sélectionnez **[!UICONTROL Supprimer le traitement]**.
1. Sélectionnez **[!UICONTROL Terminé]**.

## Options de traitement des composants

Dans un projet traité, la personne destinataire a la possibilité de **[!UICONTROL Tout afficher]** dans le panneau de gauche. [!UICONTROL Tout afficher] révèle différents ensembles de composants, en fonction des éléments suivants :

* Niveau d’autorisation de l’utilisateur ou l’utilisatrice (faisant ou non partie de l’équipe d’administration)
* Rôle du projet (personne propriétaire/éditrice ou non)
* Type de traitement appliqué (au niveau du projet)

| Type de traitement | Visible par l’administrateur | Visible par le propriétaire du projet non administrateur (ou rôle Éditeur) | Visible par le rôle dupliqué non administrateur |
| --- | --- | --- | --- |
| **Composants *masqués* dans une vue de données** | Tous les composants de la vue de données sont disponibles pour la création de rapports (sélectionnez **[!UICONTROL Tout afficher]** pour afficher les composants masqués). | Non disponible pour la création de rapports | Non disponible pour la création de rapports |
| **Composants ajoutés ou supprimés d’une vue de données** | Seuls les composants ajoutés à la vue de données (masqués ou non). Les administrateurs et administratrices ne peuvent pas créer de rapports sur des champs ou des composants qui ne sont pas définis dans la vue de données. | Seuls les composants ajoutés à la vue de données ou les composants appartenant à la personne ou partagés avec elle. Les composants masqués ne sont pas disponibles (comme le traitement des suites de rapports virtuelles). | Seuls les composants qui ont été ajoutés à la vue de données ne sont pas masqués et sont inclus dans le traitement du projet. |
| **Composants traités dans un projet** | Tous les composants de la vue de données qui sont disponibles pour la création de rapports (sélectionnez **[!UICONTROL Tout afficher]** pour afficher les composants masqués). | Tous les composants non masqués de la vue de données (pour les afficher, cliquez sur « Tout afficher »). | Seuls les composants traités, plus tous les composants appartenant à lʼutilisateur ou partagés avec lui. |
| **Projet traité utilisant une vue de données avec des composants masqués** | Tous les composants de données qui sont disponibles pour la création de rapports (sélectionnez **[!UICONTROL Tout afficher]** pour afficher les composants masqués et non traités). | Tous les composants non traités du projet, tous les composants non masqués de la vue de données et tous les composants appartenant à lʼutilisateur ou partagés avec lui. | Seuls les composants traités, plus tous les composants appartenant à lʼutilisateur ou partagés avec lui. |
