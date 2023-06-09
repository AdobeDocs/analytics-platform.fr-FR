---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f02cda499b2050cd238ca2352237ae2cc9a502d6
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 62%

---

# Notes de mise à jour de la version actuelle de Customer Journey Analytics (CJA) (juin 2023)

**Dernière mise à jour** : 6 juin 2023

Les mises à jour de Customer Journey Analytics fonctionnent sur une [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Principaux éléments de la mise à jour {#highlights}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Légendes intelligentes** | Enrichissez la narration pour les utilisateurs avec des résumés en langage naturel d’une [!UICONTROL Ligne] visualisation. [En savoir plus](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 mai 2023 | 1 juin 2023 |
| **Partage de liens pour les projets (aucune connexion requise)** | Vous pouvez désormais partager des liens en lecture seule vers les projets Analysis Workspace avec des personnes qui n’ont pas accès à Adobe Analytics. Cela inclut le partage avec des personnes hors de votre organisation, ou avec des personnes au sein de votre organisation qui ne sont pas configurées pour Adobe Analytics. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=fr#share-public-link) <p>Cette fonctionnalité est activée par défaut et peut être désactivée par l’administrateur ou administratrice système. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=fr)</p> | 3 mai 2023 | 6 juin 2023 |
| **Champs dérivés** | Il s’agit de la version initiale des champs dérivés. Un champ dérivé vous permet de définir à la volée des manipulations de données (souvent complexes) par le biais d’un créateur de règles personnalisable. Vous pouvez définir plus précisément le champ dérivé en tant que composant (mesure ou dimension) dans les vues de données, puis utiliser le champ dérivé en tant que composant dans Workspace.<p>Cette version prend en charge un modèle de canaux marketing et les fonctions suivantes :</p><ul><li>Concaténer</li><li>Cas si</li><li>Chercher et remplacer</li><li>Recherche</li><li>Analyse de l’URL</li></ul> <p>[En savoir plus](/help/data-views/derived-fields/derived-fields.md)</p> | 10 mai 2023 | 21 juin 2023 |
| **Accès PowerBI et Tableau aux vues de données CJA** | Le connecteur SQL du Customer Journey Analytics (CJA) permet l’accès SQL aux vues de données que vous avez définies dans CJA. Les ingénieurs et analystes de données plus familiarisés avec Power BI, Tableau ou d’autres outils d’intelligence et de visualisation métier peuvent désormais créer des rapports et des tableaux de bord basés sur les mêmes vues de données que les utilisateurs de CJA utilisent pour leurs projets Analysis Workspace. [En savoir plus](/help/data-views/sql-connector.md) |  | 30 juin 2023 |
| **Recherches géographiques Experience Edge** | Vous pourrez créer des rapports à l’aide des données de géolocalisation dans CJA une fois que les recherches de géolocalisation Experience Edge seront activées pour votre flux de données. |  | 30 juin 2023 |
| **Prise en charge étendue de la recherche pour les données de profil et de recherche** | Vous pourrez ajouter des jeux de données de recherche non seulement aux jeux de données d’événement, mais aussi aux jeux de données de profil et de recherche. | 21 juin 2023 | 12 juillet 2023 |
| **Prise en charge de la conversion de devise** | CJA prend en charge la conversion de devise dans le cadre du formatage d’un composant de mesure dans une vue de données. | 21 juin 2023 | 19 juillet 2023 |

{style="table-layout:auto"}

## Autres nouvelles fonctionnalités ou mises à jour {#other-new}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Vues des données Adobe Journey Optimizer** | Les administrateurs CJA ont accès à certaines vues de données supplémentaires dans CJA, intitulées &quot;AJO Data view (Sandbox-name)&quot;. Ces vues de données sont utilisées pour alimenter les rapports dans Adobe Journey Optimizer (AJO). Ils peuvent également être utilisés pour effectuer une analyse plus approfondie des activités AJO dans CJA. [En savoir plus](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html). | | 25 mai 2023 |
| **Renvoi pour les sandbox hors production** | Lors de la création d’un flux de données du connecteur source Analytics dans un sandbox hors production, le renvoi dans les sandbox hors production sera limité à 3 mois. Il sera toujours de 13 mois pour les sandbox de production. | S.O. | 26 avril 2023 |
| **Partage de liens pour les projets (aucune connexion requise)** | Vous pouvez désormais partager des liens en lecture seule vers les projets Analysis Workspace avec des personnes qui n’ont pas accès à Adobe Analytics. Cela inclut le partage avec des personnes hors de votre organisation, ou avec des personnes au sein de votre organisation qui ne sont pas configurées pour Adobe Analytics. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=fr#share-public-link) <p>Cette fonctionnalité est activée par défaut et peut être désactivée par l’administrateur ou administratrice système. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 3 mai 2023 | 6 juin 2023 |
| **Écran d’accueil mis à jour pour l’application de tableaux de bord Analytics (application mobile)** | Le nouvel écran d’accueil mis à jour vous permet d’afficher toutes vos cartes de performances dans une seule liste consolidée.  Si vous avez accès à plusieurs organisations sous une seule connexion, toutes les cartes de performances de vos organisations seront disponibles dans une seule liste. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | S.O. | 10 mai 2023 |
| **Champs dérivés** | Il s’agit de la version initiale des champs dérivés. Un champ dérivé vous permet de définir à la volée des manipulations de données (souvent complexes) par le biais d’un créateur de règles personnalisable. Vous pouvez définir plus précisément le champ dérivé en tant que composant (mesure ou dimension) dans les vues de données, puis utiliser le champ dérivé en tant que composant dans Workspace.<p>Cette version prend en charge un modèle de canaux marketing et les fonctions suivantes :</p><ul><li>Concaténer</li><li>Cas si</li><li>Chercher et remplacer</li><li>Recherche</li><li>Analyse de l’URL</li></ul> <p>[En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html?lang=fr)</p> | 10 mai 2023 | 2 août 2023 |
| **Report Builder pour CJA - Sélectionner la vue de données à partir de la cellule** | Cette fonctionnalité permet aux utilisateurs et utilisatrices de sélectionner la vue de données d’un bloc de données à partir d’une cellule. Ceci s’avère utile si vous créez un classeur et que vous disposez de plusieurs vues de données ayant une construction de données similaire et que vous souhaitez pouvoir réutiliser un classeur plusieurs fois, avec des vues de données différentes. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=fr) | S.O. | 24 mai 2023 |
| **Mise à jour de la page d’apprentissage pour CJA** | L’onglet Apprentissage de la page d’entrée du Customer Journey Analytics contient désormais du contenu spécifique à CJA, y compris du contenu axé sur la transition vers CJA à partir d’Adobe Analytics.<p>Les améliorations supplémentaires suivantes sont également disponibles dans l’onglet Apprentissage :</p><ul><li>Amélioration de la conception qui affiche plus de contenu d’apprentissage sur une seule page avec une navigation améliorée.</li><li>Possibilité de personnaliser le contenu de l’apprentissage par niveau d’expérience (débutant, intermédiaire et avancé)</li></ul><p>Auparavant, l’onglet Apprentissage de CJA contenait des informations identiques à celles de l’onglet Apprentissage dans Adobe Analytics.</p> [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | S.O. | 30 juin 2023 |
| **Tri des composants dans Analysis Workspace** | <p>Une nouvelle option de tri est désormais disponible lorsque vous affichez des composants dans le rail de gauche ou dans le dictionnaire de données dans Analysis Workspace. Vous pouvez trier les composants par Recommandé (ceux qui sont les plus couramment utilisés), Ordre alphabétique ou par Catégorie (type).</p><p>Auparavant, vous pouviez uniquement rechercher ou filtrer des composants. [En savoir plus](/help/components/overview.md)</p> | S.O. | À confirmer |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-318343 ; AN-319453

## Avis importants destinés aux administrateurs de CJA

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. | S.O. | S.O. |

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification Adobe IO OAuth serveur à serveur** | 11 mai 2023 | L’API Adobe Analytics, l’API CJA et les clients Livestream qui utilisent les informations d’identification JWT Adobe IO doivent migrer vers les informations d’identification Adobe IO OAuth serveur à serveur en procédant comme suit : **1er janvier 2025**. Adobe IO n’autorise pas la création de nouvelles informations d’identification JWT à compter du 1er mai 2024. Les clients utilisant JWT doivent créer des informations d’identification OAuth serveur à serveur ou migrer leurs informations d’identification JWT existantes vers des informations d’identification OAuth serveur à serveur. Les clients doivent également mettre à jour leurs applications clientes pour utiliser les nouvelles informations d’identification OAuth serveur à serveur. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilisation des nouvelles informations d’identification OAuth serveur à serveur](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## Ressources connexes

* [Notes de mise à jour de CJA précédentes pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
