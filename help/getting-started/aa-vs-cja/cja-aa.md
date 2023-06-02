---
title: Prise en charge des fonctionnalités de Customer Journey Analytics
description: Comparaison des fonctionnalités Customer Journey Analytics à l’ensemble des fonctionnalités d’Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 683ac8b741ed73eb301364331cebf187c8c91cd2
workflow-type: tm+mt
source-wordcount: '1953'
ht-degree: 54%

---

# Prise en charge des fonctionnalités de Customer Journey Analytics

Les tableaux suivants répertorient les fonctionnalités d’Adobe Analytics (AA) prises en charge, partiellement prises en charge ou non par Customer Journey Analytics (CJA) et celles de CJA qui ne sont pas prises en charge ou disponibles dans AA. Ces listes seront modifiées à mesure que des fonctionnalités sont ajoutées à CJA.

## Fonctionnalités/composants entièrement pris en charge {#full-support}

| Fonctionnalité Adobe Analytics | Remarques sur lʼassistance |
| --- | --- |
| Détection des anomalies | Prise en charge complète. |
| Attribution IQ | Prise en charge complète. |
| Mesures calculées | Prise en charge complète. Les mesures calculées existantes dans l’Analysis Workspace traditionnelle ne sont pas transférées vers CJA. |
| Événements du calendrier | Prise en charge complète. Les événements de calendrier ont été implémentés sous la forme d’[annotations](/help/components/annotations/overview.md) dans Workspace. |
| Téléchargement CSV | Prise en charge complète. |
| Calendriers personnalisés | Prise en charge complète. |
| Comparaison de dates | Prise en charge complète. |
| Périodes | Toutes les fonctionnalités de périodes sont prises en charge. |
| Dimensions | Prise en charge complète. CJA utilise XDM et prend en charge un nombre illimité de dimensions. CJA n’est pas lié aux eVars ou aux props personnalisées de la version classique d’Adobe Analytics. |
| Suppression du RGPD | Prise en charge complète. Notez que la gestion du RGPD s’effectue désormais en coordination avec [!UICONTROL Adobe Experience Platform]. CJA hérite des modifications de données apportées aux jeux de données sous-jacents par [!UICONTROL Experience Platform]. |
| Création de rapports sur lʼeffet élévateur et le degré de confiance | Prise en charge complète via le [panneau Expérimentation](/help/analysis-workspace/c-panels/experimentation.md) |
| Variables/Propriétés de liste | Prise en charge complète. CJA utilise XDM et prend en charge un nombre illimité de tableaux de chaînes qui peuvent être utilisés de la même manière que listVars. |
| eVars de marchandisage | Prise en charge complète par le biais des [dimensions et des mesures de liaison](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=fr#binding-dimension) |
| Mesures | Prise en charge complète ; CJA utilise le modèle de données d’expérience (XDM) et prend en charge un nombre illimité de mesures. Il n’est pas lié aux événements de succès personnalisés traditionnels d’Analytics. Certaines mesures standard ont été renommées à partir d’Analytics traditionnel : Visiteurs = Personnes, Visites = Sessions, Accès = Événements. |
| Carte de performances mobiles/Tableaux de bord | Prise en charge complète. |
| Panneaux | Le panneau vierge, le panneau Attribution, le panneau à structure libre et les Quick Insights sont entièrement pris en charge. |
| Exportation PDF | Prise en charge complète. |
| Traitement du projet | Prise en charge complète. |
| Liaison de projet | Prise en charge complète. |
| Traitement de la période de rapport | Prise en charge complète. CJA repose exclusivement sur le Traitement de la période de rapport. |
| Accès à l’API de création de rapports | Prise en charge complète. Disponible via l’[API CJA](https://developer.adobe.com/cja-apis/docs/). |
| Rapports/projets planifiés | Prise en charge complète. |
| Segments | Prise en charge complète. Maintenant appelé &quot;Filtres&quot; : notez que tous les segments existants dans Analysis Workspace traditionnel ne sont pas transférés vers CJA. |
| Suites de rapports virtuelles | Prise en charge complète. Maintenant appelé [Vues des données](/help/data-views/create-dataview.md). |
| Traitement des composants des suites de rapports virtuelles | Prise en charge complète. Fait désormais partie des Vues de données. |
| Analyse des médias en flux continu | Les données multimédia sont disponibles dans Analytics Data Connector dans le cadre des panneaux Observateurs simultanés de médias et Temps de lecture de média dans l’espace de travail. |

{style="table-layout:auto"}

## Nouvelle prise en charge {#new-support}

| Fonctionnalité | Remarques |
| --- | --- |
| Publication d’audiences (publication de segments) | Pris en charge si une licence est associée à la plateforme de données clients ou aux produits Journey Optimizer d’Adobe. La [publication d’audiences](/help/components/audiences/audiences-overview.md) envoie des audiences au profil client en temps réel dans Experience Platform. |
| Classifications | Désormais appelées « Jeux de données de recherche ». Les classifications utilisées dans Analytics peuvent être importées dans Experience Platform et CJA à l’aide du connecteur source des classifications Analytics. Les jeux de données de recherche peuvent également être transférés directement vers Experience Platform et rendus disponibles dans CJA. |
| Créateur de règles de classification | Pris en charge à l’aide de [sous-chaînes](/help/data-views/component-settings/substring.md) dans CJA. Utilise des manipulations de chaînes lors de la génération des rapports plutôt que des jeux de données de recherche. |
| Session personnalisée | Prise en charge de toutes les fonctionnalités de session personnalisée, à l’exception des événements d’arrière-plan mobiles. |
| Persistance des variables de marchandisage | Prise en charge complète par le biais des [dimensions et des mesures de liaison](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=fr#binding-dimension) |
| Attributs du client | Désormais appelés &quot;Jeux de données de profil&quot;, ils ne sont pas automatiquement importés à partir de l’Experience Cloud, mais doivent être transférés vers l’Experience Platform avant d’être disponibles dans CJA. |
| Flux de données | L’exportation des données de première génération des jeux de données est disponible via le [API Experience Platform Data Access](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) et [Destinations Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=fr). Ces options permettent d’exporter au niveau de l’événement ou de la ligne toutes les données collectées ou ingérées dans le lac de données Experience Platform. Les colonnes de données de post-traitement ne sont pas disponibles, car les colonnes de données post-traitement sont calculées au moment de la requête. L’exportation de colonnes de publication est disponible via la création de rapports. |
| Déduplication des mesures | Désormais configuré sur les mesures dans les vues de données. La déduplication des mesures se produit au niveau de la personne ou de la session, au lieu du niveau du jeu de données, de la vue de données ou de la connexion. |
| Entrées, sorties et dimensions et mesures Durée de la visite | Prises en charge (les entrées et les sorties sont désormais appelées Débuts de session et fins de session) et sont calculées d’une manière légèrement différente. |
| Paramètres de persistance des eVars | Les eVars ne font plus partie de CJA. Toutefois, les paramètres de persistance font désormais partie des Vues de données et sont disponibles pour toutes les dimensions. Gardez à l’esprit que la persistance repose sur le Traitement de la période de rapport et non sur le traitement de la collecte de données. Les Dimensions définies dans les vues de données sont limitées à une persistance maximale de 90 jours et ne prennent pas en charge une persistance illimitée. |
| Obscurcissement d’IP | Pour les clients CJA utilisant le connecteur source Analytics pour renseigner les données d’Adobe Analytics dans CJA : Les paramètres d’obscurcissement d’adresses IP appliqués dans Adobe Analytics sont transmis à vos données CJA. Vous pouvez au besoin contrôler ces paramètres dans Adobe Analytics.<p>Pour les clients CJA qui utilisent le SDK Web Experience Platform pour renseigner directement les données dans Platform et CJA. Vous pouvez utiliser la préparation de données pour la collecte de données dans Platform pour configurer des règles qui obscurcissent l’adresse IP en fonction des besoins de votre entreprise. |
| Création de rapports sur les nouvelles sessions et les sessions répétées | Anciennement effectuée à l’aide de la dimension Nombre de visites. Les sessions nouvelles ou répétées sont prises en charge [avec un intervalle de recherche en amont de 13 mois](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=fr). |
| Variable Product | Dans Experience Platform, les utilisateurs peuvent utiliser un tableau de champs de type d’objet dans un schéma de jeux de données pour répondre à ce cas d’utilisation. Dans CJA, les clients peuvent utiliser n’importe quel nombre de variables de produit et ne sont pas limités à une seule variable comme dans Adobe Analytics. |
| Partage des projets | Le partage des projets est uniquement pris en charge entre les utilisateurs de CJA - il n’existe pas de partage de projet entre CJA et l’Analysis Workspace traditionnel. |
| Visualisations | Toutes les visualisations sont prises en charge, à l’exception de la visualisation en correspondance. |
| Report Builder (plug-in Excel) | Prise en charge avec un nouveau plug-in Office 365 pour Excel. |
| Autorisations utilisateur/Contrôles d’accès aux données | CJA fait la distinction entre les administrateurs de produit, les administrateurs de profil de produit et les utilisateurs d’[Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=fr). Seuls les administrateurs de produit peuvent créer/mettre à jour/supprimer des connexions, des projets, des filtres ou des mesures calculées créées par d’autres utilisateurs, tandis que les administrateurs de produit et les administrateurs de profil de produit peuvent modifier les vues de données. D’autres autorisations d’utilisateur sont disponibles pour la création de mesures calculées, de filtres ou d’annotations. |
| Règles de traitement, règles VISTA et règles de traitement des canaux marketing | Pris en charge à l’aide de la fonctionnalité Adobe Experience Platform Data Prep pour les jeux de données basés sur WebSDK et les données du connecteur de données Analytics. |
| Canaux marketing | Lors de l’utilisation du connecteur source Analytics, les données des canaux marketing sont transmises à CJA par le biais de ce connecteur. Les règles de canal marketing sont configurées dans Adobe Analytics traditionnel et certaines règles ne sont pas prises en charge. Pour plus de détails, consultez la [documentation sur les canaux marketing de CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html). <br/>Pour les mises en oeuvre WebSDK, les règles de traitement des canaux marketing de l’heure des rapports sont prises en charge par le biais de [Champs dérivés](../../data-views/derived-fields/derived-fields.md). |

{style="table-layout:auto"}

## Prise en charge partielle {#partial}

| Fonctionnalité | Remarques |
| --- | --- |
| Groupement cross-canal et entre appareils | Pris en charge pour les jeux de données contenant directement des informations d’identité (également appelé groupement « basé sur les champs »). Le groupement basé sur les graphiques n’est pas encore pris en charge, mais il est prévu. Voir l’[analytique cross-canal](/help/cca/overview.md). |
| Filtrage des robots | Pour les jeux de données basés sur le [connecteur source dʼAdobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr), le filtrage des robots est appliqué. La logique générale de filtrage des robots pour d’autres jeux de données n’est pas exécutée par [!UICONTROL Experience Platform] ou CJA. |
| Dimensions Périphérique, Navigateur, Référent, Technologie | Pris en charge pour les jeux de données basés sur le [connecteur source dʼAdobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). Voir [documentation sur les variables Analytics prises en charge par ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=fr).<p>Si vous utilisez la collecte de données du SDK Web Experience Platform, les dimensions et les appareils basés sur la recherche de périphérique ne sont actuellement pas pris en charge. Une prise en charge est prévue. |
| Dimensions Géosegmentation | Toutes les dimensions Géosegmentation/géographie collectées dans Adobe Analytics sont transmises à CJA par le biais du [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). Les implémentations qui n’utilisent pas le connecteur source Analytics, mais qui dépendent du SDK Web Experience Platform pour la collecte de données numériques peuvent utiliser la variable [Service de recherche géographique Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr). |
| Panneaux | Le panneau vierge, le panneau Attribution, le panneau à structure libre et les Quick Insights sont entièrement pris en charge. Les panneaux Comparaison des segments et Analytics for Target (A4T) ne sont pas pris en charge. |
| Règles de traitement | Pour les jeux de données basés sur le connecteur source Analytics, les règles de traitement sont toujours appliquées. [Les fonctionnalités de préparation des données d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) peuvent également être utilisées comme remplacement des règles de traitement des données qui vont directement vers Platform. |
| A4T | La prise en charge est assurée par l’intermédiaire des champs du [connecteur source d’Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). La prise en charge des noms conviviaux d’A4T pour les activités et expériences Target est planifiée. |

{style="table-layout:auto"}

## Pas de prise en charge, mais planifiée {#planned}

| Fonctionnalité | Remarques |
| --- | --- |
| Alertes | La prise en charge est planifiée. |
| Analyse des contributions | La prise en charge est planifiée. |
| Création de rapports de Data Warehouse | La prise en charge est planifiée à partir de l’interface d’Analysis Workspace. Le [[!UICONTROL service de requête]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=fr>) d’Adobe Experience Platform fournit également une interface pour ces cas d’utilisation dans CJA. |
| Assemblage d’ID via le graphique d’appareil | La prise en charge est planifiée. |
| Modèles de projets | La prise en charge est planifiée. |
| Création de rapports en temps réel | La prise en charge est planifiée. |
| Segment IQ | La prise en charge est planifiée. |
| Conversion des devises | La prise en charge est planifiée. |
| Sources de données des ID de transaction | La prise en charge est planifiée. |
| La migration de projets/filtres/mesures calculées d’AA vers CJA | La prise en charge est planifiée. |
| Sources de données de niveau résumé | La prise en charge est planifiée. |

{style="table-layout:auto"}

## Pas de prise en charge, pas encore planifiée {#not-planned}

| Fonctionnalité | Remarques |
| --- | --- |
| Activity Map | La prise en charge n’est pas encore planifiée. |
| Advertising Cloud | La prise en charge n’est pas encore planifiée. |

{style="table-layout:auto"}

## Ne jamais prendre en charge {#never}

* Mesure Personnes à l’aide d’une opération Coop sur plusieurs appareils
* Tableaux de bord Reports &amp; Analytics
* Signets Reports &amp; Analytics
* Cibles Reports &amp; Analytics

## Fonctionnalités CJA non disponibles dans Adobe Analytics {#cja-not-aa}

Le tableau suivant répertorie les fonctionnalités qui sont disponibles dans Customer Journey Analytics (CJA), mais qui ne sont pas prises en charge dans Adobe Analytics (AA).

| Fonctionnalité | Plus de détails |
| --- | --- |
| Hébergement de tout type de données | CJA est combiné avec la capacité de l’Experience Platform à contenir tous types et schémas de données. Utilisation [Modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr), les données peuvent être représentées et organisées de manière uniforme, prêtes à être combinées et explorées. Adobe Analytics est principalement axé sur les données d’analyse web et mobile, avec certaines fonctionnalités permettant d’effectuer des [import de données](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=fr). |
| Dimensions et mesures client illimitées | Les dimensions CJA sont illimitées ; Les valeurs peuvent être numériques, textuelles, objets, listes ou mélanges de toutes les valeurs. Les Dimensions peuvent être imbriquées ou hiérarchiques. Analytics prend en charge jusqu’à 75 props et 250 eVars. |
| Cardinalité illimitée / valeurs uniques | CJA prend en charge un nombre illimité de valeurs uniques ou d’éléments de dimension qui peuvent faire l’objet de rapports dans une seule dimension. AA est limité à 500 000 valeurs uniques. Le nombre illimité de valeurs ou de dimensions uniques élimine les limitations de création de rapports et d’analyse qui existent actuellement avec la mise en oeuvre à grande échelle d’Analytics. |
| Transformations de l’heure des rapports | Les transformations de la période de rapport (mieux connues sous le nom de vues de données) dans CJA vous permettent d’interpréter plus en détail les données d’une connexion. Vous pouvez modifier ou supprimer des données sans remise en oeuvre ; utiliser des sous-chaînes pour manipuler des dimensions ; créer des mesures à partir de n’importe quelle valeur ; filtre survient. Et la transformation est faite de manière non destructrice. Adobe Analytics offre des fonctionnalités limitées par le biais de suites de rapports virtuelles et de sessions. |
| Analyse de l’expérience | CJA peut évaluer l’effet élévateur et le degré de confiance de toute expérience provenant d’une source de données définie dans le cadre d’une connexion. Cette évaluation vous permet de comprendre les relations de cause à effet entre les interactions client sur n’importe quel canal. Analytics se limite à l’analyse des expériences par le biais de l’intégration d’Analytics for Target (A4T). |
| Analyses entre appareils | CJA prend en charge la combinaison transparente de jeux de données spécifiques à l’appareil à partir de sessions non authentifiées et authentifiées. CJA propose de renvoyer les données historiques aux appareils connus. Dans Analytics, cette fonctionnalité est limitée à une seule suite de rapports et à l’utilisation d’une représentation graphique des appareils. |
| Accès SQL | À l’aide de l’option Data Distiller, CJA peut supprimer les limites des données collectées lors du traitement principal d’Adobe. Vous pouvez modifier vos données avec SQL, créer des valeurs et des jeux de données propres à votre entreprise et continuer à explorer. Analytics ne prend en charge aucun type d’accès SQL à ses données. |
| Amélioration des options de sécurité et de confidentialité - Préparation à la HIPAA | CJA est prêt pour le protocole HIPAA et offre des options de sécurité supplémentaires pour la conformité à la réglementation. Adobe Analytics n’est pas prêt pour le HIPAA. |

{style="table-layout:auto"}
