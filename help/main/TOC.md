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
source-git-commit: ad57fcbb8ff7d4a80a5e1f151c1df327af55b304
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 81%

---


# Guide Adobe Customer Journey Analytics {#using}

+ [Guide Adobe Customer Journey Analytics](../getting-started/cja-landing.md)

+ Notes de mise à jour {#releases}
   + [Dernière version](../release-notes/latest.md)
   + [Versions de 2023](../release-notes/2023.md)
   + [Versions de 2022](../release-notes/2022.md)
   + [Versions de 2021](../release-notes/2021.md)
   + [Versions de 2020](../release-notes/2020.md)
   + [Versions Customer Journey Analytics](../release-notes/releases.md)
   + [Mises à jour de la documentation de Customer Journey Analytics](../release-notes/doc-changes.md)

+ Prise en main {#cja-overview}
   + [Présentation de Customer Journey Analytics](../getting-started/cja-overview.md)
   + [Guide de démarrage rapide](../getting-started/cja-getting-started.md)
   + [Page de destination](../getting-started/landing.md)
   + [Questions fréquentes](../getting-started/cja-faq.md)
   + [Comparer Customer Journey Analytics aux solutions BI](../getting-started/cja-vs-bi.md)

+ Comparaison entre Customer Journey Analytics et Adobe Analytics {#compare-aa-cja}
   + [Évolution à partir d’Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Guide de l’utilisateur pour les utilisateurs et utilisatrices d’Adobe Analytics](../getting-started/aa-to-cja-user.md)
   + Comparaison à Adobe Analytics {#cja-aa-comparison}
      + [Vue d’ensemble](../getting-started/aa-vs-cja/overview.md)
      + [Utiliser les données Adobe Analytics dans Customer Journey Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Prise en charge des fonctionnalités de Customer Journey Analytics](../getting-started/aa-vs-cja/cja-aa.md)
      + [Comparer la terminologie des données d’Analytics transmises par le biais du connecteur source Analytics](../getting-started/aa-vs-cja/terminology.md)
      + [Comparer le traitement des données dans Adobe Analytics et Customer Journey Analytics](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Environnements de création de rapports virtuels et environnements sandbox](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Règles de traitement, VISTA et classifications par rapport à la préparation des données](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID, ECID, AACUSTOMID et le connecteur source Analytics](../getting-started/aa-vs-cja/aaid-ecid-adc.md)

+ Ingestion des données {#cja-data-ingestion}
   + [Présentation de l’ingestion des données](../data-ingestion/data-ingestion.md)
   + Guides de démarrage rapide d’ingestion et d’utilisation{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Réseau EDGE d²Adobe Experience Platform {#edge-network}
         + [SDK Web](../data-ingestion/aepwebsdk.md)
         + [SDK Mobile](../data-ingestion/aepmobilesdk.md)
         + [API du serveur](../data-ingestion/serverapi.md)
      + [Données par lot](../data-ingestion/batch.md)
      + [Données de flux](../data-ingestion/streaming.md)
      + [Connecteurs source](../data-ingestion/sources.md)

+ Connexions {#cja-connections}
   + [Présentation des connexions](../connections/overview.md)
   + [Création d’une connexion](../connections/create-connection.md)
   + [Gestion des connexions](../connections/manage-connections.md)
   + [Jeu de données d’événements combinés](../connections/combined-dataset.md)
   + [Recherches standard](../connections/standard-lookups.md)
   + [Analytique cross-canal](../connections/cca.md)

+ Vues des données {#cja-dataviews}
   + [Présentation des vues de données](../data-views/data-views.md)
   + [Création ou modification d’une vue de données](../data-views/create-dataview.md)
   + [Paramètres de session](../data-views/session-settings.md)
   + Paramètres de composant {#component-settings}
      + [Présentation des paramètres de composant](../data-views/component-settings/overview.md)
      + [Attribution](../data-views/component-settings/attribution.md)
      + [Comportement](../data-views/component-settings/behavior.md)
      + [Format](../data-views/component-settings/format.md)
      + [Inclure/Exclure les valeurs](../data-views/component-settings/include-exclude-values.md)
      + [Déduplication des mesures](../data-views/component-settings/metric-deduplication.md)
      + [Pas d’option de valeur](../data-views/component-settings/no-value-options.md)
      + [Persistance](../data-views/component-settings/persistence.md)
      + [Sous-chaîne](../data-views/component-settings/substring.md)
      + [Classification des valeurs](../data-views/component-settings/value-bucketing.md)
   + [Référence de composant standard](../data-views/component-reference.md)
   + [Connecteur SQL](../data-views/sql-connector.md)
   + [Champs dérivés](../data-views/derived-fields/derived-fields.md)
   + [Étiquettes et politiques](../data-views/data-governance.md)

+ Projets Workspace {#cja-workspace}
   + [Aperçu d’Analysis Workspace](../analysis-workspace/home.md)
   + [Exécution d’une analyse de base](../analysis-workspace/perform-basic-analysis.md)
   + [Exécuter une analyse avancée](../analysis-workspace/perform-adv-analysis.md)
   + Projets {#build-workspace-project}
      + [Présentation des projets](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Création de projets](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Enregistrement des projets](../analysis-workspace/build-workspace-project/save-projects.md)
      + Dossiers dans Espace de travail {#workspace-folders}
         + [À propos des dossiers dans Workspace](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Créer des dossiers et sous-dossiers](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Supprimer des dossiers](../analysis-workspace/build-workspace-project/workspace-folders/delete-folders.md)
         + [Ajouter des projets](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
         + [Supprimer un projet](../analysis-workspace/build-workspace-project/workspace-folders/remove-projects.md)
         + [Enregistrer un nouveau projet](../analysis-workspace/build-workspace-project/workspace-folders/save-new-project-folder.md)
      + [Raccourcis clavier](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Palettes de couleurs](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Densité d’affichage](../analysis-workspace/build-workspace-project/view-density.md)
   + Visualisations {#visualizations}
      + [Visualisations - Aperçu](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Gestion des sources de données](../analysis-workspace/visualizations/t-sync-visualization.md)
      + Tableau à structure libre {#freeform-table}
         + [Tableau à structure libre](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + Paramètres des colonnes et des lignes {#column-row-settings}
            + [Paramètres des colonnes](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Paramètres des lignes](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Éléments dynamiques ou statiques](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtrer et trier des tableaux](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Totaux de l’espace de travail](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Tableau de cohortes {#cohort-table}
         + [Qu’est-ce que l’analyse des cohortes ?](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configuration d’un rapport d’analyse des cohortes](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Cas d’utilisation de l’analyse des cohortes](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Abandon {#fallout}
         + [Abandon - Aperçu](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configuration d’une visualisation Abandons](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Abandons interdimensionnels](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Application de filtres dans l’analyse des abandons](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flux {#flow}
         + [Flux - Aperçu](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Configuration d’une visualisation de flux](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Flux interdimensionnels](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [Surface et aires empilées](../analysis-workspace/visualizations/area.md)
      + [Barres et barres empilées](../analysis-workspace/visualizations/bar.md)
      + [Graphique à puces](../analysis-workspace/visualizations/bullet-graph.md)
      + [Graphique combo](../analysis-workspace/visualizations/combo-charts.md)
      + [Anneau](../analysis-workspace/visualizations/donut.md)
      + [Histogramme](../analysis-workspace/visualizations/histogram.md)
      + [Barres horizontales et barres empilées horizontales](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Légendes intelligentes](../analysis-workspace/visualizations/intelligent-captions.md)
      + [Résumé des mesures clés](../analysis-workspace/visualizations/key-metric.md)
      + [Ligne](../analysis-workspace/visualizations/line.md)
      + [Graphique de dispersion](../analysis-workspace/visualizations/scatterplot.md)
      + [Synthèse des chiffres et synthèse des changements](../analysis-workspace/visualizations/summary-number-change.md)
      + [Text](../analysis-workspace/visualizations/text.md)
      + [Arborescence](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Panneaux {#panels}
      + [Panneaux - Aperçu](../analysis-workspace/c-panels/panels.md)
      + [Panneau d’attribution](../analysis-workspace/c-panels/attribution.md)
      + [Panneau vierge](../analysis-workspace/c-panels/blank-panel.md)
      + [Panneau Expérimentation](../analysis-workspace/c-panels/experimentation.md)
      + [Panneau à structure libre](../analysis-workspace/c-panels/freeform-panel.md)
      + [Panneau Quick Insights](../analysis-workspace/c-panels/quickinsight.md)
      + [Panneau Observateurs simultanés de médias](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Panneau Durée de lecture des médias](../analysis-workspace/c-panels/media-playback-time-spent.md)
   + Traitement, partage et planification de projets {#curate-share}
      + [Menu Partager](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Traitement des projets](../analysis-workspace/curate-share/curate.md)
      + [Partage de projets](../analysis-workspace/curate-share/share-projects.md)
      + [Création de liens partageables](../analysis-workspace/curate-share/shareable-links.md)
      + [Projets en lecture seule](../analysis-workspace/curate-share/view-only-projects.md)
   + Exporter {#export}
      + [Présentation de l’exportation](../analysis-workspace/export/export-project-overview.md)
      + [Télécharger](../analysis-workspace/export/download-send.md)
      + [Envoyer aux autres](../analysis-workspace/export/t-schedule-report.md)
      + [Exporter vers le cloud](../analysis-workspace/export/export-cloud.md)
   + Analyste virtuel {#virtual-analyst}
      + [Présentation de Virtual Analyst](../analysis-workspace/virtual-analyst/overview.md)
      + Détection des anomalies {#anomaly-detection}
         + [Détection des anomalies - Aperçu](../analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Affichage des anomalies dans Analysis Workspace](../analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [Techniques statistiques de la détection des anomalies](../analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [Préférences utilisateur](../analysis-workspace/user-preferences.md)
   + FAQ sur Workspace {#workspace-faq}
      + [Questions fréquentes](../analysis-workspace/workspace-faq/faq.md)
      + [Messages d’erreur](../analysis-workspace/workspace-faq/error-messages.md)
      + [Limites d’Analysis Workspace](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Configuration requise pour l’administration](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Accessibilité dans Analysis Workspace](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Tableaux de bord Analytics {#cja-dashboards}
   + [Tableaux de bord Analytics - Aperçu](../mobile-app/home.md)
   + [Tâches du curateur](../mobile-app/curator.md)
   + [Création dʼune carte de performance mobile](../mobile-app/create-scorecard.md)
   + [Préparation des utilisateurs en charge de lʼexécution à lʼutilisation des tableaux de bord](../mobile-app/set-up-execs.md)
   + [Guide pour une prise en main rapide destiné aux utilisateurs en charge de l’exécution](../mobile-app/executive.md)

+ Analyse guidée {#guided-analysis}
   + [Vue d’ensemble](../guided-analysis/overview.md)
   + Impact {#impact}
      + [Version](../guided-analysis/types/release.md)
      + [Première utilisation vue](../guided-analysis/types/first-use.md)
   + Entonnoir {#funnel}
      + [Vue Friction](../guided-analysis/types/friction.md)
      + [Affichage des tendances de conversion](../guided-analysis/types/conversion-trends.md)
   + Croissance des utilisateurs et des utilisatrices {#user-growth}
      + [Vue active](../guided-analysis/types/active.md)
      + [Vue de la croissance nette](../guided-analysis/types/net-growth.md)
   + Tendances {#trends}
      + [Affichage de l’utilisation](../guided-analysis/types/usage.md)
      + [Mode Fréquence](../guided-analysis/types/frequency.md)
   + [Cas pratiques du secteur](../guided-analysis/industry-use-cases.md)
   + [FAQ](../guided-analysis/faq.md)

+ Composants {#cja-components}
   + [Présentation des composants](../components/overview.md)
   + [Ajouter des descriptions des composants](../components/add-component-descriptions.md)
   + Annotations {#annotations}
      + [Aperçu des annotations](../components/annotations/overview.md)
      + [Création d’annotations](../components/annotations/create-annotations.md)
      + [Gestion des annotations](../components/annotations/manage-annotations.md)
      + [Affichage des annotations](../components/annotations/view-annotations.md)
      + [Annotations mobiles](../components/annotations/mobile-annotations.md)
   + [Projet planifié](../components/scheduled-projects-manager.md)
   + Audiences {#audiences}
      + [Présentation des audiences](../components/audiences/audiences-overview.md)
      + [Créer et publier des audiences](../components/audiences/publish.md)
      + [Gérer des audiences](../components/audiences/manage.md)
   + Dimensions {#dimensions}
      + [Aperçu des dimensions](../components/dimensions/view-dimensions.md)
      + [Ventilation des dimensions](../components/dimensions/t-breakdown-fa.md)
      + [Dimensions de répartition du temps](../components/dimensions/time-parting-dimensions.md)
      + [Dimensions à cardinalité très élevée](../components/dimensions/high-cardinality.md)
   + [Mesures](../components/apply-create-metrics.md)
   + Filtres {#cja-filters}
      + [Présentation des filtres](../components/filters/filters-overview.md)
      + [Création de filtres](../components/filters/create-filters.md)
      + [Partage de filtres](../components/filters/filters-share.md)
      + [Balisage de filtres](../components/filters/filters-tag.md)
      + [Filtrer la liste des filtres](../components/filters/filters-filter.md)
      + [Marquage de filtres comme favoris](../components/filters/filters-favorite.md)
      + [Approbation de filtres](../components/filters/filters-approve.md)
      + [Copie de filtres](../components/filters/filters-copy.md)
      + [Filtres rapides](../components/filters/quick-filters.md)
      + [Créateur de filtres](../components/filters/filter-builder.md)
      + [Gestion des filtres](../components/filters/manage-filters.md)
      + [Opérateurs](../components/filters/operators.md)
   + Mesures calculées {#cja-calcmetrics}
      + [Vue d’ensemble des mesures calculées](../components/calc-metrics/calc-metr-overview.md)
      + Workflow des mesures calculées {#cm-workflow}
         + [Workflow des mesures calculées](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Recherche de mesures](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Création de mesures](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Type de mesure et attribution](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Création d’une mesure de participation](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Mesures filtrées](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Empilage et remplacement des filtres](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Mesures filtrées et pondérées](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Filtrage des mesures calculées](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Marquage des mesures calculées comme favoris](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [Copie de mesures calculées](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [Utilisation des fonctions](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Balisage des mesures calculées](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Approbation des mesures calculées](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Partage des mesures calculées](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Gestionnaire de mesures calculées](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [Mesures calculées par défaut](../components/calc-metrics/default-calcmetrics.md)
      + [Fonctions de base](../components/calc-metrics/cm-functions.md)
      + [Fonctions avancées](../components/calc-metrics/cm-adv-functions.md)
   + Calendrier et périodes {#cja-date-ranges}
      + [Calendrier et périodes - Aperçu](../components/date-ranges/calendar.md)
      + [Création d’une plage de dates](../components/date-ranges/create.md)
      + [Gestion des périodes](../components/date-ranges/manage.md)
      + [Création de périodes personnalisées](../components/date-ranges/custom-date-ranges.md)
      + [Comparaison des dates](../components/date-ranges/time-comparison.md)
   + Exports {#exports}
      + [Configuration des comptes d’exportation cloud](/help/components/exports/cloud-export-accounts.md)
      + [Configuration des emplacements d’exportation cloud](/help/components/exports/cloud-export-locations.md)
      + [Gestion des emplacements d’exportation dans le cloud](/help/components/exports/manage-export-locations.md)
      + [Gestion des exportations](/help/components/exports/manage-exports.md)
      + [Gestion des logs d’exportation](/help/components/exports/manage-export-logs.md)
      + [Résolution des problèmes d’exportation](/help/components/exports/troubleshoot-exports.md)
   + Dictionnaire de données {#data-dictionary}
      + [Présentation du dictionnaire de données](../components/data-dictionary/data-dictionary-overview.md)
      + [Afficher des informations sur les composants dans le dictionnaire de données](../components/data-dictionary/view-data-dictionary.md)
      + [Modifier les entrées de composant dans le dictionnaire de données](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Surveiller l’intégrité du dictionnaire de données](../components/data-dictionary/monitor-data-dictionary-health.md)

+ Report Builder {#cja-reportbuilder}
   + [Présentation de Report Builder](../report-builder/report-buider-overview.md)
   + [Configuration de Report Builder](../report-builder/report-builder-setup.md)
   + [Création dʼun bloc de données](../report-builder/create-a-data-block.md)
   + [Centre Report Builder](../report-builder/report-builder-hub.md)
   + [Sélection d’une vue de données](../report-builder/select-data-view.md)
   + [Sélection dʼune période](../report-builder/select-date-range.md)
   + [Utilisation des filtres](../report-builder/work-with-filters.md)
   + [Filtrage des dimensions](../report-builder/filter-dimensions.md)
   + [Gestion des blocs de données](../report-builder/manage-reportbuilder.md)
   + [Planification de classeurs](../report-builder/schedule-reportbuilder.md)
   + [Étiquettes restreintes](../report-builder/restricted-labels.md)
   + [Paramètres de Report Builder](../report-builder/report-builder-settings.md)

+ Gestionnaire des activités de rapport {#reporting-activity-manager}
   + [Vue d’ensemble](../reporting-activity-manager/reporting-activity-overview.md)
   + [Afficher l’activité de rapport](../reporting-activity-manager/reporting-activity.md)
   + [Annuler des demandes de création de rapports](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Assemblage {#stitching}
   + [Vue d’ensemble](../stitching/overview.md)
   + [Fonctionnement de l’assemblage](../stitching/explained.md)
   + [Création et gestion de jeux de données assemblés](../stitching/stitching-ui.md)
   + [Questions fréquentes](../stitching/faq.md)

+ Analytique cross-canal {#cca}
   + [Présentation de l’analytique cross-canal](../cca/overview.md)
   + [Fonctionnement des relectures](../cca/replay.md)
   + [FAQ sur l’analytique cross-canal](../cca/faq.md)

+ Intégrations Adobe {#integrations}
   + [Présentation de l’intégration des solutions Adobe avec Customer Journey Analytics](/help/integrations/overview.md)
   + [Intégrer Adobe Analytics à Customer Journey Analytics](/help/integrations/aa.md)
   + [Intégration des données Journey Optimizer à Customer Journey Analytics](/help/integrations/ajo.md)
   + [Intégration des données de gestion de la décision à Customer Journey Analytics](/help/integrations/ajo-od.md)
   + [Intégration de Customer AI à Customer Journey Analytics](/help/integrations/customer-ai.md)

+ Gouvernance des données {#cja-privacy}
   + [Gouvernance des données](../privacy/privacy-overview.md)
   + [Journal d’audit](../privacy/audit-log.md)
   + [Clés gérées par le client](../privacy/cmk.md)

+ Cas d’utilisation {#cja-usecases}
   + [Cas d’utilisation de Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Données de Google Analytics {#ga}
      + [Présentation de la migration des données des Google Analytics vers les Customer Journey Analytics](../use-cases/ga/overview.md)
      + [Ingérer des données Google Analytics dans Platform](../use-cases/ga/backfill.md)
      + [Configuration des données de Google Analytics en flux continu dans Platform](../use-cases/ga/streaming.md)
      + [Rapport sur les données Google Analytics dans Customer Journey Analytics](../use-cases/ga/report.md)
   + Ingestion de données {#data-ingestion}
      + [Ingestion de données de Marketo Engage dans Adobe Experience Platform et création de rapports dans Customer Journey Analytics](../use-cases/data-ingestion/marketo.md)
      + [Ingestion d’audiences Adobe Experience Platform dans Customer Journey Analytics](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Vues de données {#data-views}
      + [Cas dʼutilisation des vues de données](../use-cases/data-views/data-views-usecases.md)
      + [Utiliser des dimensions et des mesures de liaison](../use-cases/data-views/binding-dimensions-metrics.md)
   + B2B {#b2b}
      + [Exemple de projet B2B](../use-cases/b2b/example.md)
      + [Ajouter des données au niveau du compte en tant que jeu de données de recherche](../use-cases/b2b/b2b.md)
   + Données cross-canal {#cross-channel}
      + [Analyse des données sur plusieurs canaux](../use-cases/cross-channel/cross-channel.md)
      + [Importer les données du centre d’appel et web](../use-cases/cross-channel/call-center.md)
   + Données Adobe Analytics {#aa-data}
      + [Utiliser les dimensions du canal marketing](../use-cases/aa-data/marketing-channels.md)
      + [Combiner des suites de rapports avec différents schémas](../use-cases/aa-data/combine-report-suites.md)
   + Données complexes {#complex-data}
      + [Utiliser des tableaux d’objets](../use-cases/object-arrays.md)

+ Administration {#cja-admin}
   + [Contrôle d’accès](../admin/cja-access-control.md)
   + [Afficher et gérer l’utilisation](../admin/estimate-usage.md)
   + [Conséquences de la suppression](../admin/cja-deletion.md)
   + [Optimisation des performances du Customer Journey Analytics](../admin/optimizing-performance.md)
   + [Adresses IP](../admin/ip-addresses.md)

+ Labs {#labs}
   + [Guide d’utilisation de Labs](../labs/labs.md)

+ Résolution des problèmes {#troubleshooting}
   + [Comparer vos données Adobe Analytics avec les données Customer Journey Analytics](../troubleshooting/compare.md)
   + [Cohérence des mesures et du nombre d’adhésions à l’audience entre la plateforme des données clients en temps réel et le Customer Journey Analytics](../troubleshooting/consistency-rcdp-cja.md)
   + [Absence d’autorisations](../troubleshooting/lack-of-permissions.md)

+ [Glossaire de Customer Journey Analytics](../getting-started/cja-glossary.md)

+ [API Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/)
