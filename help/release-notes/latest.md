---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 41cca39d73773af09981bde10c93c767ebdb77d4
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 79%

---

# Notes de mise à jour du Customer Journey Analytics actuel (CJA) (septembre 2022)

**Dernière mise à jour**: 9 septembre 2022

>[!NOTE]
>
>Cette page contient du contenu publié avant la date de publication et peut faire l’objet de modifications.

## Ressources connexes

* [Notes de mise à jour précédentes de CJA pour 2022](/help/release-notes/2022.md)

* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)

* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)

* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)

## Principales fonctionnalités

| Fonctionnalité | Description | [Date ciblée](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Panneau d’observateurs simultanés de médias** | Déterminez où s’est produit le pic d’accès simultanés et où des abandons ont eu lieu. Obtenez des informations importantes sur la qualité du contenu et l’engagement des observateurs, ainsi que de l’aide concernant la résolution de problèmes ou la planification du volume et de l’échelle. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=fr) | 9 août 2022 |
| **Panneau Temps de lecture de média** | Le panneau Temps de lecture de média fournit des informations importantes sur lʼengagement des observateurs. Il permet également aux organisations de médias dʼobtenir des informations plus approfondies et plus granulaires sur lʼinteraction client, minute par minute, grâce à une analyse avancée de la durée de la lecture et des fonctionnalités dʼanalyse par tranches horaires.<p>Vous pouvez observer la durée de visionnage de vos flux multimédias à un moment précis. Vous pouvez diviser la durée de lecture selon différentes granularités, notamment les nouvelles granularités de 5 minutes, 15 minutes et 30 minutes. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=fr) | 9 août 2022 |
| **Publication d’audiences dans le profil client en temps réel** | Permet de publier les audiences découvertes dans CJA vers Adobe Experience Platform/profil client en temps réel pour le ciblage et la personnalisation des clients. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=fr) | 17 août 2022 |
| **Assistance CJA pour des étiquettes et des stratégies de gouvernance des données** | Automatise l’intégration entre les étiquettes et les stratégies de confidentialité de CJA et Adobe Experience Platform. Les libellés de données créés sur les jeux de données consommés par Platform sont affichés dans les vues de données CJA pour stopper et ou avertir les utilisateurs qui créent des mesures et/ou des dimensions à partir de champs sensibles. En outre, lorsque les données sont exportées à partir de CJA (via la création de rapports Workspace ou Report Builder, l’exportation, l’API, etc.) des avertissements ou des étiquettes supplémentaires seront ajoutés afin d’informer les utilisateurs qu’un rapport contient des informations sensibles qui doivent être traitées d’une manière spécifique. [En savoir plus](/help/data-views/data-governance.md) | 17 août 2022 |
| **Prise en charge inter-régions pour le connecteur source Analytics** | Vous pouvez désormais ingérer des suites de rapports à partir de n’importe quelle région (États-Unis, Royaume-Uni ou Singapour). Toutefois, ces suites de rapports doivent être mappées à la même organisation que l’instance Sandbox Experience Platform dans laquelle la connexion source est en cours de création. [En savoir plus](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) | 24 août 2022 |
| **Rapports de première session** | Découvrez si une session particulière a été la toute première session d’un utilisateur. [En savoir plus](/help/data-views/data-views-usecases.md) | 24 août 2022 |
| **Panneau d’expérience pour CJA** | Ce nouveau panneau Espace de travail permet aux utilisateurs de CJA d’évaluer l’effet élévateur et le degré de confiance de toute expérience A/B à partir de n’importe quelle source (en ligne, hors ligne, à partir de solutions d’Adobe, de Adobe Journey Optimizer et même de données BYO (apportez-vous). [En savoir plus](/help/analysis-workspace/c-panels/experimentation.md) | [Version limitée](/help/release-notes/releases.md) à compter du 14 septembre 2022 |
| **Visualisation de tableaux combinés dans Workspace** | Les graphiques à virgules vous permettent de comparer plus facilement et intuitivement les mesures dans Workspace. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/combo-charts.html?lang=en) | 14 septembre 2022 |

{style=&quot;table-layout:auto&quot;}

## Correctifs

AN-298412

## Avis importants destinés aux administrateurs de CJA

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| **Amélioration du mappage IP/géolocalisation** | 9 septembre 2022 | Digital Element, le fournisseur d’Adobe pour les recherches IP, effectue une mise à niveau vers un nouveau jeu de données amélioré (NetAcuity Pulse) pour le mappage IP/géolocalisation. Adobe Analytics adoptera ce nouveau jeu de données sur **5 octobre 2022**. La nouvelle base de données sera plus précise que les versions précédentes. Certains mappages IP/géolocalisation seront modifiés/améliorés lors de l’adoption de la nouvelle base de données.<p> Les données CJA fournies par le biais du connecteur source Analytics tirent également automatiquement parti des nouveaux mappages. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
