---
title: Mises à jour de la documentation de Customer Journey Analytics
description: Répertorie les mises à jour de contenu de lʼensemble de la documentation de Customer Journey Analytics depuis décembre 2019.
exl-id: 1cfb9810-e083-4a68-9c58-295e674da8d7
solution: Customer Journey Analytics
feature: Release Notes
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '3208'
ht-degree: 79%

---

# Customer Journey Analytics - Mises à jour de la documentation

Les mises à jour suivantes ont été apportées à la documentation de Customer Journey Analytics depuis sa création.

## 2024

| Fonctionnalité | Description |
| --- | --- |
| **Février 2024** | |
| Mises à jour de la documentation sur le partage de projet | Ajout d’informations sur la procédure à suivre [afficher les projets qui sont partagés avec vous ;](/help/analysis-workspace/curate-share/share-projects.md#view-projects-shared-with-you).<p>Informations également simplifiées sur [partage de projets individuels ou multiples](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).</p> |
| Ajout d’exigences d’autorisation pour le chargement de fichiers vers Azure SAS et Azure RBAC lors de la configuration des emplacements d’exportation dans le cloud. | Ajout d’exigences d’autorisation exactes pour le chargement de fichiers vers Azure SAS et Azure RBAC lors de l’ajout de [configuration des comptes d’exportation cloud](/help/components/exports/cloud-export-accounts.md) et [configuration des emplacements d’exportation dans le cloud](/help/components/exports/cloud-export-locations.md). |
| Ajout d’exigences d’autorisation pour le transfert de fichiers vers les compartiments GCP et Rôle d’Amazon S3 lors de la configuration des emplacements d’exportation dans le cloud. | Ajout d’exigences d’autorisation exactes pour le transfert de fichiers vers les compartiments Amazon Rôle et Google Cloud Platform lorsqu’ils [configuration des emplacements d’exportation dans le cloud](/help/components/exports/cloud-export-locations.md). |
| Clarification selon laquelle les administrateurs de produit ont toujours accès à l’exportation des tables complètes | Apport des modifications suivantes afin de clarifier que les utilisateurs auxquels le rôle d’administrateur de produit est affecté ont accès à l’exportation de tables complètes à partir d’Analysis Workspace par défaut : <ul><li>Ajout d’une nouvelle puce à [Autorisations par défaut de l’administrateur de produit](/help/admin/cja-access-control.md#product-admin-default-permissions).</li><li>Ajout d’une note sous [configuration minimale requise pour exporter des tables complètes vers le cloud](/help/analysis-workspace/export/export-cloud.md#minimum-requirements).</li></ul> |
| Clarification selon laquelle les segments sont recréés lors de la migration des composants depuis Adobe Analytics | Dans le [Guide de l’utilisateur pour les utilisateurs d’Adobe Analytics](/help/getting-started/aa-to-cja-user.md), a clarifié le fait que les segments sont automatiquement recréés dans Adobe Analytics dans le cadre du processus de migration des composants et n’ont pas besoin d’être recréés manuellement. |
| Détails des enregistrements ignorés | Ajout d’une documentation sur la fonctionnalité de détails d’enregistrement ignorée dans Connexions. Voir [Détails de connexion](../connections/manage-connections.md#connection-details) pour en savoir plus. |
| **Janvier 2024** | |
| Prévisions | Ajout de la documentation sur [forecast](../analysis-workspace/c-forecast/forecasting.md), nouvelle fonctionnalité Analysis Workspace permettant de prévoir une mesure standard ou calculée avec toute granularité temporelle prise en charge (horaire, quotidien, hebdomadaire, mensuel et annuel) pour les tableaux à structure libre et les graphiques en courbes. |
| Mise à jour de la documentation pour l’ajout de comptes et d’emplacements lors de l’exportation de tableaux complets - | Mise à jour de la documentation afin de prendre en compte les mises à jour mineures de l’interface lors de la configuration d’un nouveau compte ou d’un nouvel emplacement lors de la [exportation de tables complètes à partir d’Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace).<p>Une nouvelle [!UICONTROL **Ajouter un compte**] est désormais disponible dans la [!UICONTROL **Compte**] menu déroulant. La variable [!UICONTROL **Ajouter un emplacement**] qui était auparavant disponible comme bouton en regard de l’option [!UICONTROL **Nom de l’emplacement**] est désormais disponible dans le menu lui-même. |
| Nouvelles informations de migration des composants lors de la migration depuis Adobe Analytics | Ajout d’informations à [Evolution à partir d’Adobe Analytics](/help/getting-started/aa-to-cja.md) qui fait référence au nouveau [migration des composants](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=fr) fonctionnalités documentées dans le guide d’administration d’Adobe Analytics. |
| Clarification de la disponibilité de certaines informations uniquement pour les administrateurs et administratrices. | Ajout d’informations indiquant que les colonnes &quot;Dernière utilisation&quot; et &quot;Utilisé(e) dans&quot; qui sont décrites dans la section [Gestionnaire de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-manager.md) et la variable [Gestionnaire de filtres](/help/components/filters/manage-filters.md) sont disponibles uniquement pour les administrateurs système. |
| Autorisations requises pour exporter des jeux de données | Ajout d’informations expliquant le [autorisations requises](/help/admin/cja-access-control.md) pour exporter des jeux de données vers des destinations cloud. |
| Gestion des connexions | Mise à jour de la [Gestion des connexions](../connections/manage-connections.md) article, en fonction des commentaires des clients. |
| Champs dérivés | Ajout du résumé de la fonction [limitations](/help/data-views/derived-fields/derived-fields.md#limitations) et une explication sur la façon de déterminer le nombre [opérateurs](/help/data-views/derived-fields/derived-fields.md#operators) utilisé dans une fonction. |

{style="table-layout:auto"}


## 2023

| Fonctionnalité | Description |
| --- | --- |
| **Décembre 2023** | |
| Centres de données | Ajout d’un article sur Customer Journey Analytics [emplacements d’hébergement](../technotes/cja-datacenters.md). |
| Mécanismes de sécurisation | Ajout du Customer Journey Analytics de liste d’articles [barrières de sécurité](../admin/guardrails.md). |
| Mises à jour de conversion de devise | Clarification de la documentation sur la manière de procéder [configuration de la conversion de devise](/help/data-views/component-settings/format.md). |
| Mises à jour de la documentation sur la détection des anomalies | La documentation relative à la détection des anomalies se trouvait auparavant dans une section sur Virtual Analyst. Les modifications suivantes ont été apportées : <ul><li>Le terme Virtual Analyst a été supprimé de la documentation.</li><li>La section sur la [Détection des anomalies](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) a été déplacée directement sous la section Analysis Workspace.</li></ul> |
| **Octobre 2023** | |
| Utilisation d’un champ dérivé pour définir des objectifs/cibles | Ajout [cas d’utilisation](../use-cases/goals-using-derived-fields.md) article illustrant comment utiliser des champs dérivés pour définir des objectifs/cibles et créer des rapports à leur sujet. |
| Exportation des tables complètes dans le cloud | Ajout d’une documentation sur l’exportation de tableaux complets avec des millions de lignes Workspace vers des destinations cloud. <p>L’export de tableaux complets permet une livraison unique ou planifiée de tableaux de données conçus dans Workspace avec une prise en charge allant jusqu’à cinq ventilations, cinq mesures, filtres et mesures calculées, le tout dans un tableau concaténé. Il s’agit de l’évolution des rapports des entrepôts de données dans Adobe Analytics, avec de nombreuses nouvelles fonctionnalités souvent demandées et qui ne sont pas disponibles dans les entrepôts de données aujourd’hui.</p><p>Pour plus d’informations, consultez [Export des rapports Customer Journey Analytics dans le cloud](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html?lang=fr). |
| Gestionnaire des activités de rapport | Ajout de la documentation pour le Gestionnaire des activités de création de rapports. <p>Le gestionnaire des activités de rapport vous permet d’afficher la capacité de création de rapports pour chaque connexion de votre organisation. Il fournit aux administrateurs une visibilité détaillée sur la consommation des rapports afin de diagnostiquer et de résoudre facilement les problèmes de capacité pendant les heures de pointe de la création de rapports.</p> <p>Les nouveaux articles suivants ont été ajoutés :<ul><li>[Présentation d’Activity Manager dans les rapports](/help/reporting-activity-manager/reporting-activity-overview.md)</li><li>[Afficher l’activité de création de rapports dans le Gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity.md)</li><li>[Annulation des requêtes dans le Gestionnaire des activités de création de rapports](/help/reporting-activity-manager/reporting-activity-cancel-requests.md)</ul> |
| Nouvelles colonnes sur les pages de gestion | Documentation de nouvelles colonnes désormais disponibles dans la variable [Gestionnaire de mesures calculées](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html?lang=fr) et la variable [Gestionnaire de filtres](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html?lang=fr). |
| Comparaison à Adobe Analytics | Ajout d’une [page d’aperçu](../getting-started/aa-vs-cja/overview.md) Cette section présente la comparaison et la compréhension des différences entre Customer Journey Analytics et Adobe Analytics. |
| Fonctionnalité de champs dérivés supplémentaires | Mise à jour de la documentation pour la nouvelle [`Lookup`](/help/data-views/derived-fields/derived-fields.md#lookup) de la fonction |
| **Septembre 2023** | |
| Mise à jour de la structure des articles du panneau Temps de lecture de média | Suppression du dossier Temps de lecture de média et association du contenu du dossier en un seul article : [Panneau Temps de lecture de média](/help/analysis-workspace/c-panels/media-playback-time-spent.md). <p>Cette modification est davantage conforme à la documentation des autres panneaux.</p> |
| Fonctionnalité de champs dérivés supplémentaires | Mise à jour de la documentation pour les nouvelles fonctions [`Lowercase`](/help/data-views/derived-fields/derived-fields.md#lowercase) et [`Trim`](/help/data-views/derived-fields/derived-fields.md#trim) et pour les fonctionnalités CSV supplémentaires ajoutées à la fonction [`Classify`](/help/data-views/derived-fields/derived-fields.md#classify). |
| Collecte de données régionale | [Questions fréquentes](../getting-started/cja-faq.md#12-regional-data-collection) mises à jour avec des informations sur la collecte de données régionale lors de l’utilisation de Customer Journey Analytics. |
| **Août 2023** | |
| Panneau Temps de lecture de média | Mise à jour du contenu de la section [Panneau Temps de lecture de média](/help/analysis-workspace/c-panels/media-playback-time-spent.md) afin d’améliorer la lisibilité. |
| Améliorations apportées à Report Builder | Mise à jour du contenu de la section [Planifier les classeurs](/help/report-builder/schedule-reportbuilder.md) avec des informations sur le téléchargement des tâches planifiées. Mise à jour du contenu de la section  [Créer un bloc de données](/help/report-builder/create-a-data-block.md) avec des informations sur l’utilisation de la date de début en tant que dimension. |
| Déplacement du contenu sur la gestion des projets planifiés | Création de l’article [Projets planifiés](/help/components/scheduled-projects-manager.md) dans le guide des composants Analytics. Ce contenu se trouvait auparavant dans l’article [Planification de projets](/help/analysis-workspace/export/t-schedule-report.md) dans le guide des outils Analytics. |
| Prise en charge des fonctionnalités d’Adobe Customer Journey Analytics | Ajout d’informations supplémentaires dans le tableau *Nouvelle prise en charge* des fonctionnalités de mise en session de Customer Journey Analytics par rapport à Adobe Analytics. [En savoir plus](../getting-started/aa-vs-cja/cja-aa.md#supported-in-a-new-way) |
| Évolution à partir d’Adobe Analytics | Mise à jour de la section *(Re)configuration des canaux marketing* avec une référence au modèle de fonction Canaux marketing des champs dérivés. [En savoir plus](../getting-started/aa-to-cja.md#3-reconfigure-your-marketing-channels) |
| Guides de démarrage rapide de l’ingestion de données pour les applications mobiles et d’autres plateformes | Ajout de guides supplémentaires de démarrage rapide de l’ingestion de données décrivant comment ingérer et utiliser des données provenant d’applications mobiles ou d’autres plateformes (comme les applications de bureau, les jeux sur consoles, les applications sur des décodeurs et les appareils IoT) dans Customer Journey Analytics. [En savoir plus](../data-ingestion/data-ingestion.md) |
| **Juillet 2023** | |
| Paramètres de session | Ajout d’une rubrique pour ce paramètre de vue de données. [En savoir plus](/help/data-views/session-settings.md) |
| Adobe Product Analytics | Adobe Product Analytics est une nouvelle façon d’interagir avec les données et les informations cross-canal dans Customer Journey Analytics. Grâce à ces nouvelles fonctionnalités, les équipes produit peuvent mettre en libre-service des données et des informations sur leur expérience de produit au moyen de workflows [d’analyse guidée](/help/guided-analysis/overview.md). |
| Champs dérivés | Un [champ dérivé](/help/data-views/derived-fields/derived-fields.md) vous permet de définir à la volée des manipulations de données (souvent complexes) par le biais d’un créateur de règles personnalisable. |
| Prise en charge étendue de la recherche de données de profil et de recherche | Permet d’ajouter des jeux de données en tant que recherches de champs dans les jeux de données Profil ou Recherche. Auparavant, seuls les jeux de données Événement étaient pris en charge. [En savoir plus](/help/connections/create-connection.md) |
| Améliorations apportées à Report Builder | <ul><li>[Filtrer à partir de la cellule pour plusieurs blocs de données](/help/report-builder/select-data-view.md)</li><li>[Afficher et masquer les en-têtes de lignes et de colonnes](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html#build-the-data-block)</li></ul> |
| Recherches géographiques du réseau Edge | [Paramètres du flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr) comment dispose d’un service de recherche géographique qui fournit des données géographiques unifiées. |
| **Juin 2023** | |
| Analyse cross-canal et groupement | En vue des modifications qui permettront le groupement et clarifieront la façon dont il facilite l’analyse cross-canal, la documentation relative à la fonctionnalité Analyse cross-canal désigne désormais l’[analyse cross-canal](../use-cases/cross-channel/cross-channel.md) comme une fonctionnalité et cas d’utilisation de Customer Journey Analytics, et le [Groupement](../stitching/overview.md) comme fonctionnalité essentielle pour y parvenir. |
| Accès PowerBI et Tableau aux vues de données de Customer Journey Analytics | Le connecteur SQL Customer Journey Analytics offre l’accès SQL aux vues de données que vous avez définies dans Customer Journey Analytics. [En savoir plus](/help/data-views/sql-connector.md) |
| Vues de données Adobe Journey Optimizer | L’administration Customer Journey Analytics a accès à certaines vues de données supplémentaires dans Customer Journey Analytics, intitulées « Vue de données AJO (nom du sandbox) ». [En savoir plus](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html?lang=fr). |
| Conversion des devises | Mise à jour de la documentation pour la prise en charge de la [conversion des devises](../data-views/component-settings/format.md#currency). |
| Mises à jour des mesures calculées | Les mises à jour suivantes ont été apportées à la documentation des mesures calculées afin de l’aligner sur les fonctionnalités actuelles de Customer Journey Analytics : <ul><li>Mise à jour de la liste des [mesures calculées par défaut](/help/components/calc-metrics/default-calcmetrics.md) disponibles dans Customer Journey Analytics</li><li>mise à jour des captures d’écran et des procédures dans différents articles sur les mesures calculées </li></ul> |
| **Mai 2023** | |
| Documentation des liens profonds (application mobile) | Permet aux utilisateurs et utilisatrices d’envoyer des liens vers des cartes de performance qui les dirigeront directement vers le projet de cartes de performance dans l’application. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=fr#share-scorecards-using-a-shareable-link) |
| Documentation sur la fonctionnalité « Sélectionner la vue de données à partir de la cellule » dans Report Builder | Cette fonctionnalité permet aux utilisateurs et utilisatrices de sélectionner la vue de données d’un bloc de données à partir d’une cellule. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=fr) |
| Documentation concernant la mise à jour de l’écran d’accueil pour l’application de tableaux de bord Analytics (application mobile) | Le nouvel écran d’accueil mis à jour vous permet d’afficher toutes vos cartes de performances dans une seule liste consolidée. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html?lang=fr#use-dashboards) |
| Mise à jour de l’optimisation | Mise à jour de l’article sur l’[Optimisation des performances de Customer Journey Analytics](/help/admin/optimizing-performance.md) |
| Aperçu d’Analysis Workspace | Mise à jour de la [vue d’ensemble d’Analysis Workspace](/help/analysis-workspace/home.md) pour inclure des informations d’aperçu plus générales et des liens vers le contenu approprié. |
| Création de projets | Création d’un article qui explique en détail comment [créer des projets](/help/analysis-workspace/build-workspace-project/create-projects.md) dans Analysis Workspace. |
| Tri des composants dans le rail de gauche | Ajout d’informations sur le tri de la liste des composants dans le rail de gauche. Consultez la section « Rechercher, filtrer et trier la liste des composants » dans la [Vue d’ensemble des composants](/help/components/overview.md). |
| Suppression de lignes contenant des dimensions dynamiques d’un tableau à structure libre | Ajout d’informations sur la suppression rapide de lignes spécifiques contenant des dimensions dynamiques à l’aide de l’icône x. Consultez la section « Exclure rapidement des lignes spécifiques d’un tableau » dans l’article [Filtrer et trier les tableaux](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| Bouton permettant d’ajouter une visualisation dans un panneau | Ajout d’informations sur un nouveau bouton au bas de chaque panneau d’Analysis Workspace, qui vous permet d’ajouter rapidement une visualisation. Consultez la section « Ajouter des visualisations à un panneau » dans la [Vue d’ensemble des visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md). |
| Documentation sur les légendes intelligentes | Enrichissez la mise en récit pour les utilisateurs et utilisatrices avec des [résumés en langage naturel](/help/analysis-workspace/visualizations/intelligent-captions.md) d’une visualisation Ligne. |
| Champs dérivés | Ajout de la documentation pour la fonctionnalité [Champs dérivés](../data-views/derived-fields/derived-fields.md). |
| **Avril 2023** |  |
| Vidéo sur l’utilisation des filtres comme dimensions | Mise à jour de la vidéo sur l’utilisation des filtres comme dimension. <p>Cette vidéo est liée à la page [Création de filtres](/help/components/filters/create-filters.md).</p> <p>Voici un lien direct vers la vidéo : [Utilisation de filtres comme dimensions dans Analysis Workspace](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/use-filters-as-dimensions.html?lang=fr).</p> |
| Documentation sur les filtres | Ajout d’un article sur l’utilisation du [Créateur de filtres](/help/components/filters/filter-builder.md). <p>Documentation rationalisée dans [Création de filtres](/help/components/filters/create-filters.md) et [Présentation des filtres](/help/components/filters/filters-overview.md).</p> |
| Mise à jour de la documentation du panneau Expérimentation | Ajout d’une section sur l’[interprétation des dimensions non randomisées](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/experimentation.html#non-randomized). |
| Filtres de projet (filtres ad hoc et rapides) | Documentation rationalisée sur les filtres de projet et suppression des informations dupliquées. Les étapes de création de filtres ad hoc sont désormais combinées avec les étapes pour [créer des filtres rapides](/help/components/filters/quick-filters.md). |
| **Mars 2023** | |
| Intégration des données de gestion des décisions | Ajout d’un contenu expliquant comment [intégrer des données de gestion des décisions Adobe Journey Optimizer dans Customer Journey Analytics](/help/integrations/ajo-od.md). |
| Créer des histoires de données dans les cartes de performance mobiles | Une [histoire de données](/help/mobile-app/create-scorecard.md#create-data-stories) consiste en un ensemble de points de données complémentaires, de contexte commercial et de mesures associées construit autour d’un thème centre ou d’une mesure commune. |
| Mise à jour de la prise en charge des fonctionnalités | Mise à jour de la [prise en charge des fonctionnalités de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md) avec un tableau des fonctionnalités disponibles dans Customer Journey Analytics, mais non disponible ni pris en charge dans AA. |
| Mesures calculées par défaut | Ajout de contenu expliquant les [mesures calculées par défaut fournies par Adobe](/help/components/calc-metrics/default-calcmetrics.md). |
| Dictionnaire de données | <p>Ajout d’une nouvelle documentation consacrée au dictionnaire de données, qui comprend la [Présentation](/help/components/data-dictionary/data-dictionary-overview.md), l’[Affichage](/help/components/data-dictionary/view-data-dictionary.md), la [Modification](/help/components/data-dictionary/edit-entries-data-dictionary.md) et la [Surveillance](/help/components/data-dictionary/monitor-data-dictionary-health.md) du dictionnaire de données.</p><p>Mise à jour des informations présentées dans la section [Ajouter des descriptions de composant](/help/components/add-component-descriptions.md) afin d’inclure la fonctionnalité de dictionnaire de données.</p> |
| Partage de liens pour les projets (aucune connexion requise) | <p>Mise à jour de la documentation existante pour expliquer comment partager un lien en lecture seule d’un projet avec des personnes qui n’ont pas accès à Analysis Workspace.</p> <p>Mise à jour de la documentation d’utilisation avec les sections [Partager des projets](/help/analysis-workspace/curate-share/share-projects.md) et [Créer des liens partageables](/help/analysis-workspace/curate-share/shareable-links.md).</p> <p>Ajout d’options d’administration dans les [Préférences](/help/analysis-workspace/user-preferences.md).</p> |
| **Février 2023** | |
| Comparer Customer Journey Analytics aux solutions BI | Nouveau document sur une [comparaison](../getting-started/cja-vs-bi.md) de Customer Journey Analytics à des solutions de BI standard. |
| Mettre à jour la documentation Audiences | Nouvelle section sur les [considérations relatives à la latence](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency). |
| Mettre à jour la documentation Audiences | Après avoir créé une audience, Adobe crée un [segment de streaming Experience Platform pour chaque nouvelle audience Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=fr#after-audience-created). |
| Calendriers et périodes de Workspace | Contenu mis à jour pour décrire les périodes relatives, les mises à jour des calculs de formule et les modifications de l’IU du calendrier. Voir [À propos des périodes relatives du panneau](/help/components/date-ranges/calendar.md#relative-panel-dates). |
| Cartes de performance mobiles | Nouvelle section de documentation pour décrire comment afficher et masquer les périodes de comparaison. Voir [Afficher les plages de dates de comparaison](/help/mobile-app/create-scorecard.md#show-comparison-dates) dans Customer Journey Analytics. |
| **Janvier 2023** | |
| Filtrer et trier des tableaux | Contenu mis à jour (y compris l’ajout de procédures et l’explication des options disponibles) dans l’article [Filtrer et trier des tableaux](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). Cet article a été renommé « Pagination, filtrer et trier des tableaux ». |
| Guides de démarrage rapide de l’ingestion de données | Nouvelle section de documentation sur la procédure à suivre pour [ingérer et utiliser des données](/help/data-ingestion/data-ingestion.md) dans Customer Journey Analytics. |
| Dossiers Workspace | Pages dédiées à la [Gestion des dossiers](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
| Préférences utilisateur de Workspace | De nombreuses préférences utilisateur supplémentaires sont désormais disponibles dans [Préférences](/help/analysis-workspace/user-preferences.md). |
| Enregistrement automatique des projets Workspace | Contenu mis à jour afin d’inclure la fonctionnalité d’enregistrement automatique dans [Enregistrer les projets](/help/analysis-workspace/build-workspace-project/save-projects.md). |
| Page de destination | Nouvelles mises à jour des pages de destination [Page de destination](/help/getting-started/landing.md). |
| Planifier les classeurs | Page dédiée pour décrire comment [planifier des classeurs](/help/report-builder/schedule-reportbuilder.md) dans Report Builder. |
| Prise en charge des tableaux d’objets pour les jeux de données de profil et de recherche | Mise à jour de l’[Utilisation des tableaux d’objets](/help/use-cases/object-arrays.md) et de l’[Ingestion d’audiences Adobe Experience Platform](/help/use-cases/data-ingestion/ingest-aep-segments.md) pour refléter la prise en charge des tableaux d’objets pour les jeux de données de profil et de recherche. |

{style="table-layout:auto"}

## 2022

| Date | Description de la mise à jour |
| --- | --- |
| **Décembre 2022** |  |
| 16 décembre 2022 | Nouvelle rubrique sur la [Mesure et la gestion de l’utilisation des données Customer Journey Analytics](/help/admin/estimate-usage.md). |
| **Octobre 2022** | |
| Octobre 2022 | Nouvelle rubrique sur la [protection par mot de passe des projets planifiés](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=fr#password). Cette fonctionnalité prend en charge la [Préparation du HIPAA](https://www.adobe.com/trust/compliance/hipaa-ready.html). |
| Octobre 2022 | Nouvelle rubrique sur les [Clés gérées par le client](/help/privacy/cmk.md). Cette fonctionnalité prend en charge la [Préparation du HIPAA](https://www.adobe.com/trust/compliance/hipaa-ready.html). |
| Octobre 2022 | Nouvelle rubrique sur le [Journal d’audit de Customer Journey Analytics](/help/privacy/audit-log.md). |
| Octobre 2022 | Nouvelle rubrique sur la visualisation [Résumé des mesures clés](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=fr). |
| Octobre 2022 | Nouvelle section sur la [fonctionnalité Date et Date-heure dans les vues de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#date) |
| Octobre 2022 | Application mobile : nouvelle rubrique sur les [vues détaillées personnalisées](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#view-detail-slides). |
| Octobre 2022 | Mises à jour de la rubrique [Prise en charge des fonctionnalités de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). |
| **Septembre 2022** | |
| Septembre 2022 | Nouveau cas d’utilisation sur la [Migration de données Google Analytics vers Customer Journey Analytics](/help/use-cases/ga/overview.md). |
| Septembre 2022 | Nouvelle rubrique sur les [Graphiques combinés](/help/analysis-workspace/visualizations/combo-charts.md) dans Workspace. |
| Septembre 2022 | Nouvelle rubrique sur le [Panneau Expérimentation](/help/analysis-workspace/c-panels/experimentation.md) dans Workspace. |
| **Août 2022** | |
| Août 2022 | Article d’Adobe Experience Platform sur la [prise en charge inter-régions du connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr). |
| Août 2022 | Article largement mis à jour sur le [Contrôle d’accès Customer Journey Analytics](/help/admin/cja-access-control.md). |
| Août 2022 | Nouvel article sur la [Prise en charge Customer Journey Analytics des étiquettes et des politiques de gouvernance des données](/help/data-views/data-governance.md). |
| Août 2022 | Nouvel article sur la [Comparaison de la terminologie pour les données Analytics transmises par le biais du connecteur source Analytics](/help/getting-started/aa-vs-cja/terminology.md). |
| Août 2022 | Nouvelle documentation sur la [publication d’audiences dans le profil client en temps réel](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=fr). |
| **Juillet 2022** | |
| Juillet 2022 | Documentation du [panneau Temps de lecture de média](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=fr). |
| Juillet 2022 | Documentation du [panneau Observateurs simultanés de médias](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=fr). |
| Juillet 2022 | Documentation sur les rapports de la [première session](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat). |
| **Juin 2022** | |
| Juin 2022 | Nouvel article sur les [AAID, ECID, AACUSTOMID et le connecteur source Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=fr) |
| Juin 2022 | Nouvel article sur les [Règles de traitement Adobe Analytics, VISTA et les classifications par rapport à la préparation des données pour le connecteur source Analytics](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md). |
| Juin 2022 | Nouvel article sur les [environnements de création de rapports virtuels et les environnements sandbox](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md). |
| Juin 2022 | Nouvel article sur la [Comparaison du traitement des données dans les fonctionnalités de création de rapports d’Adobe Analytics et de Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md). |
| Juin 2022 | Nouvel article sur la [combinaison de suites de rapports avec différents schémas](/help/use-cases/aa-data/combine-report-suites.md). |
| Juin 2022 | Nouvel article sur le [partage d’annotations dans les cartes de performance mobiles](/help/components/annotations/mobile-annotations.md). |
| Juin 2022 | Nouvel article sur [Analytics Labs dans Customer Journey Analytics](/help/labs/labs.md). |
| Juin 2022 | Nouvelle section sur la [prise en charge des champs numériques en tant que clés et valeurs de recherche](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr#numeric). |
| Juin 2022 | Mises à jour du [workflow de visualisation de flux](/help/analysis-workspace/visualizations/c-flow/create-flow.md). |
| **Mai 2022** | |
| Mai 2022 | Mise à jour importante de l’article sur la [Création de connexions](/help/connections/create-connection.md) dans Customer Journey Analytics. |
| Mai 2022 | Nouvel article sur comment [gérer les blocs de données dans Customer Journey Analytics Report Builder](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=fr). |
| Mai 2022 | Nouvel article sur l’[Ingestion d’audiences Adobe Experience Platform dans Customer Journey Analytics](/help/use-cases/data-ingestion/ingest-aep-segments.md). |
| **Avril 2022** | |
| Avril 2022 | Documentation sur les [sous-chaînes de dimension](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/substring.html?lang=fr). |
| Avril 2022 | Nouveau [guide de l’utilisateur de Customer Journey Analytics pour les utilisateurs et utilisatrices d’Adobe Analytics](/help/getting-started/aa-to-cja-user.md). |
| **Mars 2022** | |
| Mars 2022 | Nouvelle [documentation sur l’API Customer Journey Analytics Annotations](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/). |
| Mars 2022 | Nouvelle documentation sur [les annotations dans Workspace](/help/components/annotations/overview.md). |
| Mars 2022 | Mise à jour majeure du contenu sur l’[estimation de la taille de connexion](/help/getting-started/cja-faq.md). |
| **Février 2022** | |
| Février 2022 | Nouveau guide destiné à l’administration qui passe d’Adobe Analytics à Customer Journey Analytics : [passage d’Adobe Analytics à Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=fr) |
| **Janvier 2022** | |
| Janvier 2022 | Nouveau cas dʼutilisation relatif à lʼ[Utilisation des dimensions et des mesures de liaison dans Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md) |
| Janvier 2022 | Ajout dʼune nouvelle documentation sur les fonctionnalités [Dimensions de liaison et Mesures de liaison](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=fr#binding-dimension) et sur les nouveaux paramètres dʼattribution [[!UICONTROL Première valeur connue] et [!UICONTROL Dernière valeur connue]](/help/data-views/component-settings/persistence.md#allocation-settings). |
| Janvier 2022 | Nouvel article sur la [Comparaison entre vos données Adobe Analytics et vos données Analytics dans Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=fr) |

{style="table-layout:auto"}

## 2021

| Date | Description de la mise à jour |
| --- | --- |
| **Novembre 2021** | |
| Novembre 2021 | Mise à jour de la documentation pour les [[!UICONTROL Enregistrements ignorés]](/help/connections/manage-connections.md) sur la page Détails de la connexion. |
| **Octobre 2021** | |
| Octobre 2021 | Documentation pour [Report Builder](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/report-buider-overview.html?lang=fr#) dans Customer Journey Analytics. |
| Octobre 2021 | Documentation des API [Journal d’audit](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) Customer Journey Analytics |
| Octobre 2021 | [Visualisations pour les tableaux de bord Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=fr#apply-visualizations) documenté |
| Octobre 2021 | Document pour le créneau variable pour la [Rétention des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=fr#set-rolling-window-for-connection-data-retention) de [!UICONTROL connexion]. |
| **Septembre 2021** | |
| Septembre 2021 | Document [Déduplication des mesures](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication.html?lang=fr) |
| Septembre 2021 | [Prise en charge de l’heure d’été pour les comptes rendus de performances](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=fr#calendar) |
| Septembre 2021 | Documentation [Calendriers client](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=fr#calendar) |
| Septembre 2021 | Documentation [Champs booléens](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/behavior.html?lang=fr) |
| Septembre 2021 | Répartition des paramètres des composants dans les vues de données dans des fichiers individuels :<ul><li>Présentation des paramètres des [[!UICONTROL Composants]](/help/data-views/component-settings/overview.md)</li><li>Paramètres des composants : [[!UICONTROL attribution]](/help/data-views/component-settings/attribution.md)</li><li>Paramètres des composants : [[!UICONTROL comportement]](/help/data-views/component-settings/behavior.md)</li><li>Paramètres des composants : [[!UICONTROL mise en page]](/help/data-views/component-settings/format.md)</li><li>Paramètres des composants : [[!UICONTROL inclusion/exclusion]](/help/data-views/component-settings/include-exclude-values.md)</li><li>Paramètres des composants : [[!UICONTROL déduplication des mesures]](/help/data-views/component-settings/metric-deduplication.md)</li><li>Paramètres des composants : [[!UICONTROL aucune valeur]](/help/data-views/component-settings/no-value-options.md)</li><li>Paramètres des composants : [[!UICONTROL persistance]](/help/data-views/component-settings/persistence.md)</li><li>Paramètres des composants : [[!UICONTROL regroupement des valeurs]](/help/data-views/component-settings/value-bucketing.md)</li></ul> |
| Septembre 2021 | Nouvelle section sur les [implications de la fusion de suites de rapports](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=fr#6-considerations-when-merging-report-suites-in-cja) dans Customer Journey Analytics. |
| **Août 2021** | |
| Août 2021 | Nouvelle section sur l’amélioration de l’expérience des [Connexions](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=fr) dans Customer Journey Analytics. |
| Août 2021 | Nouvelle section sur la [sensibilité à la casse dans les dimensions de vues de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=fr#configure-behavior-settings). |
| **Juin 2021** | |
| Juin 2021 | Nouvelle documentation sur les [versions de projets précédentes](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/build-workspace-project/save-projects.html?lang=fr#previous-version) dans Espace de travail. |
| **Avril 2021** | |
| Avril 2021 | Nouvelle section sur la [persistance](/help/data-views/component-settings/persistence.md). |
| Avril 2021 | Nouvelle documentation relative à la prise en charge des projets planifiés dans Espace de travail. |
| Avril 2021 | Nouvelles rubriques sur lʼ[expérience améliorée des vues de données](/help/data-views/data-views.md). |
| Avril 2021 | Nouvelles rubriques sur lʼ[ingestion de données Google Analytics](/help/use-cases/ga/overview.md) et sur lʼ[analyse de ces données](/help/use-cases/ga/report.md). |
| Avril 2021 | Ajout dʼune rubrique sur les [rapports planifiés](/help/analysis-workspace/export/t-schedule-report.md) dans Espace de travail. |
| Avril 2021 | Nouvelle rubrique sur les [Dimensions à cardinalité élevée dans Customer Journey Analytics](/help/components/dimensions/high-cardinality.md). |
| **Mars 2021** | |
| Mars 2021 | Ajout dʼune rubrique sur la prise en charge des [tableaux de bord Analytics](/help/mobile-app/home.md) (application mobile). |
| Mars 2021 | Nouvelle rubrique sur les [préférences utilisateur](/help/analysis-workspace/user-preferences.md) dans Espace de travail. |
| **Février 2021** | |
| Février 2021 | Nouvelle rubrique sur lʼutilisation des [dimensions Canal marketing dans Adobe Experience Platform](/help/use-cases/aa-data/marketing-channels.md). |
| Février 2021 | Publication de la nouvelle documentation sur l’[API Customer Journey Analytics](https://www.adobe.io/cja-apis/docs/). |
| **Janvier 2021** | |
| Janvier 2021 | Nouvelle rubrique concernant lʼ[ajout de recherches standard à votre jeu de données](/help/connections/standard-lookups.md). |

{style="table-layout:auto"}

## 2020

| Date | Description de la mise à jour |
| --- | --- |
| 13 novembre 2020 | Nouvelles rubriques sur les [Analyse cross-canal](/help/stitching/overview.md), qui vous permet de redéfinir l’ID de personne d’un jeu de données, et permet une combinaison transparente de plusieurs jeux de données. |
| 13 novembre 2020 | Ajout dʼun nouveau cas dʼutilisation sur lʼ[importation des données du centre dʼappel et du Web](/help/use-cases/cross-channel/call-center.md). |
| 10 novembre 2020 | Ajout dʼune section sur les implications liées à la suppression de composants de données dans la [FAQ](/help/getting-started/cja-faq.md). |
| 2 novembre 2020 | Mise à jour de la page [Prise en charge des fonctionnalités de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). |
| Novembre 2020 | Ajout de contenu sur la [suppression de la limite de renvoi](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr#backfill-historical-data) pour les connexions. |
| 7 octobre 2020 | Ajout dʼune rubrique sur les [jeux de données dʼévénement combinés](/help/connections/combined-dataset.md). |
| 15 septembre 2020 | Ajout dʼune rubrique concernant lʼ[ingestion de données](/help/data-ingestion/data-ingestion.md). |
| 2 septembre 2020 | Mise à jour de la section sur les [autorisations utilisateur](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr). |
| 7 août 2020 | Ajout dʼune nouvelle rubrique sur le [Cas dʼutilisation B2B - Jeu de données de recherche](/help/use-cases/b2b/b2b.md). |
| Juillet 2020 | Ajout dʼinformations sur lʼ[option Carte dʼidentité pour lʼID de personne](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr). |
| Juillet 2020 | Ajout dʼune nouvelle rubrique sur les [tableaux dʼobjets](/help/use-cases/object-arrays.md), ou « hiérarchies de données ». |
| 14 avril 2020 | Mises à jour de la dernière interface utilisateur dans la rubrique [Création de connexions](/help/connections/create-connection.md). |
| 27 février 2020 | Mise à jour de la [Prise en charge des fonctionnalités de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). |
| Décembre 2019 | Première version de la documentation de Customer Journey Analytics |

{style="table-layout:auto"}
