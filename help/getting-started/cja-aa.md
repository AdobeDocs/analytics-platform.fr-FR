---
title: Support pour les fonctionnalités Customer Journey Analytics
description: Comparaison des fonctionnalités Customer Journey Analytics à l’ensemble des fonctionnalités d’Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
source-git-commit: 8efb8da477b2680a44294553fdca944461ba0f0c
workflow-type: tm+mt
source-wordcount: '1195'
ht-degree: 99%

---

# Support pour les fonctionnalités Customer Journey Analytics

Les tableaux suivants liste les fonctionnalités d’Adobe Analytics prises en charge, partiellement prises en charge ou non par Customer Journey Analytics (CJA). Ces listes seront modifiées à mesure que des fonctionnalités sont ajoutées à CJA.

## Fonctionnalités/composants entièrement pris en charge

| Fonctionnalité Adobe Analytics | Remarques sur lʼassistance |
| --- | --- |
| Détection des anomalies | Prise en charge complète. |
| Attribution IQ | Prise en charge complète. |
| Mesures calculées | Prise en charge complète. Notez que les mesures calculées existantes dans Analysis Workspace ne seront pas transférées vers CJA. |
| Assemblage cross-canal et entre appareils | Prise en charge complète. Voir [Analyse cross-canal](/help/connections/cca/overview.md). |
| Téléchargement CSV | Prise en charge complète. |
| Calendriers personnalisés | Prise en charge complète. |
| Comparaison de dates | Prise en charge complète. |
| Périodes | Toutes les fonctionnalités de période sont prises en charge. |
| Heure d’été | Prise en charge complète. |
| Dimensions | Prise en charge complète. CJA exploite XDM et prend en charge un nombre illimité de dimensions. CJA n’est pas lié aux eVars ou aux props personnalisées de la version classique d’Adobe Analytics. |
| Dimensions d’Analysis Workspace prêtes à l’emploi (par exemple, Type de navigateur, Type de référent, Système d’exploitation et d’autres) | CJA fournit ces dimensions de manière native tant que les champs XDM de base (tels que l’agent utilisateur ou l’ID de l’appareil) sont renseignés. Pour les clients qui utilisent Connecteur de données Analytics (ADC), certaines de ces dimensions sont disponibles, mais pas toutes. Consultez notre [documentation sur les variables Analytics prises en charge par ADC](https://docs.adobe.com/content/help/fr-FR/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Suppression du RGPD | Prise en charge complète. Notez que la gestion du RGPD s’effectue désormais en coordination avec [!UICONTROL Adobe Experience Platform]. CJA hérite des modifications de données apportées aux jeux de données sous-jacents par [!UICONTROL Experience Platform]. |
| Variables/Propriétés de liste | Prise en charge complète. CJA exploite XDM et prend en charge un nombre illimité de tableaux de chaînes offrant une utilisation similaire à celle des variables de liste. |
| Mesures | Prise en charge complète. CJA exploite le Modèle de données d’expérience (XDM) et prend en charge un nombre illimité de mesures, et n’est pas lié aux événements de succès personnalisés traditionnellement utilisés dans Analytics. Notez que certaines mesures standard ont été renommées par rapport à Analytics : Visiteurs = Personnes, Visites = Sessions, Accès = Événements. |
| Déduplication des mesures | Prise en charge complète. |
| Panneaux | Le panneau vierge, le panneau Attribution, le panneau à structure libre et les Quick Insights sont entièrement pris en charge. |
| Exportation PDF | Prise en charge complète. |
| Traitement du projet | Prise en charge complète. |
| Liaison de projet | Prise en charge complète. |
| Report Builder (module externe Excel) | Prise en charge complète (octobre 2021) |
| Traitement de la période de rapport | Prise en charge complète. CJA repose exclusivement sur le Traitement de la période de rapport. |
| Accès à l’API de création de rapports | Prise en charge complète. Disponible via l’[API CJA](https://www.adobe.io/cja-apis/docs/). |
| Rapports/projets planifiés | Prise en charge complète. |
| Segments | Prise en charge complète. Désormais appelés « Filtres ». Notez que les segments existants dans Analysis Workspace ne seront pas transférés vers CJA. |
| Autorisations utilisateur/Contrôles d’accès aux données | Prise en charge complète. CJA fait la distinction entre les administrateurs et les utilisateurs du produit [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=fr). Seuls les administrateurs de produits peuvent effectuer les actions suivantes : <ul><li>Créer/mettre à jour/supprimer des connexions ou des vues de données,</li><li>Mettre à jour/supprimer des projets, des filtres ou des mesures calculées créés par d’autres utilisateurs, et</li><li>Partager un projet Workspace avec tous les utilisateurs.</li></ul> |
| Suites de rapports virtuelles | Prise en charge complète. Désormais appelées [Vues de données](/help/data-views/create-dataview.md). |
| Traitement du composant VRS | Prise en charge complète. Désormais intégré aux vues de données. |

## Pris en charge avec des mises en garde

| Fonctionnalité | Remarques |
| --- | --- |
| A4T | La prise en charge est assurée par l’intermédiaire des champs du [Connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). |
| Classifications | Désormais appelées « Jeux de données de recherche ». Les classifications utilisées dans Analytics peuvent être importées dans Experience Platform et CJA à l’aide du connecteur de données des classifications Analytics. Les jeux de données de recherche peuvent également être transférés directement sur AEP et rendus disponibles dans CJA. |
| Session personnalisée | Prise en charge de toutes les fonctionnalités de session personnalisée autres que les accès mobiles en arrière-plan. |
| Attributs du client | Désormais appelés « Jeux de données de profil », ils ne sont pas automatiquement importés à partir d’Experience Cloud, mais devront être téléchargés sur AEP avant d’être disponibles dans CJA. |
| Dimensions Appareils, Navigateurs et Technologies | Ces dimensions sont automatiquement incluses lorsqu’un jeu de données AEP inclut des champs de schéma XDM spécifiques et est conforme à la classe XDM Experience Event. |
| Entrées, sorties et dimensions et mesures Durée de la visite | Prises en charge (les entrées et les sorties sont désormais appelées Débuts de session et fins de session) et sont calculées d’une manière légèrement différente. |
| Paramètres de persistance des eVars | Les eVars ne font plus partie de CJA. Toutefois, les paramètres de persistance font désormais partie des Vues de données et sont disponibles pour toutes les dimensions. Gardez à l’esprit que la persistance repose sur le Traitement de la période de rapport et non sur le traitement de la collecte de données. Les dimensions définies dans les vues de données sont limitées à une persistance maximale de 90 jours et ne prennent pas en charge une persistance illimitée. |
| Dimensions Géosegmentation | Toutes les dimensions Géosegmentation/géographie collectées dans Adobe Analytics sont transmises à CJA par le biais du connecteur de données Analytics. Les implémentations qui n’utilisent pas le connecteur de données Analytics, telles que celles qui reposent sur le SDK web AEP pour la collecte de données numériques, n’auront pas automatiquement l’étendue complète des recherches géographiques (le pays et l’état sont pris en charge, la ville et le code postal ne le sont pas). |
| Canaux marketing | Les données des canaux marketing sont transmises à CJA par le biais du connecteur de données Analytics. Les règles du canal marketing doivent toujours être configurées dans Adobe Analytics traditionnel. Certaines règles ne sont pas prises en charge. Pour plus de détails, consultez la [documentation sur les canaux marketing de CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=fr#cja-usecases). |
| Variable Product | Dans Experience Platform, les utilisateurs peuvent utiliser un tableau de champs de type d’objet dans un schéma de jeux de données pour répondre à ce cas d’utilisation. Dans CJA, les clients ont la possibilité d’utiliser n’importe quel nombre de variables de produit et ne sont pas limités à une seule variable, comme dans Adobe Analytics. |
| Partage des projets | Le partage des projets est uniquement pris en charge entre les utilisateurs de CJA - il n’existe pas de partage de projet entre CJA et l’Analysis Workspace traditionnel. |
| Visualisations | Toutes les visualisations sont prises en charge, à l’exception de la visualisation en correspondance. |

## Prise en charge partielle

| Fonctionnalité | Remarques |
| --- | --- |
| Filtrage des robots | Pour les jeux de données basés sur ADC (Connecteur de données Analytics), le filtrage des robots est appliqué. La logique générale de filtrage des robots pour d’autres jeux de données n’est pas exécutée par [!UICONTROL Experience Platform] ou CJA. |
| Media Analytics | Les données sur les médias sont disponibles dans le cadre du connecteur de données Analytics. |
| eVars de marchandisage | Le comportement des eVars de marchandisage peut être obtenu à l’aide des dimensions dans un tableau d’objets, étant donné qu’une eVar de marchandisage n’est pas configurée pour utiliser la persistance. Actuellement, la persistance de la dimension de marchandisage n’est pas disponible. |
| Panneaux | Le panneau vierge, le panneau Attribution, le panneau à structure libre et les Quick Insights sont entièrement pris en charge. Les panneaux Comparaison des segments, Analytics for Target (A4T) et Visionneuses simultanées de médias ne sont pas pris en charge. |
| Règles de traitement | Pour les jeux de données basés sur le connecteur de données Analytics, les règles de traitement sont toujours appliquées. [Les fonctionnalités de préparation des données d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) peuvent également être utilisées comme remplacement des règles de traitement des données qui vont directement vers Platform. |

## Non pris en charge actuellement, mais planifié

| Fonctionnalité | Remarques |
| --- | --- |
| Alertes | La prise en charge est planifiée. |
| Analyse des contributions | La prise en charge est planifiée. |
| Rapports de Data Warehouse (exportation de 100 % des lignes) | La prise en charge est planifiée à partir de l’interface d’Analysis Workspace. Le [!UICONTROL service de requête d’Experience Platform] fournit également une interface pour ces cas d’utilisation dans CJA. |
| Assemblage d’ID via le graphique d’appareil | La prise en charge est planifiée. |
| Persistance des variables de marchandisage | La prise en charge est planifiée. |
| Création de rapports en temps réel | La prise en charge est planifiée. |
| Segment IQ | La prise en charge est planifiée. |
| Publication de segments (envoi de segments de Workspace à Experience Cloud) | La prise en charge est planifiée. |

## La prise en charge n’est pas encore planifiée

| Fonctionnalité | Remarques |
| --- | --- |
| Activity Map | La prise en charge n’est pas encore planifiée. |
| Advertising Cloud | La prise en charge n’est pas encore planifiée. |
| Créateur de règles de classification | La prise en charge n’est pas encore planifiée. |
| Flux de données | La prise en charge n’est pas encore planifiée. |
| Sources de données récapitulatives | La prise en charge n’est pas encore planifiée. |

## Ne sera jamais prise en charge

* Mesure Personnes à l’aide d’une opération Coop sur plusieurs appareils
* Tableaux de bord Reports &amp; Analytics
* Signets Reports &amp; Analytics
* Cibles Reports &amp; Analytics
* Événements de calendrier Reports &amp; Analytics
* Mobile Services
