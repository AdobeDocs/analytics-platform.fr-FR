---
title: Comprendre la prise en charge des fonctionnalités Adobe Analytics lors de la mise à niveau vers Customer Journey Analytics
description: Découvrez la prise en charge des fonctionnalités Adobe Analytics lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1460cbd05cce793b25d026c413744508ab951147
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 29%

---

# Comprendre la prise en charge des fonctionnalités Adobe Analytics lors de la mise à niveau vers Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="Composants et projets"
>abstract="Les composants d’Adobe Analytics sont les suivants : Projets (avec les tableaux à structure libre et les visualisations associés), segments et mesures calculées."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Superposition d’Activity Map et suivi des liens"
>abstract="Une extension de navigateur qui vous permet d’afficher les données de suivi des liens sous forme de superposition sur votre site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="Données de classification"
>abstract="Regroupez ou catégorisez les données en tant que dimensions distinctes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="Canaux marketing"
>abstract="Créez des règles qui catégorisent la manière dont les clients arrivent sur votre site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="Flux de données"
>abstract="Exportez les données brutes d’Adobe Analytics pour les utiliser dans des outils et des processus externes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="Exportez les données traitées d’Adobe Analytics au format tableur."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="Données de streaming multimédia"
>abstract="Module complémentaire d’Adobe Analytics spécialisé dans la collecte de données multimédia, telles que l’audio, la vidéo ou le contenu en flux continu."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Utilisez les informations de cette page pour répondre aux questions de la liste de contrôle de mise à niveau du Customer Journey Analytics [](https://gigazelle.github.io/cja-ttv/).

La liste suivante affiche uniquement les fonctionnalités incluses dans la liste de contrôle de mise à niveau du Customer Journey Analytics [](https://gigazelle.github.io/cja-ttv/). Pour obtenir une liste complète des fonctionnalités Adobe Analytics prises en charge, partiellement prises en charge ou non par Customer Journey Analytics, consultez [Prise en charge des fonctionnalités de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Pensez aux fonctionnalités d’Adobe Analytics que vous souhaitez continuer à utiliser lorsque vous effectuez une mise à niveau vers Customer Journey Analytics :

| Fonctionnalité Adobe Analytics | Fonctionnalité correspondante dans Customer Journey Analytics |
|---------|----------|
| [Composants et projets Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [Migrer des projets et leurs composants associés vers Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). |
| [Superposition Activity Map et suivi des liens](https://experienceleague.adobe.com/en/docs/analytics/analyze/activity-map/overview) | Pas encore disponible |
| [Données de classification](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/c-classifications) | Les jeux de données de recherche sont la méthode de classification des données dans Customer Journey Analytics.<p>[Créez un jeu de données de recherche pour chaque dimension contenant des données de classification.](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [Canaux marketing](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | Les champs dérivés sont créés dans une vue de données. <p>[Créez un champ dérivé de canal marketing.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [Flux de données](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | L’export des données de première génération des jeux de données est disponible via l’[API Experience Platform Data Access](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=fr) et via les [Destinations Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=fr). Ces options permettent d’exporter au niveau de l’événement ou de la ligne toutes les données collectées ou ingérées dans le lac de données Experience Platform. Les colonnes de données de post-traitement ne sont pas disponibles, car les colonnes « post » sont calculées au moment de la requête. L’export de colonnes « post » est disponible via la création de rapports. |
| [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | [L’export de tableaux complets Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) correspond à l’évolution des rapports des entrepôts de données dans Adobe Analytics, avec de nombreuses nouvelles fonctionnalités souvent demandées et qui ne sont pas disponibles dans les entrepôts de données aujourd’hui. |
| [Données de streaming multimédia](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-overview) | Les données des médias en streaming sont disponibles dans le connecteur source Analytics dans le cadre des panneaux Visionneuses simultanées de médias et Temps de lecture de média dans l’espace de travail. |

