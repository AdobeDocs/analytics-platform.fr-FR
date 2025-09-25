---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 017bf3cb720ed153476d17db92e0eeca156e6b61
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 91%

---

# Notes de mise à jour actuelles de Customer Journey Analytics (septembre 2025)

**Dernière mise à jour** : mercredi 23 septembre 2025


Ces notes de mise à jour portent sur la période allant de septembre jusqu’à octobre 2025. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mises à jour de l’interface Utilisation** | L’[interface Utilisation](/help/connections/manage-connections.md#usage) ajoute désormais des informations sur le volume des données de base et la taille moyenne des lignes.<p>Pour plus d’informations, voir [Gérer des connexions](/help/connections/manage-connections.md#usage).</p> | | 4 septembre 2025 |
| **Améliorations apportées lors de la migration de projets et de composants vers Customer Journey Analytics** | Les améliorations suivantes sont désormais disponibles lors de la migration de projets et de composants d’Adobe Analytics vers Customer Journey Analytics :<ul><li>Migration simultanée de plusieurs projets.<br/>Vous pouvez migrer jusqu’à 20 projets à la fois.<br/>Auparavant, vous ne pouviez migrer qu’un seul projet à la fois.</li><li>Mise à jour des mappages pour les dimensions et les mesures déjà mappées lors d’une migration de projet précédente.<br/>Vous pouvez désormais mettre à jour ces mappages chaque fois que vous migrez un projet, même si les mêmes dimensions et mesures ont été précédemment mappées avec une migration précédente.<br/>Auparavant, tous les mappages que vous choisissiez étaient permanents pour toutes les migrations futures du projet.</li><li>Amélioration des performances pour les organisations ayant un grand nombre de projets.</li></ul><p>Cette fonctionnalité est disponible à partir de l’interface d’Adobe Analytics. Pour plus d’informations, voir [Migrer des composants et des projets d’Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/component-migration/component-migration).</p> | 15 septembre 2025 | 18 septembre 2025 |
| **La limite des clés de recherche a augmenté jusqu’à 1 milliard.** | Le nombre maximal de clés uniques pour un jeu de données de recherche peut désormais atteindre 1 milliard, selon vos droits Customer Journey Analytics. <p>Auparavant, le nombre maximal était de 10 millions pour tous les droits.<p>Pour plus d’informations, voir [Mécanismes de sécurisation](/help/technotes/guardrails.md).</p> | | vendredi 25 septembre 2025 |
| **Prise en charge des schémas ad hoc et basés sur des modèles** | Les schémas [ad hoc](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/tutorials/ad-hoc) et basés sur des modèles sont utilisés dans les workflows d’ingestion de données et de mise en miroir des données pour Experience Platform. |  | mercredi 23 septembre 2025 (version initialement prévue pour le 28 août 2025) |
| **Rapports en temps réel** | Les rapports en temps réel dans Customer Journey Analytics affichent et mettent à jour en temps réel les données et les visualisations au sein d’un ou de plusieurs panneaux dans Analysis Workspace.<br/><br/>(Lien vers la documentation à suivre.) | 18 septembre 2025 (version initialement prévue pour le 15 août 2025) | jeudi 1 octobre 2025 |
| **Prise en charge du miroir de données** | Grâce à la prise en charge des schémas basés sur des modèles et de la fonctionnalité de capture de données modifiées (CDC) pour des connecteurs source spécifiques dans Experience Platform, Customer Journey Analytics sera en mesure de prendre en charge la fonctionnalité de miroir de données des solutions d’entrepôt de données telles que [!DNL Snowflake], [!DNL Azure Databrick] et [!DNL Google BigQuery].<p>Contactez votre équipe Adobe en charge des comptes pour accéder à la version Beta.</p><p>(Lien vers la documentation à suivre.)</p> | Version de Beta, à partir du 24 septembre 2025 | À confirmer |
| **Médias en streaming : mise à jour des champs XDM pour la collecte des données des médias en streaming dans Adobe Experience Platform** | Lors de la collecte de données des médias en streaming dans Adobe Experience Platform, les chemins d’accès aux champs XDM affichés dans la section « Chemin d’accès au champ XDM » de la documentation des paramètres des médias de streaming ne doivent plus être utilisés. Au lieu de cela, les clientes et les clients qui ont implémenté le connecteur source Analytics pour collecter des données de médias en streaming dans Platform avant le 9 mai 2025 doivent migrer leurs configurations existantes vers les chemins d’accès aux champs mediaReporting, comme indiqué sous l’en-tête « Chemin d’accès au champ XDM de création de rapports » de la documentation des paramètres de médias en streaming.<p> Ces chemins d’accès aux champs se trouvent sur les pages suivantes et sont marqués comme « obsolètes » : [Paramètres audio et vidéo](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Paramètres d’annonce](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/ad-parameters), [Paramètres de chapitre](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/chapter-parameters), [Paramètres d’état du lecteur](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/player-state-parameters) et [Paramètres de qualité](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/quality-parameters). (Aucune action n’est requise de la part des clientes et des clients qui implémentent le connecteur source Analytics après le 9 mai 2025 et qui utilisent déjà uniquement les chemins XDM mediaReporting.)</p><p>L’ingestion de données sur les chemins d’accès aux champs XDM obsolètes se poursuivra jusqu’à la fin octobre 2025. Après cette date, les chemins d’accès aux champs obsolètes seront intégralement abandonnés et ne seront plus visibles dans l’interface d’utilisation de schéma Adobe Experience Platform, et les données seront envoyées uniquement à l’aide des chemins d’accès aux champs mediaReporting.</p><p>Pour plus d’informations, consultez [Migrer une implémentation du connecteur Source Analytics vers des champs de médias en streaming XDM mis à jour](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Pour obtenir de l’aide concernant la migration, contactez les services Adobe Consulting ou l’équipe en charge des comptes. </p> |  | Octobre 2025 |
| **Groupement dans les connexions** | Simplifie le groupement Customer Journey Analytics. Au lieu de dupliquer un jeu de données et d’appliquer un groupement sur le jeu de données dupliqué, le groupement est désormais effectué sur l’ingestion de données dans Customer Journey Analytics, ce qui supprime l’exigence de jeux de données et de schémas dupliqués. <p>En outre, au lieu d’avoir à demander le groupement par le biais du service clientèle, vous pouvez désormais lancer le groupement vous-même à partir d’une interface d’utilisation de connexions mise à jour.</p><p> *Les dates de publication communiquées précédemment sont repoussées en raison d’efforts supplémentaires requis. Les nouvelles dates de publication coïncident avec la période des fêtes, ce qui introduit des contraintes de publication supplémentaires. Un déploiement progressif est maintenant prévu pour garantir la stabilité et réduire au minimum les perturbations pendant la période des fêtes.*</p> <p>(Lien vers la documentation à suivre.)</p> | Fin octobre 2025 | Fin janvier 2025 |

## Correctifs dans Customer Journey Analytics

**Analysis Workspace** : AN-391719, AN-380838, AN-389402, AN-389373, AN-390851, AN-391593, AN-391404, AN-393064, AN-379337
**Composants** : AN-393810
**Content Analytics** :
**Analyse guidée** :
**Plateforme** :
**Report Builder ** : AN-387741, AN-386777, AN-388720, AN-389343
**Reporting** : AN-391439, AN-391228, AN-393620, AN-393640, AN-391334, AN-393304
**Segmentation** :
**Rapports planifiés** : AN-391150, AN-390474
**Mesures et dimensions partagées** :
**Autre** : AN-387858


## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. | | |

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
