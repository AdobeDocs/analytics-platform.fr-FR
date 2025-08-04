---
title: Guide de Customer Journey Analytics
description: Page de destination de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 830e8312b4be2ffac907baca282ce71029e6ecc5
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 98%

---

# Guide de Customer Journey Analytics

Ce guide de documentation technique fournit une aide à l’auto-assistance pour Customer Journey Analytics. Customer Journey Analytics vous permet d’importer les données de vos clientes et clients à partir de n’importe quel canal de votre choix (en ligne et hors ligne) dans Adobe Experience Platform. Analysez ensuite ces données comme vous le feriez pour vos données numériques existantes en utilisant l’Analysis Workspace actuel.

Customer Journey Analytics vous permet de contrôler la manière dont vous connectez vos données en ligne et hors ligne dans Analysis Workspace sur n’importe quel ID de client commun, ce qui vous permet d’effectuer une attribution, des segments, un flux, des abandons, etc. sur l’ensemble de vos données client.

## Nouveautés

Découvrez les améliorations les plus récentes apportées au produit et à la documentation de Customer Journey Analytics. Pour obtenir une liste complète des fonctionnalités, des améliorations et des correctifs, consultez les [notes de mise à jour](../release-notes/latest.md). Accédez à la [page des mises à jour de la documentation](../release-notes/doc-changes.md) pour connaître les dernières modifications.

>[!BEGINTABS]

>[!TAB B2B Edition]

Customer Journey Analytics B2B Edition permet aux sociétés B2B d’aligner leurs équipes marketing, ventes et produits en fournissant des informations de compte exploitables qui stimulent l’augmentation des revenus. Le compte étant placé au centre du modèle de données, toutes les analyses se concentrent sur le parcours du compte.

[![Image](assets/learn-more-button.svg)](/help/getting-started/cja-b2b-edition.md)

>[!TAB Fonctions de champ dérivées]

Nouvelles fonctions de champ dérivé : [Mathématiques des données](/help/data-views/derived-fields/derived-fields.md#date-math), [Profondeur](/help/data-views/derived-fields/derived-fields.md#depth) et [Typecast](/help/data-views/derived-fields/derived-fields.md#typecast).

[![Image](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB Analyse du contenu]

L’analyse du contenu Adobe vous permet d’examiner rapidement et facilement de grands volumes de données de contenu pour repérer des tendances, détecter des anomalies, identifier la lassitude liée au contenu et obtenir des informations issues de l’exposition du contenu.

[![Image](assets/learn-more-button.svg)](/help/content-analytics/content-analytics.md)

>[!TAB Profondeur de l’événement]

La profondeur de l’événement est une nouvelle dimension standard qui offre de nouvelles façons de mesurer et de mieux comprendre le positionnement des événements dans les sessions client. La dimension Profondeur de l’événement permet un suivi et une analyse détaillés de l’endroit où des événements spécifiques se produisent dans le flux séquentiel des interactions utilisateur au sein d’une session.

[![Image](assets/learn-more-button.svg)](/help/components/dimensions/overview.md#standard-dimensions)


>[!TAB Dimensions et mesures partagées]

Les dimensions et mesures partagées fournissent un emplacement central où gérer les dimensions et mesures qui peuvent être utilisées dans un certain nombre de vues de données. Ces composants sont particulièrement utiles aux entreprises qui utilisent plusieurs vues de données, en particulier si ces vues de données ont des paramètres de composant en commun.

[![Image](assets/learn-more-button.svg)](/help/data-views/shared-metrics-dimensions/smd-overview.md)


<!--
>[!TAB AI Assistant] 

AI Assistant is a conversational experience that allows practitioners to perform tasks at a fast pace - whether its understanding concepts, troubleshooting problems, or searching through information. It also allows non-experts to perform expert tasks and increases the overall quality of work.

[![image](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Guided Analysis] 

Guided Analysis is now available directly from within Analysis Workspace, enabling users to create dashboards with comprehensive insights from panels, visualizations, and guided analyses.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)



>[!TAB Intelligent captions v2] 

Intelligent captions are now supported, with additional interface improvements, for [Line](/help/analysis-workspace/visualizations/line.md) (including multi-line), [Bar](/help/analysis-workspace/visualizations/bar.md), [Horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md), [Area](/help/analysis-workspace/visualizations/area.md) (including multiple Area lines), [Donut](/help/analysis-workspace/visualizations/donut.md), [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), and [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md) visualizations.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Alerts] 

Alerts allow you to be notified based on changed percentages or specific data points. You can preview how often an alert will trigger, send alerts by email or SMS, create stacked alerts, and more.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Summary data] 

Allows you to bring in time-series data that does not have a person ID. This time-series data can be used to support various use cases, such as 

- Presenting high-level performance indicators as part of or next to event-level data. 
- Uploading targets or goals at an hourly or daily basis, then positioning these targets or goals against event-level metrics. 

[![image](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

-->

>[!TAB Groupement basé sur les graphiques*]

Grâce au groupement basé sur les graphiques, vous pouvez utiliser le graphique d’identité depuis le service d’identité d’Experience Platform pour obtenir une meilleure vue du parcours client en : <ul><li>associant des jeux de données avec différents identifiants sans avoir à extraire, transformer et charger des données supplémentaires pour refléter un seul identifiant ;</li> <li>améliorant la couverture de l’identité préférée ou dorée pour un jeu de données unique en partageant des identités entre les jeux de données ;</li><li>alignant des profils créés dans Real-time Customer Data Platform et Journey Optimizer avec les personnes dans Customer Journey Analytics.</li></ul>

[![Image](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_Vous devez disposer du package Prime pour le groupement basé sur les graphiques._*

>[!TAB Extension BI*]

L’extension BI permet à SQL d’accéder aux vues de données que vous avez définies dans Customer Journey Analytics. Vous pouvez désormais utiliser votre outil de BI favori (Power BI Desktop, Tableau Desktop, Looker, Jupyter Notebook et RStudio) pour créer des rapports et des tableaux de bord en fonction des vues de données que les utilisateurs et utilisatrices de Customer Journey Analytics utilisent lors de la création de leurs projets Analysis Workspace. Des [cas d’utilisation](/help/use-cases/data-views/bi-extension-usecases.md) sont fournis.

[![Image](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

*_Vous devez disposer du package Select ou d’une version supérieure pour utiliser l’extension BI._*


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
    <div><strong>Ingestion et utilisation des données</strong><br/>Découvrez les options dont vous disposez pour ingérer des données dans Experience Platform et les utiliser pour les analyses et les rapports dans Customer Journey Analytics.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>Analyse guidée</strong><br/>Découvrez comment utiliser des workflows pour obtenir des données et des informations sur l’expérience produit de votre clientèle. Product Analytics via l’analyse guidée…
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

Comprenez les différences entre Customer Journey Analytics et Adobe Analytics. et comment intégrer vos données dans la solution. Préparez, affichez, analysez et démocratisez ces données, ainsi que l’analyse et les rapports qui en résultent.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
<strong>Comparer à Adobe Analytics</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Vue d’ensemble</a> - <a href="/help/getting-started/aa-to-cja.md">Évolution</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Utiliser les données Adobe Analytics</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Prise en charge des fonctionnalités</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminologie</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Traitement des données</a> - <a href="/help/getting-started/cja-b2b-edition.md">Customer Journey Analytics B2B Edition</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
<strong>Connexions</strong><br/><a href="/help/connections/overview.md">Vue d’ensemble</a> - <a href="/help/connections/create-connection.md">Créer</a> - <a href="/help/connections/manage-connections.md">Gérer</a> - <a href="/help/stitching/overview.md">Assembler</a> - <a href="/help/connections/combined-dataset.md">Jeux de données d’événements combinés</a> - <a href="/help/connections/standard-lookups.md">Recherches standard</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
<strong>Vues de données</strong><br/><a href="/help/data-views/data-views.md">Vue d’ensemble</a> - <a href="/help/data-views/create-dataview.md">Créer ou modifier</a> - <a href="/help/data-views/session-settings.md">Paramètres de session</a> - <a href="/help/data-views/derived-fields/derived-fields.md">Champs dérivés</a> - <a href="/help/data-views/summary-data.md">Données de résumé</a> - <a href="/help/data-views/component-reference.md">Référence des composants</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Projets Workspace</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">Analyse de base</a> &amp; <a href="/help/analysis-workspace/perform-adv-analysis.md">avancée</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">Projets</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualisations</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">Panneaux</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
<strong>Analyse guidée</strong><br/><a href="/help/guided-analysis/overview.md">Vue d’ensemble</a> - <a href="/help/guided-analysis/types/active-growth.md">Croissance des utilisateurs et utilisatrices</a> - <a href="/help/guided-analysis/types/trends.md">Tendances</a> - <a href="/help/guided-analysis/types/funnel.md">Entonnoir</a> - <a href="/help/guided-analysis/types/release-impact.md">Impact</a> - <a href="/help/guided-analysis/industry-use-cases.md">Cas d’utilisation du secteur</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
<strong>Partager, exporter, intégrer</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Projets</a> - <a href="/help/mobile-app/home.md">Tableaux de bord Analytics</a> - <a href="/help/report-builder/rb-overview.md">Report Builder</a> - <a href="/help/components/exports/manage-exports.md">Export vers le cloud</a> - <a href="/help/integrations/overview.md">Intégrations</a>
    </td>
  </tr>
</table>

## Ressources supplémentaires

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/fr/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Tutoriels</a> - <a href="https://helpx.adobe.com/fr/legal/product-descriptions/customer-journey-analytics.html?lang=fr" target="_blank">Description du produit Customer Journey Analytics</a> - <a href="https://helpx.adobe.com/fr/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html?lang=fr" target="_blank">Description du produit Adobe Analytics (module complémentaire Customer Journey Analytics)</a> - <a href="https://helpx.adobe.com/fr/legal/product-descriptions/customer-journey-analytics-b2b.html?lang=fr" target="_blank">Description du produit Customer Journey Analytics B2B Edition</a> - <a href="https://developer.adobe.com/cja-apis/docs/?lang=fr" target="_blank">API Customer Journey Analytics</a> - <a href="/help/ai-assistant.md">Assistant IA</a>
</td>
<td><strong>Ingestion des données</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Vue d’ensemble</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">SDK Web</a> - <a href="/help/data-ingestion/aepmobilesdk.md">SDK Mobile</a> - <a href="/help/data-ingestion/batch.md">Lot</a> - <a href="/help/data-ingestion/streaming.md">Streaming</a> - <a href="/help/data-ingestion/sources.md">Sources</a> - <a href="/help/data-ingestion/serverapi.md">API du serveur</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Ne manquez aucune information, contribuez à la communauté et validez votre expérience Customer Journey Analytics !</b><br>Consultez la communauté Adobe Analytics pour discuter des fonctionnalités avec d’autres utilisateurs et utilisatrices. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=fr">Rejoignez la communauté aujourd’hui !</a></td></tr></tbody></table>
