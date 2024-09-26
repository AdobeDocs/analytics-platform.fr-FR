---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b7e8c535d178ef406e1563408cee83c638d6858b
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 100%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (septembre 2024)

**Dernière mise à jour** : 11 septembre 2024

Ces notes de mise à jour portent sur la période allant du 11 septembre 2024 jusqu’au début du mois d’octobre. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Informations supplémentaires dans la colonne « Utilisation dans » du gestionnaire de mesures calculées et du gestionnaire de filtres** | La colonne « Utilisation dans » du gestionnaire de mesures calculées et du gestionnaire de filtres contient les nouvelles zones de rapports suivantes :<ul><li>**Report Builder :** affiche le nombre de mesures calculées ou de filtres utilisés dans Report Builder.</li><li>**Composants ad hoc :** indique le nombre de mesures calculées ad hoc ou de filtres ad hoc utilisés dans les projets. Ces mesures calculées et filtres ad hoc (également appelés « mesures calculées rapides » et « filtres rapides ») ne peuvent être utilisés que dans le projet dans lequel ils ont été créés. Ils sont donc signalés séparément de la zone de rapport « Projet » dans la colonne « Utilisation dans ».</li></ul>Pour plus d’informations, voir [Gestionnaire de mesures calculées](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager?lang=fr) et [Gestionnaire de filtres](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters?lang=fr). |  | 11 septembre 2024 |
| **Alertes** | Les alertes dans Customer Journey Analytics envoient un avertissement en fonction de pourcentages ou de points de données spécifiques modifiés.<p>Selon votre package Customer Journey Analytics, vous pouvez également déclencher les alertes en fonction des seuils d’anomalie. Les alertes, ou alertes intelligentes, fournissent des contrôles granulaires qui s’intègrent à la détection des anomalies et se déclenchent lorsque vous en avez le plus besoin.</p><p>Le processus d’utilisation des alertes dans Customer Journey Analytics est presque identique à celui des alertes dans Adobe Analytics. Une différence majeure réside dans le fait que les alertes horaires ne sont pas disponibles dans Customer Journey Analytics. Cette différence est due au fait que l’ingestion des différents types de données d’événement pouvant être ingérés ne se termine qu’après un délai généralement compris entre 3 et 9 heures après l’heure de l’événement des données.</p><p>Pour plus d’informations sur les différences lors de l’utilisation d’alertes dans Customer Journey Analytics à partir d’Adobe Analytics, voir [Comparaison des fonctionnalités d’alertes](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).</p><p>Pour en savoir plus sur les alertes, voir [Vue d’ensemble des alertes](/help/components/c-intelligent-alerts/intelligent-alerts.md). |  | 13 septembre 2024 |
| **Mises à jour du connecteur source Adobe Analytics** | La page de l’activité du jeu de données n’affiche pas d’informations sur les lots, car le connecteur source Analytics est entièrement géré par Adobe. Vous pouvez vérifier que les données circulent en examinant les mesures relatives aux enregistrements ingérés. Pour plus d’informations, consultez le guide sur la [création d’une connexion source pour les données Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics?lang=fr). |  | Disponible maintenant |
| **Analyse guidée - Incorporer dans Workspace** | Combinez plusieurs analyses guidées en une seule vue dans Analysis Workspace. (Lien vers la documentation à suivre) | 2 octobre 2024 | vendredi 31 octobre 2024 |

## Correctifs dans Customer Journey Analytics

AN-352461 ; AN-355446 à AN-355665

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
