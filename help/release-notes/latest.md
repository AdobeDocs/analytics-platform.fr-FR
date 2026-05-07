---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: ae368ea39b6521e2e350aa7849568cd225ecef90
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 63%

---

# Notes de mise à jour de la version actuelle de Customer Journey Analytics (avril 2026)

**Dernière mise à jour**: 22 avril 2026

Ces notes de mise à jour couvrent la période des versions d’avril 2026. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Prise en charge de l’italien**<br/> Les paramètres régionaux italiens (it-IT) sont désormais pris en charge dans Analysis Workspace dans Customer Journey Analytics. <p>Customer Journey  Analytics prend en charge toutes les langues prises en charge dans l’interface d’utilisation d’Experience Platform, comme décrit dans la section [Prise en charge des navigateurs et des langues pour l’interface d’utilisation d’Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/landing/platform-ui/browser-language-support#language-support).</p><p>Vous pouvez [modifier votre langue par défaut](https://experienceleague.adobe.com/fr/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language) dans Experience Platform.</p> | | 8 avril 2026 |
| **Validation des données dans l’agent d’ingénierie Adobe** <br/>De nouvelles compétences en validation des données sont disponibles dans l’agent Data Engineering. Ces compétences aident les équipes à évaluer rapidement la qualité des données directement dans Adobe Experience Platform, avant que les données ne soient analysées dans Customer Journey Analytics. <p>Les compétences de validation des données permettent une validation à la demande, au niveau du champ et du jeu de données, associant des résumés statistiques à la détection intelligente des valeurs non valides ou anormales. </p><p>L’utilisation des compétences de validation des données réduit les efforts d’assurance qualité manuels et accélère l’intégration et les transformations de données fiables dans les workflows d’ingénierie des données.</p><p>(Lien vers la documentation à suivre.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | Mai 2026 <p>(Version initialement prévue pour le 31 mars 2026)</p> |
| **Serveurs MCP pour Customer Journey Analytics** <br/>Les serveurs MCP (Model Context Protocol) d’Analytics vous permettent de connecter un client MCP pris en charge à Adobe Customer Journey Analytics. Une fois connecté, votre client MCP peut appeler des outils spécifiques au produit pour récupérer les données, exécuter des requêtes ou effectuer des opérations prises en charge dans le cadre d’un processus LLM ou d’un processus agentique. Pour plus d’informations, voir [Serveurs MCP Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Si vous avez utilisé ces serveurs MCP pendant la période bêta, notez qu’il existe différentes URL entre les points d’entrée bêta et de production. Veillez à ce que tous les workflows d’agent créés pendant la période bêta soient mis à jour afin d’utiliser les points d’entrée de production avant le 31 mai.</p> | | 5 Mai 2026 |
| **Prise en charge de Content Analytics pour les expériences natives d’applications mobiles**<br/> Les entreprises peuvent étendre leur analyse de performance du contenu aux applications iOS et Android, en capturant des ressources d’image et des éléments d’expérience granulaires afin de déterminer quel contenu in-app génère l’engagement des utilisateurs et utilisatrices et les résultats commerciaux. La [documentation](/help/content-analytics/content-analytics.md) est mise à jour pour décrire les fonctionnalités et la configuration du canal mobile. Des informations sur l’extension [Content Analytics Mobile SDK](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) sont disponibles depuis [Adobe Developer](https://developer.adobe.com).<p>Les informations sont disponibles pour tous les clients Adobe Content Analytics.</p> | 6 Mai 2026 | 6 Mai 2026 |
| **Services de médias en streaming : prise en charge des données de planning** <br/>Vous pouvez désormais charger des données de planning antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [Charger des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 octobre 2025 | Premier semestre 2026<p>(Version initialement prévue pour le 29 octobre 2025)</p> |
| **Création de rapports d’API à plusieurs dimensions**<br/> Créez des rapports sur plusieurs dimensions dans une seule requête d’API et effectuez des recherches au niveau des dimensions. [En savoir plus](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | Mars 2026 |
| **Tri de l’API à plusieurs colonnes**<br/> Triez plusieurs objets de dimension et de mesure dans une requête API. Combinez des dimensions et des mesures dans la même définition de tri. [En savoir plus](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | Mars 2026 |

## Correctifs dans Customer Journey Analytics

**** : AN-442813, AN-442410, AN-442231, AN-441943, AN-441717, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Composants** :
**Connexions** : AN-442824, AN-440937, AN-440092, AN-429781
**Content Analytics**:
**Analyse guidée** :
**Exports** :
**Vues de données** : AN-442809, AN-434824, AN-434210, AN-424000
**Mise en œuvre** :
**** : AN-441136, AN-438147, AN-425150
**Reporting** : AN-443900, AN-441811, AN-441506, AN-440919, AN-440545, AN-440505, AN-440300
**Segmentation** :
**Rapports planifiés** :
**Mesures et dimensions partagées** :
**Autre** : AN-423359, AN-406242, AN-397985

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
