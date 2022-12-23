---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fbfc7113aef8857e11ccfba5e5e557eed16c2465
workflow-type: ht
source-wordcount: '598'
ht-degree: 100%

---

# Notes de mise à jour de Customer Journey Analytics (CJA) (octobre/novembre 2022)

**Dernière mise à jour** : 25 octobre 2022

Les mises à jour de Customer Journey Analytics fonctionnent sur une [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités clés et mises à jour

| Fonctionnalité | Description | [Début du déploiement](/help/release-notes/releases.md) | [Disponibilité générale](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| Visualisation du **[!UICONTROL résumé des mesures clés]** | La visualisation [!UICONTROL du résumé des mesures clés] vous permet de visualiser le niveau de tendance d’une mesure importante au cours d’une seule période. Elle vous permet également de comparer les performances des mesures sur deux périodes. [En savoir plus](/help/analysis-workspace/visualizations/key-metric.md) | 5 octobre 2022 | 19 octobre 2022 |
| **Variables à plusieurs valeurs non sensibles à la casse** | Pour les variables à plusieurs valeurs non sensibles à la casse, les valeurs stockées dans `mvvar1` - `mvvar3` ne seront plus automatiquement mises en minuscules. Au lieu de cela, les données transmises par le biais du connecteur source Analytics à Adobe Experience Platform et CJA refléteront la casse d’origine transmise à partir de la page. Les colonnes ASC/CJA `_experience.analytics.customDimensions.lists.list1.list[]` - `_experience.analytics.customDimensions.lists.list3.list[]` sont affectées par cette modification. | S.O. | 24 octobre 2022 |
| **Journal d’audit de CJA** | Customer Journey Analytics (CJA) vous permet de contrôler l’activité des utilisateurs dans divers services et fonctionnalités par le biais de « journaux d’audit ». Ces logs constituent un journal d’audit qui peut vous aider à résoudre les problèmes et à vous conformer efficacement aux politiques de gestion des données d’entreprise et aux exigences réglementaires, telles que la Health Insurance Portability and Accountability Act (HIPAA). Auparavant, ces journaux n’étaient disponibles que via l’API Journaux d’audit. [En savoir plus](/help/privacy/audit-log.md) | S.O. | 26 octobre 2022 |
| **Préparation du HIPAA** | Adobe prend désormais en charge la réception, l’utilisation, la maintenance ou la transmission d’informations de santé protégées dans Customer Journey Analytics et d’autres applications basées sur Experience Platform pour les clients de Healthcare Shield uniquement. Healthcare Shield est destiné aux clients du secteur de la santé qui sont soit une entité couverte, soit un associé d’entreprise aux États-Unis uniquement. [En savoir plus](https://www.adobe.com/trust/compliance/hipaa-ready.html) | S.O. | 7 novembre 2022 |
| **Protection par mot de passe des projets planifiés** | Cette fonctionnalité fait partie de la préparation HIPAA et s’applique uniquement aux clients de Healthcare Shield. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=fr#password) | S.O. | 7 novembre 2022. |

{style=&quot;table-layout:auto&quot;}

## Correctifs

* Correction d’un problème en raison duquel les versions récentes de MacOS étaient incorrectement nommées « Macintosh ». Avec ce correctif, la dimension du système d’exploitation commencera à utiliser la numérotation de version de « MacOS » à partir de MacOS 11. (AN-301834)

### Autres correctifs

AN-302367 ; AN-302562 ; AN-304036

## Avis importants destinés aux administrateurs de CJA

| Avis | Ajout ou mise à jour des avis | Description |
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
