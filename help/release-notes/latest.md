---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4f228dbe58a9efbe988f274c071c61ec5e36d321
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 100%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (juillet 2024)

**Dernière mise à jour** : mardi 29 juillet 2024

Ces notes de mise à jour portent sur la période du 17 juillet 2024 à août 2024. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Alertes intelligentes** | Les alertes intelligentes sont désormais disponibles dans Customer Journey Analytics, ce qui vous permet de recevoir immédiatement une notification en cas d’événements anormaux dans vos données.<p>Vous pouvez définir le déclenchement d’alertes en fonction de seuils d’anomalie, de modification des pourcentages ou de points de données spécifiques. Les alertes fournissent des contrôles granulaires qui s’intègrent à la détection des anomalies, et se déclenchent lorsque vous en avez le plus besoin.</p><p>Le processus d’utilisation des alertes intelligentes dans Customer Journey Analytics est presque identique à celui des alertes intelligentes dans Adobe Analytics. Une différence majeure réside dans le fait que les alertes horaires ne sont pas disponibles dans Customer Journey Analytics. Cette différence est due au fait que l’ingestion des différents types de données d’événement pouvant être ingérés ne se termine qu’après un délai généralement compris entre 3 et 9 heures après l’heure de l’événement des données.</p><p>(Liens vers la documentation mise à jour à suivre)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | À confirmer |
| **Paramètres d’administration pour contrôler les comptes et les emplacements utilisés pour l’export des rapports dans le cloud** | Un nouvel onglet [« Paramètres d’administration » dans le gestionnaire des emplacements](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only) permet à l’équipe d’administration de contrôler si les utilisateurs et utilisatrices peuvent créer et modifier des comptes et des emplacements.<p>Ces paramètres s’appliquent lorsque les personnes [configurent des comptes d’export vers le cloud](/help/components/exports/cloud-export-accounts.md) et [configurent des emplacements d’export vers le cloud](/help/components/exports/cloud-export-locations.md).</p><p>L’administration peut également limiter les types de comptes que les personnes peuvent créer et utiliser. Les types de compte comprennent Google Cloud Platform, Azure RBAC, Amazon S3, AEP Data Landing Zone, Snowflake, etc.</p><p>Auparavant, un utilisateur ou une utilisatrice pouvait créer, modifier et utiliser des comptes et des emplacements pour n’importe quel type de compte.</p> | 11 juillet 2024 | 19 juillet 2024 |
| **Sources de données de niveau résumé** | Vous permet d’importer des données de série temporelle qui ne comportent pas d’ID de personne. Ces données de série temporelle peuvent être utilisées pour prendre en charge divers cas d’utilisation, tels que les suivants :<ul><li>Présenter des indicateurs de performances de haut niveau dans ou à côté des données au niveau de l’événement. Cela peut inclure des éléments aussi simples qu’une date et une valeur de mesure unique, ou inclure plusieurs dimensions et mesures, comme les impressions publicitaires, les ouvertures d’e-mails, les dépenses publicitaires, le coût des biens vendus, etc.</li><li>Charger des cibles ou des objectifs de manière quotidienne, hebdomadaire, mensuelle ou trimestrielle et positionner ces cibles ou ces objectifs par rapport à des mesures au niveau de l’événement afin de visualiser les tendances des mesures par rapport aux cibles ou aux objectifs de l’organisation.</li></ul><p>(Liens vers la documentation mise à jour à suivre)</p> |  | lundi 11 août 2024 |
| **Champs dérivés - Fonction de déduplication** | La [fonction de déduplication](/help/data-views/derived-fields/derived-fields.md#deduplicate) dans les champs dérivés vous permet d’éviter de compter une valeur plusieurs fois. |  | 17 juillet 2024 |
| **Approvisionnement de l’analyse guidée pour les clientes et clients CJA** | L’analyse guidée permet aux utilisateurs et aux utilisatrices d’obtenir des données et des informations en libre-service de haute qualité sur le parcours client au moyen de workflows guidés, établis à partir des données cross-canal de Customer Journey Analytics. <p>Les équipes interfonctionnelles, du marketing au produit, peuvent se connecter en temps réel pour utiliser et comprendre ces rapports.</p><p>Jusqu’à 11 vues d’analyse guidée sont désormais disponibles dans les packages CJA. [En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/guided-analysis/overview)</p> |  | 17 juillet 2024 |
| **Partager les comptes et les emplacements utilisés pour l’export et l’import** | Les personnes peuvent désormais mettre les comptes et les emplacements qu’elles créent à la disposition de toutes les personnes de leur organisation. Seules les personnes propriétaires de comptes et d’emplacements, ainsi que les personnes administratrices du système, peuvent modifier et supprimer des comptes et des emplacements. Auparavant, les comptes et les emplacements ne pouvaient être utilisés que par la personne qui les avait créés. Ces paramètres sont disponibles lorsque les personnes [configurent des comptes d’export vers le cloud](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) et [configurent des emplacements d’export vers le cloud](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12 juin 2024 | 19 juillet 2024 |
| **Les audiences sont publiées dans une nouvelle section « Audiences » dans Experience Platform.** | Les audiences qui sont publiées à partir de Customer Journey Analytics sont désormais disponibles dans la nouvelle section « Audiences » d’Adobe Experience Platform.<p>Auparavant, les audiences qui étaient publiées à partir de Customer Journey Analytics étaient disponibles dans Experience Platform dans la section « Segments ».</p><p>Cette amélioration s’accompagne des avantages suivants :</p><ul><li>Les audiences n’ont plus un délai d’une heure avant d’apparaître dans Experience Platform ; elles sont disponibles quelques secondes après leur publication.</li><li>Les audiences peuvent être triées dans Experience Platform à l’aide de la colonne « Origine », qui affiche l’application à partir de laquelle l’audience a été publiée à l’origine.</li><li>Les options de filtrage et de tri d’Experience Platform vous permettent de trouver plus rapidement les audiences pertinentes.</li></ul> <p>(Lien vers la documentation à suivre)</p> |  | À confirmer |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-306000 ; AN-288748 ; AN-351547 ; AN-351110

## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. | | |

{style="table-layout:auto"}

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2024](/help/release-notes/2024.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Collection de médias en streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
