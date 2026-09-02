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
source-git-commit: 99135905f825cbef805c1664f6fb554497df3c3d
workflow-type: tm+mt
source-wordcount: 986
ht-degree: 27%

---

# Notes de mise à jour actuelles de Customer Journey Analytics (août 2026)

**Dernière mise à jour** : 5 août 2026

Ces notes de mise à jour couvrent la période de publication d’août 2026. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Améliorations de la zone de travail de Parcours**<br> Les améliorations de la zone de travail de Parcours suivantes sont désormais disponibles :<ul><li>Comparez le parcours à une période précédente. Comparez le parcours actuel au parcours 4 semaines avant, 2 trimestres avant, 1 an avant ou à une période personnalisée.</li><li>Pour un nœud sélectionné, affichez les principaux éléments de dimension qui se trouvent après le nœud sélectionné à tout moment dans le parcours. Utilisez cette option lorsque le nœud sélectionné est l’événement clé de votre analyse et que vous souhaitez voir ce que les personnes font à tout moment par la suite.<p>Auparavant, seuls les principaux nœuds immédiats pouvaient être affichés avant ou après le nœud sélectionné. </p></li><li>Modifiez la forme et le style des flèches entre les nœuds. Faites glisser des flèches entre les nœuds pour modifier la forme (courbure) de la flèche, puis cliquez avec le bouton droit sur une flèche pour modifier son style de l’une des manières suivantes : pleine, tirets, pointillés, tirets ou animés.</li></ul><p></p>Pour plus d’informations, consultez [Configuration d’une visualisation Zone de travail de parcours](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md). |  | 18 Août 2026 |
| **Prise en charge de libellés d’utilisation des données supplémentaires**<br> Customer Journey Analytics prend désormais en charge les libellés d’utilisation des données supplémentaires suivants pour les éléments d’un jeu de données :<ul><li>C2 - Restreindre l’exportation de données tierces (disponible maintenant)</li><li>C3 - Restreindre la combinaison de données directement identifiables (disponible maintenant)</li><li>C9 - Restreindre la science des données (publication prévue en août ou en septembre)</li></ul><p>Pour plus d’informations, voir [Libellés, politiques et actions marketing](/help/data-views/data-governance.md).</p> | | Août ou septembre 2026 |
| **Content Analytics : Paid media data** <br/>Paid media est désormais disponible en tant que troisième canal pour Content Analytics.<p>(Lien vers la documentation à suivre.)</p> | | 31 Août 2026 |
| **B2B : combinaison de comptes de personne à compte**<br> La combinaison de comptes B2B enrichit vos jeux de données d’événement avec des informations de compte et permet une analyse complète sur l’ensemble du parcours client dans Customer Journey Analytics. <p>Lorsque les événements ne disposent pas d’un identifiant de compte, ce que Customer Journey Analytics B2B edition exige pour l’ingestion, l’assemblage de comptes dérive et ajoute automatiquement ces informations à l’aide du jeu de données de mappage personne-compte que vous fournissez.</p><p>Pour plus d’informations, voir [Assemblage de personnes B2B avec compte](/help/stitching/b2b/b2b-person-to-account-stitching.md).</p> | | 31 Août 2026 |
| **Guide des premiers appels de l’API de rapport**<br> Le guide des premiers appels de l’API Adobe Customer Journey Analytics fournit des instructions et des exemples pour configurer les requêtes de rapport de base. | | 10 Août 2026 |
| **Guide de tendance de la date de l’API de rapport**<br> Le guide de tendance de la date de l’API Adobe Customer Journey Analytics fournit des instructions et des exemples pour configurer les requêtes de rapport de base. | | 17 Août 2026 |
| **Limiter les segments à la période du rapport**<br/> Les données d’un rapport Workspace peuvent s’étendre au-delà de la période du rapport lorsqu’un segment inclut des composants de période.<p>Une nouvelle option est désormais disponible. Elle vous permet de limiter les résultats à la période du rapport, quels que soient les composants de date inclus dans le segment. <p>Cette option est disponible lors de la création ou de la modification d’un segment dont le conteneur de niveau supérieur est Personne.</p><p>Pour plus d’informations, voir [Création de segments](/help/components/segments/seg-builder.md#components).</p> | 26 Août 2026 | 9 septembre 2026 |
| **Filtrage et création de rapports concernant les politiques de consentement**<br> Vous pouvez désormais créer des rapports sur les visiteurs qui correspondent à vos politiques de consentement Adobe Experience Platform. (Les dimensions et mesures de la politique de consentement sont ajoutées aux vues de données dans votre connexion.)<p>De plus, vous pouvez exclure les visiteurs non consentants avant que leurs données ne soient ingérées dans Customer Journey Analytics.</p><p>(Lien vers la documentation à suivre.)<!--For more information, see Consent reporting and filtering overview.--></p> | | Septembre 2026 |

### Correctifs dans Customer Journey Analytics

**** : AN-466867, AN-465995, AN-465315, AN-465313, AN-464375, AN-463634, AN-463248, AN-463175, AN-463049, AN-462347, AN-462124, AN-461922, AN-458398, AN-457849, AN-455002, AN-453357, AN-456863, AN-459816, AN-459034, AN-460774, AN-460671, AN-457760, AN-443594
**Composants** :
**Connexions** : AN-464934, AN-460768
**Content Analytics** :
**Analyse guidée** :
**Exports** : AN-451819, AN-448419, AN-456001
**Vues de données** : AN-453201, AN-441965, AN-460967
**Ingestion de données** : AN-462123, AN-451836, AN-453790, AN-459000, AN-456057, AN-461271, AN-459016, AN-460935
**Mise en œuvre** :
**** : AN-465346, AN-464768, AN-464580, AN-464301, AN-463048, AN-462800, AN-457042, AN-461033, AN-459042, AN-454250, AN-451735, AN-450776, AN-450200, AN-451665
**Reporting** : AN-463576, AN-462400, AN-456394, AN-455619, AN-459530, AN-454103, AN-452866, AN-461181
**Segmentation** : AN-459002, AN-457730, AN-457146
**Rapports planifiés** : AN-455009, AN-460037, AN-462093
**Dimensions et mesures partagées** :
**Analyse de l’audience** : AN-458292
**Autre** : AN-466935, AN-462116, AN-454493, AN-457666, AN-457557, AN-456742, AN-437975, AN-460959

## Fonctionnalités reportées

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Services de médias en streaming : prise en charge des données de planning** <br/>Vous pouvez désormais charger des données planifiées antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [Chargement des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data). | 29 octobre 2025 | À confirmer<p>(Initialement prévu pour le 29 octobre 2025)</p> |

>[!MORELIKETHIS]
>
>* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2026](/help/release-notes/2026.md)
>* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
>* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
>* Notes de mise à jour d’[CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
>* [Mises à jour de la documentation de ](/help/release-notes/doc-changes.md)

