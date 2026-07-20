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
source-git-commit: 587265d7613f732af811a77a947b0ce96ccad9bf
workflow-type: tm+mt
source-wordcount: 696
ht-degree: 39%

---

# Notes de mise à jour actuelles de Customer Journey Analytics (juillet 2026)

**Dernière mise à jour** : 8 juillet 2026

Ces notes de mise à jour couvrent la période de publication de juillet 2026. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Analyse sous-événement** <br/>L&#39;analyse sous-événement permet d&#39;analyser les données à un niveau plus granulaire que le niveau de l&#39;événement. Au lieu de filtrer des événements entiers, vous pouvez segmenter des conteneurs individuels au sein d’un événement. <p>Par exemple, vous pouvez segmenter une catégorie de produits spécifique sans inclure tous les autres produits achetés dans la même commande. Vous pouvez également définir des objets ou des tableaux qui font partie de vos données d’événement en tant que conteneurs distincts dans une vue de données.</p><p>(Lien vers la documentation à suivre.)</p> | 15 juillet 2026 | Fin juillet 2026 |
| **B2B edition : la prise en charge des jeux de données ad hoc et relationnels** <br/>Les jeux de données ad hoc et relationnels sont désormais également pris en charge dans les connexions basées sur les comptes dans Customer Journey Analytics B2B edition.<p>(Lien vers la documentation à suivre.)</p> | | 20 Juillet 2026 |
| **Content Analytics : Paid media data** <br/>Paid media est désormais disponible en tant que troisième canal pour Content Analytics.<p>(Lien vers la documentation à suivre.)</p> | | 31 juillet 2026 |
| **Mise à jour de l’interface d’utilisation des connexions** <br/>dans l’interface d’utilisation lors de la gestion des connexions, vous pouvez désormais voir les détails d’utilisation de chaque module individuel, tels que Customer Journey Analytics ou Customer Journey Analytics B2B edition. <p>En outre, vous pouvez désormais ventiler les rapports d’utilisation de chacun des modules par mois.</p><p>(Lien vers la documentation à suivre.)</p> | | 31 juillet 2026 |
| **Coworker d’entreprise CX : valider vos données lors de la migration d’Adobe Analytics vers Customer Journey Analytics** <br/>Une nouvelle compétence dans le Coworker d’entreprise CX vous permet de valider les données de votre implémentation Customer Journey Analytics par rapport aux données de votre implémentation Adobe Analytics existante. <p>Cette compétence compare automatiquement chaque dimension, mesure et tendance individuellement selon les besoins. Il peut également comparer toutes les suites de rapports Adobe Analytics à toutes les vues de données Customer Journey Analytics. Les compétences génèrent ensuite des informations et des recommandations pilotées par l’IA que vous pouvez mettre en œuvre pour faciliter votre migration vers Customer Journey Analytics.</p><p>(Lien vers la documentation à suivre.)</p> | | Fin juillet 2026 |
| **Classifications intégrées**<br/>[ Les classifications intégrées](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md#inline-classifications) vous permettent de renommer ou de combiner des lignes dans un tableau à structure libre. Et pour créer un champ dérivé à partir des lignes modifiées d’un tableau. | | 20 Juillet 2026 |

### Correctifs dans Customer Journey Analytics

**** : AN-457527, AN-451161, AN-459034, AN-458071, AN-458398
**Composants** :
**Connexions** : AN-457065
**Content Analytics** :
**Analyse guidée** :
**Exports** :
**Vues des données** : AN-453201
**Ingestion des données** :
**Mise en œuvre** :
**** : AN-457533, AN-453683
**Reporting** : AN-457607, AN-447692, AN-451259, AN-455713
**Segmentation** :
**Rapports planifiés** : AN-450715
**Dimensions et mesures partagées** :
**Analyse de l’audience** :
**Autre** : AN-457063

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

