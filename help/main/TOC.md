---
git-repo: https://github.com/AdobeDocs/analytics-platform.fr-FR
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Guide de Customer Journey Analytics
user-guide-description: Découvrez Customer Journey Analytics (CJA) et comment utiliser Analysis Workspace avec des données d’Experience Platform.
breadcrumb-title: Guide de Customer Journey Analytics
source-git-commit: 7e6383bf94e10f6ab6f9db990f4ef3df0fb826d3
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 97%

---


# Guide de Customer Journey Analytics {#using}

+ [Guide de Customer Journey Analytics](../getting-started/cja-landing.md)

+ Notes de mise à jour {#releases}
   + [Dernière version](../release-notes/latest.md)
   + [Versions de 2023](../release-notes/2023.md)
   + [Versions de 2022](../release-notes/2022.md)
   + [Versions de 2021](../release-notes/2021.md)
   + [Versions de 2020](../release-notes/2020.md)
   + [Versions de CJA](../release-notes/releases.md)
   + [Mises à jour de la documentation de CJA](../release-notes/doc-changes.md)

+ Prise en main {#cja-overview}
   + [Présentation de Customer Journey Analytics](../getting-started/cja-overview.md)
   + [Guide de démarrage rapide](../getting-started/cja-getting-started.md)
   + [Page de destination](../getting-started/landing.md)
   + [Questions fréquentes](../getting-started/cja-faq.md)
   + [Comparer CJA aux solutions BI](../getting-started/cja-vs-bi.md)

+ Comparaison entre Customer Journey Analytics et Adobe Analytics {#compare-aa-cja}
   + [Évolution à partir d’Adobe Analytics ](../getting-started/aa-to-cja.md)
   + [Guide de l’utilisateur pour les utilisateurs et utilisatrices d’Adobe Analytics](../getting-started/aa-to-cja-user.md)
   + Comparaison à Adobe Analytics {#cja-aa-comparison}
      + [Utiliser les données Adobe Analytics dans Customer Journey Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Prise en charge des fonctionnalités de Customer Journey Analytics](../getting-started/aa-vs-cja/cja-aa.md)
      + [Comparez la terminologie des données d’Analytics transmises par le biais du connecteur source Analytics.](../getting-started/aa-vs-cja/terminology.md)
      + [Comparaison du traitement des données dans Adobe Analytics et CJA](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Environnements de création de rapports virtuels et environnements sandbox](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Règles de traitement, VISTA et classifications par rapport à la préparation des données](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID, ECID, AACUSTOMID et le connecteur source Analytics](../getting-started/aa-vs-cja/aaid-ecid-adc.md)

+ Ingestion des données {#cja-data-ingestion}
   + [Présentation de l’ingestion des données](../data-ingestion/data-ingestion.md)
   + Guides de démarrage rapide d’ingestion et d’utilisation {#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + [SDK Web Adobe Experience Platform et réseau Edge](../data-ingestion/aepwebsdk.md)
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
      + Durée de lecture des médias {#media-playback-timespent}
         + [Aperçu](../analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [Paramètres d’entrée et de sortie](../analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [Questions fréquentes](../analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + Traitement, partage et planification de projets {#curate-share}
      + [Menu Partager](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Traitement des projets](../analysis-workspace/curate-share/curate.md)
      + [Partage de projets](../analysis-workspace/curate-share/share-projects.md)
      + [Création de liens partageables](../analysis-workspace/curate-share/shareable-links.md)
      + [Projets en lecture seule](../analysis-workspace/curate-share/view-only-projects.md)
      + [Téléchargement de fichiers PDF ou CSV](../analysis-workspace/curate-share/download-send.md)
      + [Planification de projets](../analysis-workspace/curate-share/t-schedule-report.md)
   + Analyste virtuel {#virtual-analyst}
      + [Présentation de Virtual Analyst](../analysis-workspace/virtual-analyst/overview.md)
      + Détection des anomalies {#anomaly-detection}
         + [Détection des anomalies - Aperçu](../analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Affichage des anomalies dans Analysis Workspace](../analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [Techniques statistiques de la détection des anomalies](../analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [Préférences utilisateur](../analysis-workspace/user-preferences.md)

   + FAQ sur Workspace {#workspace-faq}
      + [Questions fréquentes](../analysis-workspace/workspace-faq/faq.md)
      + [Optimisation des performances d’Analysis Workspace](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Messages d’erreur](../analysis-workspace/workspace-faq/error-messages.md)
      + [Limites d’Analysis Workspace](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Configuration requise pour l’administration](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Accessibilité dans Analysis Workspace](../analysis-workspace/workspace-faq/aw-accessibility.md)
      + [« Long-tail » dans Analysis Workspace](../analysis-workspace/workspace-faq/long-tail.md)











+ Composants {#cja-components}
   + [Présentation des composants](../components/overview.md)
   + [Ajouter des descriptions des composants](../components/add-component-descriptions.md)
   + Annotations {#annotations}
      + [Aperçu des annotations](../components/annotations/overview.md)
      + [Création d’annotations](../components/annotations/create-annotations.md)
      + [Gestion des annotations](../components/annotations/manage-annotations.md)
      + [Affichage des annotations](../components/annotations/view-annotations.md)
      + [Annotations mobiles](../components/annotations/mobile-annotations.md)
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
      + [Filtres rapides](../components/filters/quick-filters.md)
      + [Créateur de filtres](../components/filters/filter-builder.md)
      + [Gestion des filtres](../components/filters/manage-filters.md)
      + [Opérateurs](../components/filters/operators.md)
   + Mesures calculées {#cja-calcmetrics}
      + [Présentation des mesures calculées](../components/calc-metrics/calc-metr-overview.md)
      + Workflow des mesures calculées {#cm-workflow}
         + [Workflow des mesures calculées](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Recherche de mesures](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Création de mesures](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Type de mesure et attribution](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Création d’une mesure simple « Pages vues par visite »](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Mesures filtrées](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Empilage et remplacement des segments](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Mesures filtrées et pondérées](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Utilisation des fonctions](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Mesure de participation](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Balisage des mesures calculées](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Approbation des mesures calculées](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Partage des mesures calculées](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Gestionnaire de mesures calculées](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [Mesures calculées par défaut](../components/calc-metrics/default-calcmetrics.md)
      + [Fonctions de base](../components/calc-metrics/cm-functions.md)
      + [Fonctions avancées](../components/calc-metrics/cm-adv-functions.md)
   + Périodes {#cja-date-ranges}
      + [Présentation des périodes](../components/date-ranges/overview.md)
      + [Création d’une plage de dates](../components/date-ranges/create.md)
      + [Gestion des périodes](../components/date-ranges/manage.md)
      + [Aperçu du calendrier](../components/date-ranges/calendar.md)
      + [Création de périodes personnalisées](../components/date-ranges/custom-date-ranges.md)
      + [Comparaison des dates](../components/date-ranges/time-comparison.md)
   + Dictionnaire de données {#data-dictionary}
      + [Présentation du dictionnaire de données](../components/data-dictionary/data-dictionary-overview.md)
      + [Afficher des informations sur les composants dans le dictionnaire de données](../components/data-dictionary/view-data-dictionary.md)
      + [Modifier les entrées de composant dans le dictionnaire de données](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Surveiller l’intégrité du dictionnaire de données](../components/data-dictionary/monitor-data-dictionary-health.md)
+ Tableaux de bord Analytics {#cja-dashboards}
   + [Tableaux de bord Analytics - Aperçu](../mobile-app/home.md)
   + [Tâches du curateur](../mobile-app/curator.md)
   + [Création dʼune carte de performance mobile](../mobile-app/create-scorecard.md)
   + [Préparation des utilisateurs en charge de lʼexécution à lʼutilisation des tableaux de bord](../mobile-app/set-up-execs.md)
   + [Guide pour une prise en main rapide destiné aux utilisateurs en charge de l’exécution](../mobile-app/executive.md)
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

+ Analytique cross-canal {#cca}
   + [Présentation de l’analytique cross-canal](../cca/overview.md)
   + [Fonctionnement des relectures](../cca/replay.md)
   + [FAQ sur l’analytique cross-canal](../cca/faq.md)

+ Intégrations Adobe {#integrations}
   + [Présentation de l’intégration des solutions Adobe à CJA](/help/integrations/overview.md)
   + [Intégrer Adobe Analytics à Customer Journey Analytics](/help/integrations/aa.md)
   + [Intégrer des données Journey Optimizer à CJA](/help/integrations/ajo.md)
   + [Intégration des données de gestion de décision à CJA](/help/integrations/ajo-od.md)
   + [Intégrer l’IA dédiée aux clients à CJA](/help/integrations/customer-ai.md)

+ Gouvernance des données {#cja-privacy}
   + [Gouvernance des données](../privacy/privacy-overview.md)
   + [Journal d’audit](../privacy/audit-log.md)
   + [Clés gérées par le client](../privacy/cmk.md)

+ Cas d’utilisation {#cja-usecases}
   + [Cas d’utilisation de Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Données de Google Analytics {#ga}
      + [Présentation de la migration des données de Google Analytics vers CJA](../use-cases/ga/overview.md)
      + [Ingérer des données Google Analytics dans Platform](../use-cases/ga/backfill.md)
      + [Configuration des données de Google Analytics en flux continu dans Platform](../use-cases/ga/streaming.md)
      + [Rapport sur les données Google Analytics dans CJA](../use-cases/ga/report.md)
   + Ingestion de données {#data-ingestion}
      + [Ingestion de données Marketo Engage dans AEP et création de rapports dans CJA](../use-cases/data-ingestion/marketo.md)
      + [Ingestion d’audiences AEP dans CJA](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Vues de données {#data-views}
      + [Cas dʼutilisation des vues de données](../use-cases/data-views/data-views-usecases.md)
      + [Utiliser des dimensions et des mesures de liaison](../use-cases/data-views/binding-dimensions-metrics.md)
   + B2B {#b2b}
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
   + [Optimisation des performances de CJA](../admin/cja-performance.md)

+ Labs {#labs}
   + [Guide d’utilisation de Labs](../labs/labs.md)

+ Résolution des problèmes {#troubleshooting}
   + [Comparer vos données Adobe Analytics aux données CJA](../troubleshooting/compare.md)
   + [Cohérence des mesures et du nombre d’adhésions à l’audience entre Real-Time CDP et CJA](../troubleshooting/consistency-rcdp-cja.md)

+ [Glossaire CJA](../getting-started/cja-glossary.md)

+ [API CJA](https://developer.adobe.com/cja-apis/docs/)
