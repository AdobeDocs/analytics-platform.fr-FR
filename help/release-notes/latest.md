---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 9f60d83673591aebeffeb6442bf9f8b897ab2f20
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 95%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (janvier 2024)

**Dernière mise à jour** : 30 janvier 2024

Ces notes de mise à jour portent sur la période du 8 janvier 2024 au 13 février 2024. Les mises à jour d’Adobe Customer Journey Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Détails des enregistrements ignorés** | Vous pouvez récupérer des détails sur les raisons pour lesquelles les enregistrements sont ignorés lors de la configuration d’une connexion. Voir [Détails de la connexion](../connections/manage-connections.md#connection-details) pour plus d’informations. | mardi 5 février 2024 | mardi 5 février 2024 |
| **Prévision de séries temporelles** | La [prévision](../analysis-workspace/c-forecast/forecasting.md) est une nouvelle fonction d’Analysis Workspace qui permet de prévoir une mesure standard ou calculée avec toutes les granularités temporelles prises en charge (horaires, quotidiennes, hebdomadaires, mensuelles et annuelles) pour les tableaux à structure libre et les graphiques linéaires. | 31 janvier 2024 | 21 février 2024 |
| **Mises à jour de la visualisation du résumé des mesures clés** | Avec la visualisation du résumé des mesures clés, la période de comparaison peut désormais se mettre à jour automatiquement, selon que l’option Période de comparaison que vous choisissez est relative à la période principale ou fixe. [En savoir plus](/help/analysis-workspace/visualizations/key-metric.md). | S.O. | 17 janvier 2024 |
| **Adobe Product Analytics : analyse des taux de rétention** | Les taux de rétention sont une nouvelle analyse guidée qui vous permet de mesurer les habitudes de retour régulières de vos utilisateurs. [En savoir plus](../guided-analysis/types/retention-rates.md) | S.O. | 8 janvier 2024 |
| **Adobe Product Analytics : incrustation de lignes de tendance** | Les lignes de tendance sont un nouveau paramètre d’incrustation disponible dans la vue [Tendances d’utilisation](/help/guided-analysis/types/usage.md). Elles permettent de représenter plus clairement un modèle dans les données. | S.O. | 17 janvier 2024 |
| **Adobe Product Analytics : améliorations du rail de requête** | Dans l’analyse guidée, le rail de requête de gauche inclut désormais les paramètres Type d’affichage et Compté comme, auparavant disponibles dans les paramètres de visualisation. | S.O. | 31 janvier 2024 |
| **Adobe Product Analytics : analyse du flux des utilisateurs** | Les flux d’utilisateurs sont une nouvelle analyse guidée qui vous permet d’explorer des flux d’événements individuels de personnes, ce qui peut vous aider à trouver des schémas d’expérience et à raconter de meilleures stories d’utilisateurs. | S.O. | 7 février 2024 |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-310972 ; AN-332774 ; AN-332793 ; AN-332796 ; AN-333157 ; AN-334067 ; AN-334134 ; AN-334968 ; AN-335315 ; AN-335518 ; AN-335533 ; AN-335736 ;

## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| Ajout de membres aux objets d’API Adobe | 17 janvier 2024 | Adobe peut ajouter des membres de requête et de réponse facultatifs (paires nom/valeur) aux objets d’API existants sans préavis ni modification du contrôle de version. Ces ajouts doivent constituer des modifications sans ruptures pour votre mise en œuvre. Adobe vous recommande de vous référer à la documentation de l’API de tout outil tiers que vous intégrez à nos API, afin que ces ajouts soient ignorés dans le traitement s’ils ne sont pas compris. Adobe ne supprimera pas de paramètres ni n’ajoutera de paramètres requis sans d’abord fournir une notification standard via les notes de mise à jour. |

{style="table-layout:auto"}

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
