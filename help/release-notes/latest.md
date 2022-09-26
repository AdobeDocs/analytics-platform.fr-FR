---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: d2aec8976d7d81c28a6b9b76c58fec0fc2c3b360
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 91%

---

# Notes de mise à jour de la version actuelle de Customer Journey Analytics (CJA) (septembre 2022)

**Dernière mise à jour** : 14 septembre 2022

Les versions de Customer Journey Analytics fonctionnent sur une [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Ressources connexes

* [Notes de mise à jour de CJA précédentes pour 2022](/help/release-notes/2022.md)

* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)

* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)

* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)

## Principales fonctionnalités

| Fonctionnalité | Description | [Date ciblée](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Prise en charge inter-régions pour le connecteur source Analytics** | Vous pouvez désormais ingérer des suites de rapports à partir de n’importe quelle région (États-Unis, Royaume-Uni ou Singapour). Toutefois, ces suites de rapports doivent être mappées à la même organisation que l’instance Sandbox Experience Platform dans laquelle la connexion source est en cours de création. [En savoir plus](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) | 24 août 2022 |
| **Rapports de première session** | Déterminez si une session particulière a été la toute première d’un utilisateur. [En savoir plus](/help/data-views/data-views-usecases.md) | 24 août 2022 |
| **Panneau d’expérience pour CJA** | Ce nouveau panneau Workspace permet aux utilisateurs de CJA d’évaluer l’effet élévateur et le degré de confiance de toute expérience A/B, quelle qu’en soit la source : en ligne, hors ligne, à partir de solutions d’Adobe, d’Adobe Journey Optimizer et même de données BYO (apportez vos propres données). [En savoir plus](/help/analysis-workspace/c-panels/experimentation.md) | [Version limitée](/help/release-notes/releases.md) à compter du 14 septembre 2022 |
| **Visualisation de graphiques combinés dans Workspace** | Les graphiques combinés vous permettent de comparer plus facilement et intuitivement les mesures dans Workspace. [En savoir plus](/help/analysis-workspace/visualizations/combo-charts.md) | 14 septembre 2022 |
| **Assistance CJA pour des étiquettes et des stratégies de gouvernance des données** | Automatise l’intégration entre les étiquettes et les stratégies de confidentialité de CJA et Adobe Experience Platform. Les libellés de données créés sur les jeux de données consommés par Platform sont affichés dans les vues de données CJA pour stopper et ou avertir les utilisateurs qui créent des mesures et/ou des dimensions à partir de champs sensibles. En outre, lorsque les données sont exportées à partir de CJA (via la création de rapports Workspace ou Report Builder, l’exportation, l’API, etc.) des avertissements ou des étiquettes supplémentaires seront ajoutés afin d’informer les utilisateurs qu’un rapport contient des informations sensibles qui doivent être traitées d’une manière spécifique. [En savoir plus](/help/data-views/data-governance.md) | 14 septembre 2022 |

{style=&quot;table-layout:auto&quot;}

## Correctifs

AN-298412

## Avis importants destinés aux administrateurs de CJA

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| **Amélioration du mappage IP/géolocalisation** | 9 septembre 2022 | Digital Element, le fournisseur d’Adobe pour les recherches IP, effectue une mise à niveau vers un nouveau jeu de données amélioré (NetAcuity Pulse) pour le mappage IP/géolocalisation. Adobe Analytics adoptera ce nouveau jeu de données le **5 octobre 2022**. La nouvelle base de données sera plus précise que les versions précédentes. Certains mappages IP/géolocalisation seront modifiés/améliorés lors de l’adoption de la nouvelle base de données.<p> Les données CJA fournies par le biais du connecteur source Analytics tirent également automatiquement parti des nouveaux mappages. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
