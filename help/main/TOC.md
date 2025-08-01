---
git-repo: https://github.com/AdobeDocs/analytics-platform.fr-FR
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Guide de Customer Journey Analytics
user-guide-description: Découvrez Adobe Customer Journey Analytics et comment utiliser Analysis Workspace avec des données d’Experience Platform.
breadcrumb-title: Guide de Customer Journey Analytics
source-git-commit: 1b81b0fb81119132b6568726761e9897c2b4e47c
workflow-type: tm+mt
source-wordcount: '1278'
ht-degree: 99%

---

# Guide d’Adobe Customer Journey Analytics {#using}

+ [Guide d’Adobe Customer Journey Analytics](../getting-started/cja-landing.md)

+ Notes de mise à jour {#releases}
   + [Dernière mise à jour de Customer Journey Analytics](../release-notes/latest.md)
   + [Notes de version préliminaire de Customer Journey Analytics](../release-notes/pre-release-notes.md)
   + [Versions de 2025](../release-notes/2025.md)
   + [Versions de 2024](../release-notes/2024.md)
   + [Versions de 2023](../release-notes/2023.md)
   + [Versions de 2022](../release-notes/2022.md)
   + [Versions de 2021](../release-notes/2021.md)
   + [Versions de 2020](../release-notes/2020.md)
   + [Stratégie de mise à jour des fonctionnalités](../release-notes/releases.md)
   + [Mises à jour de la documentation](../release-notes/doc-changes.md)

+ Commencer {#cja-overview}
   + Customer Journey Analytics {#cja-b2c-overview}
      + [Présentation](../getting-started/cja-overview.md)
      + [Guide de démarrage rapide](../getting-started/cja-getting-started.md)
      + [Page de destination](../getting-started/landing.md)
      + [Questions fréquentes](../getting-started/cja-faq.md)
      + [Comparer aux solutions BI](../getting-started/cja-vs-bi.md)
      + [Assistant IA](../ai-assistant.md)
      + [Agent Data Insights](../data-analysis-ai.md)
   + Customer Journey Analytics B2B Edition {#cja-b2b}
      + [Présentation](/help/getting-started/cja-b2b-edition.md)
      + [Concepts et fonctionnalités B2B](/help/getting-started/cja-b2b-concepts-features.md)
      + [Guide de démarrage rapide](/help/getting-started/cja-b2b-quick-start-guide.md)
      + [Guide de transition](/help/getting-started/cja-b2b-transition.md)

+ Mettre à niveau et comparer {#compare-aa-cja}
   + Mettre à niveau vers Customer Journey Analytics {#upgrade-to-cja}
      + [Commencer](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [Choisir votre chemin de mise à niveau](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Envoyer des données à Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [Conserver les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
      + [Processus de mise à niveau recommandé](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)
      + Concevoir et créer un schéma {#schema}
         + [Concevoir votre schéma](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)
         + [Créer votre schéma](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)
         + [Utiliser votre schéma existant](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)
      + Créer un train de données {#create-datastream}
         + [Créer un train de données](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)
         + [Ajouter Platform en tant que service](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)
      + Créer des jeux de données {#create-datasets}
         + [Créer un jeu de données](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)
         + [Créer des jeux de données de recherche pour les classifications](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)
         + [Surveiller l’ingestion des jeux de données](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)
      + Implémenter le SDK web avec des balises {#create-tags}
         + [Créer une balise pour votre propriété](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)
         + [Ajouter l’extension SDK web à votre balise](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)
         + [Implémenter la balise de chargement pour l’extension SDK web](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)
         + [Ajouter une logique de collecte de données XDM à votre balise](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)
      + [Implémenter le SDK web manuellement](/help/getting-started/cja-upgrade/cja-upgrade-manual.md)
      + [Implémenter le SDK web avec l’API](/help/getting-started/cja-upgrade/cja-upgrade-api.md)
      + [Créer une connexion](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)
      + [Créer une vue de données](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)
      + [Créer un champ dérivé d’un canal marketing](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)
      + [Valider un flux de données](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)
      + [Configurer Streaming Media Collection](/help/getting-started/cja-upgrade/cja-upgrade-streaming-media.md)
      + Conserver les données historiques avec le connecteur source Analytics {#historical-data-source-connector}
         + [Créer un schéma XDM pour le connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)
         + [Créer des champs de mappage et du connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)
         + [Ajouter le jeu de données du connecteur source Analytics à la connexion](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)
      + [Estimer quand désactiver Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)
      + [Désactiver Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)
      + Autres méthodes de mise à niveau {#alternative-upgrade-methods}
         + [Désactiver la collecte de données AppMeasurement](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)
         + [Envoyer la couche de données](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)
         + [Connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)
      + Autres scénarios de mise à niveau {#other-upgrade-scenarios}
         + [Passer du connecteur source Analytics au SDK web](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)
         + [Mettre à niveau à partir d’une solution d’analyse autre qu’Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-third-party-solution.md)
      + Informations supplémentaires {#additional-information}
         + [Comprendre la mise en œuvre d’Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md)
         + [Prise en charge des fonctionnalités Adobe Analytics lors de la mise à niveau](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)
         + [Fonctionnalités Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md)
         + [Options d’implémentation du SDK web](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md)
         + [Configurer le SDK web Adobe Analytics pour Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)
         + [Utiliser la personnalisation avec Adobe Journey Optimizer](/help/getting-started/cja-upgrade/cja-upgrade-personalization-journeyoptimizer.md)
   + Comparer à Adobe Analytics {#cja-aa-comparison}
      + [Présentation](../getting-started/aa-vs-cja/overview.md)
      + [Utilisation de données Adobe Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Prise en charge des fonctionnalités](../getting-started/aa-vs-cja/cja-aa.md)
      + [Comparaison de la terminologie](../getting-started/aa-vs-cja/terminology.md)
      + [Comparaison du traitement des données](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Environnements](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Traitement d’Analytics par rapport à la préparation des données](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [Identités Analytics](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Évolution à partir d’Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Guide de l’utilisateur pour les utilisateurs et utilisatrices d’Adobe Analytics](../getting-started/aa-to-cja-user.md)

+ Ingestion de données {#cja-data-ingestion}
   + [Vue d’ensemble de l’ingestion de données](../data-ingestion/data-ingestion.md)
   + Guides de démarrage rapide d’ingestion et d’utilisation{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Experience Platform Edge Network {#edge-network}
         + [SDK web](../data-ingestion/aepwebsdk.md)
         + [SDK mobile](../data-ingestion/aepmobilesdk.md)
         + [API du serveur](../data-ingestion/serverapi.md)
      + [Données par lot](../data-ingestion/batch.md)
      + [Données de flux](../data-ingestion/streaming.md)
      + [Connecteurs source](../data-ingestion/sources.md)

+ Connexions {#cja-connections}
   + [Vue d’ensemble des connexions](../connections/overview.md)
   + [Créer ou modifier une connexion](../connections/create-connection.md)
   + [Gérer des connexions](../connections/manage-connections.md)
   + [Jeu de données d’événements combinés](../connections/combined-dataset.md)
   + [Recherches standard](../connections/standard-lookups.md)
   + [Recherches B2B](../connections/transform-datasets-b2b-lookups.md)

+ Vues des données {#cja-dataviews}
   + [Vue d’ensemble des vues de données](../data-views/data-views.md)
   + [Création ou modification d’une vue de données](../data-views/create-dataview.md)
   + [Paramètres de session](../data-views/session-settings.md)
   + Paramètres de composant {#component-settings}
      + [Présentation des paramètres de composant](../data-views/component-settings/overview.md)
      + [Attribution](../data-views/component-settings/attribution.md)
      + [Comportement](../data-views/component-settings/behavior.md)
      + [Mise en forme](../data-views/component-settings/format.md)
      + [Valeurs d’inclusion/exclusion](../data-views/component-settings/include-exclude-values.md)
      + [Déduplication des mesures](../data-views/component-settings/metric-deduplication.md)
      + [Pas d’option de valeur](../data-views/component-settings/no-value-options.md)
      + [Persistance](../data-views/component-settings/persistence.md)
      + [Sous-chaîne](../data-views/component-settings/substring.md)
      + [Groupe de données de résumé](../data-views/component-settings/summary-data-group.md)
      + [Groupement des valeurs](../data-views/component-settings/value-bucketing.md)
   + [Référence de composant standard](../data-views/component-reference.md)
   + [Extension BI](../data-views/bi-extension.md)
   + [Champs dérivés](../data-views/derived-fields/derived-fields.md)
   + [Champs dérivés (limités)](../data-views/derived-fields/derived-fields-limited.md)
   + [Données de résumé](../data-views/summary-data.md)
   + [Libellés et politiques](../data-views/data-governance.md)
   + Mesures et dimensions partagées{#shared-metrics-dimensions}
      + [Présentation](/help/data-views/shared-metrics-dimensions/smd-overview.md)
      + [Éditeur](/help/data-views/shared-metrics-dimensions/shared-component-editor.md)

+ Outils {#tools}
   + Transfert de ressources {#asset-transfer}
      + [Transférer des ressources](../tools/asset-transfer/transfer-assets.md)
   + Utilisation du produit {#product-usage}
      + [Présentation](../tools/product-usage/usage-overview.md)
      + [Paramètres des données](../tools/product-usage/data-settings.md)
      + [Paramètres d’exclusion](../tools/product-usage/opt-out-settings.md)

+ Projets Workspace {#cja-workspace}
   + [Vue d’ensemble d’Analysis Workspace](../analysis-workspace/home.md)
   + [Exécution d’une analyse de base](../analysis-workspace/perform-basic-analysis.md)
   + [Exécuter une analyse avancée](../analysis-workspace/perform-adv-analysis.md)
   + Projets {#build-workspace-project}
      + [Présentation](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Démarrer rapidement des projets](/help/analysis-workspace/build-workspace-project/starter-projects.md)
      + [Créer des projets](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Ouvrir des projets](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [Commentaires dans les projets](/help/analysis-workspace/build-workspace-project/comment-projects.md)
      + [Enregistrer des projets](../analysis-workspace/build-workspace-project/save-projects.md)
      + [Table des matières](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
      + Dossiers dans Workspace {#workspace-folders}
         + [Présentation](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Créer des dossiers](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Gérer des dossiers](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [Ajouter ou déplacer des projets](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [Touches de raccourci](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Palettes de couleurs](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Densité de la vue](../analysis-workspace/build-workspace-project/view-density.md)
      + [Débogueur](../analysis-workspace/build-workspace-project/debugger.md)
   + Modèles {#templates}
      + [Utiliser des modèles](../analysis-workspace/templates/use-templates.md)
      + [Créer et gérer des modèles](../analysis-workspace/templates/create-templates.md)
   + Visualisations {#visualizations}
      + [Présentation](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Gérer des sources de données](../analysis-workspace/visualizations/t-sync-visualization.md)
      + [Légendes intelligentes](../analysis-workspace/visualizations/intelligent-captions.md)
      + Tableau à structure libre {#freeform-table}
         + [Présentation](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + [Créer des liens hypertextes](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
         + Paramètres des colonnes et des lignes {#column-row-settings}
            + [Paramètres des colonnes](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Paramètres des lignes](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Éléments dynamiques et statiques](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtrer et trier](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Totaux](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Table de cohorte {#cohort-table}
         + [Présentation](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configurer](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Cas d’utilisation](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Abandon {#fallout}
         + [Présentation](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configurer](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Abandons interdimensionnels](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Appliquer des segments](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flux {#flow}
         + [Présentation](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Configurer](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Flux interdimensionnels](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + Zone de travail de parcours {#journey-canvas}
         + [Présentation](../analysis-workspace/visualizations/journey-canvas/journey-canvas.md)
         + [Configurer](../analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)
         + [Résoudre des problèmes](../analysis-workspace/visualizations/journey-canvas/journey-canvas-troubleshooting.md)
      + [Aires (empilées)](../analysis-workspace/visualizations/area.md)
      + [Barres (empilées)](../analysis-workspace/visualizations/bar.md)
      + [Puces](../analysis-workspace/visualizations/bullet-graph.md)
      + [Combo](../analysis-workspace/visualizations/combo-charts.md)
      + [Anneau](../analysis-workspace/visualizations/donut.md)
      + [Histogramme](../analysis-workspace/visualizations/histogram.md)
      + [Barres horizontales (empilées)](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Résumé des mesures clés](../analysis-workspace/visualizations/key-metric.md)
      + [Graphique linéaire](../analysis-workspace/visualizations/line.md)
      + [Carte](/help/analysis-workspace/visualizations/map.md)
      + [Nuage de points](../analysis-workspace/visualizations/scatterplot.md)
      + [En-tête de section](/help/analysis-workspace/visualizations/section-header.md)
      + [Synthèse de nombres et de variations](../analysis-workspace/visualizations/summary-number-change.md)
      + [Texte](../analysis-workspace/visualizations/text.md)
      + [Plan en arborescence](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Panneaux {#panels}
      + [Présentation](../analysis-workspace/c-panels/panels.md)
      + [Panneau vierge](../analysis-workspace/c-panels/blank-panel.md)
      + [Attribution](../analysis-workspace/c-panels/attribution.md)
      + [Expérimentation](../analysis-workspace/c-panels/experimentation.md)
      + [Tableau à structure libre](../analysis-workspace/c-panels/freeform-panel.md)
      + [Audience moyenne par minute de média](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [Visites simultanées de médias](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Temps de lecture de média](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [Élément suivant ou précédent](../analysis-workspace/c-panels/next-previous.md)
      + [Aperçu rapide](../analysis-workspace/c-panels/quickinsight.md)
   + Traiter et partager {#curate-share}
      + [Présentation](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Traitement des projets](../analysis-workspace/curate-share/curate.md)
      + [Partager des projets](../analysis-workspace/curate-share/share-projects.md)
      + [Création de liens partageables](../analysis-workspace/curate-share/shareable-links.md)
      + [Projets en lecture seule](../analysis-workspace/curate-share/view-only-projects.md)
   + Exporter {#export}
      + [Présentation](../analysis-workspace/export/export-project-overview.md)
      + [Télécharger](../analysis-workspace/export/download-send.md)
      + [Envoyer et planifier](../analysis-workspace/export/t-schedule-report.md)
      + [Exporter vers le cloud](../analysis-workspace/export/export-cloud.md)
   + Attribution {#attribution}
      + [Vue d’ensemble d’attribution](../analysis-workspace/attribution/overview.md)
      + [Modèle, conteneur et intervalle de recherche en amont](../analysis-workspace/attribution/models.md)
      + [Attribution algorithmique](../analysis-workspace/attribution/algorithmic.md)
      + [Bonnes pratiques](../analysis-workspace/attribution/best-practices.md)
      + [Questions fréquentes](../analysis-workspace/attribution/faq.md)
   + Détection des anomalies {#anomaly-detection}
      + [Présentation](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Afficher les anomalies](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [Techniques statistiques](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + Prévisions {#forecasting}
      + [Présentation](../analysis-workspace/c-forecast/forecasting.md)
      + [Afficher des prévisions](../analysis-workspace/c-forecast/view-forecasts.md)
      + [Techniques statistiques](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [Préférences de l’utilisateur ou de l’utilisatrice](../analysis-workspace/user-preferences.md)
   + Questions fréquentes sur Workspace et plus {#workspace-faq}
      + [Questions fréquentes](../analysis-workspace/workspace-faq/faq.md)
      + [Optimiser les performances](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Erreur et résolution des problèmes](../analysis-workspace/workspace-faq/error-messages.md)
      + [Limites](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Exigences](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Accessibilité](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Content Analytics {#content-analytics}
   + [Présentation](/help/content-analytics/content-analytics.md)
   + Rapport {#report}
      + [Présentation](/help/content-analytics/report/report.md)
      + [Composants](/help/content-analytics/report/components.md)
   + Configuration {#configuration}
      + [Présentation](/help/content-analytics/config/configuration.md)
      + [Configuration guidée](/help/content-analytics/config/guided.md)
      + [Configuration manuelle](/help/content-analytics/config/manual.md)
      + [Collecte de données](/help/content-analytics/config/datacollection.md)

+ Tableaux de bord Analytics {#cja-dashboards}
   + [Présentation](../mobile-app/home.md)
   + [Tâches d’édition](../mobile-app/curator.md)
   + [Créer des cartes de performance mobiles](../mobile-app/create-scorecard.md)
   + [Gérer les cartes de performance mobiles](../mobile-app/manage-scorecard.md)
   + [Préparation des utilisateurs en charge de lʼexécution à lʼutilisation des tableaux de bord](../mobile-app/set-up-execs.md)
   + [Guide pour une prise en main rapide destiné aux utilisateurs en charge de l’exécution](../mobile-app/executive.md)

+ Analyse guidée {#guided-analysis}
   + [Présentation](../guided-analysis/overview.md)
   + [Croissance active](../guided-analysis/types/active-growth.md)
   + [Tendances de conversion](../guided-analysis/types/conversion-trends.md)
   + [Engagement](../guided-analysis/types/engagement.md)
   + [Impact de la première utilisation](../guided-analysis/types/first-use-impact.md)
   + [Fréquence](../guided-analysis/types/frequency.md)
   + [Entonnoir](../guided-analysis/types/funnel.md)
   + [Croissance nette](../guided-analysis/types/net-growth.md)
   + [Impact de la nouvelle version](../guided-analysis/types/release-impact.md)
   + [Rétention](../guided-analysis/types/retention.md)
   + [Chronologie](../guided-analysis/types/timeline.md)
   + [Tendances](../guided-analysis/types/trends.md)
   + [Cas dʼutilisation du secteur](../guided-analysis/industry-use-cases.md)
   + [Questions fréquentes](../guided-analysis/faq.md)

+ Composants {#cja-components}
   + [Présentation](../components/overview.md)
   + [Utiliser les composants](../components/use-components-in-workspace.md)
   + [Ajouter des descriptions des composants](../components/add-component-descriptions.md)
   + Annotations {#annotations}
      + [Présentation](../components/annotations/overview.md)
      + [Création d’annotations](../components/annotations/create-annotations.md)
      + [Gestion des annotations](../components/annotations/manage-annotations.md)
      + [Affichage des annotations](../components/annotations/view-annotations.md)
      + [Annotations de carte de performance mobile](../components/annotations/mobile-annotations.md)
   + Audiences {#audiences}
      + [Présentation des audiences](../components/audiences/audiences-overview.md)
      + [Créer et publier des audiences](../components/audiences/publish.md)
      + [Gérer des audiences](../components/audiences/manage.md)
   + Dimensions {#dimensions}
      + [Présentation](../components/dimensions/overview.md)
      + [Aperçu des dimensions](../components/dimensions/view-dimensions.md)
      + [Ventilation des dimensions](../components/dimensions/t-breakdown-fa.md)
      + [Dimensions de répartition du temps](../components/dimensions/time-parting-dimensions.md)
      + [Dimensions de cardinalité élevée](../components/dimensions/high-cardinality.md)
   + [Mesures](../components/apply-create-metrics.md)
   + Segments {#segments}
      + [Présentation](/help/components/segments/seg-overview.md)
      + [Créer des segments](/help/components/segments/seg-create.md)
      + [Créer des segments](/help/components/segments/seg-builder.md)
      + [Segments rapides](/help/components/segments/seg-quick.md)
      + [Segments séquentiels](/help/components/segments/seg-sequential-build.md)
      + [Partager des segments](/help/components/segments/seg-share.md)
      + [Baliser des segments](/help/components/segments/seg-tag.md)
      + [Filtrer la liste de segments](/help/components/segments/seg-filter.md)
      + [Marquer des segments comme favoris](/help/components/segments/seg-favorite.md)
      + [Approuver des segments](/help/components/segments/seg-approve.md)
      + [Copier des segments](/help/components/segments/seg-copy.md)
      + [Gérer les segments](/help/components/segments/seg-manage.md)
      + [Opérateurs](/help/components/segments/seg-operators.md)
      + [Utiliser les segments](/help/components/segments/seg-use.md)
   + Mesures calculées {#cja-calcmetrics}
      + [Présentation](../components/calc-metrics/calc-metr-overview.md)
      + Workflow {#cm-workflow}
         + [Créer des mesures calculées](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Rechercher des mesures](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Créer des mesures calculées](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Exemple simple](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Exemple plus complexe](../components/calc-metrics/cm-workflow/cm-orders-participation.md)
         + [Type de mesure et attribution](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Mesures de participation](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Mesures segmentées](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Empilage et remplacement des segments](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Filtrer des mesures calculées](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Marquer des mesures calculées en tant que favoris](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [Copier des mesures calculées](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [Utilisation des fonctions](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Baliser des mesures calculées](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Approbation des mesures calculées](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Partage des mesures calculées](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Gestion des mesures calculées](../components/calc-metrics/cm-workflow/cm-manager.md)
         + [Exemples](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
      + [Modèles de mesures calculées](../components/calc-metrics/default-calcmetrics.md)
      + [Fonctions de base](../components/calc-metrics/cm-functions.md)
      + [Fonctions avancées](../components/calc-metrics/cm-adv-functions.md)
   + Périodes {#cja-date-ranges}
      + [Présentation](../components/date-ranges/overview.md)
      + [Créer des périodes](../components/date-ranges/create.md)
      + [Gestion des périodes](../components/date-ranges/manage.md)
      + [Comparaison des dates](../components/date-ranges/time-comparison.md)
      + [Exemples](../components/date-ranges/custom-date-ranges.md)
   + Alertes {#alerts}
      + [Vue d’ensemble](/help/components/c-intelligent-alerts/intelligent-alerts.md)
      + [Créer des alertes](/help/components/c-intelligent-alerts/alert-builder.md)
      + [Gérer les alertes](/help/components/c-intelligent-alerts/alert-manager.md)
      + [Comparaison des fonctionnalités](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)
      + [Cas d’utilisation](/help/components/c-intelligent-alerts/alerts-use-cases.md)
   + Exports {#exports}
      + [Configurer des comptes d’export cloud](/help/components/exports/cloud-export-accounts.md)
      + [Configurer des emplacements d’export cloud](/help/components/exports/cloud-export-locations.md)
      + [Gérer des emplacements d’export dans le cloud](/help/components/exports/manage-export-locations.md)
      + [Gérer des exports](/help/components/exports/manage-exports.md)
      + [Gérer les journaux d’export](/help/components/exports/manage-export-logs.md)
      + [Résoudre les problèmes d’export](/help/components/exports/troubleshoot-exports.md)
   + Dictionnaire de données {#data-dictionary}
      + [Présentation](../components/data-dictionary/data-dictionary-overview.md)
      + [Afficher des informations sur les composants dans le dictionnaire de données](../components/data-dictionary/view-data-dictionary.md)
      + [Modifier les entrées de composant dans le dictionnaire de données](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Surveiller l’intégrité du dictionnaire de données](../components/data-dictionary/monitor-data-dictionary-health.md)
   + Créer des rapports en temps réel {#real-time-reporting}
      + [Présentation](/help/components/real-time/real-time.md)
      + [Utiliser la création de rapports en temps réel](/help/components/real-time/use-real-time.md)
   + [Projets planifiés](../components/scheduled-projects-manager.md)
+ Report Builder {#cja-reportbuilder}
   + [Présentation](../report-builder/rb-overview.md)
   + [Configuration de Report Builder](../report-builder/report-builder-setup.md)
   + [Créer un bloc de données](../report-builder/create-a-data-block.md)
   + [Hub Report Builder](../report-builder/report-builder-hub.md)
   + [Sélectionner une vue de données](../report-builder/select-data-view.md)
   + [Sélectionner une période](../report-builder/select-date-range.md)
   + [Utiliser des segments](../report-builder/work-with-filters.md)
   + [Filtrer des dimensions](../report-builder/filter-dimensions.md)
   + [Gérer les blocs de données](../report-builder/manage-reportbuilder.md)
   + [Planifier des classeurs pour les e-mails](../report-builder/schedule-reportbuilder.md)
   + [Planifier des classeurs pour les exports cloud](../report-builder/report-builder-export.md)
   + [Gérer les plannings de classeurs](/help/report-builder/manage-schedules-reportbuilder.md)
   + [Libellés restreints](../report-builder/restricted-labels.md)
   + [Paramètres de Report Builder](../report-builder/report-builder-settings.md)


+ Gestionnaire des activités de rapport {#reporting-activity-manager}
   + [Présentation](../reporting-activity-manager/reporting-activity-overview.md)
   + [Afficher l’activité de rapport](../reporting-activity-manager/reporting-activity.md)
   + [Annuler des demandes de création de rapports](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Groupement {#stitching}
   + [Présentation](/help/stitching/overview.md)
   + [Groupement basé sur les champs](/help/stitching/fbs.md)
   + [Groupement basé sur les graphes](/help/stitching/gbs.md)
   + [Utilisation du groupement](/help/stitching/use-stitching.md)
   + [Créer et gérer des jeux de données groupés](/help/stitching/stitching-ui.md)
   + [Valider le groupement](/help/stitching/validate.md)
   + [Questions fréquentes](/help/stitching/faq.md)

+ Intégrations Adobe {#integrations}
   + [Présentation](/help/integrations/overview.md)
   + [Intégrer Adobe Analytics](/help/integrations/aa.md)
   + [Intégrer Target](/help/integrations/at.md)
   + [Intégrer des données Journey Optimizer](/help/integrations/ajo.md)
   + [Intégrer les données de gestion des décisions](/help/integrations/ajo-od.md)
   + [Intégrer l’IA dédiée aux clientes et clients](/help/integrations/customer-ai.md)

+ Gouvernance des données {#cja-privacy}
   + [Gouvernance des données](../privacy/privacy-overview.md)
   + [Journal d’audit](../privacy/audit-log.md)
   + [Clés gérées par le client](../privacy/cmk.md)

+ Cas d’utilisation {#cja-usecases}
   + [Cas d’utilisation de Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Données Adobe Analytics {#aa-data}
      + [Utiliser les dimensions du canal marketing](../use-cases/aa-data/marketing-channels.md)
      + [Combiner des suites de rapports avec différents schémas](../use-cases/aa-data/combine-report-suites.md)
   + B2B {#b2b}
      + [Exemple de projet B2B basé sur les personnes](../use-cases/b2b/example.md)
      + B2B Edition {#b2b-edition}
         + [Vue d’ensemble des cas d’utilisation](/help/use-cases/b2b/b2b-edition/use-cases-overview.md)
         + [Configuration](/help/use-cases/b2b/b2b-edition/setup.md)
         + [Optimiser le marketing de compte](/help/use-cases/b2b/b2b-edition/optimize-account-marketing.md)
         + [Développer les comptes clés](/help/use-cases/b2b/b2b-edition/grow-key-accounts.md)
         + [Créer la valeur du produit](/help/use-cases/b2b/b2b-edition/build-product-value.md)
   + Données complexes {#complex-data}
      + [Utiliser des tableaux d’objets](../use-cases/object-arrays.md)
   + Données cross-canal {#cross-channel}
      + [Analyse des données sur plusieurs canaux](../use-cases/cross-channel/cross-channel.md)
      + [Importer les données du centre d’appel et web](../use-cases/cross-channel/call-center.md)
   + Export de données {#data-export}
      + [Présentation](../use-cases/data-export/overview.md)
      + [Extension BI](../use-cases/data-export/bi-extension.md)
      + [Exporter les jeux de données](../use-cases/data-export/export-datasets.md)
      + [Exporter le tableau complet](../use-cases/data-export/export-full-table.md)
      + [Jeux de données du service de requête et d’export](../use-cases/data-export/queryservice-export-datasets.md)
   + Ingestion de données {#data-ingestion}
      + [Ingérer et utiliser des données de Marketo Engage](../use-cases/data-ingestion/marketo.md)
      + [Ingérer et utiliser des audiences Experience Platform](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Vues des données {#data-views}
      + [Cas dʼutilisation des vues de données](/help/use-cases/data-views/data-views-usecases.md)
      + [Utiliser des dimensions et des mesures de liaison](/help/use-cases/data-views/binding-dimensions-metrics.md)
      + [Utiliser des données de résumé](/help/use-cases/data-views/summary-data.md)
      + [Cas d’utilisation de l’extension BI](/help/use-cases/data-views/bi-extension-usecases.md)
   + Champs dérivés {#derived-fields}
      + [Créer un rapport sur les objectifs](../use-cases/goals-using-derived-fields.md)
   + Analyse de produit {#product-analysis}
      + [Analyse de produit](/help/use-cases/product-analysis.md)
   + Groupement {#stitching}
      + [Périphériques partagés](/help/use-cases/stitching/shared-devices.md)
   + Données tierces {#third-party}
      + [Présentation](/help/use-cases/third-party/overview.md)
      + Google Analytics {#ga}
         + [Migrer des données à partir de Google Analytics](/help/use-cases/third-party/ga/overview.md)
         + [Ingérer des données historiques de Google Analytics](/help/use-cases/third-party/ga/backfill.md)
         + [Configurer des données de Google Analytics en streaming](/help/use-cases/third-party/ga/streaming.md)
         + [Créer un rapport sur des données de Google Analytics](/help/use-cases/third-party/ga/report.md)
      + Quantum Metric {#qm}
         + [Présentation](/help/use-cases/third-party/quantum-metric/qm-overview.md)
         + [Lier des lectures de session](/help/use-cases/third-party/quantum-metric/tie-session-replays.md)
         + [Utiliser des cartes thermiques](/help/use-cases/third-party/quantum-metric/heatmap.md)
         + [Ajouter des événements de friction](/help/use-cases/third-party/quantum-metric/friction-events.md)
         + [Connecteur source](/help/use-cases/third-party/quantum-metric/source-connector.md)

+ Labs {#labs}
   + [Guide d’utilisation de Labs](../labs/labs.md)

+ Résolution des problèmes {#troubleshooting}
   + [Comparer des données](../troubleshooting/compare.md)
   + [Cohérence des mesures et des audiences](../troubleshooting/consistency-rcdp-cja.md)
   + [Absence d’autorisations](../troubleshooting/lack-of-permissions.md)

+ Notes techniques {#technotes}
   + [Contrôle d’accès](../technotes/access-control.md)
   + [Centres de données](../technotes/data-centers.md)
   + [Conséquences de la suppression](../technotes/deletion.md)
   + [Domaines](../technotes/domains.md)
   + [Glossaire](../technotes/glossary.md)
   + [Mécanismes de sécurisation](../technotes/guardrails.md)
   + [Adresses IP](../technotes/ip-addresses.md)
   + [Optimiser les performances](../technotes/optimizing-performance.md)
   + [Gérer l’utilisation](../technotes/estimate-usage.md)

+ [API Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/?lang=fr)
