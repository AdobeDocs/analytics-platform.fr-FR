---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e1254a5ecff0f638cbef1051564c1ce856f715bd
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 51%

---

# Notes de mise à jour actuelles d’Adobe Customer Journey Analytics (octobre 2023)

**Dernière mise à jour** : 4 octobre 2023

Ces notes de mise à jour portent sur la période du 4 octobre 2023 au 24 octobre 2023. Les mises à jour d’Adobe Customer Journey Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Exportation des tables complètes dans le cloud** | L’exportation de tableaux complets Customer Journey Analytics vous permet d’exporter des millions de lignes Workspace vers des destinations cloud. L’exportation de tableaux complets permet une livraison unique ou planifiée de tableaux de données conçus dans Workspace avec la prise en charge de cinq ventilations, cinq mesures, filtres et mesures calculées au maximum, le tout dans un tableau concaténé. Il s’agit de l’évolution des rapports Data Warehouse dans Adobe Analytics, avec de nombreuses nouvelles fonctionnalités souvent demandées qui ne sont pas disponibles dans Data Warehouse aujourd’hui. Les options d’exportation dans le cloud incluent :<ul><li>Zone d’entrée des données Adobe Experience Platform</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>SAS Azure</li><li>RBAC Azure</li><li>Snowflake</li></ul>Pour plus d’informations, voir [Exportation des rapports des Customer Journey Analytics dans le cloud](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html). | 4 octobre 2023 | 19 octobre 2023 |
| **Nouvelles colonnes disponibles lors de la gestion des composants** | Les nouvelles colonnes suivantes sont désormais disponibles dans le [Gestionnaire de mesures calculées](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html) et le [Gestionnaire de filtres](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html) lors de la gestion des composants :<ul><li>Utilisation dans</li><li>Dernière utilisation</li></ul>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs et utilisatrices de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié. Vous pouvez utiliser le dictionnaire de données avec ces informations pour vous aider à effectuer le suivi et à mieux comprendre comment les composants sont utilisés dans votre organisation. | 23 septembre 2023 | 4 octobre 2023 |
| **Migration de projets Adobe Analytics et de tout composant inclus vers Customer Journey Analytics** | Vous pouvez désormais migrer vos projets Adobe Analytics vers Customer Journey Analytics. Ce processus simplifie la transition d’Adobe Analytics vers Customer Journey Analytics. Lorsque vous migrez des projets vers Customer Journey Analytics, les ressources sont mappées d’une suite de rapports Adobe Analytics à une vue de données de Customer Journey Analytics. **Vous migrez des projets vers Customer Journey Analytics à partir de l’interface d’Adobe Analytics.** [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html) | S.O. | 4 octobre 2023 |
| **Adobe Product Analytics : Afficher/Masquer les séries** | Cliquez sur la légende du graphique ou les lignes du tableau pour contrôler la visibilité des séries dans vos visualisations.  En savoir plus (bientôt disponible) | S.O. | 4 octobre 2023 |
| **Annotations dans Adobe Product Analytics** | Les projets d’analyse guidée prennent désormais en charge la possibilité d’afficher des annotations. Reportez-vous à chaque type de vue dans [Analyse guidée](/help/guided-analysis/overview.md) pour plus d’informations sur l’interaction avec les annotations. | S.O. | 4 octobre 2023 |
| **Gestionnaire des activités de rapport** | Le Gestionnaire d’activités de création de rapports vous permet d’afficher la capacité de création de rapports pour chaque connexion de votre organisation. Il fournit aux administrateurs une visibilité détaillée sur la consommation des rapports afin de diagnostiquer et de résoudre facilement les problèmes de capacité pendant les heures de pointe de la création de rapports. Les principales fonctionnalités du Gestionnaire des activités de création de rapports sont les suivantes :<ul><li>Annuler les demandes de création de rapports en cours (y compris les demandes provenant d’analyses guidées et d’exports de tableau complets)</li><li>Limitation des requêtes suivantes pour une période définie</li></ul>Outre l’annulation de requêtes en cours, les administrateurs peuvent désormais limiter les requêtes pour une période définie. Les administrateurs peuvent limiter les requêtes par requête, projet ou utilisateur.  En savoir plus (bientôt disponible) | 17 octobre 2023 | 23 octobre 2023 |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-325940; AN-326468; AN-328301; AN-328640; AN-329370

## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. | S.O. | S.O. |

{style="table-layout:auto"}

## Avis de fin de vie

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les API Adobe Analytics et Customer Journey Analytics et les clients et clientes Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
