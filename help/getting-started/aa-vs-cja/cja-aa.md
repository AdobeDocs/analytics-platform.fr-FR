---
title: Support pour les fonctionnalités Customer Journey Analytics
description: Comparaison des fonctionnalités Customer Journey Analytics à l’ensemble des fonctionnalités d’Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 94b3e7417b82e9ae3ad080884d4c184bee412c2c
workflow-type: ht
source-wordcount: '1521'
ht-degree: 100%

---

# Support pour les fonctionnalités Customer Journey Analytics

Les tableaux suivants listent les fonctionnalités d’Adobe Analytics prises en charge, partiellement prises en charge ou non prises en charge par Customer Journey Analytics (CJA). Ces listes seront modifiées à mesure que des fonctionnalités sont ajoutées à CJA.

## Fonctionnalités/composants entièrement pris en charge

| Fonctionnalité Adobe Analytics | Remarques sur lʼassistance |
| --- | --- |
| Détection des anomalies | Prise en charge complète. |
| Attribution IQ | Prise en charge complète. |
| Publication auprès d’une audience | Prise en charge complète. Appelé Publication de segments (envoi de segments depuis Espace de travail vers Experience Cloud) dans AA. La [publication d’audiences](/help/components/audiences/audiences-overview.md) envoie des audiences au profil client en temps réel dans Experience Platform. |
| Mesures calculées | Prise en charge complète. Notez que les mesures calculées existantes dans Analysis Workspace ne seront pas transférées vers CJA. |
| Événements du calendrier | Prise en charge complète. Les événements de calendrier ont été implémentés sous la forme d’[annotations](/help/components/annotations/overview.md) dans Workspace. |
| Créateur de règles de classification | Prise en charge complète. Les règles sont des [sous-chaînes](/help/data-views/component-settings/substring.md) dans CJA. Utilise des manipulations de chaînes à la génération des rapports plutôt que des jeux de données de recherche. |
| Assemblage cross-canal et entre appareils | Prise en charge complète. Voir [Cross-Channel Analytics](/help/connections/cca/overview.md). |
| Téléchargement CSV | Prise en charge complète. |
| Calendriers personnalisés | Prise en charge complète. |
| Comparaison de dates | Prise en charge complète. |
| Périodes | Toutes les fonctionnalités de périodes sont prises en charge. |
| Heure d’été | Prise en charge complète. |
| Dimensions Appareil, Navigateur, Référent, Technologie | Ces dimensions sont automatiquement incluses lorsqu’un jeu de données AEP inclut des champs de schéma XDM spécifiques et est conforme à la classe Événement d’expérience XDM. Consultez notre [documentation sur les variables Analytics prises en charge par ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=fr).<p>Si vous n’utilisez pas Adobe Source Connector pour renseigner les données d’Adobe Analytics dans CJA, mais que vous utilisez plutôt la collecte de données du SDK Web Experience Platform, les périphériques et dimensions basés sur la recherche de périphériques ne sont actuellement pas pris en charge. Ils seront pris en charge dans un avenir proche. |
| Dimensions | Prise en charge complète. CJA exploite XDM et prend en charge un nombre illimité de dimensions. CJA n’est pas lié aux eVars ou aux props personnalisées de la version classique d’Adobe Analytics. |
| Suppression du RGPD | Prise en charge complète. Notez que la gestion du RGPD s’effectue désormais en coordination avec [!UICONTROL Adobe Experience Platform]. CJA hérite des modifications de données apportées aux jeux de données sous-jacents par [!UICONTROL Experience Platform]. |
| Variables/Propriétés de liste | Prise en charge complète. CJA exploite XDM et prend en charge un nombre illimité de tableaux de chaînes offrant une utilisation similaire à celle des listVars. |
| Persistance des variables de marchandisage | Prise en charge complète par le biais des [dimensions et des mesures de liaison](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=fr#binding-dimension) |
| eVars de marchandisage | Prise en charge complète par le biais des [dimensions et des mesures de liaison](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=fr#binding-dimension) |
| Mesures | Prise en charge complète. CJA exploite le Modèle de données d’expérience (XDM) et prend en charge un nombre illimité de mesures, et n’est pas lié aux événements de succès personnalisés traditionnellement utilisés dans Analytics. Notez que certaines mesures standard ont été renommées par rapport à Analytics : Visiteurs = Personnes, Visites = Sessions, Accès = Événements. |
| Déduplication des mesures | Prise en charge complète. |
| Carte de performances mobiles/Tableaux de bord | Prise en charge complète. |
| Panneaux | Le panneau vierge, le panneau Attribution, le panneau à structure libre et les Quick Insights sont entièrement pris en charge. |
| Exportation PDF | Prise en charge complète. |
| Traitement du projet | Prise en charge complète. |
| Liaison de projet | Prise en charge complète. |
| Report Builder (module externe Excel) | Prise en charge complète. |
| Traitement de la période de rapport | Prise en charge complète. CJA repose exclusivement sur le Traitement de la période de rapport. |
| Accès à l’API de création de rapports | Prise en charge complète. Disponible via l’[API CJA](https://www.adobe.io/cja-apis/docs/). |
| Rapports/projets planifiés | Prise en charge complète. |
| Segments | Prise en charge complète. Désormais appelés « Filtres ». Notez que les segments existants dans Analysis Workspace ne seront pas transférés vers CJA. |
| Analyse des médias en flux continu | Les données multimédia seront disponibles le 30 juillet 2022 dans le cadre des panneaux Observateurs simultanés de médias et Temps de lecture de média dans l’espace de travail. |
| Autorisations utilisateur/Contrôles d’accès aux données | Prise en charge complète. CJA fait la distinction entre les administrateurs et les utilisateurs du produit [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=fr). Seuls les administrateurs de produits peuvent effectuer les actions suivantes : <ul><li>Créer/mettre à jour/supprimer des connexions ou des vues de données</li><li>Mettre à jour/supprimer des projets, des filtres ou des mesures calculées créés par d’autres utilisateurs, et</li><li>Partager un projet d’espace de travail avec tous les utilisateurs.</li></ul> |
| Suites de rapports virtuelles | Prise en charge complète. Désormais appelées [Vues de données](/help/data-views/create-dataview.md). |
| Traitement du composant VRS | Prise en charge complète. Désormais intégré aux vues de données. |

{style=&quot;table-layout:auto&quot;}

## Pris en charge avec des mises en garde

| Fonctionnalité | Remarques |
| --- | --- |
| A4T | La prise en charge est assurée par l’intermédiaire des champs du [Connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). |
| Classifications | Désormais appelées « Jeux de données de recherche ». Les classifications utilisées dans Analytics peuvent être importées dans Experience Platform et CJA à l’aide du connecteur source des classifications Analytics. Les jeux de données de recherche peuvent également être transférés directement sur AEP et rendus disponibles dans CJA. |
| Session personnalisée | Prise en charge de toutes les fonctionnalités de session personnalisée sauf les accès mobiles en arrière-plan. |
| Attributs du client | Désormais appelés « Jeux de données de profil », ils ne sont pas automatiquement importés à partir d’Experience Cloud, mais devront être téléchargés sur AEP avant d’être disponibles dans CJA. |
| Dimensions [!UICONTROL Appareil], [!UICONTROL Navigateur], [!UICONTROL Référent], [!UICONTROL Technologie] | Ces dimensions sont automatiquement incluses lorsqu’un jeu de données AEP inclut des champs de schéma XDM spécifiques et est conforme à la classe Événement d’expérience XDM. Consultez notre [documentation sur les variables Analytics prises en charge par le connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=fr). Pour les clients CJA qui n’utilisent pas le connecteur source pour renseigner les données d’Adobe Analytics dans CJA, mais qui utilisent plutôt la collecte de données du SDK web AEP, [!UICONTROL Appareil] et les dimensions basées sur la recherche d’appareil ne sont actuellement pas prises en charge, mais le seront prochainement. |
| Entrées, sorties et dimensions et mesures Durée de la visite | Prises en charge (les entrées et les sorties sont désormais appelées Débuts de session et fins de session) et sont calculées d’une manière légèrement différente. |
| Paramètres de persistance des eVars | Les eVars ne font plus partie de CJA. Toutefois, les paramètres de persistance font désormais partie des Vues de données et sont disponibles pour toutes les dimensions. Gardez à l’esprit que la persistance repose sur le Traitement de la période de rapport et non sur le traitement de la collecte de données. Les dimensions définies dans les vues de données sont limitées à une persistance maximale de 90 jours et ne prennent pas en charge une persistance illimitée. |
| Dimensions Géosegmentation | Toutes les dimensions Géosegmentation/géographie collectées dans Adobe Analytics sont transmises à CJA par le biais du [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). Les implémentations qui n’utilisent pas le connecteur source Analytics, telles que celles qui reposent sur le SDK Web AEP pour la collecte de données numériques, n’auront pas automatiquement l’étendue complète des recherches géographiques : le pays et l’état sont pris en charge dans le monde entier, la ville et le code postal ne le sont pas. |
| Obscurcissement d’IP | Pour les clients CJA utilisant le connecteur source Analytics pour renseigner les données d’Adobe Analytics dans CJA : Les paramètres d’obscurcissement d’adresses IP appliqués dans Adobe Analytics sont transmis à vos données CJA. Vous pouvez au besoin contrôler ces paramètres dans Adobe Analytics.<p>Pour les clients CJA qui utilisent le SDK Web d’Adobe Experience Platform pour renseigner directement les données dans Platform et CJA : Vous pouvez utiliser la préparation de données pour la collecte de données dans Platform pour configurer des règles qui obscurciront l’adresse IP en fonction des besoins de votre entreprise. |
| Canaux marketing | Les données des canaux marketing sont transmises à CJA par le biais du connecteur source Analytics. Les règles du canal marketing doivent toujours être configurées dans Adobe Analytics traditionnel. Certaines règles ne sont pas prises en charge. Pour plus de détails, consultez la [documentation sur les canaux marketing de CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=fr#cja-usecases). |
| Création de rapports sur les nouvelles sessions et les sessions répétées | Prise en charge le 17 août 2022, [avec un intervalle de recherche en amont de 13 mois](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=fr#new-repeat). |
| Variable Product | Dans Experience Platform, les utilisateurs peuvent utiliser un tableau de champs de type d’objet dans un schéma de jeux de données pour répondre à ce cas d’utilisation. Dans CJA, les clients ont la possibilité d’utiliser n’importe quel nombre de variables de produit et ne sont pas limités à une seule variable, comme dans Adobe Analytics. |
| Partage des projets | Le partage des projets est uniquement pris en charge entre les utilisateurs de CJA - il n’existe pas de partage de projet entre CJA et l’Analysis Workspace traditionnel. |
| Visualisations | Toutes les visualisations sont prises en charge, à l’exception de la visualisation en correspondance. |

{style=&quot;table-layout:auto&quot;}

## Prise en charge partielle

| Fonctionnalité | Remarques |
| --- | --- |
| Filtrage des robots | Pour les jeux de données basés sur le [connecteur source dʼAdobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr), le filtrage des robots est appliqué. La logique générale de filtrage des robots pour d’autres jeux de données n’est pas exécutée par [!UICONTROL Experience Platform] ou CJA. |
| Panneaux | Le panneau vierge, le panneau Attribution, le panneau à structure libre et les Quick Insights sont entièrement pris en charge. Les panneaux Comparaison des segments et Analytics for Target (A4T) ne sont pas pris en charge. |
| Règles de traitement | Pour les jeux de données basés sur le connecteur source Analytics, les règles de traitement sont toujours appliquées. [Les fonctionnalités de préparation des données d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) peuvent également être utilisées comme remplacement des règles de traitement des données qui vont directement vers Platform. |

{style=&quot;table-layout:auto&quot;}

## Non pris en charge actuellement, mais planifié

| Fonctionnalité | Remarques |
| --- | --- |
| Alertes | La prise en charge est planifiée. |
| Analyse des contributions | La prise en charge est planifiée. |
| Rapports de Data Warehouse (exportation de 100 % des lignes) | La prise en charge est planifiée à partir de l’interface d’Analysis Workspace. Le [[!UICONTROL service de requête]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=fr) d’Adobe Experience Platform fournit également une interface pour ces cas d’utilisation dans CJA. |
| Assemblage d’ID via le graphique d’appareil | La prise en charge est planifiée. |
| Création de rapports sur lʼeffet élévateur et le degré de confiance | La prise en charge est planifiée. |
| Règles de traitement, règles VISTA et règles de traitement des canaux marketing | La prise en charge est planifiée, mais les règles interviendront au moment de la requête plutôt que lors de la collecte de données. Cela permettra aux manipulations de données dʼêtre plus flexibles, rétroactives et non destructives. |
| Modèles de projets | La prise en charge est planifiée. |
| Création de rapports en temps réel | La prise en charge est planifiée. |
| Segment IQ | La prise en charge est planifiée. |

{style=&quot;table-layout:auto&quot;}

## La prise en charge n’est pas encore planifiée

| Fonctionnalité | Remarques |
| --- | --- |
| Activity Map | La prise en charge n’est pas encore planifiée. |
| Advertising Cloud | La prise en charge n’est pas encore planifiée. |
| Conversion des devises | La prise en charge n’est pas encore planifiée. |
| Flux de données | La prise en charge n’est pas encore planifiée. |
| Sources de données récapitulatives | La prise en charge n’est pas encore planifiée. |
| Sources de données des ID de transaction | La prise en charge n’est pas encore planifiée. |

{style=&quot;table-layout:auto&quot;}

## Ne sera jamais prise en charge

* Mesure Personnes à l’aide d’une opération Coop sur plusieurs appareils
* Tableaux de bord Reports &amp; Analytics
* Signets Reports &amp; Analytics
* Cibles Reports &amp; Analytics
* Mobile Services
