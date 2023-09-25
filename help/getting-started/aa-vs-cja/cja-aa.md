---
title: Prise en charge des fonctionnalités de Customer Journey Analytics
description: Comparaison des fonctionnalités Customer Journey Analytics à l’ensemble des fonctionnalités d’Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
source-git-commit: e77dbb491178ffbe26fcec21d8b456cc3befbd1d
workflow-type: tm+mt
source-wordcount: '2140'
ht-degree: 97%

---

# Prise en charge des fonctionnalités Adobe Customer Journey Analytics

Les tableaux suivants répertorient les fonctionnalités d’Adobe Analytics prises en charge, partiellement prises en charge ou non prises en charge dans Customer Journey Analytics, ainsi que les fonctionnalités de Customer Journey Analytics non prises en charge ou non disponibles dans Adobe Analytics. Ces listes seront modifiées à mesure que des fonctionnalités seront ajoutées à Customer Journey Analytics.

## Fonctionnalités/composants entièrement pris en charge {#full-support}

| Fonctionnalité Adobe Analytics | Remarques sur lʼassistance |
| --- | --- |
| Détection des anomalies | Prise en charge complète. |
| Attribution IQ | Prise en charge complète. |
| Mesures calculées | Prise en charge complète. Les mesures calculées existantes dans Analysis Workspace classique ne sont pas transférées vers Customer Journey Analytics. |
| Événements du calendrier | Prise en charge complète. Les événements de calendrier ont été implémentés sous la forme d’[annotations](/help/components/annotations/overview.md) dans Workspace. |
| Téléchargement CSV | Prise en charge complète. |
| Calendriers personnalisés | Prise en charge complète |
| Comparaisons de dates | Prise en charge complète |
| Périodes | Toutes les fonctionnalités de périodes sont prises en charge. |
| Dimensions | Prise en charge complète. Customer Journey Analytics utilise XDM et prend en charge un nombre illimité de dimensions. Customer Journey Analytics n’est pas lié aux eVars ou aux props personnalisées de la version classique d’Adobe Analytics. |
| Suppression du RGPD | Prise en charge complète. Notez que la gestion du RGPD s’effectue désormais en coordination avec [!UICONTROL Adobe Experience Platform]. Customer Journey Analytics hérite des modifications de données apportées aux jeux de données sous-jacents par [!UICONTROL Experience Platform]. |
| Création de rapports sur lʼeffet élévateur et le degré de confiance | Prise en charge complète via le [panneau Expérimentation](/help/analysis-workspace/c-panels/experimentation.md) |
| Variables/Propriétés de liste | Prise en charge complète. Customer Journey Analytics exploite XDM et prend en charge un nombre illimité de tableaux de chaînes offrant une utilisation similaire à celle des listVars. |
| eVars de marchandisage | Prise en charge complète par le biais des [dimensions et des mesures de liaison](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=fr#binding-dimension) |
| Mesures | Prise en charge complète. Customer Journey Analytics exploite le Modèle de données d’expérience (XDM) et prend en charge un nombre illimité de mesures. Il n’est pas lié aux événements de succès personnalisés traditionnellement utilisés dans Adobe Analytics. Certaines mesures standard ont été renommées par rapport à Adobe Analytics : Visiteurs = Personnes, Visites = Sessions, Accès = Événements. |
| Carte de performances mobiles/Tableaux de bord | Prise en charge complète. |
| Panneaux | Le panneau vierge, le panneau Attribution, le panneau à structure libre et les Quick Insights sont entièrement pris en charge. |
| Export PDF | Prise en charge complète |
| Traitement du projet | Prise en charge complète |
| Liaison de projet | Prise en charge complète |
| Traitement de la période de rapport | Prise en charge complète. Customer Journey Analytics repose exclusivement sur le traitement de la période de rapport. |
| Accès à l’API de création de rapports | Prise en charge complète. Disponible via l’[API Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/). |
| Rapports/Projets planifiés | Prise en charge complète. |
| Segments | Prise en charge complète. Désormais appelés Filtres. Notez que les segments existants dans Analysis Workspace ne seront pas transférés vers Customer Journey Analytics. |
| Suites de rapports virtuelles | Prise en charge complète. Maintenant appelées [Vues de données](/help/data-views/create-dataview.md). |
| Traitement des composants des suites de rapports virtuelles | Prise en charge complète. Fait désormais partie des Vues de données. |
| Analyse des médias de streaming | Les données multimédia sont disponibles dans le connecteur source Analytics dans le cadre des panneaux Visionneuses simultanées de médias et Temps de lecture de média dans l’espace de travail. |

{style="table-layout:auto"}

## Nouvelle prise en charge {#new-support}

| Fonctionnalité | Remarques |
| --- | --- |
| Publication dʼaudiences | Pris en charge si une licence est associée à la plateforme de données clients ou aux produits Journey Optimizer d’Adobe. La [publication d’audiences](/help/components/audiences/audiences-overview.md) envoie des audiences au profil client en temps réel dans Experience Platform. |
| Classifications | Désormais appelées « Jeux de données de recherche ». Les classifications utilisées dans Analytics peuvent être importées dans Experience Platform et Customer Journey Analytics à l’aide du connecteur source des classifications Analytics. Les jeux de données de recherche peuvent également être transférés directement vers Experience Platform et rendus disponibles dans Customer Journey Analytics. |
| Créateur de règles de classification | Pris en charge à l’aide des [sous-chaînes](/help/data-views/component-settings/substring.md) dans Customer Journey Analytics. Utilise des manipulations de chaînes lors de la génération des rapports plutôt que des jeux de données de recherche. |
| Durée de session personnalisée | La durée de session peut être configurée via les [Paramètres de session](../../data-views/create-dataview.md#session-settings) dans une vue Données. Voir [Paramètres de session](../../data-views/session-settings.md) pour plus d’informations. <br/>La gestion des événements d’arrière-plan mobile est prise en charge par le SDK Mobile Adobe Experience Platform. Voir [Cycle de vie du réseau Edge](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) pour plus d’informations. |
| Conversion des devises | Prise en charge dans le cadre du [formatage d’un composant de mesure](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=fr#currency) dans une vue de données. |
| Persistance des variables de marchandisage | Prise en charge complète par le biais des [dimensions et des mesures de liaison](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=fr#binding-dimension) |
| Attributs du client | Désormais appelés Jeux de données de profil, ils ne sont pas automatiquement importés à partir d’Experience Cloud, mais doivent être transférés vers Experience Platform avant d’être disponibles dans Customer Journey Analytics. |
| Flux de données | L’export des données de première génération des jeux de données est disponible via l’[API Experience Platform Data Access](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=fr) et via les [Destinations Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=fr). Ces options permettent d’exporter au niveau de l’événement ou de la ligne toutes les données collectées ou ingérées dans le lac de données Experience Platform. Les colonnes de données de post-traitement ne sont pas disponibles, car les colonnes « post » sont calculées au moment de la requête. L’export de colonnes « post » est disponible via la création de rapports. |
| Entrées, sorties et dimensions et mesures Durée de la visite | Prises en charge (les entrées et les sorties sont désormais appelées Débuts de session et fins de session) et sont calculées d’une manière légèrement différente. |
| Paramètres de persistance des eVars | Les eVars ne font plus partie de Customer Journey Analytics. Toutefois, les paramètres de persistance font désormais partie des Vues de données et sont disponibles pour toutes les dimensions. Gardez à l’esprit que la persistance repose sur le Traitement de la période de rapport et non sur le traitement de la collecte de données. Les dimensions définies dans les vues de données sont limitées à une persistance maximale de 90 jours et ne prennent pas en charge la persistance illimitée. |
| Dimensions Géosegmentation | Toutes les dimensions Géosegmentation/géographie collectées dans Adobe Analytics sont transmises à Customer Journey Analytics par le biais du [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). Les implémentations qui n’utilisent pas le connecteur source Analytics, mais qui dépendent du SDK Web Experience Platform pour la collecte de données numériques, peuvent utiliser le [service de recherche géographique Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr). |
| Obscurcissement d’IP | Pour les personnes qui utilisent Customer Journey Analytics avec le connecteur source Analytics pour renseigner les données d’Adobe Analytics dans Customer Journey Analytics : les paramètres d’obscurcissement d’adresses IP appliqués dans Adobe Analytics sont transmis à vos données Customer Journey Analytics. Vous pouvez au besoin contrôler ces paramètres dans Adobe Analytics.<p>Pour les personnes utilisant Customer Journey Analytics avec le SDK Web Experience Platform afin de renseigner directement les données dans Platform et dans Customer Journey Analytics : vous pouvez utiliser la préparation de données pour la collecte de données dans Platform, afin de configurer des règles qui obscurcissent l’adresse IP en fonction des besoins de votre entreprise. |
| Canaux marketing | Lors de l’utilisation du connecteur source Analytics, les données des canaux marketing sont transmises dans Customer Journey Analytics par le biais de ce connecteur. Les règles de canal marketing sont toujours configurées dans la version standard d’Adobe Analytics et certaines règles ne sont pas prises en charge. Voir [Canaux marketing Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html?lang=fr) pour plus d’informations. <br/>Pour les mises en œuvre WebSDK, les règles de traitement des canaux marketing au moment du rapport sont prises en charge par le biais de [Champs dérivés](../../data-views/derived-fields/derived-fields.md). |
| Déduplication des mesures | Désormais configuré sur les mesures dans les vues de données. La déduplication des mesures se produit au niveau de la personne ou de la session, au lieu du niveau du jeu de données, de la vue de données ou de la connexion. |
| Création de rapports sur les nouvelles sessions et les sessions répétées | Anciennement effectuée à l’aide de la dimension Nombre de visites. Les sessions nouvelles ou répétées sont prises en charge [avec un intervalle de recherche en amont de 13 mois](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=fr). |
| Règles de traitement, règles VISTA et règles de traitement des canaux marketing | Pris en charge à l’aide de la fonctionnalité Adobe Experience Platform Data Prep pour les jeux de données basés sur WebSDK et les données du connecteur source Analytics. |
| Variable products | Dans Experience Platform, il est possible d’utiliser un tableau d’objets dans un schéma de jeux de données pour répondre à ce cas d’utilisation. Dans Customer Journey Analytics, les clients et clientes ont la possibilité d’utiliser n’importe quel nombre de variables de produit et ne sont pas limités à une seule variable, comme dans Adobe Analytics. |
| Partage des projets | Le partage des projets est uniquement pris en charge entre les personnes utilisant Customer Journey Analytics. Il n’existe pas de partage de projet entre Customer Journey Analytics et Analysis Workspace traditionnel. |
| Report Builder | Prise en charge avec un nouveau plug-in Office 365 pour Excel. |
| Autorisations utilisateur/Contrôles d’accès aux données | Customer Journey Analytics fait la distinction entre les administrateurs/administratrices de produit, les administrateurs/administratrices de profil de produit et les utilisateurs/utilisatrices d’[Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=fr). Seuls les administrateurs et administratrices de produit peuvent créer/mettre à jour/supprimer des connexions, des projets, des filtres ou des mesures calculées créés par d’autres utilisateurs ou utilisatrices, tandis que les administrateurs et administratrices de produit et les administrateurs et administratrices de profil de produit peuvent modifier les vues de données. D’autres autorisations d’utilisateurs et utilisatrices sont disponibles pour des éléments tels que la création de mesures calculées, les filtres ou les annotations. |
| Visualisations | Toutes les visualisations sont prises en charge, à l’exception de la visualisation en correspondance. |

{style="table-layout:auto"}

## Prise en charge partielle {#partial}

| Fonctionnalité | Remarques |
| --- | --- |
| Groupement cross-canal et entre appareils | Pris en charge pour les jeux de données contenant directement des informations d’identité (également appelé groupement « basé sur les champs »). Le groupement basé sur les graphiques n’est pas encore pris en charge, mais il est prévu. Voir [Groupement](../../stitching/overview.md). |
| Filtrage des robots | Pour les jeux de données basés sur le [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr), le filtrage des robots est appliqué. La logique générale de filtrage des robots pour d’autres jeux de données n’est pas exécutée par [!UICONTROL Experience Platform] ou Customer Journey Analytics. |
| Dimensions Appareil, Navigateur, Référent, Technologie | Pris en charge pour les jeux de données basés sur le [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). Consultez notre [documentation sur les variables Analytics prises en charge par ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=fr).<p>Si vous utilisez la collecte de données du SDK Web Experience Platform, les dimensions et les appareils basés sur la recherche d’appareils ne sont actuellement pas pris en charge. Une prise en charge est prévue. |
| Panneaux | Le panneau vierge, le panneau Attribution, le panneau à structure libre et les Quick Insights sont entièrement pris en charge. Les panneaux Comparaison des segments et Analytics for Target (A4T) ne sont pas pris en charge. |
| Règles de traitement | Pour les jeux de données basés sur le connecteur source Analytics, les règles de traitement sont toujours appliquées. [Les fonctionnalités de préparation des données d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) peuvent également être utilisées comme remplacement des règles de traitement des données qui vont directement vers Platform. |
| Analytics for Target (A4T) | La prise en charge partielle est assurée par l’intermédiaire des champs du [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). La prise en charge des noms conviviaux d’A4T pour les activités et expériences Target est planifiée. |

{style="table-layout:auto"}

## La prise en charge est planifiée {#planned}

| Fonctionnalité | Remarques |
| --- | --- |
| Alertes | La prise en charge est planifiée. |
| Analyse des contributions | La prise en charge est planifiée. |
| Création de rapports de Data Warehouse | La prise en charge est planifiée à partir de l’interface d’Analysis Workspace. Le [[!UICONTROL service de requête]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=fr>) d’Adobe Experience Platform fournit également une interface pour ces cas d’utilisation dans Customer Journey Analytics. |
| Assemblage d’ID via le graphique d’appareil | La prise en charge est planifiée. |
| Modèles de projets | La prise en charge est planifiée. |
| Création de rapports en temps réel | La prise en charge est planifiée. |
| Segment IQ | La prise en charge est planifiée. |
| Sources de données des ID de transaction | La prise en charge est planifiée. |
| Migration de projets, filtres et mesures calculées d’Adobe Analytics vers Customer Journey Analytics | La prise en charge est planifiée. |
| Sources de données de niveau résumé | La prise en charge est planifiée. |

{style="table-layout:auto"}

## La prise en charge n’est pas encore planifiée {#not-planned}

| Fonctionnalité | Remarques |
| --- | --- |
| Activity Map | La prise en charge n’est pas encore planifiée. |
| Advertising Cloud | La prise en charge n’est pas encore planifiée. |

{style="table-layout:auto"}

## Jamais pris en charge {#never}

* Mesure Personnes à l’aide d’une opération Coop sur plusieurs appareils
* Tableaux de bord Reports &amp; Analytics
* Signets Reports &amp; Analytics
* Cibles Reports &amp; Analytics

## Fonctionnalités Adobe Customer Journey Analytics non disponibles dans Adobe Analytics {#cja-not-aa}

Le tableau suivant répertorie les fonctionnalités disponibles dans Customer Journey Analytics qui ne sont pas prises en charge dans Adobe Analytics.

| Fonctionnalité | Plus de détails |
| --- | --- |
| Hébergement de tout type de données | Customer Journey Analytics est associé à la capacité d’Experience Platform à contenir tous types et schémas de données. Grâce au [Modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr), les données peuvent être représentées et organisées de manière uniforme, prêtes à être combinées et explorées. Adobe Analytics est principalement axé sur les données d’analyse web et mobile, avec certaines fonctionnalités permettant d’[importer les données](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=fr). |
| Dimensions et mesures client illimitées | Les dimensions Customer Journey Analytics sont illimitées ; les valeurs peuvent être numériques, textuelles, objets, listes ou des mélanges de toutes les valeurs. Les dimensions peuvent être imbriquées ou hiérarchiques. Analytics prend en charge jusqu’à 75 props et 250 eVars. |
| Valeurs uniques illimitées | Customer Journey Analytics prend en charge un nombre illimité de valeurs uniques ou d’éléments de dimension qui peuvent faire l’objet de rapports dans une seule dimension. Adobe Analytics est limitée à 500 000 valeurs uniques. Le nombre illimité de valeurs ou de dimensions uniques élimine les limitations de création de rapports et d’analyse qui existent actuellement avec l’implémentation à grande échelle d’Analytics. |
| Conversions au moment du rapport | Les vues de données dans Customer Journey Analytics vous permettent d’interpréter plus en détail les données d’une connexion. Vous pouvez modifier ou supprimer des données sans modifier la mise en œuvre, utiliser des sous-chaînes pour manipuler des dimensions, créer des mesures à partir de n’importe quelle valeur, ou encore filtrer les sous-événements. Toutes ces transformations sont faites de manière non destructive. Adobe Analytics offre des fonctionnalités limitées par le biais de suites de rapports virtuelles et de durées de session personnalisées. |
| Analyse de l’expérimentation | Customer Journey Analytics peut évaluer l’effet élévateur et le degré de confiance de toute expérience provenant d’une source de données définie dans le cadre d’une connexion. Cette évaluation vous permet de comprendre les relations de cause à effet entre les interactions client qui s’étendent sur n’importe quel canal. Analytics se limite à l’analyse de l’expérimentation par le biais d’A4T. |
| Analyses entre appareils | Customer Journey Analytics prend en charge la combinaison transparente des jeux de données spécifiques à l’appareil à partir de sessions non authentifiées et authentifiées. Customer Journey Analytics propose de renvoyer les données historiques vers les appareils connus. Dans Analytics, cette fonctionnalité est limitée à une seule suite de rapports et à l’utilisation d’un graphique de l’appareil. |
| Accès SQL | À l’aide de l’option Data Distiller, Customer Journey Analytics peut supprimer les limites des données collectées lors du traitement du serveur principal d’Adobe. Vous pouvez modifier vos données grâce à SQL, créer des valeurs et des jeux de données propres à votre entreprise et continuer à explorer. Analytics ne prend en charge aucun type d’accès SQL à ses données. |
| Amélioration des options de sécurité et de confidentialité - Préparation du HIPAA | Customer Journey Analytics est prêt pour le HIPAA et propose des options de sécurité supplémentaires pour la conformité à la réglementation. Adobe Analytics n’est pas prêt pour le HIPAA. |
| Possibilité de combiner des jeux de données (tels que des suites de rapports Adobe Analytics) | Customer Journey Analytics vous permet de combiner les données de plusieurs suites de rapports comme s’il s’agissait d’une seule suite de rapports dans Adobe Analytics. |
| Champs dérivés | Les champs dérivés permettent des transformations de l’heure des rapports sur vos données. Les données peuvent être combinées, corrigées ou créées à la volée et s’appliquer rétroactivement à tous les rapports. |

{style="table-layout:auto"}
