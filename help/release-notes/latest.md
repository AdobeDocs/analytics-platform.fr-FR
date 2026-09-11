---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 04accc9ba060da60916cf4c3bc66710f57f50cda
workflow-type: tm+mt
source-wordcount: 1263
ht-degree: 20%

---

# Notes de mise à jour actuelles de Customer Journey Analytics (septembre 2026)

**Dernière mise à jour** : 9 septembre 2026

Ces notes de mise à jour couvrent la période de publication de septembre 2026. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Plug-in de serveur MCP**<br/> utilisez les nouveaux plug-ins de serveur MCP Customer Journey Analytics pour ChatGPT et Claude afin d’accéder rapidement à vos données. <p>Pour plus d’informations, consultez le guide du plug-in [ChatGPT](https://developer.adobe.com/analytics-mcp/docs/guides/chatgpt) et le guide du connecteur [Claude](https://developer.adobe.com/analytics-mcp/docs/guides/claude).</p> | 1er septembre 2026 | 1er septembre 2026 |
| **Prise en charge de libellés d’utilisation des données supplémentaires**<br> Customer Journey Analytics prend désormais en charge les libellés d’utilisation des données supplémentaires suivants pour les éléments d’un jeu de données :<ul><li>C2 - Restreindre l’exportation de données tierces (disponible maintenant)</li><li>C3 - Restreindre la combinaison de données directement identifiables (disponible maintenant)</li><li>C9 - Restreindre la science des données (publication prévue en août ou en septembre)</li></ul><p>Pour plus d’informations, voir [Libellés, politiques et actions marketing](/help/data-views/data-governance.md).</p> | | 3 septembre 2026 |
| **Filtrage et création de rapports concernant les politiques de consentement**<br> Vous pouvez désormais créer des rapports sur les visiteurs qui correspondent à vos politiques de consentement Adobe Experience Platform. (Les dimensions et mesures de la politique de consentement sont ajoutées aux vues de données dans votre connexion.)<p>De plus, vous pouvez exclure les visiteurs non consentants avant que leurs données ne soient ingérées dans Customer Journey Analytics.</p><p>(Lien vers la documentation à suivre.)<!--For more information, see Consent reporting and filtering overview.--></p> | | Septembre 2026 |
| **Limiter les segments à la période du rapport**<br/> Les données d’un rapport Workspace peuvent s’étendre au-delà de la période du rapport lorsqu’un segment inclut des composants de période.<p>Une nouvelle option est désormais disponible. Elle vous permet de limiter les résultats à la période du rapport, quels que soient les composants de date inclus dans le segment.</p><p>Cette option est disponible lors de la création ou de la modification d’un segment dont le conteneur de niveau supérieur est Personne.</p><p>Pour plus d’informations, voir [Création de segments](/help/components/segments/seg-builder.md#components).</p> | 26 Août 2026 | 9 septembre 2026 |
| **Analysez les expériences client LLM dans Analysis Workspace avec les informations de conversation**<br/> Customer Journey Analytics apporte désormais des données de conversation non structurées dans Analysis Workspace, ce qui vous permet de créer des rapports sur les expériences de navigation et d’achat basées sur LLM qui se produisent dans vos propriétés.<p>Grâce à cette fonctionnalité, vous pouvez :</p><ul><li>Collectez les invites, les réponses et les métadonnées de l’agent à partir des agents de conversation (les agents personnalisés de votre organisation ou Adobe Brand Concierge) via Web SDK.</li><li>Analysez l’intention, le ton et le sentiment afin de comprendre ce que les clients demandent, comment votre agent répond et ce que vos clients pensent de leurs interactions.</li><li>Analysez à grande échelle à l’aide de votre schéma, de vos jeux de données et de vos vues de données existants, puis obtenez des informations sur les surfaces dans Analysis Workspace.</li><li>Connectez les conversations aux résultats en liant les interactions des agents à vos parcours clients généraux, afin de pouvoir mesurer l’impact réel sur la conversion, l’engagement, etc.</li></ul><p>Auparavant, les expériences basées sur LLM étaient difficiles à mesurer et presque impossibles à connecter à vos parcours clients existants.</p><p>(Lien vers la documentation à suivre.)</p> | | 22 septembre 2026 |
| **Rapports sur la population totale**<br/> vous pouvez désormais analyser et générer des rapports sur les entités définies dans des jeux de données de profil et de recherche qui existent dans une connexion Customer Journey Analytics. Cette analyse et ce compte rendu des performances vont au-delà des séries temporelles d’événements des jeux de données d’événements. <p>Cette fonctionnalité active de nouvelles classes de requêtes, de mesures et de définitions d’audience qui reflètent l’étendue complète de la base de clients d’une entreprise.</p><p>(Lien vers la documentation à suivre.)</p> | | 22 septembre 2026 |
| **Alertes horaires**<br/> Vous pouvez désormais définir la granularité horaire d’une alerte sur Horaire.<p>Les alertes horaires sont destinées aux données qui arrivent au cours d’une heure donnée. Si les données ont une latence supérieure à une heure, une granularité plus longue garantit que l’alerte évalue des données complètes. Vérifiez auprès de l’ingénieur de données si vous n’êtes pas sûr du temps nécessaire aux données pour arriver.</p>p>(Lien vers la documentation à suivre.)</p> | | Septembre 2026 |
| **La diffusion des alertes respecte strictement le délai configuré**<br/> Les alertes sont désormais diffusées à la fin de la fenêtre de délai que vous avez définie, que les données soient terminées ou en cours de réception pour la plage d’événements spécifiée. Toutes les données qui arrivent après la période de temporisation ne sont pas incluses dans l’alerte.<p>Auparavant, les alertes incluaient une vérification de traitement en arrière-plan qui attendait les données arrivant en retard, même si cela signifiait que les alertes étaient diffusées après la fenêtre de délai configurée.</p>p>(Lien vers la documentation à suivre.)</p> | | Septembre 2026 |
| **Intégration de**<br/> connectez Adobe Brand Visibility aux données Customer Journey Analytics de votre entreprise afin de mesurer la manière dont les découvertes pilotées par l’IA se traduisent par un engagement réel sur le site web et des résultats commerciaux.<p>(Lien vers la documentation à suivre.)</p> | | Septembre 2026 |
| **Compétences de mise à niveau et d’implémentation dans CX Enterprise Coworker**<br> De nouvelles compétences sont bientôt disponibles pour Coworker. Ces compétences facilitent les mises à niveau et implémentations de Customer Journey Analytics :<ul><li>**Compétences relatives aux guides d’implémentation** : générez une liste personnalisée des étapes et recommandations de mise à niveau ou d’implémentation. Les conseils de mise à niveau et d’implémentation peuvent ensuite être transformés en projet Collègues à l’aide d’un playbook prédéfini.</li><li>**Compétences intelligentes de mise à niveau et de liste de contrôle d’implémentation** : utilisez le projet Coworker pour gérer et suivre la progression de l’implémentation par rapport à la liste de contrôle de mise à niveau ou d’implémentation personnalisée, maintenir le statut du projet, collaborer entre les équipes, affecter des tâches et introduire des points de contrôle d’approbation si nécessaire.</li><li>**Compétences en validation des données** : vérifiez que votre implémentation est correctement configurée et alignée avec les bonnes pratiques.</li></ul><p>(Liens vers la documentation à suivre.)</p> | | 30 septembre 2026 |

### Correctifs dans Customer Journey Analytics

**** : AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373, AN-492801, AN-488821, AN-488452, AN-486517, AN-478930, AN-468325
**Composants** :
**Connexions** : AN-451458, AN-365942
**Content Analytics** :
**Analyse guidée** : AN-485600
**Exports** : AN-489161, AN-467131, AN-464746, AN-469034, AN-447252, AN-437803, AN-394444
**Vues de données** : AN-478732, AN-468836, AN-467851, AN-487651, AN-423592
**Ingestion de données** : AN-489829, AN-489722, AN-469451, AN-467436, AN-467049, AN-466087, AN-465049, AN-463524, AN-457433, AN-490288, AN-487500, AN-390916, AN-342311
**Mise en œuvre** :
**** : AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695, AN-492330, AN-490564, AN-468293, AN-460921
**Reporting** : AN-479145, AN-469095, AN-468070, AN-467786, AN-456684, AN-465257, AN-422685, AN-406114, AN-356706, AN-322733
**Segmentation** : AN-486561, AN-278260
**Rapports planifiés** : AN-479157
**Dimensions et mesures partagées** :
**Analyse de l’audience** : AN-468237, AN-462553
**Autre** : AN-469601, AN-462817, AN-362308, AN-349757, AN-326432, AN-326345, AN-324341, AN-309317

## Fonctionnalités reportées

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Services de médias en streaming : prise en charge des données de planning** <br/>Vous pouvez désormais charger des données de planning antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Voici des exemples de contenu dynamique pris en charge avec le chargement planifié des données :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les données d’audience de chaque programme diffusé pendant la période que vous indiquez dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile d’associer avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il était impossible de l’associer à des sujets ou à des segments de programme individuels.</p><p>Pour plus d’informations, voir [Chargement des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 octobre 2025 | À confirmer<p>(Initialement prévu pour le 29 octobre 2025)</p> |

>[!MORELIKETHIS]
>
>* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2026](/help/release-notes/2026.md)
>* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
>* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
>* Notes de mise à jour d’[CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
>* [Mises à jour de la documentation de ](/help/release-notes/doc-changes.md)

