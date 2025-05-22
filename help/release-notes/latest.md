---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1adc69c05abd1a5a99f3b6b8547b8b1508da0c59
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 32%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (mai 2025)

**Dernière mise à jour** : vendredi 22 mai 2025


Ces notes de mise à jour couvrent la période du 22 avril au 18 juin 2025. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics B2B edition** | Customer Journey Analytics B2B edition aide les sociétés B2B à aligner leurs équipes de marketing, de vente et de produits en fournissant des informations de compte exploitables qui stimulent la croissance du chiffre d’affaires. Le compte étant placé au centre du modèle de données, toutes les analyses se concentrent sur le parcours de compte. L’ajout d’une nouvelle couche d’entités (comptes, opportunités et groupes d’achats) en plus des événements basés sur la personne et le temps, crée une vue d’ensemble complète du cycle de vie du marketing B2B et des recettes. [En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | jeudi 18 juin 2025 |
| **Data Insights Agent** | Le Data Insights Agent, qui fait partie de l’assistant d’IA dans Customer Journey Analytics, est un agent de conversation d’IA génératif. Il utilise des composants de votre vue de données et de vos données réelles pour répondre rapidement et efficacement aux questions centrées sur les données en créant des visualisations pertinentes dans Analysis Workspace. [En savoir plus](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) |  | jeudi 28 mai 2025 |
| **Ajouter et afficher des commentaires dans les projets Analysis Workspace** | La nouvelle fonctionnalité [commentaires](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) d’Analysis Workspace vous permet de partager des informations et de poser des questions dans le cadre d’un projet Analysis Workspace. Cela peut rationaliser les discussions sur les données, en maintenant les conversations dans le contexte des données qui font l’objet de discussions. Vous pouvez : <ul><li>Commenter tout projet Analysis Workspace auquel vous avez accès</li><li>Commenter un point spécifique d’une visualisation ou faire des commentaires généraux sur un projet</li><li>Taguer d’autres utilisateurs pour les informer de vos commentaires</li><li>Gérer les commentaires existants (modifier, épingler, résoudre, etc.)</li></ul>Les administrateurs et administratrices de Customer Journey Analytics peuvent [désactiver les commentaires au niveau de l’organisation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Les propriétaires de projet peuvent [désactiver les commentaires au niveau du projet](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | jeudi 25 juin 2025 |
| **Augmentation des limites d&#39;exportation de tables complètes** | Adobe a augmenté le nombre de colonnes utilisables avec l’[exportation de table complète](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics), passant de 5 dimensions et 5 mesures à 10 dimensions et 10 mesures. Cela s’applique à tous les niveaux Customer Journey Analytics. Les droits pour le nombre de lignes pouvant être exportées ne changent pas. |  | 30 avril 2025 |
| **Mise à jour des champs XDM pour la collecte des données des médias de streaming dans Adobe Experience Platform** | Lors de la collecte de données Streaming Media dans Adobe Experience Platform, les chemins d’accès aux champs XDM affichés sous l’en-tête « Chemin d’accès au champ XDM » de la documentation des paramètres Streaming Media ne doivent plus être utilisés. Ces chemins d’accès aux champs se trouvent sur les pages suivantes et sont marqués comme « Obsolètes » : [Paramètres audio et vidéo](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Paramètres d’annonce](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Paramètres de chapitre](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Paramètres d’état du lecteur](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters) et [Paramètres de qualité](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). <p>Au lieu de cela, les clients doivent migrer vers les chemins d’accès aux champs `mediaReporting`, comme indiqué sous l’en-tête « Chemin d’accès au champ XDM de la création de rapports » de la documentation des paramètres de streaming multimédia référencée ci-dessus.<p>Pendant une période de transition de trois mois, l’ingestion des données sur les chemins d’accès aux champs XDM obsolètes se poursuivra. Cependant, à la fin du mois de juillet 2025, les chemins de champ obsolètes seront entièrement supprimés et ne seront plus visibles dans l’interface utilisateur du schéma Adobe Experience Platform, et les données seront envoyées uniquement à l’aide des chemins de champ `mediaReporting`.<p>Les clients qui ont implémenté le connecteur source Analytics pour collecter les données Streaming Media dans Platform avant le 22 avril 2025 doivent migrer leurs configurations existantes pour utiliser les nouveaux chemins de champ. Cette migration doit être terminée d’ici la fin du mois de juillet 2025. Pour obtenir de l’aide concernant la migration, contactez les services Adobe Consulting ou l’équipe en charge des comptes. Aucune action n’est requise de la part des clientes et des clients qui implémentent le connecteur source Analytics après le 22 avril 2025.</p> |  | 22 avril 2025 |
| **Regroupement : récupération d’identifiants persistants et temporaires à partir de XDM IdentityMap** | Cette fonctionnalité prend en charge l’utilisation d’identités stockées dans XDM IdentityMap pour le processus de regroupement. IdentityMap peut être utilisé pour des ID persistants ou temporaires pour un regroupement basé sur des champs, ou pour des ID persistants pour un regroupement basé sur des graphiques.  Vous pouvez utiliser un espace de noms spécifique ou une identité principale à partir d’IdentityMap. Pour en savoir plus, cliquez [ici](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/fbs#identitymap) et [ici](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs#identitymap). |  | mardi 28 avril 2025 |
| **Mesures et dimensions partagées entre les vues de données** | Ce vous permet d’appliquer des paramètres de dimensions et de mesures à plusieurs vues de données. Les modifications apportées à une dimension ou à une mesure partagée s’appliquent à toutes les instances de cette dimension ou mesure dans toutes les vues de données concernées. Cette interface permet aux administrateurs et aux administratrices Customer Journey Analytics de gérer plus facilement les composants lorsque de nombreuses vues de données sont utilisées. [En savoir plus](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 30 avril 2025 |
| **Dimension Profondeur de l’événement** | Une nouvelle [dimension Profondeur de l’événement](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components) a été ajoutée à la liste des composants standard requis pour une vue de données. |  | vendredi 8 mai 2025 |
| **Le panneau de gauche d’Analysis Workspace ne s’ouvre plus et se ferme au survol** | Le panneau de gauche d’Analysis Workspace permet d’ajouter des éléments tels que des composants, des panneaux et des visualisations à votre projet. L’option permettant d’ouvrir temporairement le panneau de gauche en pointant sur l’une des icônes à l’extrême gauche n’est plus disponible. Il vous suffit de cliquer sur l’une de ces icônes pour garder le panneau ouvert, puis de cliquer sur la même icône pour le fermer. |  | vendredi 29 mai 2025 |
| **Désactiver le fichier manifeste lors de l&#39;export de tables complètes** | Vous permet de désactiver le fichier manifeste inclus par défaut lors de l’exportation de tables complètes à partir d’Analysis Workspace. [En savoir plus](/help/analysis-workspace/export/export-cloud.md) |  | mercredi 20 mai 2025 |


## Correctifs dans Customer Journey Analytics

**Analysis Workspace**: AN-361874; AN-371360; AN-373079; AN-374382; AN-374447; AN-375277; AN-375680
**Audiences** : AN-372343
**Journal d’audit** : AN-378168
**Connexions** : AN-373121 ; AN-372996
**Suppression des données** : AN-375450
**Champs dérivés** : AN-373689 ; AN-377852
**Emplacements d’exportation** : AN-374167
**Zone de travail de Parcours** : AN-373319
**Report Builder**: AN-369786
**Reporting** : AN-377326 ; AN-378051
**Responsable des activités de rapport** : AN-377148


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
