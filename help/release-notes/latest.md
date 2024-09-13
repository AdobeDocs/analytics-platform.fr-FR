---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7b368f81c4036a3992fdfc34b983f344a61dc2fb
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 52%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (septembre 2024)

**Dernière mise à jour** : jeudi 11 septembre 2024

Ces notes de mise à jour portent sur la période du 11 septembre 2024 au début du mois d’octobre. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Informations supplémentaires dans la colonne &quot;Utilisé(e) dans&quot; du gestionnaire de mesures calculées et du gestionnaire de filtres** | La colonne « Utilisation dans » du gestionnaire de mesures calculées et du gestionnaire de filtres contient les nouvelles zones de rapports suivantes :<ul><li>**Report Builder** : indique le nombre de mesures ou de filtres calculés utilisés dans le Report Builder.</li><li>**Composants ad hoc** : indique le nombre de mesures calculées ad hoc ou de filtres ad hoc utilisés dans les projets. Ces mesures calculées et filtres ad hoc (également appelés « mesures calculées rapides » et « filtres rapides ») ne peuvent être utilisés que dans le projet dans lequel ils ont été créés. Ils sont donc signalés séparément de la zone de rapport « Projet » dans la colonne « Utilisation dans ».</li></ul>Pour plus d’informations, voir [Gestionnaire de mesures calculées](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager) et [Gestionnaire de filtres](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-filters/manage-filters). |  | 11 septembre 2024 |
| **Alertes intelligentes** | Les alertes intelligentes de Customer Journey Analytics permettent de recevoir immédiatement une notification en cas d’événements anormaux dans vos données.<p>Vous pouvez définir le déclenchement d’alertes en fonction de seuils d’anomalie, de modification des pourcentages ou de points de données spécifiques. Les alertes fournissent des contrôles granulaires qui s’intègrent à la détection des anomalies, et se déclenchent lorsque vous en avez le plus besoin.</p><p>Le processus d’utilisation des alertes intelligentes dans Customer Journey Analytics est presque identique à celui des alertes intelligentes dans Adobe Analytics. Une différence majeure réside dans le fait que les alertes horaires ne sont pas disponibles dans Customer Journey Analytics. Cette différence est due au fait que l’ingestion de données pour les différents types de données d’événement pouvant être ingérés n’est terminée qu’après un délai, généralement compris entre 3 et 9 heures après l’heure de l’événement de données. [En savoir plus](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/c-intelligent-alerts/intellligent-alerts) |  | Mid septembre 2024 |
| **Mises à jour du connecteur source Adobe Analytics** | La page de l’activité du jeu de données n’affiche pas d’informations sur les lots, car Analytics Source Connector est entièrement géré par Adobe. Vous pouvez vérifier que les données circulent en examinant les mesures relatives aux enregistrements ingérés. Pour plus d’informations, consultez le guide sur la [création d’une connexion source pour les données Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) . |  | Disponible maintenant |
| **Utilisation Analytics** | Découvrez comment votre entreprise utilise Customer Journey Analytics. L’activation de cette fonction crée un jeu de données dans Adobe Experience Platform qui collecte des données lorsque n’importe qui dans votre entreprise utilise Analysis Workspace. Une connexion et une vue de données sont également automatiquement créées, ce qui vous donne accès à des dimensions telles que les types de projet principaux, les utilisateurs les plus actifs et les composants les plus utilisés dans les projets. (Lien vers la documentation à suivre) |  | 18 septembre 2024 |
| **Analyse guidée : Incorporer dans Workspace** | Combinez plusieurs analyses guidées en une seule vue dans Analysis Workspace. (Lien vers la documentation à suivre) | lundi 22 septembre 2024 | jeudi 2 octobre 2024 |


## Correctifs dans Customer Journey Analytics

AN-352461 ; AN-355446 : AN-355665

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
