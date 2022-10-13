---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 45e4a60b6bbf38e33f307dbbbf68ab3124dd6a33
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 45%

---

# Notes de mise à jour du Customer Journey Analytics (CJA) (octobre 2022)

**Dernière mise à jour**: 13 octobre 2022

Les mises à jour de Customer Journey Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Ressources connexes

* [Notes de mise à jour de CJA précédentes pour 2022](/help/release-notes/2022.md)

* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)

* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)

* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)

## Fonctionnalités clés et mises à jour

| Fonctionnalité | Description | [Date ciblée](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Panneau d’expérience** | Ce nouveau panneau Workspace permet aux utilisateurs de CJA d’évaluer l’effet élévateur et le degré de confiance de toute expérience A/B à partir de n’importe quelle source (en ligne, hors ligne, à partir de solutions d’Adobe, d’Adobe Journey Optimizer et même de données BYO). [En savoir plus](/help/analysis-workspace/c-panels/experimentation.md) | 5 octobre 2022 |
| **[!UICONTROL Résumé des mesures clés] visualisation** | Le [!UICONTROL Résumé des mesures clés] la visualisation vous permet de visualiser les tendances d’une mesure importante au cours d’une seule période. Il vous permet également de comparer les performances des mesures sur deux périodes. En savoir plus | Déploiement par phases commençant le 5 octobre 2022 |
| **Prise en charge des champs de date dans CJA** | Permet à CJA de générer des rapports sur les champs de date et de date-heure. [En savoir plus](/help/data-views/data-views-usecases.md#date) | 5 octobre 2022 |
| **Application mobile : Affichages détaillés personnalisés** | Les vues détaillées personnalisées vous permettent d’être encore plus ciblé sur les informations que vous partagez avec votre audience, en leur permettant de vous concentrer sur les informations les plus importantes. Vous pouvez modifier la mise en page de la vue détaillée associée à chaque mosaïque de Fiche d’évaluation et vous pouvez ajouter du texte pour mieux expliquer ce que l’utilisateur peut voir dans les données. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=fr) | 5 octobre 2022 |
| **Variables à plusieurs valeurs non sensibles à la casse** | Pour les variables à plusieurs valeurs insensibles à la casse, les valeurs stockées dans mvvar1 - mvvar3 ne seront plus automatiquement mises en minuscules. Au lieu de cela, les données transmises par le biais du connecteur source Analytics à Adobe Experience Platform et CJA refléteront le cas d’origine transmis à partir de la page. | 24 octobre 2022 |

{style=&quot;table-layout:auto&quot;}

## Avis importants destinés aux administrateurs de CJA

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| **Landing Page par défaut** | 29 septembre 2023 | Le [nouvelle landing page](/help/getting-started/landing.md) qui a été introduit au début de cette année deviendra l’expérience par défaut pour tous les utilisateurs de **Janvier 2023**. La page actuelle sera obsolète et tout le monde devra utiliser la nouvelle expérience. |
| **Amélioration du mappage IP/géolocalisation** | 29 septembre 2022 | Digital Element, le fournisseur d’Adobe pour les recherches IP, effectue une mise à niveau vers un nouveau jeu de données amélioré (NetAcuity Pulse) pour le mappage IP/géolocalisation. Adobe Analytics a reporté l’adoption de ce nouveau jeu de données sur **Janvier 2023**. La nouvelle base de données sera plus précise que les versions précédentes. Certains mappages IP/géolocalisation seront modifiés/améliorés lors de l’adoption de la nouvelle base de données.<p> Données CJA fournies par le biais de [!UICONTROL Connecteur source Analytics] tirera également automatiquement parti des nouveaux mappages. |
| **[!UICONTROL Détection des anomalies] conditions d’exécution automatique** | 29 septembre 2022 | Aujourd&#39;hui, [!UICONTROL Détection des anomalies] s’exécute automatiquement sur toutes les colonnes des tableaux à structure libre de série temporelle. Afin de garantir que les données sont disponibles pour l’analyse et que les projets se chargent plus rapidement, Adobe modifie la manière dont [!UICONTROL Détection des anomalies] s’exécute automatiquement. Démarrage **26 octobre 2022**, la détection des anomalies s’exécute automatiquement uniquement sur la première colonne de mesures d’un tableau. Vous pouvez configurer les paramètres de colonne pour qu’ils s’exécutent. [!UICONTROL Détection des anomalies] sur d’autres colonnes, le cas échéant. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
