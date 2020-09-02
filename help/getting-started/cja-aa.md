---
title: Support pour les fonctionnalités Customer Journey Analytics
description: Comparaison des fonctionnalités Customer Journey Analytics à l’ensemble des fonctionnalités d’Adobe Analytics.
translation-type: tm+mt
source-git-commit: 9733d6471e6f1c886fd27b702654349d6760870c
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 97%

---


# Support pour les fonctionnalités Customer Journey Analytics

Les tableaux suivants liste les fonctionnalités d’Adobe Analytics prises en charge, partiellement prises en charge ou non par Customer Journey Analytics (CJA). Ces listes seront modifiées à mesure que des fonctionnalités sont ajoutées à CJA.

## Fonctionnalités/composants entièrement pris en charge

| Fonctionnalité | Remarques |
| --- | --- |
| Mesures | CJA exploite le Modèle de données d’expérience (XDM) et prend en charge un nombre illimité de mesures, et n’est pas lié aux événements de succès personnalisés traditionnellement utilisés dans Analytics. Notez que certaines mesures standard ont été renommées par rapport à Analytics : Visiteurs = Personnes, Visites = Sessions, Accès = Événements. |
| Dimensions | CJA exploite XDM et prend en charge un nombre illimité de dimensions, et n’est pas lié aux événements de succès personnalisés traditionnellement utilisés dans Analytics. |
| Variables/Propriétés de liste | CJA exploite XDM et prend en charge un nombre illimité de variables de liste. |
| Périodes | La prise en charge du calendrier personnalisé est planifiée. |
| Mesures calculées | Notez que les mesures calculées existantes dans Analysis Workspace ne seront pas transférées vers CJA. |
| Segments | Désormais appelés « Filtres » : notez que les segments existants dans Analysis Workspace ne seront pas transférés vers CJA. |
| Détection des anomalies | Prise en charge complète en septembre 2020 |
| Attribution IQ | Prise en charge complète. |
| Traitement du projet | Prise en charge complète. |
| Liaison de projet | Prise en charge complète. |
| Comparaison de dates | Prise en charge complète. |
| Suites de rapports virtuelles | Maintenant appelées [Vues de données](/help/data-views/create-dataview.md). |
| Traitement du composant VRS | Fait désormais partie des Vues de données. |
| Traitement de la période de rapport | CJA repose exclusivement sur le Traitement de la période de rapport. |
| Suppression du RGPD | Veuillez noter que le RGPD est maintenant géré en coordination avec [!UICONTROL Experience Platform] - CJA hérite des changements de données apportés par [!UICONTROL Experience Platform] aux jeux de données sous-jacents. |

## Pris en charge avec des mises en garde

| Fonctionnalité | Remarques |
| --- | --- |
| Variable Product | La variable Product actuellement disponible pour le rapports pour les données conformes au schéma d’événement d’expérience (en particulier à l’aide de l’objet productListItems). |
| Visualisations | Toutes les visualisations sont prises en charge, à l’exception de la visualisation en correspondance. |
| AAM Audiences | Si les clients utilisent des jeux de données [!UICONTROL Analytics Data Connector], ces données feront partie des données ADC. |
| Partage des projets | Le partage des projets est uniquement pris en charge entre les utilisateurs de CJA - il n’existe pas de partage de projet entre CJA et l’Analysis Workspace traditionnel. |
| Session personnalisée | Prise en charge de toutes les fonctionnalités de session personnalisée autres que les accès mobiles en arrière-plan. |
| Paramètres de persistance des eVars | Les eVars ne font plus partie de CJA. Toutefois, les paramètres de persistance font désormais partie des Vues de données et sont disponibles pour toutes les dimensions. Gardez à l’esprit que la persistance repose sur le Traitement de la période de rapport et non sur le traitement de la collecte de données. Cela signifie que toute persistance sera basée sur la plage de dates du rapports plutôt que sur l’ensemble des données. |
| Classifications | Désormais appelés « Jeux de données de recherche », ils ne sont pas automatiquement importés à partir de l’Analytics traditionnel. Ils devront être transférés sur AEP avant d’être disponibles dans CJA. |
| Attributs du client | Désormais appelés « Jeux de données de profil », ils ne sont pas automatiquement importés à partir d’Experience Cloud, mais devront être transférés sur AEP avant d’être disponibles dans CJA. |

## Prise en charge partielle

| Fonctionnalité | Remarques |
| --- | --- |
| Dimensions Analysis Workspace prêtes à l’emploi (par exemple, Type de navigateur, Type de référent, Canaux marketing, Nombre de visites, etc.) | CJA ne fournit pas ces dimensions de manière native. Pour les clients qui utilisent Analytics Data Connector (ADC), certaines de ces dimensions sont disponibles, mais pas toutes. Consultez notre [documentation sur les variables Analytics prises en charge par ADC](https://docs.adobe.com/content/help/fr-FR/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Panneaux | Le panneau vierge, le panneau Attribution, le panneau à structure libre et les Quick Insights sont entièrement pris en charge. Les panneaux Comparaison des segments et Analytics for Target (A4T) ne sont pas pris en charge. |
| eVars de marchandisage | Les eVars de marchandisage ne fonctionnent qu’avec des jeux de données basés sur ADC, sauf si elles se conforment strictement au même schéma XDM (semblable aux limites des listes de produits ci-dessus). |
| Filtrage des robots | Pour les jeux de données basés sur ADC (Analytics Data Connector), le filtrage des robots est appliqué. La logique générale de filtrage des robots pour d’autres jeux de données n’est pas exécutée par [!UICONTROL Experience Platform] ou CJA. |
| Règles de traitement | Pour les jeux de données basés sur ADC, les règles de traitement restent appliquées. |
| Ajout d’identités sur plusieurs appareils | Les clients sont limités à des assemblages « en une fois » des données par l’intermédiaire du Query Service, ou doivent actuellement appliquer cette logique aux données avant l’ingestion des données [!UICONTROL Experience Platform]. |

## Non pris en charge actuellement, mais planifié

| Fonctionnalité | Remarques |
| --- | --- |
| Analyse des contributions | La prise en charge est planifiée. |
| Segment IQ | La prise en charge est planifiée. |
| Publication de segments (envoi de segments de Workspace à Experience Cloud) | La prise en charge est planifiée. |
| Autorisations utilisateur/Contrôles d’accès aux données | Tous les utilisateurs de CJA ont les mêmes contrôles d’accès - cela signifie que tous les utilisateurs ont accès à toutes les connexions, vues de données, etc. Fondamentalement, tous les utilisateurs sont des utilisateurs de niveau administrateur dans CJA. La prise en charge est planifiée pour 2020. |
| Téléchargement CSV | La prise en charge est planifiée. |
| Rapports/projets planifiés | La prise en charge est planifiée. |
| Alertes | La prise en charge est planifiée. |
| Calendriers personnalisés | La prise en charge est planifiée. |
| Canaux marketing | La prise en charge est planifiée. |
| Exportation PDF | La prise en charge est planifiée. |
| Accès à l’API de création de rapports | La prise en charge est planifiée. Elle ne sera disponible qu’avec l’API 2.0. |
| Assemblage d’ID via le graphique d’appareil | La prise en charge est planifiée. |

## La prise en charge n’est pas encore planifiée.

| Fonctionnalité | Remarques |
| --- | --- |
| A4T | La prise en charge n’est pas encore planifiée. |
| Media Analytics | La prise en charge n’est pas encore planifiée. |
| Advertising Cloud | La prise en charge n’est pas encore planifiée. |
| Report Builder (module externe Excel) | La prise en charge n’est pas encore planifiée. |
| Activity Map | La prise en charge n’est pas encore planifiée. |
| Créateur de règles de classification | La prise en charge n’est pas encore planifiée. |
| Sources de données récapitulatives | La prise en charge n’est pas encore planifiée. |
| Création de rapports en temps réel | La prise en charge n’est pas encore planifiée. |

## Ne sera jamais prise en charge

* Mesure Personnes à l’aide d’une opération Coop sur plusieurs appareils
* Tableaux de bord Reports &amp; Analytics
* Signets Reports &amp; Analytics
* Cibles Reports &amp; Analytics
* Événements de calendrier Reports &amp; Analytics
* Ad Hoc Analysis
* rapports Data Warehouse - [!UICONTROL Service Requête Experience Platform] sera la nouvelle interface pour ces cas d&#39;utilisation dans CJA.
* Mobile Services
* Flux de données
