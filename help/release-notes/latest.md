---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 785ea95049135adef888c20a6d9fef9f31439a7d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Notes de mise à jour du Customer Journey Analytics (CJA) (octobre 2022)

**Dernière mise à jour** : 18 octobre 2022

Les mises à jour de Customer Journey Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Ressources connexes

* [Notes de mise à jour de CJA précédentes pour 2022](/help/release-notes/2022.md)

* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)

* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)

* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)

## Fonctionnalités clés et mises à jour

| Fonctionnalité | Description | [Date ciblée](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Dossiers dans les projets Workspace** | Les dossiers dans les projets Workspace aident les utilisateurs à organiser et catégoriser leurs projets à l’aide de dossiers pour une meilleure récupération et un meilleur accès. Un dossier d’entreprise partagé permet aux administrateurs de créer et de partager facilement du contenu avec tous les utilisateurs de Workspace. [En savoir plus](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md) | 19 octobre 2022 |
| **Panneau d’expérience** | Ce nouveau panneau Workspace permet aux utilisateurs de CJA d’évaluer l’effet élévateur et le degré de confiance de toute expérience A/B à partir de n’importe quelle source (en ligne, hors ligne, à partir de solutions d’Adobe, d’Adobe Journey Optimizer et même de données BYO). [En savoir plus](/help/analysis-workspace/c-panels/experimentation.md) | 5 octobre 2022 |
| Visualisation du **[!UICONTROL résumé des mesures clés]** | La visualisation du [!UICONTROL résumé des mesures clés] vous permet de visualiser le niveau de tendance d’une mesure importante au cours d’une période unique. Elle vous permet également de comparer les performances des mesures sur deux périodes. En savoir plus | Le déploiement par phases commence le 5 octobre 2022. |
| **Prise en charge des champs de date dans CJA** | Permet à CJA de générer des rapports sur les champs de date et de date-heure. [En savoir plus](/help/data-views/data-views-usecases.md#date) | 5 octobre 2022 |
| **Application mobile : vues détaillées personnalisées** | Les vues détaillées personnalisées vous permettent de cibler encore mieux les informations que vous partagez avec votre audience, en lui permettant de se concentrer sur ce qui est le plus important. Vous pouvez modifier la mise en page de la vue détaillée associée à chaque vignette de carte de performance et vous pouvez ajouter du texte pour mieux expliquer ce que l’utilisateur peut voir dans les données. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=fr) | 5 octobre 2022 |
| **Variables à plusieurs valeurs non sensibles à la casse** | Pour les variables à plusieurs valeurs non sensibles à la casse, les valeurs stockées dans `mvvar1` - `mvvar3` ne sera plus automatiquement mis en minuscules. Au lieu de cela, les données transmises par le biais du connecteur source Analytics à Adobe Experience Platform et CJA refléteront le cas d’origine transmis à partir de la page. | 24 octobre 2022 |

{style=&quot;table-layout:auto&quot;}

## Avis importants destinés aux administrateurs de CJA

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| **Page de destination par défaut** | 29 septembre 2023 | La [nouvelle page de destination](/help/getting-started/landing.md) qui a été introduite en début d’année deviendra l’expérience par défaut pour tous les utilisateurs en **janvier 2023**. La page actuelle deviendra obsolète et tout le monde devra utiliser la nouvelle expérience. |
| **Amélioration du mappage IP/géolocalisation** | 29 septembre 2022 | Digital Element, le fournisseur d’Adobe pour les recherches IP, effectue une mise à niveau vers un nouveau jeu de données amélioré (NetAcuity Pulse) pour le mappage IP/géolocalisation. Adobe Analytics a reporté l’adoption de ce nouveau jeu de données sur **Janvier 2023**. La nouvelle base de données sera plus précise que les versions précédentes. Certains mappages IP/géolocalisation seront modifiés/améliorés lors de l’adoption de la nouvelle base de données.<p> Données CJA fournies par le biais de [!UICONTROL Connecteur source Analytics] tirera également automatiquement parti des nouveaux mappages. |
| Conditions d’exécution automatique de la **[!UICONTROL détection des anomalies]** | 29 septembre 2022 | Aujourd’hui, la [!UICONTROL détection des anomalies] s’exécute automatiquement sur toutes les colonnes des tableaux à structure libre de série temporelle. Afin de garantir que les données sont disponibles pour l’analyse et que les projets se chargent plus rapidement, Adobe modifie la manière dont [!UICONTROL Détection des anomalies] s’exécute automatiquement. À compter du **26 octobre 2022**, la détection des anomalies s’exécutera automatiquement uniquement sur la première colonne de mesures d’un tableau. Vous pouvez configurer les paramètres de colonne pour qu’ils s’exécutent. [!UICONTROL Détection des anomalies] sur d’autres colonnes, le cas échéant. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
