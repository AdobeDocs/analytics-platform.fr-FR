---
title: Prise en charge des fonctionnalités de Customer Journey Analytics
description: Comparaison des fonctionnalités Customer Journey Analytics à l’ensemble des fonctionnalités d’Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: ht
source-wordcount: '2315'
ht-degree: 100%

---

# Prise en charge des fonctionnalités de Customer Journey Analytics

Les tableaux suivants répertorient les fonctionnalités propres à Customer Journey Analytics, de même que les fonctionnalités Adobe Analytics prises en charge, partiellement prises en charge ou non prises en charge dans Customer Journey Analytics. Ces listes seront modifiées à mesure que des fonctionnalités seront ajoutées à Customer Journey Analytics.

## Fonctionnalités propres à Adobe Customer Journey Analytics {#cja-not-aa}

Le tableau suivant répertorie les fonctionnalités disponibles dans Customer Journey Analytics qui ne sont pas prises en charge dans Adobe Analytics.

| Fonctionnalité | Plus de détails |
| --- | --- |
| **Possibilité de combiner des jeux de données (tels que des suites de rapports Adobe Analytics)** | Customer Journey Analytics vous permet de [combiner les données](/help/connections/combined-dataset.md) de plusieurs suites de rapports comme s’il s’agissait d’une seule suite de rapports dans Adobe Analytics. |
| **Hébergement de tout type de données** | Customer Journey Analytics est associé à la capacité d’Experience Platform à contenir tous types et schémas de données. Grâce au [Modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr), les données peuvent être représentées et organisées de manière uniforme, prêtes à être combinées et explorées. Adobe Analytics est principalement axé sur les données d’analyse web et mobile, avec certaines fonctionnalités permettant d’[importer les données](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=fr). |
| **Analyses entre appareils** | Customer Journey Analytics prend en charge la combinaison transparente des jeux de données spécifiques à l’appareil à partir de sessions non authentifiées et authentifiées. Customer Journey Analytics propose de renvoyer les données historiques vers les appareils connus. Dans Adobe Analytics, cette fonctionnalité est limitée à une seule suite de rapports et à l’utilisation d’un graphique de l’appareil. |
| **Améliorations des dimensions** | Customer Journey Analytics offre une plus grande flexibilité lors de l’utilisation de dimensions : <ul><li>**Dimensions numériques personnalisées** : [créez vos propres dimensions numériques dans une vue de données](/help/data-views/create-dataview.md#components).</li><li>**Trier des dimensions basées sur des chaînes** : [triez par ordre alphabétique les dimensions basées sur des chaînes dans un tableau à structure libre.](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>Dans Adobe Analytics, seules quelques dimensions numériques intégrées étaient disponibles. Le tri par dimensions basées sur des chaînes n’était pas possible.</p> |
| **Champs dérivés** | Les [champs dérivés](/help/data-views/derived-fields/derived-fields.md) permettent des transformations de vos données au moment d’établir votre rapport. Les données peuvent être combinées, corrigées ou créées à la volée. Ces transformations peuvent s’appliquer rétroactivement à tous les rapports. |
| **Amélioration des options de sécurité et de confidentialité** - Préparation à la loi HIPAA | Customer Journey Analytics est conforme à l’HIPAA et propose des [options de sécurité supplémentaires](/help/privacy/cmk.md) pour la conformité à la réglementation. Adobe Analytics n’est pas prêt pour l’HIPAA. |
| **Analyse de l’expérimentation** | Customer Journey Analytics peut [évaluer l’effet élévateur et le degré de confiance de toute expérience](/help/analysis-workspace/c-panels/experimentation.md) provenant d’une source de données définie dans le cadre d’une connexion. Cette évaluation vous permet de comprendre les relations de cause à effet entre les interactions client qui s’étendent sur n’importe quel canal. Analytics se limite à l’analyse de l’expérimentation par le biais d’A4T. |
| **Prévisions** | La [prévision](/help/analysis-workspace/c-forecast/forecasting.md) est une fonctionnalité d’IA/ML qui inclut une prédiction statistique pour les données de série temporelle en fonction des données historiques qui existent déjà dans Customer Journey Analytics. Les prévisions peuvent apparaître dans les tableaux à structure libre et dans les visualisations des graphiques linéaires. |
| **Analyse guidée** | L’[analyse guidée](/help/guided-analysis/overview.md) est un format de création de rapports destiné aux utilisateurs et aux utilisatrices, qui leur permet de répondre rapidement à leurs besoins en matière de données de manière autonome, afin d’obtenir rapidement des informations de qualité et prendre davantage de décisions éclairées. L’analyse guidée fait partie d’Adobe Product Analytics. |
| **Légendes intelligentes** | Les sous-titres intelligents utilisent le machine learning avancé et l’IA générative pour fournir des informations précieuses en langage naturel aux visualisations Workspace. La version initiale fournit des informations générées automatiquement pour la visualisation des [lignes](/help/analysis-workspace/visualizations/line.md). |
| **Transformations au moment du rapport** | Les [vues de données](/help/data-views/data-views.md) dans Customer Journey Analytics vous permettent d’interpréter plus en détail les données d’une connexion. Vous pouvez modifier ou supprimer des données sans modifier la mise en œuvre, utiliser des sous-chaînes pour manipuler des dimensions, créer des mesures à partir de n’importe quelle valeur, ou encore filtrer les sous-événements. Toutes ces transformations sont faites de manière non destructive. Adobe Analytics offre des fonctionnalités limitées par le biais de suites de rapports virtuelles et de durées de session personnalisées. |
| **Extension BI** | L’[extension BI](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-usecases/data-export/bi-extension) vous permet de connecter CJA directement aux outils de visualisation de BI populaires, tels que PowerBI ou Tableau. En utilisant cette extension, vous pouvez faire en sorte que vos rapports BI correspondent exactement à ce que vous voyez dans Analysis Workspace et dans d’autres interfaces de création de rapports CJA. Il s’agit d’un moyen beaucoup plus simple d’obtenir des rapports BI pour CJA sans avoir à recréer des rapports/mesures à partir de données brutes. |
| **Accès SQL** | À l’aide de l’option Data Distiller, Customer Journey Analytics peut supprimer les limites des données collectées lors du traitement du serveur principal d’Adobe. Vous pouvez modifier vos données grâce à SQL, créer des valeurs et des jeux de données propres à votre entreprise et continuer à explorer. Analytics ne prend en charge aucun type d’accès SQL à ses données. |
| **Assemblage** | Le [Groupement](/help/stitching/overview.md) est une puissante fonctionnalité qui élève la capacité d’un jeu de données d’événement relative à l’analyse cross-canal. L’analyse cross-canal est un cas d’utilisation principal que Customer Journey Analytics peut traiter, ce qui vous permet de combiner et d’exécuter en toute transparence des rapports sur plusieurs jeux de données de différents canaux, en fonction d’un identifiant commun (ID de personne). |
| **Dimensions et mesures illimitées de la clientèle** | Les dimensions Customer Journey Analytics sont illimitées ; les valeurs peuvent être numériques, textuelles, objets, listes ou des mélanges de toutes les valeurs. Les dimensions peuvent être imbriquées ou hiérarchiques. <br/>En revanche, Adobe Analytics prend en charge jusqu’à 75 props et 250 eVars. |
| **Valeurs uniques illimitées** | Customer Journey Analytics prend en charge un nombre illimité de valeurs uniques ou d’éléments de dimension qui peuvent faire l’objet de rapports dans une seule dimension.<p>Il n’y a pas de [limites de cardinalité sur une dimension](/help/components/dimensions/high-cardinality.md), ce qui permet à toute valeur unique d’apparaître et d’être comptabilisée.</p><p>Cette approche élimine les limites de création de rapports et d’analyses qui peuvent exister avec les implémentations Adobe Analytics à grande échelle, ce qui se traduit par des libellés [!UICONTROL Faible trafic].</p><p>Dans Customer Journey Analytics, il est possible de voir un libellé [!UICONTROL Valeurs uniques dépassées], mais elles se produisent beaucoup moins fréquemment et peuvent être atténuées en appliquant un filtre ou un segment aux données.</p> |

## Fonctionnalités/composants Adobe Analytics entièrement pris en charge {#full-support}

| Fonctionnalité Adobe Analytics | Remarques sur lʼassistance |
| --- | --- |
| **Détection des anomalies** | Prise en charge complète |
| **Attribution IQ** | Prise en charge complète |
| **Détection de robots** | [Prise en charge complète](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) |
| **Mesures calculées** | Prise en charge complète. Les mesures calculées existantes dans Analysis Workspace classique ne sont pas transférées vers Customer Journey Analytics. |
| **Événements du calendrier** | Prise en charge complète. Les événements de calendrier ont été implémentés sous la forme d’[annotations](/help/components/annotations/overview.md) dans Workspace. |
| **Téléchargement CSV** | Prise en charge complète |
| **Calendriers personnalisés** | Prise en charge complète |
| **Comparaisons de dates** | Prise en charge complète |
| **Périodes** | Toutes les fonctionnalités de périodes sont prises en charge. |
| **Dimensions** | Prise en charge complète. Customer Journey Analytics utilise XDM et prend en charge un nombre illimité de dimensions. Customer Journey Analytics n’est pas lié aux eVars ou aux props personnalisées de la version classique d’Adobe Analytics. |
| **Suppression du RGPD** | Prise en charge complète. Notez que la gestion du RGPD s’effectue désormais en coordination avec [!UICONTROL Adobe Experience Platform]. Customer Journey Analytics hérite des modifications de données apportées aux jeux de données sous-jacents par [!UICONTROL Experience Platform]. |
| **Création de rapports sur lʼeffet élévateur et le degré de confiance** | Prise en charge complète via le [panneau Expérimentation](/help/analysis-workspace/c-panels/experimentation.md) |
| **Variables/Propriétés de liste** | Prise en charge complète. Customer Journey Analytics exploite XDM et prend en charge un nombre illimité de tableaux de chaînes offrant une utilisation similaire à celle des listVars. |
| **eVars de marchandisage** | Prise en charge complète par le biais des [dimensions et des mesures de liaison](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=fr#binding-dimension) |
| **Mesures** | Prise en charge complète. Customer Journey Analytics exploite le Modèle de données d’expérience (XDM) et prend en charge un nombre illimité de mesures. Il n’est pas lié aux événements de succès personnalisés traditionnellement utilisés dans Adobe Analytics. Certaines mesures standard ont été renommées par rapport à Adobe Analytics : Visiteurs et visiteuses = Personnes, Visites = Sessions, Accès = Événements. |
| **Migration de projets, filtres et mesures calculées d’Adobe Analytics vers Customer Journey Analytics** | Prise en charge complète. |
| **Carte de performance mobile/Tableaux de bord** | Prise en charge complète |
| **Panneaux** | Prise en charge complète des panneaux suivants : Panneau vierge, Attribution, Structure libre, Aperçu rapide et Élément suivant ou précédent. |
| **Export PDF** | Prise en charge complète |
| **Traitement du projet** | Prise en charge complète |
| **Liaison de projet** | Prise en charge complète |
| **Traitement de la période de rapport** | Prise en charge complète; Customer Journey Analytics repose exclusivement sur le traitement de la période de rapport. |
| **Accès à l’API de création de rapports** | Prise en charge complète ; disponible via l’[API Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/). |
| **Rapports/Projets planifiés** | Prise en charge complète |
| **Segments** | Prise en charge complète. Désormais appelés Filtres. Notez que les segments existants dans Analysis Workspace ne seront pas transférés vers Customer Journey Analytics. |
| **Module complémentaire Collection de médias en streaming** | Les données des médias en streaming sont disponibles dans le connecteur source Analytics dans le cadre des panneaux Visionneuses simultanées de médias et Temps de lecture de média dans l’espace de travail. |
| **Sources de données de niveau résumé** | Prise en charge complète |
| **Suites de rapports virtuelles** | Prise en charge complète. Maintenant appelées [Vues de données](/help/data-views/create-dataview.md). |
| **Traitement des composants des suites de rapports virtuelles** | Prise en charge complète. Fait désormais partie des vues de données. |
| **Dimensions Appareil, Navigateur, Référent, Technologie** | Prise en charge pour les jeux de données basés sur le [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) et pour les jeux de données générés par le SDK web. Consultez notre [documentation sur les variables Analytics prises en charge via ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html). Si vous utilisez la collecte de données du SDK Web Experience Platform, les dimensions et les appareils basés sur la recherche d’appareils ne sont actuellement pas pris en charge. Une prise en charge est prévue à l’avenir. Pour ajouter des recherches de périphérique et de navigateur à votre flux de données de SDK web, reportez-vous à [cette documentation](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr) |

## Nouvelle prise en charge {#new-support}

| Fonctionnalité | Remarques |
| --- | --- |
| **Alertes** | Le processus d’[utilisation des alertes dans Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) est presque identique à celui des alertes dans Adobe Analytics. <p>Toutefois, en raison du délai de collecte de données dans Customer Journey Analytics, les alertes horaires ne sont pas disponibles. Dans Customer Journey Analytics, les alertes peuvent être configurées tous les jours, toutes les semaines ou tous les mois.</p> |
| **Analytics for Target (A4T)** | L’[intégration entre Adobe Customer Journey Analytics et Target](https://experienceleague.adobe.com/fr/docs/target/using/integrate/cja/target-reporting-in-cja) fournit des outils puissants d’analyse et de gain de temps destinés à votre programme d’optimisation. |
| **Publication dʼaudiences** | Pris en charge si une licence est associée à la plateforme de données clients ou aux produits Journey Optimizer d’Adobe. La [publication d’audiences](/help/components/audiences/audiences-overview.md) envoie des audiences au profil client en temps réel dans Experience Platform. |
| **Classifications** | Désormais appelées « Jeux de données de recherche ». Les classifications utilisées dans Analytics peuvent être importées dans Experience Platform et Customer Journey Analytics à l’aide du connecteur source des classifications Analytics. Les jeux de données de recherche peuvent également être transférés directement vers Experience Platform et rendus disponibles dans Customer Journey Analytics. |
| **Créateur de règles de classification** | Pris en charge à l’aide des [sous-chaînes](/help/data-views/component-settings/substring.md) dans Customer Journey Analytics. Utilise des manipulations de chaînes lors de la génération des rapports plutôt que des jeux de données de recherche. |
| **Durée de session personnalisée** | La durée de session peut être configurée via les [Paramètres de session](../../data-views/create-dataview.md#session-settings) dans une vue Données. Voir [Paramètres de session](../../data-views/session-settings.md) pour plus d’informations. <br/>La gestion des événements d’arrière-plan mobile est prise en charge par le SDK Mobile Adobe Experience Platform. Voir [Cycle de vie du réseau Edge](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) pour plus d’informations. |
| **Conversion de devises** | Prise en charge dans le cadre du [formatage d’un composant de mesure](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html#currency) dans une vue de données. |
| **Attributs du client** | Désormais appelés Jeux de données de profil, ils ne sont pas automatiquement importés à partir d’Experience Cloud, mais doivent être transférés vers Experience Platform avant d’être disponibles dans Customer Journey Analytics. |
| **Flux de données** | L’export des données de première génération des jeux de données est disponible via l’[API Experience Platform Data Access](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=fr) et via les [Destinations Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=fr). Ces options permettent d’exporter au niveau de l’événement ou de la ligne toutes les données collectées ou ingérées dans le lac de données Experience Platform. Les colonnes de données de post-traitement ne sont pas disponibles, car les colonnes « post » sont calculées au moment de la requête. L’export de colonnes « post » est disponible via la création de rapports. |
| **Création de rapports d’entrepôt de données** | [L’export de tableaux complets Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) correspond à l’évolution des rapports des entrepôts de données dans Adobe Analytics, avec de nombreuses nouvelles fonctionnalités souvent demandées et qui ne sont pas disponibles dans les entrepôts de données aujourd’hui. |
| **Entrées, sorties et dimensions et mesures du temps passé** | Prises en charge (les entrées et les sorties sont désormais appelées Débuts de session et fins de session) et sont calculées d’une manière légèrement différente. |
| **Paramètres de persistance des eVars** | Les eVars ne font plus partie de Customer Journey Analytics. Toutefois, les paramètres de persistance font désormais partie des Vues de données et sont disponibles pour toutes les dimensions. Gardez à l’esprit que la persistance repose sur le Traitement de la période de rapport et non sur le traitement de la collecte de données. Les dimensions définies dans les vues de données sont limitées à une persistance maximale de 90 jours et ne prennent pas en charge la persistance illimitée. |
| **Dimensions Géosegmentation** | [Prise en charge complète](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr) |
| **Groupement basé sur les graphiques** | Par le biais du [groupement basé sur les graphiques](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/stitching/overview#graph-based-stitching), vous pouvez exploiter la puissance du graphique d’identité dans le [service d’identités Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/home) pour élever les jeux de données à leur identité préférée. |
| **Alertes** | Le processus d’utilisation des [alertes](/help/components/c-intelligent-alerts/intelligent-alerts.md) dans Customer Journey Analytics est presque identique à celui des alertes dans Adobe Analytics. Cependant, il existe des [différences importantes](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/alerts/alerts-feature-comparison). |
| **Obscurcissement d’IP** | Pour les personnes qui utilisent Customer Journey Analytics avec le connecteur source Analytics pour renseigner les données d’Adobe Analytics dans Customer Journey Analytics : les paramètres d’obscurcissement d’adresses IP appliqués dans Adobe Analytics sont transmis à vos données Customer Journey Analytics. Vous pouvez au besoin contrôler ces paramètres dans Adobe Analytics.<p>Pour les personnes utilisant Customer Journey Analytics avec le SDK Web Experience Platform afin de renseigner directement les données dans Platform et dans Customer Journey Analytics : vous pouvez utiliser la préparation de données pour la collecte de données dans Platform, afin de configurer des règles qui obscurcissent l’adresse IP en fonction des besoins de votre entreprise. |
| **Canaux marketing** | Lors de l’utilisation du connecteur source Analytics, les données des canaux marketing sont transmises dans Customer Journey Analytics par le biais de ce connecteur. Les règles de canal marketing sont toujours configurées dans la version standard d’Adobe Analytics et certaines règles ne sont pas prises en charge. Voir [Canaux marketing Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html?lang=fr) pour plus d’informations. <br/>Pour les mises en œuvre WebSDK, les règles de traitement des canaux marketing au moment du rapport sont prises en charge par le biais de [Champs dérivés](../../data-views/derived-fields/derived-fields.md). |
| **Persistance des variables de marchandisage** | Prise en charge complète par le biais des [dimensions et des mesures de liaison](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=fr#binding-dimension) |
| **Déduplication des mesures** | Désormais configuré sur les mesures dans les vues de données. La déduplication des mesures se produit au niveau de la personne ou de la session, au lieu du niveau du jeu de données, de la vue de données ou de la connexion. |
| **Création de rapports sur les nouvelles sessions et les sessions répétées** | Anciennement effectuée à l’aide de la dimension Nombre de visites. Les sessions nouvelles ou répétées sont prises en charge [avec un intervalle de recherche en amont de 13 mois](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html). |
| **Règles de traitement, règles VISTA et règles de traitement des canaux marketing** | Prise en charge à l’aide de la fonctionnalité de préparation des données d’Adobe Experience Platform et des [champs dérivés](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html?lang=fr) pour les jeux de données basés sur le SDK web et les données du connecteur source Analytics. |
| **Variable products** | Dans Experience Platform, il est possible d’utiliser un tableau d’objets dans un schéma de jeux de données pour répondre à ce cas d’utilisation. Dans Customer Journey Analytics, les clients et clientes ont la possibilité d’utiliser n’importe quel nombre de variables de produit et ne sont pas limités à une seule variable, comme dans Adobe Analytics. |
| **Partage des projets** | Le partage des projets est uniquement pris en charge entre les personnes utilisant Customer Journey Analytics. Il n’existe pas de partage de projet entre Customer Journey Analytics et Analysis Workspace traditionnel. |
| **Report Builder** | Prise en charge avec un nouveau plug-in Office 365 pour Excel. |
| **Autorisations d’utilisation/Contrôles d’accès aux données** | Customer Journey Analytics fait la distinction entre les administrateurs et administratrices de produit, les administrateurs et administratrices de profil de produit et les utilisateurs et utilisatrices d’[Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=fr). Seuls les administrateurs et administratrices de produit peuvent créer/mettre à jour/supprimer des connexions, des projets, des filtres ou des mesures calculées créés par d’autres utilisateurs ou utilisatrices, tandis que les administrateurs et administratrices de produit et les administrateurs et administratrices de profil de produit peuvent modifier les vues de données. D’autres autorisations d’utilisateurs et utilisatrices sont disponibles pour des éléments tels que la création de mesures calculées, les filtres ou les annotations. |
| **Visualisations** | Toutes les visualisations Workspace sont prises en charge, à l’exception de la visualisation des mappages. |
| **Groupement cross-canal et entre appareils** | Pris en charge pour les jeux de données d’événement contenant des informations d’identité. Voir [Groupement](../../stitching/overview.md). |

## Prise en charge partielle {#partial}

| Fonctionnalité | Remarques |
| --- | --- |
| **Panneaux** | Le panneau vierge, le panneau Attribution, le panneau à structure libre et les Quick Insights sont entièrement pris en charge. Les panneaux Comparaison des segments et Analytics for Target (A4T) ne sont pas pris en charge. |

## La prise en charge est planifiée {#planned}

| Fonctionnalité | Remarques |
| --- | --- |
| **Analyse des contributions** | La prise en charge est planifiée. |
| **Modèles de projets** | La prise en charge est planifiée. |
| **Création de rapports en temps réel** | La prise en charge est planifiée. |
| **Segment IQ** | La prise en charge est planifiée. |
| **Sources de données des ID de transaction** | La prise en charge est planifiée. |

## La prise en charge n’est pas encore planifiée {#not-planned}

| Fonctionnalité | Remarques |
| --- | --- |
| **Activity Map** | La prise en charge n’est pas encore planifiée. |
| **Advertising Cloud** | La prise en charge n’est pas encore planifiée. |

{style="table-layout:auto"}

## Ne sera jamais prise en charge {#never}

* Mesure Personnes à l’aide d’une opération Coop sur plusieurs appareils
