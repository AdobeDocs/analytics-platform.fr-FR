---
description: Le traitement permet de limiter les composants avant de partager un projet.
keywords: Traitement d’Analysis Workspace
title: Traitement des projets
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '493'
ht-degree: 100%

---

# Traitement des projets

Le traitement vous permet de limiter les composants (dimensions, mesures, filtres, périodes) avant de partager un projet. Lorsqu’un destinataire ouvre le projet, il voit un ensemble limité de composants que vous avez traités à sa place. Le traitement est une étape facultative mais recommandée avant de partager un projet.

>[!NOTE]
> Les profils de produit constituent le principal mécanisme contrôlant ce que voit un utilisateur. Ils sont gérés via l’[Admin Console pour Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr). Le traitement est un filtre secondaire.

## Application du traitement du projet

1. Cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Traiter les données du projet]**.
Les composants utilisés dans le projet seront automatiquement ajoutés.
1. (Facultatif) Pour ajouter d’autres composants, faites glisser les composants que vous souhaitez partager depuis le rail de gauche vers le champ [!UICONTROL Traiter les composants].
1. Cliquez sur **[!UICONTROL Terminé]**.

Le traitement peut également être appliqué à partir du menu [!UICONTROL Partager] en cliquant sur **[!UICONTROL Traiter et partager]**. Cette option traite automatiquement le projet en fonction des composants utilisés dans ce dernier. Vous pouvez ajouter d’autres composants en suivant les étapes ci-dessus.

![](assets/curation-field.png)

## Affichage du projet traité

Lorsqu’un destinataire ouvre un projet traité, il ne voit que l’ensemble de composants traités que vous avez définis :

![](assets/curate-project.png)

## Suppression du traitement du projet

Pour supprimer le traitement du projet et restaurer l’ensemble complet des composants dans le rail de gauche :

1. Cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Traiter les données du projet]**.
1. Cliquez sur **[!UICONTROL Supprimer le traitement]**.
1. Cliquez sur **[!UICONTROL Terminé]**.

## Options de traitement des composants

Dans un projet traité, le destinataire a la possibilité de **[!UICONTROL Tout afficher]** dans le rail de gauche. [!UICONTROL Tout afficher] révèle différents ensembles de composants, en fonction des éléments suivants :

* Niveau d’autorisation de l’utilisateur (administrateur ou non)
* Rôle du projet (propriétaire/éditeur ou non)
* Type de traitement appliqué (au niveau du projet)

| Type de traitement | Visible par l’administrateur | Visible par le propriétaire du projet non administrateur (ou rôle Éditeur) | Visible par le rôle dupliqué non administrateur |
| --- | --- | --- | --- |
| **Composants « masqués » dans une vue de données** | Tous les composants de la vue de données disponibles pour la création de rapports (cliquez sur « Tout afficher » pour afficher les composants masqués). | Non disponible pour la création de rapports | Non disponible pour la création de rapports |
| **Composants ajoutés ou supprimés d’une vue de données** | Seuls les composants ajoutés à la vue de données (masqués ou non). Les administrateurs ne peuvent pas créer de rapports sur des champs ou des composants qui ne sont pas définis par la vue de données. | Seuls les composants ajoutés à la vue de données ou les composants appartenant à l’utilisateur ou partagés avec lui. Les composants masqués ne sont pas disponibles (comme le traitement des suites de rapports virtuelles). | Seuls les composants qui ont été ajoutés à la vue de données, qui ne sont pas masqués et qui ont été inclus dans le traitement du projet. |
| **Composants traités dans un projet** | Tous les composants de la vue de données disponibles pour la création de rapports (cliquez sur « Tout afficher » pour afficher les composants masqués). | Tous les composants non masqués de la vue de données (pour les afficher, cliquez sur « Tout afficher »). | Seuls les composants traités, plus tous les composants appartenant à lʼutilisateur ou partagés avec lui. |
| **Projet traité utilisant une vue de données avec des composants masqués** | Tous les composants de données disponibles pour la création de rapports (cliquez sur « Tout afficher » pour afficher les composants masqués et non traités). | Tous les composants non traités du projet, tous les composants non masqués de la vue de données et tous les composants appartenant à lʼutilisateur ou partagés avec lui. | Seuls les composants traités, plus tous les composants appartenant à lʼutilisateur ou partagés avec lui. |
