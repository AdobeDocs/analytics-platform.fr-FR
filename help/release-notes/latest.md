---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour du Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: eff900722dc06d3bb272d1143c0e2344855e3c5c
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 29%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (janvier 2025)

**Dernière mise à jour** : jeudi 22 janvier 2025

Ces notes de mise à jour couvrent la période du 23 octobre 2024 au 30 janvier 2025. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Expérience d’utilisation des connexions mise à jour** | L’onglet **[!UICONTROL Utilisation]** dans Connexion fournit désormais des visualisations améliorées pour ces types de lignes à signaler : données de base, ingérées et historiques. Vous pouvez également afficher et ventiler les données d’utilisation par connexion, jeu de données, sandbox ou balise. [En savoir plus](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/manage-connections#connections-usage) |  | jeudi 15 janvier 2025 |
| **API pour migrer des projets Adobe Analytics et tout composant inclus vers Customer Journey Analytics** | Une API est désormais disponible pour migrer vos projets Adobe Analytics et les composants inclus vers Customer Journey Analytics. Auparavant, la migration des projets et des composants n’était disponible que via l’interface utilisateur. [En savoir plus](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=CJA%20Migration%20APIs). Sélectionnez **API de migration CJA** dans la liste déroulante. |  | jeudi 15 janvier 2025 |
| **Utilisation de modèles personnalisés dans Customer Journey Analytics sur la page Rapports de Journey Optimizer** | Vous pouvez désormais personnaliser la nouvelle interface de création de rapports dans Adobe Journey Optimizer en créant ou en modifiant un modèle dans Customer Journey Analytics, puis en enregistrant le modèle à utiliser sur la page Rapports dans Journey Optimizer. Auparavant, la nouvelle interface de création de rapports de Adobe Journey Optimizer ne pouvait pas être personnalisée. <p>Pour plus d’informations, voir « Créer un modèle » ou « Modifier ou supprimer un modèle » dans [Créer et gérer des modèles](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/templates/create-templates).  |  | jeudi 15 janvier 2025 |
| **Modèles dans Analysis Workspace** | Les modèles sont désormais disponibles dans Customer Journey Analytics.<ul><li>**Modèles préconfigurés** : une grande sélection de modèles préconfigurés est disponible. Vous pouvez utiliser ces modèles pour obtenir des informations rapides sur les scénarios de création de rapports les plus courants. Les modèles préconfigurés peuvent être utilisés en l’état. Elles peuvent également être utilisées comme point de départ pour un projet, qui peut ensuite être personnalisé pour mieux répondre à un objectif spécifique. [En savoir plus](/help/analysis-workspace/templates/use-templates.md)</li><li>**Modèles d’entreprise** : les administrateurs peuvent créer des modèles d’entreprise pour répondre aux besoins des cas d’utilisation spécifiques à leur organisation. Les modèles d’entreprise créés par les administrateurs sont disponibles pour les utilisateurs de leur entreprise. [En savoir plus](/help/analysis-workspace/templates/create-templates.md)</li></ul> | Janvier 15 | vendredi 30 janvier 2025 |
| **Utilisation du produit** | Découvrez comment votre entreprise utilise Customer Journey Analytics. L’activation de cette fonction crée un jeu de données dans Adobe Experience Platform qui collecte des données lorsque n’importe qui dans votre entreprise utilise Analysis Workspace. Une connexion et une vue de données sont également automatiquement créées, ce qui vous donne accès à des dimensions telles que les principaux types de projets, les utilisateurs et utilisatrices les plus actifs et les composants les plus appréciés dans les projets. [En savoir plus](/help/tools/product-usage/usage-overview.md) | 23 octobre 2024 | 22 janvier 2025 |
| **Légendes intelligentes v2** | Les légendes intelligentes sont désormais prises en charge pour les visualisations suivantes : Multiligne, Barre, Barre horizontale, Anneau, Zone, Flux et Abandon. Vous pouvez choisir d’afficher toutes les légendes intelligentes en même temps dans une vue développée ou d’afficher des légendes intelligentes individuelles dans une vue détaillée. [En savoir plus](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) |  | 22 janvier 2025 |
| **Ajout d’analyses guidées aux projets depuis l’analyse guidée** | Permet d’ajouter des analyses guidées aux projets Workspace à partir de l’analyse guidée. Vous pouvez également ajouter des analyses guidées directement dans Analysis Workspace. [En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/guided-analysis/overview) |  | 22 janvier 2025 |
| **Media Collection : mises à jour du connecteur Source d’Adobe pour le nouveau XDM de création de rapports multimédia** | Le connecteur Source Analytics mappe automatiquement les données de médias en flux continu dans Adobe Analytics aux mêmes champs utilisés par le SDK Web. Actuellement, les données sont mappées à la fois à l’ancien et au nouvel emplacement, mais seul le nouvel emplacement sera utilisé à l’avenir. (Lien vers la documentation à suivre) |  | vendredi 30 janvier 2025 |

## Correctifs dans Customer Journey Analytics

Alertes : AN-363263 ; AN-364880 ; AN-365029 ; AN-365960
Audiences : AN-362564 ; AN-363254 ;
Ingestion des données : AN-362359 ; AN-362751
Vues de données : AN-362089 ; AN-365213 ; AN-365770 ; AN-366171
Champs dérivés : AN-359711 ; AN-362496
Emplacements d’exportation : AN-363999
Exportation complète de la table : AN-363055
Report Builder : AN-362937
Workspace : AN-359012 ; AN-359145 ; AN-359914 ; AN-361455 ; AN-361934 ; AN-362469 ; AN-363460 ; AN-364714 ; AN-364918 ; AN-366277 ;


## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. | | |

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2024](/help/release-notes/2024.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
