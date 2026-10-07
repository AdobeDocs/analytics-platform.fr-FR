---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Affichez les dernières notes de mise à jour de Customer Journey Analytics, y compris les nouvelles fonctionnalités, les problèmes résolus et les versions reportées pour la période en cours.
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
    internal-label: Templates
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
    internal-label: Audiences
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
    internal-label: Connections
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 0a83f4d08806b4d9b97265989f9d687011b232c3
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 28%
---
# Notes de mise à jour actuelles de Customer Journey Analytics (octobre 2026)

**Dernière mise à jour** : 7 octobre 2026

Ces notes de mise à jour couvrent la période de publication d’octobre 2026. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Autorisation en lecture seule pour le serveur MCP Customer Journey Analytics**<br/> Les administrateurs peuvent désormais donner aux utilisateurs un accès en lecture seule au serveur MCP Customer Journey Analytics. Le nouvel élément d’autorisation [!UICONTROL MCP Read Only] permet aux utilisateurs et utilisatrices d’accéder à tous les outils en lecture seule, sans leur permettre de créer des projets, des segments ou des mesures calculées.<p>L’élément d’autorisation [!UICONTROL Accès MCP] existant est renommé [!UICONTROL Accès complet MCP]. Les utilisateurs et utilisatrices bénéficiant de cette autorisation conservent l’accès à tous les outils, y compris ceux qui créent, modifient ou suppriment des composants.</p><p>Pour plus d&#39;informations, voir [Serveur Customer Journey Analytics MCP](https://developer.adobe.com/analytics-mcp/docs/cja/).</p> | | 6 Octobre 2026 |
| **Analysez les expériences client LLM dans Analysis Workspace avec les informations de conversation**<br/> Customer Journey Analytics apporte désormais des données de conversation non structurées dans Analysis Workspace, ce qui vous permet de créer des rapports sur les expériences de navigation et d’achat basées sur LLM qui se produisent dans vos propriétés.<p>Grâce à cette fonctionnalité, vous pouvez :</p><ul><li>Collectez les invites, les réponses et les métadonnées de l’agent à partir des agents de conversation (les agents personnalisés de votre organisation ou Adobe Brand Concierge) via Web SDK.</li><li>Analysez l’intention, le ton et le sentiment afin de comprendre ce que les clients demandent, comment votre agent répond et ce que vos clients pensent de leurs interactions.</li><li>Analysez à grande échelle à l’aide de votre schéma, de vos jeux de données et de vos vues de données existants, puis obtenez des informations sur les surfaces dans Analysis Workspace.</li><li>Connectez les conversations aux résultats en liant les interactions des agents à vos parcours clients généraux, afin de pouvoir mesurer l’impact réel sur la conversion, l’engagement, etc.</li></ul><p>Auparavant, les expériences basées sur LLM étaient difficiles à mesurer et presque impossibles à connecter à vos parcours clients existants.</p><p>Pour plus d’informations, voir [Informations sur les conversations](/help/conversation-insights/overview.md).</p> | | 8 octobre 2026<p>(Initialement prévu pour le 22 septembre 2026)</p> |
| **Générer automatiquement des descriptions de composant** <br/>Vous pouvez désormais générer automatiquement des descriptions pour les dimensions, les mesures, les mesures calculées, les segments et les périodes. Cela permet aux utilisateurs et utilisatrices de Workspace de savoir quels composants utiliser, en particulier dans les organisations qui disposent de bibliothèques de composants volumineuses. <p>Vous pouvez générer une description pour un seul composant ou générer des descriptions pour de nombreux composants en même temps.</p> <p>(Lien vers la documentation à suivre.)<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 28 Octobre 2026 |
| **Intégration de**<br/> connectez Adobe Brand Visibility aux données Customer Journey Analytics de votre entreprise afin de mesurer la manière dont les découvertes pilotées par l’IA se traduisent par un engagement réel sur le site web et des résultats commerciaux.<p>(Lien vers la documentation à suivre.)</p> | | Octobre 2026 |


### Correctifs dans Customer Journey Analytics

**** : AN-495340, AN-494789, AN-493307, AN-468900
**Composants** : AN-492523
**Connexions** : AN-492236
**Content Analytics** :
**Analyse guidée** : AN-495592
**Exports** : AN-495077, AN-494337, AN-486563, AN-469919, AN-462560, AN-462372
**Vues de données** : AN-492093, AN-467770, AN-455367, AN-444467
**Ingestion de données** : AN-496439, AN-495339, AN-493456, AN-491984, AN-490515, AN-490479, AN-470065
**Mise en œuvre** :
**** : AN-496602, AN-494224, AN-493737, AN-493508, AN-493505, AN-492806, AN-468981, AN-454376
**Reporting** : AN-495661, AN-493562, AN-487058, AN-478768
**Segmentation** :
**Rapports planifiés** : AN-491103, AN-468049
**Mesures et dimensions partagées** : AN-493722
**Analyse de l’audience** : AN-469101
**Autre** : AN-493865

## Fonctionnalités reportées

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Rapports sur la population totale**<br/> vous pouvez désormais analyser et générer des rapports sur les entités définies dans des jeux de données de profil et de recherche qui existent dans une connexion Customer Journey Analytics. Cette analyse et ce compte rendu des performances vont au-delà des séries temporelles d’événements des jeux de données d’événements. <p>Cette fonctionnalité active de nouvelles classes de requêtes, de mesures et de définitions d’audience qui reflètent l’étendue complète de la base de clients d’une entreprise.</p><p>(Lien vers la documentation à suivre.)</p> | | À confirmer<p>(Initialement prévu pour le 22 septembre 2026)</p> |
| **Services de médias en streaming : prise en charge des données de planning** <br/>Vous pouvez désormais charger des données de planning antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Voici des exemples de contenu dynamique pris en charge avec le chargement planifié des données :</p><ul><li>Plateformes FAST (Free Ad-Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les données d’audience de chaque programme diffusé pendant la période que vous indiquez dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile d’associer avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il était impossible de l’associer à des sujets ou à des segments de programme individuels.</p><p>Pour plus d’informations, voir [Chargement des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 octobre 2025 | À confirmer<p>(Initialement prévu pour le 29 octobre 2025)</p> |

>[!MORELIKETHIS]
>
>* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2026](/help/release-notes/2026.md)
>* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
>* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
>* [Notes de mise à jour de ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
>* [Mises à jour de la documentation de ](/help/release-notes/doc-changes.md)

