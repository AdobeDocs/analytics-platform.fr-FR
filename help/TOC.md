---
git-repo: https://github.com/AdobeDocs/analytics-platform.fr-FR
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Guide de Customer Journey Analytics
user-guide-description: Ce guide fournit une assistance pour Customer Journey Analytics, la solution nouvelle génération d’Adobe pour lʼCross-Channel Analytics, basée sur Adobe Experience Platform.
breadcrumb-title: Guide de Customer Journey Analytics
source-git-commit: fbe6f346d35d5f80fcbc9ed69b3ab4730c0715d6
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 97%

---


# Guide de Customer Journey Analytics {#using}

+ [Guide de Customer Journey Analytics](getting-started/cja-landing.md)
+ Notes de mise à jour {#releases}
   + [Dernière version](release-notes/latest.md)
   + [Versions de 2022](release-notes/2022.md)
   + [Versions de 2021](release-notes/2021.md)
   + [Versions de 2020](release-notes/2020.md)
   + [Versions de CJA](release-notes/releases.md)
   + [Mises à jour de la documentation de CJA](release-notes/doc-changes.md)
+ Présentation de Customer Journey Analytics {#cja-overview}
   + [Présentation de Customer Journey Analytics](getting-started/cja-overview.md)
   + [Prise en main](getting-started/cja-getting-started.md)
   + [Page de destination de Customer Journey Analytics](getting-started/landing.md)
   + [Questions fréquentes](getting-started/cja-faq.md)
   + [Passage d’Adobe Analytics à Customer Journey Analytics](getting-started/aa-to-cja.md)
   + [Guide de l’utilisateur pour les nouveaux utilisateurs de Customer Journey Analytics](getting-started/aa-to-cja-user.md)
   + [Support pour les fonctionnalités Customer Journey Analytics](getting-started/cja-aa.md)
   + [Conséquences de la suppression](getting-started/cja-deletion.md)
   + [Glossaire CJA](getting-started/cja-glossary.md)
+ Connexions {#cja-connections}
   + [Présentation des connexions](connections/overview.md)
   + [Création d’une connexion](connections/create-connection.md)
   + [Gestion des connexions](connections/manage-connections.md)
   + [Jeu de données d’événements combinés](connections/combined-dataset.md)
   + [Recherches standard](connections/standard-lookups.md)
   + Cross-Channel Analytics {#cca}
      + [Présentation de l’Cross-Channel Analytics](connections/cca/overview.md)
      + [Fonctionnement des relectures](connections/cca/replay.md)
      + [FAQ sur l’Cross-Channel Analytics](connections/cca/faq.md)
+ Vues des données {#cja-dataviews}
   + [Présentation des vues de données](data-views/data-views.md)
   + [Création ou modification d’une vue de données](data-views/create-dataview.md)
   + Paramètres de composant {#component-settings}
      + [Présentation des paramètres de composant](data-views/component-settings/overview.md)
      + [Attribution](data-views/component-settings/attribution.md)
      + [Comportement](data-views/component-settings/behavior.md)
      + [Format](data-views/component-settings/format.md)
      + [Inclure/Exclure les valeurs](data-views/component-settings/include-exclude-values.md)
      + [Déduplication des mesures](data-views/component-settings/metric-deduplication.md)
      + [Pas d’option de valeur](data-views/component-settings/no-value-options.md)
      + [Persistance](data-views/component-settings/persistence.md)
      + [Sous-chaîne](data-views/component-settings/substring.md)
      + [Classification des valeurs](data-views/component-settings/value-bucketing.md)
   + [Référence de composant standard](data-views/component-reference.md)
   + [Cas dʼutilisation des vues de données](data-views/data-views-usecases.md)
+ Projets Workspace {#cja-workspace}
   + [Aperçu d’Analysis Workspace](analysis-workspace/home.md)
   + [Exécution d’une analyse de base](analysis-workspace/perform-basic-analysis.md)
   + [Exécuter une analyse avancée](analysis-workspace/perform-adv-analysis.md)
   + Projets {#build-workspace-project}
      + [Présentation des projets](analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Enregistrement des projets](analysis-workspace/build-workspace-project/save-projects.md)
      + [Raccourcis clavier](analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Palettes de couleurs](analysis-workspace/build-workspace-project/color-palettes.md)
      + [Densité d’affichage](analysis-workspace/build-workspace-project/view-density.md)
   + Visualisations {#visualizations}
      + [Visualisations - Aperçu](analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Gestion des sources de données](analysis-workspace/visualizations/t-sync-visualization.md)
      + Tableau à structure libre {#freeform-table}
         + [Tableau à structure libre](analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + Paramètres des colonnes et des lignes {#column-row-settings}
            + [Paramètres des colonnes](analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Paramètres des lignes](analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Éléments dynamiques ou statiques](analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Pagination, filtrage et tri des tables](analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.md)
         + [Totaux de l’espace de travail](analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Tableau de cohortes {#cohort-table}
         + [Qu’est-ce que l’analyse des cohortes ?](analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configuration d’un rapport d’analyse des cohortes](analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Cas d’utilisation de l’analyse des cohortes](analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Abandon {#fallout}
         + [Abandon - Aperçu](analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configuration d’une visualisation Abandons](analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Abandons interdimensionnels](analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Application de filtres dans l’analyse des abandons](analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flux {#flow}
         + [Flux - Aperçu](analysis-workspace/visualizations/c-flow/flow.md)
         + [Configuration d’une visualisation de flux](analysis-workspace/visualizations/c-flow/creating-flow-report.md)
         + [Paramètres de flux](analysis-workspace/visualizations/c-flow/flow-settings.md)
         + [Flux interdimensionnels](analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [Histogramme](analysis-workspace/visualizations/histogram.md)
      + [Venn](analysis-workspace/visualizations/venn.md)
      + [Surface et aires empilées](analysis-workspace/visualizations/area.md)
      + [Barres et barres empilées](analysis-workspace/visualizations/bar.md)
      + [Graphique à puces](analysis-workspace/visualizations/bullet-graph.md)
      + [Anneau](analysis-workspace/visualizations/donut.md)
      + [Barres horizontales et barres empilées horizontales](analysis-workspace/visualizations/horizontal-bar.md)
      + [Ligne](analysis-workspace/visualizations/line.md)
      + [Graphique de dispersion](analysis-workspace/visualizations/scatterplot.md)
      + [Synthèse des chiffres et synthèse des changements](analysis-workspace/visualizations/summary-number-change.md)
      + [Text](analysis-workspace/visualizations/text.md)
      + [Arborescence](analysis-workspace/visualizations/treemap.md)
   + Panneaux {#panels}
      + [Panneaux - Aperçu](analysis-workspace/c-panels/panels.md)
      + [Panneau d’attribution](analysis-workspace/c-panels/attribution.md)
      + [Panneau vierge](analysis-workspace/c-panels/blank-panel.md)
      + [Panneau à structure libre](analysis-workspace/c-panels/freeform-panel.md)
      + [Panneau Quick Insights](analysis-workspace/c-panels/quickinsight.md)
   + Traitement, partage et planification de projets {#curate-share}
      + [Menu Partager](analysis-workspace/curate-share/send-schedule-files.md)
      + [Traitement des projets](analysis-workspace/curate-share/curate.md)
      + [Partage de projets](analysis-workspace/curate-share/share-projects.md)
      + [Création de liens partageables](analysis-workspace/curate-share/shareable-links.md)
      + [Projets en lecture seule](analysis-workspace/curate-share/view-only-projects.md)
      + [Téléchargement de fichiers PDF ou CSV](analysis-workspace/curate-share/download-send.md)
      + [Planification de projets](analysis-workspace/curate-share/t-schedule-report.md)
   + Attribution IQ {#attribution}
      + [Présentation d’Attribution](analysis-workspace/attribution/overview.md)
      + [Modèles d’attribution et intervalles de recherche en amont](analysis-workspace/attribution/models.md)
      + [Attribution algorithmique](analysis-workspace/attribution/algorithmic.md)
      + [Bonnes pratiques en matière dʼattribution](analysis-workspace/attribution/best-practices.md)
      + [FAQ](analysis-workspace/attribution/faq.md)
   + Analyste virtuel {#virtual-analyst}
      + [Présentation de Virtual Analyst](analysis-workspace/virtual-analyst/overview.md)
      + Détection des anomalies {#anomaly-detection}
         + [Détection des anomalies - Aperçu](analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Affichage des anomalies dans Analysis Workspace](analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [Techniques statistiques de la détection des anomalies](analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [Préférences de l’utilisateur](analysis-workspace/user-preferences.md)
   + FAQ sur l’espace de travail {#workspace-faq}
      + [Questions fréquentes](analysis-workspace/workspace-faq/faq.md)
      + [Optimisation des performances d’Analysis Workspace](analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Messages d’erreur](analysis-workspace/workspace-faq/error-messages.md)
      + [Limites d’Analysis Workspace](analysis-workspace/workspace-faq/aw-limitations.md)
      + [Configuration requise pour l’administration](analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Accessibilité dans Analysis Workspace](analysis-workspace/workspace-faq/aw-accessibility.md)
      + [« Long-tail » dans Analysis Workspace](analysis-workspace/workspace-faq/long-tail.md)
+ Report Builder {#cja-reportbuilder}
   + [Présentation de Report Builder](report-builder/report-buider-overview.md)
   + [Configuration de Report Builder](report-builder/report-builder-setup.md)
   + [Création dʼun bloc de données](report-builder/create-a-data-block.md)
   + [Centre Report Builder](report-builder/report-builder-hub.md)
   + [Sélection dʼune période](report-builder/select-date-range.md)
   + [Utilisation des filtres](report-builder/work-with-filters.md)
   + [Filtrage des dimensions](report-builder/filter-dimensions.md)
   + [Gestion des blocs de données](report-builder/manage-reportbuilder.md)
   + [Paramètres de Report Builder](report-builder/report-builder-settings.md)
+ Composants {#cja-components}
   + [Présentation des composants](components/overview.md)
   + Annotations {#annotations}
      + [Aperçu des annotations](components/annotations/overview.md)
      + [Création d’annotations](components/annotations/create-annotations.md)
      + [Gestion des annotations](components/annotations/manage-annotations.md)
      + [Affichage des annotations](components/annotations/view-annotations.md)
   + Audiences {#audiences}
      + [Présentation des audiences](components/audiences/audiences-overview.md)
      + [Création et publication d’audiences](components/audiences/publish.md)
      + [Gestion des audiences](components/audiences/manage.md)
   + Dimensions {#dimensions}
      + [Aperçu des dimensions](components/dimensions/view-dimensions.md)
      + [Ventilation des dimensions](components/dimensions/t-breakdown-fa.md)
      + [Dimensions de répartition du temps](components/dimensions/time-parting-dimensions.md)
      + [Dimensions à cardinalité très élevée](components/dimensions/high-cardinality.md)
   + [Mesures](components/apply-create-metrics.md)
   + Filtres {#cja-filters}
      + [Présentation des filtres](components/filters/filters-overview.md)
      + [Création d’un filtre](components/filters/create-filters.md)
      + [Gestion des filtres](components/filters/manage-filters.md)
      + [Filtres rapides](components/filters/quick-filters.md)
      + [Filtres ad hoc](components/filters/ad-hoc-filters.md)
      + [Opérateurs](components/filters/operators.md)
   + Mesures calculées {#cja-calcmetrics}
      + [Présentation des mesures calculées](components/calc-metrics/calc-metr-overview.md)
      + Workflow des mesures calculées {#cm-workflow}
         + [Workflow des mesures calculées](components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Recherche de mesures](components/calc-metrics/cm-workflow/cm-finding.md)
         + [Création de mesures](components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Type de mesure et attribution](components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Création d’une mesure simple « Pages vues par visite »](components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Mesures filtrées](components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Empilage et remplacement des segments](components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Mesures filtrées et pondérées](components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Utilisation des fonctions](components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Mesure de participation](components/calc-metrics/cm-workflow/participation-metric.md)
         + [Balisage des mesures calculées](components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Approbation des mesures calculées](components/calc-metrics/cm-workflow/cm-approving.md)
         + [Partage des mesures calculées](components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Gestionnaire de mesures calculées](components/calc-metrics/cm-workflow/cm-manager.md)
      + [Fonctions de base](components/calc-metrics/cm-functions.md)
      + [Fonctions avancées](components/calc-metrics/cm-adv-functions.md)
   + Périodes {#cja-date-ranges}
      + [Présentation des périodes](components/date-ranges/overview.md)
      + [Création d’une plage de dates](components/date-ranges/create.md)
      + [Gestion des périodes](components/date-ranges/manage.md)
      + [Aperçu du calendrier](components/date-ranges/calendar.md)
      + [Création de périodes personnalisées](components/date-ranges/custom-date-ranges.md)
      + [Comparaison des dates](components/date-ranges/time-comparison.md)
+ Tableaux de bord Analytics {#cja-dashboards}
   + [Tableaux de bord Analytics - Aperçu](mobile-app/home.md)
   + [Tâches du curateur](mobile-app/curator.md)
   + [Création dʼune carte de performance](mobile-app/create-scorecard.md)
   + [Préparation des utilisateurs en charge de lʼexécution à lʼutilisation des tableaux de bord](mobile-app/set-up-execs.md)
   + [Guide pour une prise en main rapide destiné aux utilisateurs en charge de l’exécution](mobile-app/executive.md)
+ Cas d’utilisation {#cja-usecases}
   + [Cas d’utilisation de Customer Journey Analytics](use-cases/cja-usecases.md)
   + [Utilisation de tableaux d’objets](use-cases/object-arrays.md)
   + [Utilisation de dimensions et de mesures de liaison](use-cases/binding-dimensions-metrics.md)
   + [(B2B) Ajout de données au niveau du compte en tant que jeu de données de recherche](use-cases/b2b.md)
   + [Ingestion de données Marketo Engage dans AEP et création de rapports dans CJA](use-cases/marketo.md)
   + [Ingestion d’audiences AEP dans CJA](use-cases/ingest-aep-segments.md)
   + [Analyse des données sur plusieurs canaux](use-cases/cross-channel.md)
   + [Importer les données du centre d’appel et web](use-cases/call-center.md)
   + [Cas d’utilisation d’ingestion de données](use-cases/data-ingestion.md)
   + [Utiliser les dimensions du canal marketing](use-cases/marketing-channels.md)
   + [Ingestion de données Google Analytics dans Adobe Experience Platform](use-cases/ga-to-cja.md)
   + [Rapport sur les données Google Analytics dans CJA](use-cases/ga-to-cja-reporting.md)
+ Labs {#labs}
   + [Guide d’utilisation de Labs](labs/labs.md)
+ Résolution des problèmes {#troubleshooting}
   + [Comparaison de vos données Adobe Analytics aux données CJA](troubleshooting/compare.md)
+ Confidentialité {#cja-privacy}
   + [Présentation de la confidentialité](privacy/privacy-overview.md)
