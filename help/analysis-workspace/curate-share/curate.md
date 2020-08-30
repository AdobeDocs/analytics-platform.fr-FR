---
description: Le traitement permet de limiter les composants avant de partager un projet.
keywords: Analysis Workspace curation
title: Traitement des projets Workspace
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 100%

---


# Traitement des projets Workspace

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

Le traitement vous permet de limiter les composants (dimensions, mesures, segments, périodes) avant de partager un projet. Lorsqu’un destinataire ouvre le projet, il voit un ensemble limité de composants que vous avez traités à sa place. Le traitement est une étape facultative mais recommandée avant de partager un projet.

>[!NOTE]
> Les profils de produit constituent le principal mécanisme contrôlant ce que voit un utilisateur. Ils sont gérés via l’Admin Console pour Adobe Experience Cloud. Le traitement est un filtre secondaire.

## Application du traitement du projet

1. Cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Traiter les données du projet]**.
Les composants utilisés dans le projet seront automatiquement ajoutés.
   **Remarque** : si un projet comporte plusieurs suites de rapports, un champ de traitement s’affiche pour chaque suite de rapports du projet.
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

## Traitement des suites de rapports virtuelles

Pour appliquer le traitement au niveau d’une suite de rapports, de sorte qu’elle s’applique simultanément à de nombreux projets, vous pouvez [traiter des composants dans une suite de rapports virtuelle](https://docs.adobe.com/content/help/fr-FR/analytics/components/virtual-report-suites/vrs-components.html).

>[!NOTE]
> Le traitement des suites de rapports virtuelles est toujours appliqué avant le traitement du projet. Cela signifie que même si votre projet traité inclut certains composants, ils seront exclus si la suite de rapports virtuelle traitée ne les inclut pas.

## Option Afficher tous les composants

Dans un projet traité ou une suite de rapports virtuelle, le destinataire aura la possibilité de **[!UICONTROL Tout afficher]** dans le rail de gauche. [!UICONTROL Tout afficher] révèle différents ensembles de composants, en fonction des éléments suivants :

* Niveau d’autorisation de l’utilisateur (administrateur ou non)
* Rôle du projet (propriétaire/éditeur ou non)
* Type de traitement appliqué (suite de rapports virtuelle ou projet)

| Type de traitement | Administrateurs | Rôle de propriétaire ou d’éditeur de projet non-administrateur | Rôle de duplication ou d’affichage non-administrateur |
|---|---|---|---|
| Suites de rapports virtuelles non traitées | Tous les composants de suites de rapports virtuelles non traités | Composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés | Composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés |
| Projet traité | Tous les composants de projets non traités | Tous les composants de projets non traités | Composants de projets non traités possédés par ce rôle ou avec lequel ils ont été partagés |
| Projet traité dans une de suite de rapports virtuelle traitée | Tous les composants non traités ci-dessous **[!UICONTROL Composants de projets non traités]** et **[!UICONTROL Composants de suites de rapports virtuelles non traités]** | Tous les composants de projets non traités ET les composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés | Composants de projets et de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés |
