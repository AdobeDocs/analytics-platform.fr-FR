---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7fc7475001505749cf59aa82a62e5abb7e81ea97
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 41%

---

# Notes de mise à jour actuelles de Customer Journey Analytics (avril 2026)

**Dernière mise à jour** : 9 avril 2026

Ces notes de mise à jour couvrent la période de publication d’avril 2026. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Prise en charge de l’italien**<br/> Les paramètres régionaux italiens (it-IT) sont désormais pris en charge dans Analysis Workspace dans Customer Journey Analytics. <p>Customer Journey Analytics prend en charge toutes les langues prises en charge dans l’interface utilisateur d’Experience Platform, comme décrit dans la section [Prise en charge des navigateurs et des langues pour l’interface utilisateur d’Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#language-support).</p><p>Vous pouvez [modifier votre langue par défaut](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language) dans Experience Platform.</p> | | jeudi 8 avril 2026 |
| **Validation des données dans l’agent d’ingénierie Adobe** <br/>De nouvelles compétences en validation des données sont disponibles dans Data Engineering Agent. Ces compétences aident les équipes à évaluer rapidement la qualité des données directement dans Adobe Experience Platform, avant que les données ne soient analysées dans Customer Journey Analytics. <p>Les compétences de validation des données permettent une validation à la demande, au niveau du champ et du jeu de données, associant des résumés statistiques à la détection intelligente des valeurs non valides ou anormales. </p><p>L’utilisation des compétences de validation des données réduit les efforts d’assurance qualité manuels et accélère l’intégration et les transformations de données fiables dans les workflows d’ingénierie des données.</p><p>(Lien vers la documentation à suivre.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | Fin avril 2026 <p>(Version initialement prévue pour le mercredi 31 mars 2026)</p> |
| **Serveurs MCP pour Customer Journey Analytics** <br/>Vous pouvez désormais lier Customer Journey Analytics à vos workflows agentiques existants à l’aide du protocole MCP (Model Context Protocol). Vous pouvez demander des rapports et des informations en utilisant le langage naturel.<p>(Lien vers la documentation à suivre.)</p> | | Fin avril 2026 |
| **Services de médias en flux continu : prennent en charge les données de planning** <br/>Vous pouvez désormais charger les données de planning du contenu multimédia en flux continu précédent pour suivre plus facilement et plus précisément l’audience.<p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [Charger des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 octobre 2025 | Premier semestre 2026<p>(Version initialement prévue pour le 29 octobre 2025)</p> |
| **Rapports sur les API à plusieurs dimensions**<br/> Générez des rapports sur plusieurs dimensions dans une seule requête API et effectuez des recherches au niveau des dimensions. [En savoir plus](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | Mars 2026 |
| **Tri d’API à plusieurs colonnes**<br/> Triez plusieurs objets de dimension et de mesure dans une requête API. Combinez des dimensions et des mesures dans la même définition de tri. [En savoir plus](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | Mars 2026 |

## Correctifs dans Customer Journey Analytics

**&#x200B;**&#x200B;: AN-442813, AN-442410, AN-442231, AN-441943, AN-441717, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Composants** :
**Connexions** : AN-442824, AN-440937, AN-440092, AN-429781
**Content Analytics**:
**Analyse guidée** :
**Exports** :
**Vues de données** : AN-442809, AN-434824, AN-434210, AN-424000
**Implémentation** :
**Report Builder**: AN-441136, AN-438147, AN-425150
**Reporting** : AN-443900, AN-441811, AN-441506, AN-440919, AN-440545, AN-440505, AN-440300
**Segmentation** :
**Rapports planifiés** :
**Mesures et dimensions partagées** :
**Autre** : AN-423359, AN-406242, AN-397985

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
