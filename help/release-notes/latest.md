---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Affichez les dernières notes de mise à jour de Customer Journey Analytics, y compris les nouvelles fonctionnalités, les problèmes résolus et les versions reportées pour la période en cours.
hold: true
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
source-git-commit: 4f62a406436915d581ab30f26b82544388957782
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 29%
---
# Notes de mise à jour actuelles de Customer Journey Analytics (septembre 2026)

**Dernière mise à jour** : 9 septembre 2026

Ces notes de mise à jour couvrent la période de publication de septembre 2026. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Analysez les expériences client LLM dans Analysis Workspace avec les informations de conversation**<br/> Customer Journey Analytics apporte désormais des données de conversation non structurées dans Analysis Workspace, ce qui vous permet de créer des rapports sur les expériences de navigation et d’achat basées sur LLM qui se produisent dans vos propriétés.<p>Grâce à cette fonctionnalité, vous pouvez :</p><ul><li>Collectez les invites, les réponses et les métadonnées de l’agent à partir des agents de conversation (les agents personnalisés de votre organisation ou Adobe Brand Concierge) via Web SDK.</li><li>Analysez l’intention, le ton et le sentiment afin de comprendre ce que les clients demandent, comment votre agent répond et ce que vos clients pensent de leurs interactions.</li><li>Analysez à grande échelle à l’aide de votre schéma, de vos jeux de données et de vos vues de données existants, puis obtenez des informations sur les surfaces dans Analysis Workspace.</li><li>Connectez les conversations aux résultats en liant les interactions des agents à vos parcours clients généraux, afin de pouvoir mesurer l’impact réel sur la conversion, l’engagement, etc.</li></ul><p>Auparavant, les expériences basées sur LLM étaient difficiles à mesurer et presque impossibles à connecter à vos parcours clients existants.</p><p>Pour plus d’informations, voir [Informations sur les conversations](/help/conversation-insights/overview.md)</p> | | 8 octobre 2026<p>(Initialement prévu pour le 22 septembre 2026)</p> |
| **Générer automatiquement des descriptions de composant** <br/>Vous pouvez désormais générer automatiquement des descriptions pour les dimensions, les mesures, les mesures calculées, les segments et les périodes. Cela permet aux utilisateurs de Workspace de savoir quels composants utiliser, en particulier dans les organisations qui disposent de bibliothèques de composants volumineuses. <p>Vous pouvez générer une description pour un seul composant ou générer des descriptions pour de nombreux composants en même temps.</p> <p>(Lien vers la documentation à suivre.)<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 28 Octobre 2026 |
| **Intégration de**<br/> connectez Adobe Brand Visibility aux données Adobe Analytics de votre entreprise afin de mesurer la manière dont les découvertes pilotées par l’IA se traduisent par un engagement réel sur le site web et des résultats commerciaux.<p>(Lien vers la documentation à suivre.)</p> | | Octobre 2026</p> |


### Correctifs dans Customer Journey Analytics

**&#x200B;**&#x200B;: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373, AN-492801, AN-488821, AN-488452, AN-486517, AN-478930, AN-468325
**Composants** :
**Connexions** : AN-451458, AN-365942
**Content Analytics** :
**Analyse guidée** : AN-485600
**Exports** : AN-489161, AN-467131, AN-464746, AN-469034, AN-447252, AN-437803, AN-394444
**Vues de données** : AN-478732, AN-468836, AN-467851, AN-487651, AN-423592
**Ingestion de données** : AN-489829, AN-489722, AN-469451, AN-467436, AN-467049, AN-466087, AN-465049, AN-463524, AN-457433, AN-490288, AN-487500, AN-390916, AN-342311
**Mise en œuvre** :
**&#x200B;**&#x200B;: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695, AN-492330, AN-490564, AN-468293, AN-460921
**Reporting** : AN-479145, AN-469095, AN-468070, AN-467786, AN-456684, AN-465257, AN-422685, AN-406114, AN-356706, AN-322733
**Segmentation** : AN-486561, AN-278260
**Rapports planifiés** : AN-479157
**Dimensions et mesures partagées** :
**Analyse de l’audience** : AN-468237, AN-462553
**Autre** : AN-469601, AN-462817, AN-362308, AN-349757, AN-326432, AN-326345, AN-324341, AN-309317

## Fonctionnalités reportées

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Rapports sur la population totale**<br/> vous pouvez désormais analyser et générer des rapports sur les entités définies dans des jeux de données de profil et de recherche qui existent dans une connexion Customer Journey Analytics. Cette analyse et ce compte rendu des performances vont au-delà des séries temporelles d’événements des jeux de données d’événements. <p>Cette fonctionnalité active de nouvelles classes de requêtes, de mesures et de définitions d’audience qui reflètent l’étendue complète de la base de clients d’une entreprise.</p><p>(Lien vers la documentation à suivre.)</p> | | À confirmer<p>(Initialement prévu pour le 22 septembre 2026)</p> |
| **Services de médias en streaming : prise en charge des données de planning** <br/>Vous pouvez désormais charger des données de planning antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Voici des exemples de contenu dynamique pris en charge avec le chargement planifié des données :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les données d’audience de chaque programme diffusé pendant la période que vous indiquez dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile d’associer avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il était impossible de l’associer à des sujets ou à des segments de programme individuels.</p><p>Pour plus d’informations, voir [Chargement des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 octobre 2025 | À confirmer<p>(Initialement prévu pour le 29 octobre 2025)</p> |

>[!MORELIKETHIS]
>
>* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2026](/help/release-notes/2026.md)
>* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
>* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
>* [Notes de mise à jour de &#x200B;](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
>* [Mises à jour de la documentation de &#x200B;](/help/release-notes/doc-changes.md)

