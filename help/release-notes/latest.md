---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3955f7c8da90481610328c0657b33e81ad6c0057
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 47%

---

# Notes de mise à jour actuelles de Customer Journey Analytics (janvier 2026)

**Dernière mise à jour** : jeudi 14 janvier 2026

Ces notes de mise à jour couvrent la période de publication de janvier 2026. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analyse des audiences des jeux de données de profil Experience Platform dans Customer Journey Analytics** | Vous pouvez désormais ingérer des données d’appartenance à une audience à partir de jeux de données Profil Experience Platform dans une connexion Customer Journey Analytics. Les audiences deviennent disponibles en tant que nouvelles dimensions à utiliser dans Analysis Workspace.<p>Cela est rendu possible grâce à une nouvelle fonctionnalité dans Customer Journey Analytics permettant d’ingérer des mappages d’objets XDM, ce qui permet d’ingérer des identifiants d’audience de profil.</p><p>Auparavant, seules les cartes XDM simples pouvaient être ingérées dans Customer Journey Analytics.</p><p>En plus de pouvoir ajouter des données d’audience en tant que dimensions à n’importe quel projet dans Analysis Workspace, les nouveaux modèles Workspace suivants sont également disponibles :</p><ul><li>Présentation d’Audience Analytics</li><li>Présentation de la politique de consentement</li></ul><p>Pour plus d’informations, voir [Présentation de l’analyse de l’audience](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/audience-analysis/audience-analysis-overview.html).</p> | 22 octobre 2025 | mercredi 27 janvier 2026 <p> (Initialement prévu pour le 22 janvier 2026)</p> |
| **Mise en récit des données : générer des présentations de diapositives à partir de rapports Workspace** | Vous pouvez désormais générer automatiquement une présentation de diapositives (au format .pptx) à partir d’un rapport Analysis Workspace. Workspace détecte les informations clés de votre rapport et les convertit en diapositives prêtes à être présentées aux parties prenantes.<p>Cette fonctionnalité réduit le temps et les efforts nécessaires pour faire ressortir les conclusions, élaborer des récits à l’intention de la direction et communiquer l’incidence sur l’entreprise.</p><p>Pour plus d’informations, consultez la section [Mise en récit des données : générer des présentations de diapositives à partir de rapports Workspace](/help/analysis-workspace/curate-share/generate-slides.md).</p> | 22 octobre 2025 | jeudi 28 janvier 2026 |
| **Inclure plusieurs colonnes de dimension dans un tableau à structure libre** | Vous pouvez désormais inclure jusqu’à 5 colonnes de dimension dans un tableau à structure libre, ce qui vous permet d’afficher plusieurs éléments de dimension côte à côte. Chaque ligne d’éléments de dimension se comporte comme un seul élément de dimension concaténé.<p>Vous pouvez appliquer des filtres, un tri, des répartitions, etc. aux tableaux à structure libre à plusieurs colonnes de dimensions afin de créer une analyse plus approfondie et plus personnalisée.</p><p>Auparavant, vous pouviez inclure une seule colonne de dimension dans un tableau à structure libre.</p><p>Pour plus d’informations, voir [Inclure plusieurs colonnes de dimensions dans un tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | jeudi 28 janvier 2026 | jeudi 18 février 2026 |
| **Trier les tableaux sur plusieurs colonnes** | Vous pouvez désormais trier les données d’un tableau à structure libre selon plusieurs colonnes dans Analysis Workspace, qu’il s’agisse de dimensions ou de mesures.<p>Lorsque vous triez des données pour plusieurs colonnes, les données sont triées en fonction de la priorité que vous attribuez à chaque colonne. La numérotation de priorité s’affiche en regard de l’icône de tri.</p><p>(Lien vers la documentation à suivre.)<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | jeudi 28 janvier 2026 | jeudi 18 février 2026 |
| **Combiner des sources de données provenant de plusieurs organisations IMS** | Vous pouvez désormais utiliser le connecteur Source Analytics pour combiner plusieurs sources de données provenant de plusieurs organisations IMS. Cela permet aux organisations d’avoir une vue combinée de leurs données client, même lorsque ces données client sont réparties sur plusieurs organisations IMS. <p>**Remarque :** cette configuration n’est disponible qu’en envoyant une demande à l’assistance clientèle d’Adobe.</p>  <p>(Lien vers la documentation à suivre.)</p> |  | samedi 30 janvier 2026 |
| **Groupement dans les connexions** | Le processus d’assemblage dans Customer Journey Analytics est désormais plus simple. Au lieu de dupliquer un jeu de données et d’appliquer un groupement sur le jeu de données dupliqué, le groupement est désormais effectué sur l’ingestion de données dans Customer Journey Analytics, ce qui supprime l’exigence de jeux de données et de schémas dupliqués. <p>En outre, vous pouvez désormais [lancer le groupement vous-même via une interface de connexions mise à jour](/help/stitching/use-stitching-ui.md), au lieu d’avoir à demander le groupement via l’assistance clientèle d’Adobe.</p><p> *Les dates de publication communiquées précédemment ont été reportées en raison des efforts supplémentaires requis et de la saison des fêtes. Un déploiement progressif est maintenant prévu pour garantir la stabilité et réduire au minimum les perturbations pendant la période des fêtes.*</p> | 28 octobre 2025 | samedi 30 janvier 2026 |
| **Prise en charge de la mise en miroir des données** | Grâce à la prise en charge des schémas basés sur des modèles et de la fonctionnalité de capture de données modifiées (CDC) pour des connecteurs sources spécifiques dans Experience Platform, Customer Journey Analytics sera en mesure de prendre en charge la fonctionnalité de [mise en miroir des données](/help/data-mirror/data-mirror.md) des solutions d’entrepôt de données telles que [!DNL Snowflake], [!DNL Azure Databricks] et [!DNL Google BigQuery].<p>Contactez votre équipe Adobe en charge des comptes pour accéder à la version bêta.</p> | Version bêta : 24 septembre 2025 | À confirmer |
| **Services de médias en streaming : prise en charge des données de planning** | Vous pouvez désormais charger des données planifiées antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [Charger des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 octobre 2025 | Premier semestre 2026<p>(Version initialement prévue pour le 29 octobre 2025)</p> |

## Correctifs dans Customer Journey Analytics

**Analysis Workspace** : AN-423389, AN-423316, AN-422636, AN-422482, AN-422121, AN-422116, AN-422027, AN-421134, AN-420187, AN-406271, AN-406188, AN-405997, AN-405983, AN-405796, AN-405033, AN-404893, AN-404871, AN-404842, AN-404713, AN-404502, AN-404353, AN-404352, AN-404048, AN-403241, AN-402523, AN-400795, AN-396149 390990 390646 383484 376980 371729 347570 404835
**Composants** :
**Content Analytics**:
**Analyse guidée** : AN-421274
**Exports** :
**Vues de données** : AN-421891, AN-404627
**Implémentation** :
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Rapports** :
**Segmentation** :
**Rapports planifiés** : AN-423087, AN-422686
**Mesures et dimensions partagées** :
**Autre** : AN-422946, AN-422775, AN-422273, AN-422100, AN-420045, AN-404891, AN-390912


## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. |  |  |

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
