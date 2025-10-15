---
title: Comparer les données du connecteur source Analytics à Adobe Analytics
description: Découvrez les différences de données lors de l’affichage de rapports similaires dans Adobe Analytics et Customer Journey Analytics.
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: service de requête ; Service de requête ; syntaxe sql
source-git-commit: d96404479aabe6020566e693245879b5ad4fad9c
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 100%

---

# Comparer les données du connecteur source Analytics à Adobe Analytics

Suite à lʼadoption de Customer Journey Analytics par votre organisation, vous pouvez constater certaines différences entre les données Adobe Analytics et Customer Journey Analytics. Ces différences sont normales et peuvent se produire pour plusieurs raisons. Customer Journey Analytics est conçu pour vous permettre de remédier à certaines des limites imposées à vos données dans Adobe Analytics. Cette flexibilité peut entraîner des différences dans la façon dont Customer Journey Analytics interprète les données. Utilisez cet article pour comprendre les différences potentielles entre la manière dont Customer Journey Analytics et Adobe Analytics traitent vos données.

Cette page suppose que vous ingérez des données Adobe Analytics dans Adobe Experience Platform à l’aide du [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr), puis que vous avez créé une [connexion](/help/connections/overview.md) et une [vue de données](/help/data-views/data-views.md) dans Customer Journey Analytics.

![Flux de données d’Adobe Analytics par le biais du connecteur de données vers Adobe Experience Platform et vers Customer Journey Analytics à l’aide des connexions CJA.](assets/compare.png)

Les raisons suivantes sont celles pour lesquelles les données peuvent différer entre les plateformes de création de rapports :

* **Jeux de données ou suites de rapports différents** : assurez-vous que la suite de rapports dans Adobe Analytics et la suite de rapports à partir de laquelle le connecteur source obtient des données sont identiques.
* **Paramètres du calendrier** : les suites de rapports dans Adobe Analytics contiennent un fuseau horaire et d’autres paramètres de calendrier que vous pouvez configurer. De même, les vues de données dans Customer Journey Analytics comportent un paramètre distinct que vous pouvez contrôler. Assurez-vous que ces paramètres correspondent entre les produits si vous souhaitez la parité.
* **Jeux de données supplémentaires** : Customer Journey Analytics permet d’inclure plusieurs jeux de données dans une seule connexion. Ces différences incluent des jeux de données d’événement, de profil ou de recherche supplémentaires. Cette fonctionnalité constitue un facteur de différenciation essentiel entre Adobe Analytics et Customer Journey Analytics, permettant d’insérer des informations dans des données cross-canal.
* **Jeux de données groupés** : Adobe permet d’analyser les ID de personne entre deux jeux de données, ce qui entraîne la création d’un nouveau jeu de données contenant des ID groupés. Ces [jeux de données groupés](/help/stitching/overview.md) contiennent des données supplémentaires, au-delà de ce qu’offre une suite de rapports Adobe Analytics.
* **Sources de données** : Customer Journey Analytics n’inclut aucun type de [Sources de données](https://experienceleague.adobe.com/fr/docs/analytics/import/data-sources/overview) chargé dans une suite de rapports Adobe Analytics, et notamment aucune source de données de résumé ou source de données d’ID de transaction.
* **Paramètres de dimension et de mesure** : dans une vue de données, chaque dimension et mesure contient ses propres paramètres, modifiables par votre organisation. Ces modifications s’appliquent au moment de l’exécution du rapport, et donc de manière rétroactive. Les paramètres de dimension et de mesures d’Adobe Analytics modifient la manière dont les données sont collectées, ce qui permet d’appliquer ces modifications à partir de ce moment-là. Si vous avez modifié les paramètres des composants dans l’un des produits, cela peut créer des différences en matière de rapports. Si vous vous concentrez sur une dimension spécifique, assurez-vous que les paramètres d’attribution et de persistance correspondent entre Adobe Analytics et Customer Journey Analytics.

  >[!TIP]
  >
  >Adobe recommande vivement que les dimensions dans Adobe Analytics utilisent l’attribution suivante : « [!UICONTROL Le dernier] ». Ce paramètre d’attribution assure une flexibilité bien plus grande en la matière dans Customer Journey Analytics.

* **Définition de visite** : en plus des paramètres de dimension et de mesure individuels, la vue de données elle-même contient des paramètres qui modifient fondamentalement la manière dont les données des visiteurs et visiteuses sont interprétées. Par exemple, vous pouvez appliquer un segment à une vue de données entière (comme une [suite de rapports virtuelle](https://experienceleague.adobe.com/fr/docs/analytics/components/virtual-report-suites/vrs-about) dans Adobe Analytics). Vous pouvez également modifier la définition d’une durée de visite ou démarrer automatiquement une nouvelle visite pour l’un des événements souhaités. Chacun de ces paramètres peut avoir une incidence notable sur les différences de rapports entre Customer Journey Analytics et Adobe Analytics.

## Vérification du nombre d’enregistrements entre les produits

Si tous les paramètres ci-dessus semblent similaires et que vous souhaitez au moins valider le nombre d’enregistrements entre les produits, vous pouvez suivre les étapes suivantes :

1. Dans les [services de requête](https://experienceleague.adobe.com/fr/docs/experience-platform/query/home) dʼAdobe Experience Platform, exécutez la requête Nombre total d’enregistrements par horodatage suivante :

   ```sql
   SELECT
     Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) AS Day,
     Count(_id) AS Records
   FROM  {dataset}
   WHERE   timestamp >= from_utc_timestamp('{fromDate}','UTC')
     AND timestamp < from_utc_timestamp('{toDate}','UTC')
     AND timestamp IS NOT NULL
     AND enduserids._experience.aaid.id IS NOT NULL
   GROUP BY Day
   ORDER BY Day;
   ```

1. Dans les [Flux de données](https://experienceleague.adobe.com/fr/docs/analytics/export/analytics-data-feed/data-feed-overview) d’Adobe Analytics, générez des fichiers de flux pour la période souhaitée. Comptez le nombre de lignes dans chaque fichier, en identifiant et en excluant les lignes suivantes :

   * `exclude_hit` n’est pas `0` (données exclues d’Analysis Workspace dans les deux produits)
   * `hit_source` est `0`, `3`, `5`, `7`, `8`, `9` ou `10` (sources de données et autres données hors accès)
   * `page_event` est `53` ou `63` (accès persistants aux médias en streaming)

   Les lignes correspondant à l’un des critères ci-dessus sont exclues du workflow d’ingestion du connecteur source Analytics et doivent donc également être exclues lors du comptage des lignes des flux de données.

1. Le nombre total d’enregistrements dans les services de requêtes doit correspondre au nombre de lignes dans un flux de données pour la même période.
