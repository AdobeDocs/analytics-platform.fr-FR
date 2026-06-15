---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: c818dd36bc900b3945b87503afad8e944a3716a7
workflow-type: tm+mt
source-wordcount: 721
ht-degree: 38%

---

# Notes de mise à jour actuelles de Customer Journey Analytics (mai 2026)

**Dernière mise à jour** : 13 mai 2026

Ces notes de mise à jour couvrent la période de publication de mai 2026. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Collections de Postman de l’API CJA** <br/>Une collection Postman téléchargeable est disponible pour appeler les points d’entrée de l’API CJA.<p>Pour plus d’informations, voir le référentiel Github [analytics-cja-postman-collections](https://github.com/AdobeDocs/analytics-cja-postman-collections).  </p> | | 1er mai 2026 |
| **Serveurs MCP pour Customer Journey Analytics** <br/>Les serveurs MCP (Model Context Protocol) d’Analytics vous permettent de connecter un client MCP pris en charge à Adobe Customer Journey Analytics. Une fois connecté, votre client MCP peut appeler des outils spécifiques au produit pour récupérer les données, exécuter des requêtes ou effectuer des opérations prises en charge dans le cadre d’un processus LLM ou d’un processus agentique. Pour plus d’informations, voir [Serveurs MCP Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Si vous avez utilisé ces serveurs MCP pendant la période bêta, notez qu’il existe différentes URL entre les points d’entrée bêta et de production. Veillez à ce que tous les workflows d’agent créés pendant la période bêta soient mis à jour afin d’utiliser les points d’entrée de production avant le 31 mai.</p> | | 5 Mai 2026 |
| **Prise en charge de Content Analytics pour les expériences natives d’applications mobiles**<br/> Les entreprises peuvent étendre leur analyse de performance du contenu aux applications iOS et Android, en capturant des ressources d’image et des éléments d’expérience granulaires afin de déterminer quel contenu in-app génère l’engagement des utilisateurs et utilisatrices et les résultats commerciaux.<p> La [documentation](/help/content-analytics/content-analytics.md) est mise à jour pour décrire les fonctionnalités et la configuration du canal mobile. Des informations sur l’extension [Content Analytics Mobile SDK](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) sont disponibles sur [Adobe Developer](https://developer.adobe.com/).</p><p>Les informations sont disponibles pour tous les clients Adobe Content Analytics.</p> | | 6 Mai 2026 |
| **Améliorations de la zone de travail de Parcours** <br/> Les améliorations suivantes sont disponibles dans les visualisations de la zone de travail de Parcours : <ul><li>[Exclure des nœuds](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#exclude-nodes) d’un parcours.</li><li>Utilisez les données d’abandon d’un nœud pour [créer des segments](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-a-segment-based-on-a-node-or-arrow), [tendances](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#view-trend-data), [audiences](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-an-audience) et [répartitions](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#apply-a-breakdown).</li></ul> | | 18 Mai 2026 |
| **Content Analytics : les miniatures et les aperçus de visualisation en ligne** <br/>[miniatures et aperçus](/help/content-analytics/report/report.md) sont désormais disponibles pour les ressources et les expériences dans les visualisations en ligne pour Content Analytics. |  | 20 Mai 2026 |
| **Services de médias en streaming : prise en charge des données de planning** <br/>Vous pouvez désormais charger des données de planning antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [Charger des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 octobre 2025 | Premier semestre 2026<p>(Version initialement prévue pour le 29 octobre 2025)</p> |

{style="table-layout:auto"}


## Correctifs dans Customer Journey Analytics

**** : AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-439797, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189 425215
**Composants** :
**Connexions** : AN-449652, AN-444560, AN-442824, AN-440937, AN-440092, AN-439823, AN-429781
**Content Analytics**:
**Analyse guidée** :
**Exports** : AN-438953, AN-437115
**Vues des données** : AN-442809
**Mise en œuvre** :
**** : AN-448697, AN-447128, AN-441148, AN-441136, AN-438147, AN-425150
**Reporting** : AN-445123, AN-442231, AN-442169, AN-441811, AN-441733, AN-440505, AN-440300, AN-434824, AN-434210, AN-424000, AN-423359, AN-406242, AN-
**Segmentation** :
**Rapports planifiés** :
**Mesures et dimensions partagées** :
**Autre** : AN-449159, AN-444661, AN-443900, AN-397985

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour de CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
