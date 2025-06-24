---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: cbe5f3894a01f662a6ebe9c380583d0a039863fd
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 72%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (juin 2025)

**Dernière mise à jour** : 18 juin 2025


Ces notes de mise à jour portent sur la période du mardi 2 juin 2025 au mercredi 15 juillet 2025. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Le panneau de gauche d’Analysis Workspace ne s’ouvre plus et se ferme lorsque la souris le survole.** | Le panneau de gauche d’Analysis Workspace permet d’ajouter des éléments tels que des composants, des panneaux et des visualisations à votre projet. L’option permettant d’ouvrir temporairement le panneau de gauche en pointant sur l’une des icônes tout à gauche n’est plus disponible. Il vous suffit désormais de cliquer sur l’une de ces icônes pour que le panneau reste ouvert, puis de cliquer sur la même icône pour le fermer. |  | mardi 2 juin 2025 <p>(Version initialement prévue pour le 29 mai 2025)</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition permet aux entreprises B2B d’aligner leurs équipes marketing, commerciale et produits en fournissant des informations de compte exploitables qui stimulent l’augmentation des revenus. Le compte étant placé au centre du modèle de données, toutes les analyses se concentrent sur le parcours de compte. L’ajout d’une nouvelle couche d’entités (comptes, opportunités et groupes d’achat) en plus des événements basés sur les personnes et le temps, crée une vue d’ensemble complète du cycle de vie du marketing et des revenus B2B. [En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 18 juin 2025 |
| **Prise en charge des destinations cloud sécurisées dans Report Builder** | Vous pouvez désormais exporter des rapports de Report Builder vers les destinations d’espace de stockage suivantes :<ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>SAS Azure</li><li>RBAC Azure</li></ul><p>Auparavant, vous pouviez partager des classeurs avec d’autres utilisateurs par e-mail, mais vous ne pouviez pas exporter des rapports de Report Builder vers des destinations cloud.</p><p>Pour plus d’informations, voir [Planification de classeurs en exportant vers des destinations cloud](/help/report-builder/report-builder-export.md).</p> |  | 19 Juin 2025 (Initialement Le 18 Juin 2025) |
| **Nouvelle expérience de prévisualisation** | Le panneau d’aperçu, qui est utilisé lorsque vous créez un segment ou configurez les paramètres d’une vue de données, utilise désormais une visualisation à barres horizontales au lieu d’une visualisation en anneau. |  | 18 juin 2025 |
| **Boîte de dialogue Modèle d’attribution modifié** | Vous pouvez désormais définir le conteneur et la période séparément dans la boîte de dialogue du modèle d’attribution. |  | 18 juin 2025 |
| **Carte de la connexion** | Une nouvelle [interface de mappage des connexions](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-connections/create-connection#connection-map) est disponible pour afficher visuellement votre configuration de connexion. |  | 18 juin 2025 |
| **Ajouter et afficher des commentaires dans les projets Analysis Workspace** | Une nouvelle [fonctionnalité de commentaires](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) dans Analysis Workspace vous permet de partager des informations et de poser des questions dans le cadre d’un projet Analysis Workspace. Celle-ci peut optimiser les discussions sur les données, en maintenant les conversations dans le contexte spécifique des données concernées. Vous pouvez : <ul><li>Commenter tout projet Analysis Workspace auquel vous avez accès</li><li>Commenter un élément spécifique d’une visualisation ou écrire des commentaires généraux sur un projet</li><li>Mentionner d’autres utilisateurs et utilisatrices pour les informer de vos commentaires</li><li>Gérer des commentaires existants (modifier, épingler, résoudre, etc.)</li></ul>Les administrateurs et les administratrices Customer Journey Analytics peuvent [désactiver les commentaires au niveau de l’organisation](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Les propriétaires de projet peuvent [désactiver les commentaires au niveau du projet](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). | 25 juin 2025 | samedi 11 juillet 2025 <p>(Version initialement prévue pour le 29 mai 2025)</p> |
| **Prise en charge du pré-rendu de Chrome** | Contrôlez le comportement des bibliothèques de collecte de données lorsque Chrome effectue le pré-rendu d’une page. (Lien vers la documentation à venir) |  | 30 juin 2025 |

## Correctifs dans Customer Journey Analytics

**Alertes** : AN-379554
**Analysis Workspace**: AN-339607; AN-379222; AN-381138; AN-383291
**B2B** : AN-376028
Extension **BI pour Tableau** : AN-377488
**Composants** : AN-376174
**Vues des données** : AN-379011
**Emplacements d’exportation** : AN-382191
**Exportation complète de table** : AN-375646 ; AN-376986 ; AN-380355 ; AN-381310
**Zone de travail de Parcours** : AN-375865 ; AN-378011
**Report Builder**: AN-369786; AN-371395; AN-372809
**Rapports** : AN-372615 ; AN-378578 ;


## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. | | |

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
