---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b5877ff515147964c2d4fbd6eaa43a8a99f0fe0
workflow-type: ht
source-wordcount: '540'
ht-degree: 100%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (août 2024)

**Dernière mise à jour** : 14 août 2024

Ces notes de mise à jour portent sur la période du 14 août 2024 à septembre 2024. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Sources de données de niveau résumé** | Vous permet d’importer des données de série temporelle qui ne comportent pas d’ID de personne. Ces données de série temporelle peuvent être utilisées pour prendre en charge divers cas d’utilisation, tels que les suivants :<ul><li>Présenter des indicateurs de performances de haut niveau dans ou à côté des données au niveau de l’événement. Cela peut inclure des éléments aussi simples qu’une date et une valeur de mesure unique, ou inclure plusieurs dimensions et mesures, comme les impressions publicitaires, les ouvertures d’e-mails, les dépenses publicitaires, le coût des biens vendus, etc.</li><li>Chargement de cibles ou d’objectifs toutes les heures ou tous les jours, puis positionnement de ces cibles ou objectifs par rapport aux mesures au niveau de l’événement. Cela permet de visualiser la tendance des mesures par rapport aux cibles ou aux objectifs de l’entreprise.</li></ul><p>Pour plus d’informations, voir la section [Données de résumé](/help/data-views/summary-data.md).</p> | 13 août 2024 | 21 août 2024 |
| **Les audiences sont publiées dans une nouvelle section « Audiences » dans Experience Platform.** | Les audiences qui sont publiées à partir de Customer Journey Analytics sont désormais disponibles dans la nouvelle section « Audiences » d’Adobe Experience Platform.<p>Auparavant, les audiences qui étaient publiées à partir de Customer Journey Analytics étaient disponibles dans Experience Platform dans la section « Segments ».</p><p>Cette amélioration s’accompagne des avantages suivants :</p><ul><li>Les audiences n’ont plus un délai d’une heure avant d’apparaître dans Experience Platform ; elles sont disponibles quelques secondes après leur publication.</li><li>Les audiences peuvent être triées dans Experience Platform à l’aide de la colonne « Origine », qui affiche l’application à partir de laquelle l’audience a été publiée à l’origine.</li><li>Les options de filtrage et de tri d’Experience Platform vous permettent de trouver plus rapidement les audiences pertinentes.</li></ul> <p>Pour plus d’informations, voir la section [Utiliser des audiences Customer Journey Analytics dans Experience Platform](/help/components/audiences/publish.md#use-customer-journey-analytics-audiences-in-experience-platform) dans l’article [Créer et publier des audiences](/help/components/audiences/publish.md).</p> | Septembre 2024 | Septembre 2024 |
| **Alertes intelligentes** | Les alertes intelligentes de Customer Journey Analytics permettent de recevoir immédiatement une notification en cas d’événements anormaux dans vos données.<p>Vous pouvez définir le déclenchement d’alertes en fonction de seuils d’anomalie, de modification des pourcentages ou de points de données spécifiques. Les alertes fournissent des contrôles granulaires qui s’intègrent à la détection des anomalies, et se déclenchent lorsque vous en avez le plus besoin.</p><p>Le processus d’utilisation des alertes intelligentes dans Customer Journey Analytics est presque identique à celui des alertes intelligentes dans Adobe Analytics. Une différence majeure réside dans le fait que les alertes horaires ne sont pas disponibles dans Customer Journey Analytics. Cette différence est due au fait que l’ingestion des différents types de données d’événement pouvant être ingérés ne se termine qu’après un délai généralement compris entre 3 et 9 heures après l’heure de l’événement des données.</p><p>(Liens vers la documentation mise à jour à suivre)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | À confirmer |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-354359; AN-351646; AN-346873; AN-352504; AN-353755; AN-354199; AN-354268; AN-354791; AN-354598; AN-354462; AN-354547;

## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. | | |

{style="table-layout:auto"}

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2024](/help/release-notes/2024.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Collection de médias en streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
