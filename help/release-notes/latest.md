---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a7636909c0570655ee6d3638e56828916044d2bd
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 68%

---

# Notes de mise à jour du Customer Journey Analytics (CJA) (octobre/novembre 2022)

**Dernière mise à jour** : 19 octobre 2022

Les mises à jour de Customer Journey Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités clés et mises à jour

| Fonctionnalité | Description | [Début du déploiement](/help/release-notes/releases.md) | [Disponibilité générale](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| Visualisation **du**[!UICONTROL  résumé des mesures clés] | La visualisation [!UICONTROL du résumé des mesures clés] vous permet de visualiser le niveau de tendance d’une mesure importante au cours d’une seule période. Elle vous permet également de comparer les performances des mesures sur deux périodes. [En savoir plus](/help/analysis-workspace/visualizations/key-metric.md) | 5 octobre 2022 | 19 octobre 2022 |
| **Variables à plusieurs valeurs qui ne respectent pas la casse** | Pour les variables à plusieurs valeurs non sensibles à la casse, les valeurs stockées dans `mvvar1` - `mvvar3` ne sera plus automatiquement mis en minuscules. Au lieu de cela, les données transmises par le biais du connecteur source Analytics à Adobe Experience Platform et CJA refléteront le cas d’origine transmis à partir de la page. | S.O. | 24 octobre 2022 |
| **Journal d’audit CJA** | Customer Journey Analytics (CJA) vous permet de contrôler l’activité des utilisateurs pour divers services et fonctionnalités sous la forme de &quot;journaux d’audit&quot;. Ces journaux constituent un journal de vérification qui peut vous aider à résoudre les problèmes et à vous conformer efficacement aux politiques de gestion des données d’entreprise et aux exigences réglementaires, telles que la Loi sur la transférabilité et la responsabilité de l’assurance-santé (HIPAA). Auparavant, ces journaux n’étaient disponibles que via l’API Journaux d’audit. [Documentation à suivre] | S.O. | 26 octobre 2022 |
| **Préparation du HIPAA** | Description à suivre | S.O. | 7 novembre 2022 |

{style=&quot;table-layout:auto&quot;}

## Correctifs

* Correction d’un problème en raison duquel les versions récentes de MacOS étaient incorrectement nommées &quot;Macintosh&quot;. Avec ce correctif, la dimension du système d’exploitation commencera à utiliser la numérotation de version &quot;MacOS&quot;, à partir de MacOS 11. (AN-301834)

### Autres  correctifs

AN-302367 ; AN-302562

## Avis importants destinés aux administrateurs de CJA

| Avis | Avis ajouté ou mis à jour | Description |
| --- | --- | --- |
| **Page de destination par défaut** | 29 septembre 2023 | La [nouvelle page de destination](/help/getting-started/landing.md) qui a été introduite en début d’année deviendra l’expérience par défaut pour tous les utilisateurs en **janvier 2023**. La page actuelle deviendra obsolète et tout le monde devra utiliser la nouvelle expérience. |
| **Amélioration du mappage IP/géolocalisation** | 29 septembre 2022 | Digital Element, le fournisseur d’Adobe pour les recherches IP, effectue une mise à niveau vers un nouveau jeu de données amélioré (NetAcuity Pulse) pour le mappage IP/géolocalisation. Adobe Analytics a reporté l’adoption de ce nouveau jeu de données à **janvier 2023**. La nouvelle base de données sera plus précise que les versions précédentes. Certains mappages IP/géolocalisation seront modifiés/améliorés lors de l’adoption de la nouvelle base de données.<p> Les données CJA fournies par le biais du [!UICONTROL connecteur source Analytics] tireront également automatiquement parti des nouveaux mappages. |
| Conditions d’exécution automatique de la **[!UICONTROL détection des anomalies]** | 29 septembre 2022 | Aujourd’hui, la [!UICONTROL détection des anomalies] s’exécute automatiquement sur toutes les colonnes des tableaux à structure libre de série temporelle. Afin de garantir que les données sont disponibles pour l’analyse et que les projets se chargent plus rapidement, Adobe modifie la manière dont la [!UICONTROL détection des anomalies] s’exécute automatiquement. À compter du **26 octobre 2022**, la détection des anomalies s’exécutera automatiquement uniquement sur la première colonne de mesures d’un tableau. Si nécessaire, vous pouvez configurer les paramètres des colonnes pour exécuter la [!UICONTROL détection des anomalies] sur d’autres colonnes. |

{style=&quot;table-layout:auto&quot;}


## Ressources connexes

* [Notes de mise à jour de CJA précédentes pour 2022](/help/release-notes/2022.md)

* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)

* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)

* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)

* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
