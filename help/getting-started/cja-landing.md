---
title: Guide de Customer Journey Analytics
description: Page de destination de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 8b90f74d64ef35f4a9f0f1177dab27c9680ccb4c
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 95%

---

# Guide de Customer Journey Analytics

Ce guide de documentation technique fournit une aide à l’auto-assistance pour Customer Journey Analytics. Customer Journey Analytics vous permet d’importer les données de vos clientes et clients à partir de n’importe quel canal de votre choix (en ligne et hors ligne) dans Adobe Experience Platform. Analysez ensuite ces données comme vous le feriez pour vos données numériques existantes en utilisant l’Analysis Workspace actuel.

Customer Journey Analytics vous permet de contrôler la manière dont vous connectez vos données en ligne et hors ligne dans Analysis Workspace sur n’importe quel ID de client commun, ce qui vous permet d’effectuer une attribution, des filtres, un flux, un abandon, etc. sur l’ensemble de vos données client.

## Nouveautés

Découvrez les améliorations les plus récentes apportées au produit et à la documentation de Customer Journey Analytics. Pour obtenir une liste complète des fonctionnalités, des améliorations et des correctifs, consultez les [notes de mise à jour](../release-notes/latest.md). Visitez la [page des mises à jour de la documentation](../release-notes/doc-changes.md) pour être à jour avec les dernières modifications.

>[!BEGINTABS]

>[!TAB Assistant IA]

L’assistant IA est une expérience conversationnelle qui permet aux utilisateurs et utilisatrices d’effectuer rapidement des tâches, que ce soit en termes de compréhension des concepts, de résolution des problèmes ou de recherche d’informations. Il permet également aux personnes n’étant pas spécialisées d’effectuer des tâches expertes et d’améliorer la qualité générale du travail.

[![Image](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Analyse guidée]

L’analyse guidée est désormais disponible directement dans Analysis Workspace, ce qui permet aux utilisateurs et utilisatrices de créer des tableaux de bord avec des informations complètes issues de panneaux, de visualisations et d’analyses guidées.

[![Image](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)

>[!TAB Alertes]

Les alertes envoient un avertissement en fonction de pourcentages ou de points de données spécifiques modifiés. Vous pouvez prévisualiser la fréquence à laquelle une alerte sera déclenchée, envoyer des alertes par e-mail ou par SMS, créer des alertes empilées, etc.

[![Image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)

>[!TAB Données de résumé]

Vous permet d’importer des données de série temporelle qui ne comportent pas d’ID de personne. Ces données de série temporelle peuvent être utilisées pour prendre en charge divers cas d’utilisation, tels que les suivants :

- Présenter des indicateurs de performances de haut niveau dans ou à côté des données au niveau de l’événement.
- Charger les cibles ou les objectifs toutes les heures ou tous les jours, puis positionner ces cibles ou objectifs par rapport aux mesures au niveau de l’événement.

[![Image](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

>[!TAB Groupement basé sur les graphiques*]

Grâce au groupement basé sur les graphiques, vous pouvez utiliser le graphique d’identité depuis le service d’identité d’Experience Platform pour obtenir une meilleure vue du parcours client en : <ul><li>associant des jeux de données avec différents identifiants sans avoir à extraire, transformer et charger des données supplémentaires pour refléter un seul identifiant ;</li> <li>améliorant la couverture de l’identité préférée ou dorée pour un jeu de données unique en partageant des identités entre les jeux de données ;</li><li>alignant des profils créés dans Real-time Customer Data Platform et Journey Optimizer avec les personnes dans Customer Journey Analytics.</li></ul>

[![Image](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_Vous devez disposer du package Prime pour le groupement basé sur les graphiques._*

>[!TAB Recherches B2B]

Dans le cadre de la configuration d’une connexion, vous pouvez transformer des jeux de données pour des schémas de recherche B2B spécifiques afin de mieux prendre en charge les recherches basées sur des personnes sur les données B2B.

[![Image](assets/learn-more-button.svg)](/help/connections/transform-datasets-b2b-lookups.md)

>[!TAB Champs dérivés]

De nouvelles fonctions de champs dérivés (Mathématique, Suivant ou Précédent, Résumer, Dédupliquer) et des modèles de fonctions supplémentaires (tels que Rebonds, Nom convivial de jeu de données, Période de fêtes, Objectifs mensuels, Détection de robots simple, etc.) sont désormais disponibles.

[![Image](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB Extension BI*]

L’extension BI permet à SQL d’accéder aux vues de données que vous avez définies dans Customer Journey Analytics. Vous pouvez désormais utiliser votre outil de BI préféré pour créer des rapports et des tableaux de bord basés sur les mêmes vues de données que celles utilisées par les utilisateurs Customer Journey Analytics avec leurs projets Analysis Workspace. [Cas d’utilisation](/help/use-cases/data-views/bi-extension-usecases.md) fournis.

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
      <strong>Comparaison avec Adobe Analytics</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Vue d’ensemble</a> - <a href="/help/getting-started/aa-to-cja.md">Évolution</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Utilisation des données Adobe Analytics</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Prise en charge des fonctionnalités</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminologie</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Traitement des données</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>Connexions</strong><br/><a href="/help/connections/overview.md">Vue d’ensemble</a> - <a href="/help/connections/create-connection.md">Créer</a> - <a href="/help/connections/manage-connections.md">Gérer</a> - <a href="/help/stitching/overview.md">Assembler</a> - <a href="/help/connections/combined-dataset.md">Jeu de données d’événement combiné</a> - <a href="/help/connections/standard-lookups.md">Recherches standard</a>
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
<strong>Partager, exporter, intégrer</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Projets</a> - <a href="/help/mobile-app/home.md">Tableaux de bord Analytics</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a> - <a href="/help/components/exports/manage-exports.md">Export vers le cloud</a> - <a href="/help/integrations/overview.md">Intégrations</a>
    </td>
  </tr>
</table>

## Ressources supplémentaires

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/fr/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Tutoriels</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=fr" target="_blank">Description du produit Customer Journey Analytics</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html?lang=fr" target="_blank">Description du produit Adobe Analytics (module complémentaire Customer Journey Analytics)</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">API de Customer Journey Analytics</a> - <a href="/help/ai-assistant.md">Assistant IA</a>
</td>
<td><strong>Ingestion des données</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Vue d’ensemble</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">SDK Web</a> - <a href="/help/data-ingestion/aepmobilesdk.md">SDK Mobile</a> - <a href="/help/data-ingestion/batch.md">Lot</a> - <a href="/help/data-ingestion/streaming.md">Streaming</a> - <a href="/help/data-ingestion/sources.md">Sources</a> - <a href="/help/data-ingestion/serverapi.md">API du serveur</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Ne manquez aucune information, contribuez à la communauté et validez votre expérience Customer Journey Analytics !</b><br>Consultez la communauté Adobe Analytics pour discuter des fonctionnalités avec d’autres utilisateurs et utilisatrices. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=fr">Rejoignez la communauté aujourd’hui !</a></td></tr></tbody></table>
