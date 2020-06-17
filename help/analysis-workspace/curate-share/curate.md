---
description: Le traitement vous permet de limiter les composants avant de partager un projet.
keywords: Analysis Workspace curation
title: Traiter les projets Workspace
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 35%

---


# Traiter les projets Workspace

>[!NOTE] Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

Le traitement vous permet de limiter les composants (dimensions, mesures, segments, plages de dates) avant de partager un projet. Lorsqu’un destinataire ouvre le projet, il voit un ensemble limité de composants que vous avez traités pour eux. Le traitement est une étape facultative mais recommandée avant de partager un projet.

>[!NOTE]
> Les profils de produit constituent le principal mécanisme contrôlant ce que voit un utilisateur. Ils sont gérés via Adobe Experience Cloud Admin Console. Le traitement est un filtre secondaire.

## Appliquer le traitement du projet

1. Click **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
Les composants utilisés dans le projet seront automatiquement ajoutés.
   **Remarque**: Si un projet comporte plusieurs suites de rapports, un champ de traitement s’affiche pour chaque suite de rapports du projet.
1. (Facultatif) Pour ajouter d’autres composants, faites glisser les composants que vous souhaitez partager depuis le rail de gauche vers le champ [!UICONTROL Traiter les composants] .
1. Cliquez sur **[!UICONTROL Terminé]**.

Le traitement peut également être appliqué à partir du menu [!UICONTROL Partager] en cliquant sur **[!UICONTROL Traiter et Partager]**. Cette option traite automatiquement le projet en fonction des composants utilisés dans le projet. Vous pouvez ajouter d’autres composants en suivant les étapes ci-dessus.

![](assets/curation-field.png)

## vue de projet traitée

Lorsqu’un destinataire ouvre un projet traité, il ne voit que l’ensemble de composants traités que vous avez définis :

![](assets/curate-project.png)

## Supprimer la gestion du projet

Pour supprimer la gestion du projet et restaurer l&#39;ensemble complet des composants dans le rail de gauche :
1. Click **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
1. Cliquez sur **[!UICONTROL Supprimer le traitement]**.
1. Cliquez sur **[!UICONTROL Terminé]**.

## Traitement de la suite de rapports virtuelle

Pour appliquer la gestion au niveau d’une suite de rapports, de sorte qu’elle s’applique simultanément à de nombreux projets, vous pouvez [traiter des composants dans une suite de rapports virtuelle](https://docs.adobe.com/content/help/fr-FR/analytics/components/virtual-report-suites/vrs-components.html).

>[!NOTE]
> Le traitement des suites de rapports virtuelles est toujours appliqué avant le traitement du projet. Cela signifie que même si votre projet traité inclut certains composants, ils seront exclus si la suite de rapports virtuelle traitée ne les inclut pas.

## Afficher tous les composants, option

Dans un projet organisé ou une suite de rapports virtuelle, le destinataire aura la possibilité d&#39; **[!UICONTROL afficher tous les]** composants dans le rail de gauche. [!UICONTROL Tout] afficher révèle différents jeux de composants, en fonction des éléments suivants :

* Niveau d’autorisation de l’utilisateur (administrateur ou non-administrateur)
* Rôle du projet (propriétaire/éditeur ou non)
* Type de traitement appliqué (SRV ou projet)

| Type de traitement | Administrateurs | Propriétaire ou rôle de modification du projet non administrateur | Rôle duplicata ou vue non administrateur |
|---|---|---|---|
| Suites de rapports virtuelles non traitées | Tous les composants de suites de rapports virtuelles non traités | Composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés | Composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés |
| Projet traité | Tous les composants de projets non traités | Tous les composants de projets non traités | Composants de projets non traités possédés par ce rôle ou avec lequel ils ont été partagés |
| Projet traité dans une de suite de rapports virtuelle traitée | Tous les composants non traités ci-dessous  **[!UICONTROL Composants de projets non traités]** et **[!UICONTROL Composants de suites de rapports virtuelles non traités]** | Tous les composants de projets non traités ET les composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés | Composants de projets et de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés |
