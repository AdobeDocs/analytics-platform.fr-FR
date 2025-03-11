---
title: Comprendre la prise en charge des fonctionnalités d’Adobe Analytics lors de la mise à niveau vers Customer Journey Analytics
description: Découvrez la prise en charge des fonctionnalités Adobe Analytics lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 55%

---

# Comprendre la prise en charge des fonctionnalités d’Adobe Analytics lors de la mise à niveau vers Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="Composants et projets"
>abstract="Les composants d’Adobe Analytics sont les suivants : les projets (avec leurs tableaux à structure libre et leurs visualisations), les segments et les mesures calculées."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Superposition de Activity Map et suivi des liens"
>abstract="Une extension de navigateur qui vous permet de voir les données de suivi des liens en superposition sur votre site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map-support"
>title="La prise en charge du recouvrement Activity Map n’est pas encore disponible"
>abstract="La prise en charge du recouvrement Activity Map n’est pas encore disponible dans Customer Journey Analytics. Il est prévu qu’il soit disponible à l’avenir."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="Données de classification"
>abstract="Regroupez ou classez les données dans des dimensions distinctes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="Canaux marketing"
>abstract="Créez des règles qui catégorisent la façon dont les clients arrivent sur votre site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="Flux de données"
>abstract="Exportez des données brutes d’Adobe Analytics pour les utiliser dans des outils et processus externes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="Exportez les données traitées par Adobe Analytics dans un format de feuille de calcul."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="Données de médias en streaming"
>abstract="Un module complémentaire d’Adobe Analytics et de Customer Journey Analytics spécialisé dans la collecte de données sur les médias, tels que l’audio, la vidéo ou le contenu en streaming."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="Migrer des projets et des composants"
>abstract="Intégrez les projets Adobe Analytics et leurs composants associés vers Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

La liste suivante affiche uniquement les fonctionnalités d’Adobe Analytics qui doivent être prises en compte lors du processus de mise à niveau vers Customer Journey Analytics. Pour obtenir une liste complète des fonctionnalités Adobe Analytics entièrement prises en charge, partiellement prises en charge ou non prises en charge dans Customer Journey Analytics, consultez [Prise en charge des fonctionnalités Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Tenez compte des fonctionnalités d’Adobe Analytics que vous souhaitez continuer à utiliser lors de la mise à niveau vers Customer Journey Analytics :

| Fonctionnalité Adobe Analytics | Fonctionnalité correspondante dans Customer Journey Analytics |
|---------|----------|
| [Composants et projets Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [Migrer des projets et leurs composants associés vers Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). |
| [Superposition Activity Map et suivi des liens](https://experienceleague.adobe.com/en/docs/analytics/analyze/activity-map/overview) | Pas encore disponible |
| [Données de classification](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/c-classifications) | Les jeux de données de recherche sont la méthode de classification des données dans Customer Journey Analytics.<p>[Créez un jeu de données de recherche pour chaque dimension contenant des données de classification.](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [Canaux marketing](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | Les champs dérivés sont créés dans une vue de données. <p>[Créez un champ dérivé de canal marketing.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [Flux de données](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | Experience Platform et Customer Journey Analytics fournissent un certain nombre de fonctionnalités qui, seules ou combinées, peuvent résoudre les différents besoins d’exportation. Ces fonctionnalités incluent [l’API Data Access d’Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=fr) [les destinations Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=fr), [l’exportation de table complète de Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) et l’intégration de l’outil [BI](/help/data-views/bi-extension.md).<p>Pour plus d’informations sur les options d’exportation, voir [Cas pratiques d’exportation de données](/help/use-cases/data-export/overview.md).</p> |
| [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | [L’export de tableaux complets Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) correspond à l’évolution des rapports des entrepôts de données dans Adobe Analytics, avec de nombreuses nouvelles fonctionnalités souvent demandées et qui ne sont pas disponibles dans les entrepôts de données aujourd’hui. |
| [Données de streaming multimédia](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-overview) | Les données des médias en streaming sont disponibles dans le connecteur source Analytics dans le cadre des panneaux Visionneuses simultanées de médias et Temps de lecture de média dans l’espace de travail. |
