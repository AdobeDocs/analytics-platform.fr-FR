---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 2828a38161222a5433b15045a70cb25cfbc8bae7
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 100%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (octobre 2023)

**Dernière mise à jour** : 4 octobre 2023

Ces notes de mise à jour portent sur la période du 4 octobre 2023 au 24 octobre 2023. Les mises à jour d’Adobe Customer Journey Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Exporter des tableaux complets dans le cloud** | L’export de tableaux complets Customer Journey Analytics vous permet d’exporter des millions de lignes Workspace vers des destinations dans le cloud. <p>L’export de tableaux complets permet une livraison unique ou planifiée de tableaux de données conçus dans Workspace avec une prise en charge allant jusqu’à cinq ventilations, cinq mesures, filtres et mesures calculées, le tout dans un tableau concaténé. Il s’agit de l’évolution des rapports des entrepôts de données dans Adobe Analytics, avec de nombreuses nouvelles fonctionnalités souvent demandées et qui ne sont pas disponibles dans les entrepôts de données aujourd’hui.</p><p> Les options d’export dans le cloud incluent :</p><ul><li>Zone d’entrée des données Adobe Experience Platform</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>SAS Azure</li><li>RBAC Azure</li><li>Snowflake</li></ul>Pour plus d’informations, consultez [Export des rapports Customer Journey Analytics dans le cloud](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html?lang=fr). | 4 octobre 2023 | 19 octobre 2023 |
| **Nouvelles colonnes disponibles lors de la gestion des composants** | Les nouvelles colonnes suivantes sont désormais disponibles dans le [Gestionnaire de mesures calculées](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html?lang=fr) et le [Gestionnaire de filtres](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html?lang=fr) lors de la gestion des composants :<ul><li>Utilisation dans</li><li>Dernière utilisation</li></ul>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs et utilisatrices de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié. Vous pouvez utiliser le dictionnaire de données avec ces informations pour vous aider à effectuer le suivi et à mieux comprendre comment les composants sont utilisés dans votre organisation. | 23 septembre 2023 | 4 octobre 2023 |
| **Migrer des projets Adobe Analytics et tout composant inclus vers Customer Journey Analytics** | Vous pouvez désormais migrer vos projets Adobe Analytics vers Customer Journey Analytics. Ce processus simplifie la transition d’Adobe Analytics vers Customer Journey Analytics. <p>Lorsque vous migrez des projets vers Customer Journey Analytics, les ressources sont mappées d’une suite de rapports Adobe Analytics à une vue de données de Customer Journey Analytics.</p> <p>Vous migrez des projets vers Customer Journey Analytics à partir de l’interface d’Adobe Analytics. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=fr)</p> | S.O. | 9 octobre 2023 |
| **Adobe Product Analytics : afficher/masquer les séries** | Cliquez sur la légende du graphique ou les lignes du tableau pour contrôler la visibilité des séries dans vos visualisations.  [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/overview.html?lang=fr) | S.O. | 4 octobre 2023 |
| **Annotations dans Adobe Product Analytics** | L’analyse guidée prend désormais en charge la possibilité d’afficher les annotations créées dans Customer Journey Analytics. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/annotations/overview.html?lang=fr) | S.O. | 4 octobre 2023 |
| **Gestionnaire des activités de rapport** | Le gestionnaire des activités de rapport vous permet d’afficher la capacité de création de rapports pour chaque connexion de votre organisation. Il offre aux administrateurs et administratrices une visibilité détaillée sur la consommation de rapports et permet de diagnostiquer et de résoudre facilement les problèmes de capacité pendant les heures de pointe de la création de rapports. Les principales fonctionnalités du gestionnaire des activités de rapport sont les suivantes :<ul><li>Annuler les demandes de création de rapports en cours (y compris les demandes provenant d’analyses guidées et d’exports de tableau complets)</li><li>Limiter les demandes suivantes pendant une période définie</li></ul>En plus d’annuler des demandes en cours, les administrateurs et administratrices peuvent désormais limiter les demandes pour une période définie. Les administrateurs et administratrices peuvent limiter les demandes par demande, projet ou utilisateur ou utilisatrice.  [En savoir plus](/help/reporting-activity-manager/reporting-activity-overview.md) | 17 octobre 2023 | 23 octobre 2023 |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-325940, AN-326468, AN-328301, AN-328640, AN-329370

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
