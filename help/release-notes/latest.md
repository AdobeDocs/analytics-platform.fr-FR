---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7e6383bf94e10f6ab6f9db990f4ef3df0fb826d3
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 26%

---

# Notes de mise à jour de la version actuelle de Customer Journey Analytics (CJA) (mai 2023)

**Dernière mise à jour** : 8 mai 2023

Les mises à jour de Customer Journey Analytics fonctionnent sur une [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités clés et mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Renvoi pour les environnements de test hors production** | Lors de la création d’un flux de données Analytics Source Connector dans un environnement de test hors production, le renvoi dans les environnements de test hors production sera limité à 3 mois. Il restera à 13 mois pour les environnements de test de production. | S.O. | 26 avril 2023 |
| **Partage de liens pour les projets (aucune connexion requise)** | Vous pouvez désormais partager des liens en lecture seule vers les projets Analysis Workspace avec des personnes qui n’ont pas accès à Adobe Analytics. Cela inclut le partage avec des personnes en dehors de votre organisation ou au sein de votre organisation qui ne sont pas configurées pour Adobe Analytics. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>Cette fonctionnalité est activée par défaut et peut être désactivée par l’administrateur système. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 3 mai 2023 | Juin 2023 |
| **Écran d’accueil mis à jour pour l’application de tableaux de bord Analytics (application mobile)** | Le nouvel écran d’accueil mis à jour vous permet d’afficher toutes vos fiches d’évaluation dans une seule liste de fiches d’évaluation consolidée.  Si vous avez accès à plusieurs organisations sous une seule connexion, toutes les Fiches d’évaluation de vos organisations seront disponibles dans une seule liste. | S.O. | 10 mai 2023 |
| **Champs dérivés** | Il s’agit de la version initiale des champs dérivés. Un champ dérivé vous permet de définir à la volée des manipulations de données (souvent complexes) par le biais d’un créateur de règles personnalisable. Vous pouvez définir plus précisément le champ dérivé en tant que composant (mesure ou dimension) dans les vues de données, puis utiliser le champ dérivé en tant que composant dans Workspace.<p>Cette version prend en charge un modèle de canaux marketing et les fonctions suivantes :</p><ul><li>Concaténer</li><li>Cas si</li><li>Chercher et Remplacer</li><li>Recherche</li><li>Analyse de l’URL</li></ul> <p>[En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 10 mai 2023 | À confirmer |
| **Report Builder pour CJA - Sélectionner la vue de données à partir de la cellule** | Cette fonctionnalité permet aux utilisateurs de sélectionner la vue de données d’un bloc de données à partir d’une cellule. Ceci s’avère utile si vous créez un classeur et que vous disposez de plusieurs vues de données ayant une construction de données similaire et que vous souhaitez pouvoir réutiliser un classeur plusieurs fois, avec des vues de données différentes. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | S.O. | 24 mai 2023 |
| **Tri des composants dans Analysis Workspace** | <p>Une nouvelle option de tri est désormais disponible lorsque vous affichez des composants dans le rail de gauche ou dans le dictionnaire de données dans Analysis Workspace. Vous pouvez trier les composants par Recommandé (ceux qui sont les plus couramment utilisés), Alphabétique ou Catégoriel (type).</p><p>Auparavant, vous pouviez uniquement rechercher ou filtrer des composants. [En savoir plus](/help/components/overview.md)</p> | S.O. | 17 mai 2023 |
| **Suppression de lignes contenant des dimensions dynamiques d’un tableau à structure libre** | Dans un tableau à structure libre d’Analysis Workspace, vous pouvez désormais supprimer rapidement des lignes spécifiques contenant des dimensions dynamiques à l’aide de l’icône x. Dans ce cas, une règle de filtrage &quot;N’est pas égale&quot; est automatiquement appliquée.<p>Auparavant, la seule manière de supprimer des lignes contenant des dimensions dynamiques consistait à créer manuellement une règle dans la boîte de dialogue Filtre. [En savoir plus](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | S.O. | 17 mai 2023 |
| **Nouveau bouton pour ajouter une visualisation dans un panneau** | Un nouveau bouton est désormais disponible au bas de chaque panneau dans Analysis Workspace, ce qui vous permet d’ajouter rapidement une visualisation. <p>Auparavant, les seules méthodes permettant d’ajouter une visualisation à un panneau étaient de faire glisser une visualisation depuis le rail de gauche, de dupliquer ou de copier une visualisation existante ou de créer un panneau vierge. [En savoir plus](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | S.O. | 17 mai 2023 |
| **Lien profond (application mobile)** | Permet aux utilisateurs d’envoyer des liens vers des Fiches d’évaluation qui les mèneront directement au projet de Fiche d’évaluation dans l’application. Cela facilite encore le partage de projets et améliore l’engagement d’une audience moins technique. | S.O. | 17 mai 2023 |
| **Légendes intelligentes** | Enrichissez la narration pour les utilisateurs avec des résumés en langage naturel d’une [!UICONTROL Ligne] visualisation. [En savoir plus](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 mai 2023 | 1 juin 2023 |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-316412 ; AN-317105 ; AN-318122 ; AN-317353

## Avis importants destinés aux administrateurs de CJA

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. | S.O. | S.O. |

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification Adobe IO OAuth serveur à serveur** | 11 mai 2023 | L’API Adobe Analytics, l’API CJA et les clients Livestream qui utilisent les informations d’identification JWT Adobe IO doivent migrer vers les informations d’identification Adobe IO OAuth serveur à serveur en procédant comme suit : **1er janvier 2025**. Adobe IO n’autorise pas la création de nouvelles informations d’identification JWT à compter du 1er mai 2024. Les clients utilisant JWT doivent créer des informations d’identification OAuth serveur à serveur ou migrer leurs informations d’identification JWT existantes vers des informations d’identification OAuth serveur à serveur. Les clients doivent également mettre à jour leurs applications clientes pour utiliser les nouvelles informations d’identification OAuth serveur à serveur. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilisation des nouvelles informations d’identification OAuth serveur à serveur](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul>![](assets/jwt.png) |

{style="table-layout:auto"}

## Ressources connexes

* [Notes de mise à jour de CJA précédentes pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
