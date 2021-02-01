---
title: Support pour les fonctionnalités Customer Journey Analytics
description: Comparaison des fonctionnalités Customer Journey Analytics à l’ensemble des fonctionnalités d’Adobe Analytics.
translation-type: tm+mt
source-git-commit: c70662468126279110f14291c135a3f60dd919db
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 75%

---


# Support pour les fonctionnalités Customer Journey Analytics

Les tableaux suivants liste les fonctionnalités d’Adobe Analytics prises en charge, partiellement prises en charge ou non par Customer Journey Analytics (CJA). Ces listes seront modifiées à mesure que des fonctionnalités sont ajoutées à CJA.

## Fonctionnalités/composants entièrement pris en charge

| Fonction Adobe Analytics | Remarques |
| --- | --- |
| Mesures | CJA exploite le Modèle de données d’expérience (XDM) et prend en charge un nombre illimité de mesures, et n’est pas lié aux événements de succès personnalisés traditionnellement utilisés dans Analytics. Notez que certaines mesures standard ont été renommées par rapport à Analytics : Visiteurs = Personnes, Visites = Sessions, Accès = Événements. |
| Dimensions | CJA exploite XDM et prend en charge un nombre illimité de dimensions, et n’est pas lié aux événements de succès personnalisés traditionnellement utilisés dans Analytics. |
| Variables/Propriétés de liste | CJA exploite XDM et prend en charge un nombre illimité de variables de liste. |
| Périodes | La prise en charge du calendrier personnalisé est planifiée. |
| Mesures calculées | Notez que les mesures calculées existantes dans Analysis Workspace ne seront pas transférées vers CJA. |
| Segments | Désormais appelés « Filtres » : notez que les segments existants dans Analysis Workspace ne seront pas transférés vers CJA. |
| Détection des anomalies | Prise en charge complète. |
| Attribution IQ | Prise en charge complète. |
| Traitement du projet | Prise en charge complète. |
| Liaison de projet | Prise en charge complète. |
| Comparaison de dates | Prise en charge complète. |
| Suites de rapports virtuelles | Maintenant appelées [Vues de données](/help/data-views/create-dataview.md). |
| Traitement du composant VRS | Fait désormais partie des Vues de données. |
| Traitement de la période de rapport | CJA repose exclusivement sur le Traitement de la période de rapport. |
| Suppression du RGPD | Notez que GDPR est maintenant géré en coordination avec [!UICONTROL Adobe Experience Platform] - CJA hérite des changements de données [!UICONTROL Experience Platform] apportés aux jeux de données sous-jacents. |
| Autorisations utilisateur/Contrôles d’accès aux données | CJA fait la distinction entre les administrateurs et les utilisateurs du produit Adobe Admin Console. Seuls les administrateurs du produit peuvent 1) créer/mettre à jour/supprimer des connexions ou des vues de données, 2) mettre à jour/supprimer des projets, des filtres ou des mesures calculées qui ont été créés par d’autres utilisateurs et 3) partager un projet Workspace avec tous les utilisateurs. |
| Dimensions d’Analysis Workspace prêtes à l’emploi (par exemple, Type de navigateur, Type de Parrain, Système d’exploitation, etc.) | CJA fournit ces dimensions de manière native tant que les champs XDM de base (tels que l’agent utilisateur ou l’ID de périphérique) sont renseignés. Pour les clients qui utilisent Connecteur de données Analytics (ADC), certaines de ces dimensions sont disponibles, mais pas toutes. Consultez notre [documentation sur les variables Analytics prises en charge par ADC](https://docs.adobe.com/content/help/fr-FR/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Accès à l’API de création de rapports | Actuellement disponible à l’aide de l’API Analytics 2.0. |

## Pris en charge avec des mises en garde

| Fonctionnalité | Remarques |
| --- | --- |
| Variable Product | Dans l’Experience Platform, les utilisateurs peuvent utiliser un tableau de champs de type Objet dans un schéma de jeux de données pour satisfaire ce cas d’utilisation. Dans CJA, les clients ont la possibilité d’utiliser n’importe quel nombre de variables de produit et ne sont pas limités à une seule variable, comme en Adobe Analytics. |
| Canaux marketing | Canaux marketing flux de données vers la CJA via le connecteur de données Analytics. Les règles du canal marketing doivent toujours être configurées dans Adobe Analytics traditionnel. Certaines règles ne sont pas prises en charge. Pour plus de détails, consultez la [documentation sur les canaux marketing de CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=fr-FR#cja-usecases). |
| Visualisations | Toutes les visualisations sont prises en charge, à l’exception de la visualisation en correspondance. |
| Partage des projets | Le partage des projets est uniquement pris en charge entre les utilisateurs de CJA - il n’existe pas de partage de projet entre CJA et l’Analysis Workspace traditionnel. |
| Session personnalisée | Prise en charge de toutes les fonctionnalités de session personnalisée autres que les accès mobiles en arrière-plan. |
| Paramètres de persistance des eVars | Les eVars ne font plus partie de CJA. Toutefois, les paramètres de persistance font désormais partie des Vues de données et sont disponibles pour toutes les dimensions. Gardez à l’esprit que la persistance repose sur le Traitement de la période de rapport et non sur le traitement de la collecte de données. Les Dimensions définies dans les Vues de données sont limitées à une persistance maximale de 90 jours et ne prennent pas en charge une persistance illimitée. |
| Classifications | Maintenant appelé &quot;Jeu de données de recherche&quot;. Les classifications utilisées dans Analytics peuvent être importées dans l’Experience Platform et la CJA à l’aide du Connecteur de données des classifications Analytics. Les jeux de données de recherche peuvent également être téléchargés directement sur AEP et rendus disponibles dans CJA. |
| Attributs du client | Désormais appelés « Jeux de données de profil », ils ne sont pas automatiquement importés à partir d’Experience Cloud, mais devront être transférés sur AEP avant d’être disponibles dans CJA. |
| Dimensions Appareils, Navigateurs et Technologies | Ces dimensions sont automatiquement incluses lorsqu’un jeu de données AEP inclut des champs de schéma XDM spécifiques et est conforme à la classe XDM Experience Event. |
| Dimensions et mesures des entrées, sorties et durée | Prises en charge (les entrées et les sorties sont désormais appelées Débuts de session et fins de session) et sont calculées d’une manière légèrement différente. |

## Prise en charge partielle

| Fonctionnalité | Remarques |
| --- | --- |
| Panneaux | Le panneau vierge, le panneau Attribution, le panneau à structure libre et les Quick Insights sont entièrement pris en charge. Les panneaux Comparaison des segments, Analytics for Target (A4T) et Visionneuses simultanées de médias ne sont pas pris en charge. |
| eVars de marchandisage | Le comportement des eVars de marchandisage peut être réalisé à l’aide de dimensions dans une matrice d’objets, étant donné qu’un eVar de marchandisage n’est pas configuré pour utiliser la persistance. Actuellement, la persistance de la dimension de marchandisage n’est pas disponible. |
| Filtrage des robots | Pour les jeux de données basés sur ADC (Connecteur de données Analytics), le filtrage des robots est appliqué. La logique générale de filtrage des robots pour d’autres jeux de données n’est pas exécutée par [!UICONTROL Experience Platform] ou CJA. |
| Règles de traitement | Pour les jeux de données basés sur ADC, les règles de traitement restent appliquées. |
| Ajout d’identités sur plusieurs appareils | La CJA prend en charge l’assemblage d’identités inter-appareils et entre canaux de façon continue, y compris la réaffirmation périodique des données historiques. Actuellement, cette opération ne peut être réalisée qu’à l’aide d’une seule identité de client associée à un seul ID de cookie. |
| Media Analytics | Les données sur les médias sont disponibles dans le cadre du connecteur de données Analytics. |

## Non pris en charge actuellement, mais planifié

| Fonctionnalité | Remarques |
| --- | --- |
| Analyse des contributions | La prise en charge est planifiée. |
| Segment IQ | La prise en charge est planifiée. |
| Publication de segments (envoi de segments de Workspace à Experience Cloud) | La prise en charge est planifiée. |
| Téléchargement CSV | La prise en charge est planifiée. |
| Calendriers personnalisés | La prise en charge est planifiée. |
| Déduplication des mesures | La prise en charge est planifiée. |
| Persistance des variables de marchandisage | La prise en charge est planifiée. |
| Rapports/projets planifiés | La prise en charge est planifiée. |
| Alertes | La prise en charge est planifiée. |
| Exportation PDF | La prise en charge est planifiée. |
| Assemblage d’ID via le graphique d’appareil | La prise en charge est planifiée. |
| Report Builder (module externe Excel) | La prise en charge est planifiée. |
| Création de rapports en temps réel | La prise en charge est planifiée. |

## La prise en charge n’est pas encore planifiée.

| Fonctionnalité | Remarques |
| --- | --- |
| A4T | La prise en charge n’est pas encore planifiée. |
| Advertising Cloud | La prise en charge n’est pas encore planifiée. |
| Activity Map | La prise en charge n’est pas encore planifiée. |
| Créateur de règles de classification | La prise en charge n’est pas encore planifiée. |
| Sources de données récapitulatives | La prise en charge n’est pas encore planifiée. |

## Ne sera jamais prise en charge

* Mesure Personnes à l’aide d’une opération Coop sur plusieurs appareils
* Tableaux de bord Reports &amp; Analytics
* Signets Reports &amp; Analytics
* Cibles Reports &amp; Analytics
* Événements de calendrier Reports &amp; Analytics
* Ad Hoc Analysis
* Reporting Data Warehouse - [!UICONTROL Experience Platform Query Service] sera la nouvelle interface pour ces cas d’utilisation dans CJA.
* Mobile Services
* Flux de données
