---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 08fafc8191d72c95f35fc3d574f5d247d616d4d3
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 98%

---

# Notes de mise à jour de la version actuelle de Customer Journey Analytics (octobre 2025)

**Dernière mise à jour** : 14 octobre 2025

Ces notes de mise à jour portent sur la période allant d’octobre jusqu’au début du mois de novembre 2025. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Critères de filtre inclus dans les visualisations en ligne et les graphiques sparkline** | Désormais, tous les critères de filtre de recherche que vous appliquez à un filtre de tableau à structure libre sont toujours inclus dans les graphiques sparkline. En outre, vous pouvez inclure des critères de filtre de recherche dans n’importe quelle visualisation en ligne connectée.<p>Vous pouvez configurer les visualisations en ligne pour inclure des critères de filtre de recherche en sélectionnant le graphique sparkline dans l’en-tête de colonne des mesures du tableau connecté.</p><p>Auparavant, les critères de filtre de recherche n’étaient pas inclus dans les graphiques sparkline ou les visualisations en lignes connectées.</p><p>Pour plus d’informations, consultez [Afficher des données de tendance d’un tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).</p> | | 15 octobre 2025 |
| **Mise en récit des données : générer des présentations de diapositives à partir de rapports Workspace** | Vous pouvez désormais générer automatiquement une présentation de diapositives (au format .pptx) à partir d’un rapport Analysis Workspace. Workspace détecte les informations clés de votre rapport et les convertit en diapositives prêtes à être présentées aux parties prenantes.<p>Cette fonctionnalité réduit le temps et les efforts nécessaires pour faire ressortir les conclusions, élaborer des récits à l’intention de la direction et communiquer l’incidence sur l’entreprise.</p><p>Pour plus d’informations, consultez la section [Mise en récit des données : générer des présentations de diapositives à partir de rapports Workspace](/help/analysis-workspace/curate-share/generate-slides.md).</p> | 22 octobre 2025 | Janvier 2026 |
| **Reporting en temps réel** | [Le reporting en temps réel dans Customer Journey Analytics](/help/components/real-time/real-time.md) affiche et met à jour en temps réel les données et les visualisations au sein d’un ou de plusieurs panneaux dans Analysis Workspace. | 18 septembre 2025 (version initialement prévue pour le 15 août 2025) | 22 octobre 2025 |
| **Prise en charge de la mise en miroir des données** | Grâce à la prise en charge des schémas basés sur des modèles et de la fonctionnalité de capture de données modifiées (CDC) pour des connecteurs sources spécifiques dans Experience Platform, Customer Journey Analytics sera en mesure de prendre en charge la fonctionnalité de [mise en miroir des données](/help/data-mirror/data-mirror.md) des solutions d’entrepôt de données telles que [!DNL Snowflake], [!DNL Azure Databricks] et [!DNL Google BigQuery].<p>Contactez votre équipe Adobe en charge des comptes pour accéder à la version bêta.</p> | Version bêta : 24 septembre 2025 | À confirmer |
| **Groupement dans les connexions** | Simplifie le groupement Customer Journey Analytics. Au lieu de dupliquer un jeu de données et d’appliquer un groupement sur le jeu de données dupliqué, le groupement est désormais effectué sur l’ingestion de données dans Customer Journey Analytics, ce qui supprime l’exigence de jeux de données et de schémas dupliqués. <p>En outre, au lieu d’avoir à demander le groupement par le biais du service clientèle, vous pouvez désormais lancer le groupement vous-même à partir d’une interface d’utilisation de connexions mise à jour.</p><p> *Les dates de publication communiquées précédemment sont repoussées en raison d’efforts supplémentaires requis. Les nouvelles dates de publication coïncident avec la période des fêtes, ce qui introduit des contraintes de publication supplémentaires. Un déploiement progressif est maintenant prévu pour garantir la stabilité et réduire au minimum les perturbations pendant la période des fêtes.*</p> <p>(Lien vers la documentation à suivre.)</p> | 28 octobre 2025 | 30 avril 2026 |
| **Services de médias en streaming : prise en charge des données de planning** | Vous pouvez désormais charger des données planifiées antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [&#x200B; Chargement des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 octobre 2025 | Premier semestre 2026<p>(Version initialement prévue pour le jeudi 29 octobre 2025)</p> |
| **Connecteur source Analytics : recherche de suites de rapports dans Experience Platform** | La clientèle disposant d’un grand nombre de suites de rapports peut désormais rechercher la suite de rapports à laquelle elle souhaite se connecter dans le workflow de flux de données du connecteur source Analytics. <p>Auparavant, les clientes et clients devaient faire défiler une liste potentiellement longue de suites de rapports.</p><p>(Lien vers la documentation à suivre.) | | 30 octobre 2025 |
| **Médias en streaming : mise à jour des champs XDM pour la collecte des données des médias en streaming dans Adobe Experience Platform** | Lors de la collecte de données des médias en streaming dans Adobe Experience Platform, les chemins d’accès aux champs XDM affichés dans la section « Chemin d’accès au champ XDM » de la documentation des paramètres des médias de streaming ne doivent plus être utilisés. Au lieu de cela, les clientes et les clients qui ont implémenté le connecteur source Analytics pour collecter des données de médias en streaming dans Platform avant le 9 mai 2025 doivent migrer leurs configurations existantes vers les chemins d’accès aux champs mediaReporting, comme indiqué sous l’en-tête « Chemin d’accès au champ XDM de création de rapports » de la documentation des paramètres de médias en streaming.<p> Ces chemins d’accès aux champs se trouvent sur les pages suivantes et sont marqués comme « obsolètes » : [Paramètres audio et vidéo](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Paramètres d’annonce](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/ad-parameters), [Paramètres de chapitre](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/chapter-parameters), [Paramètres d’état du lecteur](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/player-state-parameters) et [Paramètres de qualité](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/quality-parameters). (Aucune action n’est requise de la part des clientes et des clients qui implémentent le connecteur source Analytics après le 9 mai 2025 et qui utilisent déjà uniquement les chemins XDM mediaReporting.)</p><p>L’ingestion de données sur les chemins d’accès aux champs XDM obsolètes se poursuivra jusqu’à la fin octobre 2025. Après cette date, les chemins d’accès aux champs obsolètes seront intégralement abandonnés et ne seront plus visibles dans l’interface d’utilisation de schéma Adobe Experience Platform, et les données seront envoyées uniquement à l’aide des chemins d’accès aux champs mediaReporting.</p><p>Pour plus d’informations, consultez [Migrer une implémentation du connecteur Source Analytics vers des champs de médias en streaming XDM mis à jour](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Pour obtenir de l’aide concernant la migration, contactez les services Adobe Consulting ou l’équipe en charge des comptes. </p> |  | Octobre 2025 |

## Correctifs dans Customer Journey Analytics

**Analysis Workspace** : AN-400507, AN-400265, AN-399209, AN-397146, AN-394992, AN-390795
**Composants** :
**Content Analytics** :
**Exports** : AN-399012, AN-388578
**Analyse guidée** :
**Implémentation** : AN-397551, AN-397550, AN-397190, AN-396127
**Report Builder** : AN-401127, AN-400618, AN-392971, AN-391692
**Création de rapports** :
**Segmentation** :
**Rapports planifiés** :
**Mesures et dimensions partagées** :
**Autre** :


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
