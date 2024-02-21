---
title: Guide de Customer Journey Analytics
description: Page de destination de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 2f5bd8bec1580077675d249fa0431d84ee2269fa
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 94%

---

# Guide de Customer Journey Analytics

Ce guide de documentation technique fournit une aide à l’auto-assistance pour Customer Journey Analytics. Customer Journey Analytics vous permet d’importer les données de votre clientèle de n’importe quel canal de votre choix (en ligne ou hors ligne) dans Adobe Experience Platform, puis d’analyser ces données comme vous le feriez pour vos données numériques existantes à l’aide d’Analysis Workspace.

Customer Journey Analytics vous permet de contrôler la manière dont vous connectez vos données en ligne et hors ligne dans Analysis Workspace sur n’importe quel ID de client commun, ce qui vous permet d’effectuer une attribution, des filtres, un flux, un abandon, etc. sur l’ensemble de vos données client.

## Nouveautés

Découvrez les améliorations les plus récentes apportées au produit et à la documentation de Customer Journey Analytics. Pour obtenir une liste complète des fonctionnalités, des améliorations et des correctifs, consultez les [Notes de mise à jour](../release-notes/latest.md). Tenez-vous au courant des dernières modifications apportées à notre documentation en consultant la [page des mises à jour de la documentation](../release-notes/doc-changes.md).

>[!BEGINTABS]

>[!TAB Prévisionnel]

La prévision est une fonction d’Analysis Workspace qui permet de prévoir une mesure standard ou calculée avec toute granularité temporelle prise en charge (par heure, par jour, par semaine, par mois et par an). Les prévisions sont disponibles uniquement pour les données liées aux séries temporelles.

[![image](assets/learn-more-button.svg)](/help/analysis-workspace/c-forecast/forecasting.md)


>[!TAB Analyse guidée* - Taux de rétention]

Un nouveau type d’affichage indiquant le pourcentage d’utilisateurs et utilisatrices revenant après leur engagement initial au cours de la période souhaitée. L’axe horizontal représente le nombre de jours depuis l’engagement initial d’un utilisateur ou d’une utilisatrice. L’axe vertical représente le pourcentage d’utilisateurs et utilisatrices qui reprennent le contact.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/types/retention-rates.md)

<span style="color:gray">*_L’analyse guidée est une fonctionnalité d’Adobe Product Analytics, un module complémentaire payant de Customer Journey Analytics._</span>


>[!TAB Analyse guidée* - Tendances]

Les superpositions de tendance sont désormais disponibles dans la vue Utilisation, qui permet de représenter plus clairement un modèle dans les données. Les types de tendance disponibles sont Linéaire, Logarithmique et Moyenne glissante.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/types/usage.md)

<span style="color:gray">*_L’analyse guidée est une fonctionnalité d’Adobe Product Analytics, un module complémentaire payant de Customer Journey Analytics._</span>


>[!TAB Visualisation du résumé des mesures clés]

Avec la visualisation du résumé des mesures clés, la période de comparaison peut désormais se mettre à jour automatiquement, selon que l’option Période de comparaison que vous choisissez est relative à la période principale ou fixe.

[![image](assets/learn-more-button.svg)](/help/analysis-workspace/visualizations/key-metric.md)

>[!ENDTABS]

## Commencer avec les principes de base

Commencez par lire le contenu des liens ci-dessous pour vous familiariser avec les capacités et les fonctionnalités de Customer Journey Analytics.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>Au-delà des données en ligne</strong><br/>Découvrez comment Customer Journey Analytics se compare à Adobe Analytics, quelles fonctionnalités sont partagées et comment utiliser vos données Analytics.</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>Ingestion et utilisation des données</strong><br/>Découvrez les options dont vous avez besoin pour ingérer des données dans Experience Platform et les utiliser pour les analyses et les rapports dans Customer Journey Analytics.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>Analyse guidée</strong><br/>Découvrez comment utiliser des workflows pour obtenir des données et des informations sur l’expérience produit de votre clientèle. Product Analytics via l’analyse guidée...
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>Utilisez Analysis Workspace pour effectuer des analyses de base et avancées, telles que des diagrammes d’attribution, de flux et d’abandons, ainsi que des ventilations de dimensions.</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/guided-analysis/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/analysis-workspace/home.md"><img src="./assets/learn-more-button.svg"></a></td>
    </tr>
</table>

## Explorer la documentation

Comprenez comment Customer Journey Analytics se compare à Adobe Analytics et comment intégrer vos données dans la solution. Préparez, affichez, analysez et démocratisez ces données, ainsi que l’analyse et les rapports qui en résultent.

<table style="table-layout:auto">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>Comparaison avec Adobe Analytics</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Vue d’ensemble</a> - <a href="/help/getting-started/aa-to-cja.md">Évolution</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Utilisation des données Adobe Analytics</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Prise en charge des fonctionnalités</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminologie</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Traitement des données</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>Connexions</strong><br/><a href="/help/connections/overview.md">Vue d’ensemble</a> - <a href="/help/connections/create-connection.md">Créer</a> - <a href="/help/connections/manage-connections.md">Gérer</a> - <a href="/help/stitching/overview.md">Assembler</a> - <a href="/help/connections/combined-dataset.md">Jeu de données d’événement combiné</a> - <a href="/help/connections/standard-lookups.md">Recherches standard</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>Vues de données</strong><br/><a href="/help/data-views/data-views.md">Vue d’ensemble</a> - <a href="/help/data-views/create-dataview.md">Créer ou modifier</a> - <a href="/help/data-views/session-settings.md">Paramètres de session</a> - <a href="/help/data-views/derived-fields/derived-fields.md">Champs dérivés</a> - <a href="/help/data-views/component-reference.md">Référence des composants</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Projets Workspace</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">Analyse de base</a> &amp; <a href="/help/analysis-workspace/perform-adv-analysis.md">avancée</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">Projets</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualisations</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">Panneaux</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>Analyse guidée</strong><br/><a href="/help/guided-analysis/overview.md">Vue d’ensemble</a> - <a href="/help/guided-analysis/types/active.md">Croissance des utilisateurs et utilisatrices</a> - <a href="/help/guided-analysis/types/usage.md">Tendances</a> - <a href="/help/guided-analysis/types/friction.md">Entonnoir</a> - <a href="/help/guided-analysis/types/release.md">Impact</a> - <a href="/help/guided-analysis/industry-use-cases.md">Cas d’utilisation du secteur</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>Partager, exporter, intégrer</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Projets</a> - <a href="/help/mobile-app/home.md">Tableaux de bord Analytics</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a>  - <a href="/help/integrations/overview.md">Intégrations</a>
    </td>
  </tr>
</table>

## Ressources supplémentaires

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/overview.html?lang=fr" target="_blank">Tutoriels</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=fr" target="_blank">Description du produit Customer Journey Analytics</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html?lang=fr" target="_blank">Description du produit Adobe Analytics (module complémentaire Customer Journey Analytics)</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">API de Customer Journey Analytics</a>
</td>
<td><strong>Ingestion des données</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Vue d’ensemble</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">SDK Web</a> - <a href="/help/data-ingestion/aepmobilesdk.md">SDK Mobile</a> - <a href="/help/data-ingestion/batch.md">Lot</a> - <a href="/help/data-ingestion/streaming.md">Streaming</a> - <a href="/help/data-ingestion/sources.md">Sources</a> - <a href="/help/data-ingestion/serverapi.md">API du serveur</a>
</td>
</tr></table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Ne manquez aucune information, contribuez à la communauté et validez votre expérience Customer Journey Analytics !</b><br>Consultez la communauté Adobe Analytics pour discuter des fonctionnalités avec d’autres utilisateurs et utilisatrices. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=fr">Rejoignez la communauté aujourd’hui !</a></td></tr></tbody></table>
