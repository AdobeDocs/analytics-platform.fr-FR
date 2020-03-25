---
title: Prise en charge des fonctionnalités d’analyse du parcours client
description: Fonctionnalités d’analyse du parcours du client par rapport à l’ensemble des fonctionnalités d’Adobe Analytics.
translation-type: tm+mt
source-git-commit: 1d65b22ab2323bebf42b2782b2bab2ed52869a02

---


# Prise en charge des fonctionnalités d’analyse du parcours client

Les tableaux suivants  quelles fonctionnalités d’Adobe Analytics sont prises en charge, partiellement ou non, dans les analyses de parcours du client (CJA). Ces  changeront au fil du temps à mesure que des fonctionnalités sont ajoutées à la CJA.

## Fonctionnalités/composants entièrement pris en charge

| Fonctionnalité | Remarques |
| --- | --- |
| Mesures | CJA tire parti du modèle de données d’expérience (XDM) et prend en charge des mesures illimitées et n’est pas lié au de réussite personnalisé d’Analytics traditionnel. Notez que certaines mesures standard ont été renommées d’Analytics classiques : = Personnes, Visites = Sessions, Accès = . |
| Dimensions | CJA exploite XDM et prend en charge un nombre illimité de dimensions et n’est pas lié au de réussite personnalisé d’Analytics traditionnel. |
| Variables /props  | CJA exploite XDM et prend en charge un nombre illimité de variables de |
| Périodes | La prise en charge du calendrier personnalisé est prévue. |
| Mesures calculées | Notez que les mesures calculées existantes dans l’espace de travail  classique  l’espace de travail ne seront pas portées vers la CJA. |
| Segments | Désormais appelé &quot;&quot; - notez que les segments existants dans  traditionnel de l’espace de travail ne seront pas portés vers CJA. |
| Attribution IQ | Prise en charge complète |
| Traitement du projet | Prise en charge complète |
| Liaison de projet | Prise en charge complète |
| Comparaison de dates | Prise en charge complète |
| Suites de rapports virtuelles | Maintenant appelé [de données](/help/data-views/create-dataview.md). |
| Traitement du composant VRS | Fait désormais partie du  de données. |
| Traitement du temps des rapports | CJA repose exclusivement sur le traitement du temps des rapports. |
| Suppression de GDPR | Notez que GDPR est désormais géré en coordination avec Adobe Experience Platform : CJA hérite des modifications apportées aux données par Experience Platform aux jeux de données sous-jacents. |

## Pris en charge avec des avertissements

| Fonctionnalité | Remarques |
| --- | --- |
| Variable de produit | Variable de produit actuellement disponible pour les  pour les données conformes à l’ de l’d’expérience (en particulier à l’aide de l’objet productListItems). |
| Visualisations | Toutes les visualisations sont prises en charge, à l’exception de la visualisation Carte. |
|  AAM  | Si les clients utilisent les jeux de données du connecteur de données Analytics, ces données feront partie des données ADC. |
| Partage de projet | Le partage de projet est uniquement pris en charge entre les utilisateurs de CJA - il n’existe pas de partage de projet entre CJA et l’espace de travail  traditionnel . |
| Sessionisation personnalisée | Prise en charge de toutes les fonctionnalités de session personnalisée autres que les accès en arrière-plan mobiles. |
| Paramètres de persistance des eVars | Les eVars ne font plus partie de la CJA. Toutefois, les paramètres de persistance font désormais partie des  du de données et sont disponibles pour toutes les dimensions. N’oubliez pas que la persistance est basée sur le traitement de l’heure des rapports et non sur le traitement de la collecte de données. Cela signifie que toute persistance sera basée sur la plage de dates  du plutôt que sur l’ensemble des données. |
| Classifications | Désormais appelés &quot;ensembles de données de recherche&quot;, ils ne sont pas automatiquement importés à partir d’Analytics traditionnels. Ils devront être téléchargés vers AEP avant d’être disponibles dans CJA. |
| Attributs du client | Désormais appelés &quot;jeux de données &quot;, ils ne sont pas automatiquement importés à partir d’Experience Cloud, mais ils devront être téléchargés vers AEP avant d’être disponibles dans CJA. |

## Prise en charge partielle

| Fonctionnalité | Remarques |
| --- | --- |
|  prêtes à l’emploi  dimensions de l’espace de travail (par ex., type de navigateur, type de,de marketing, nombre de visites, etc.) | CJA ne fournit pas ces dimensions de manière native. Pour les clients qui utilisent le connecteur de données Analytics (ADC), certaines de ces dimensions sont disponibles, mais pas toutes. Reportez-vous à notre [documentation sur les variables Analytics prises en charge via ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Panneaux | Le panneau vierge, le panneau d’attribution et le panneau à structure libre sont entièrement pris en charge. La comparaison de segments n’est pas prise en charge. |
| eVars de marchandisage | Les eVars de marchandisage fonctionnent uniquement avec les jeux de données basés sur ADC, à moins qu’elles ne soient strictement conformes au même  XDM (similaire aux limites de de produit ci-dessus). |
| Filtrage des robots | Pour les jeux de données basés sur ADC (Analytics Data Connector), le filtrage des robots est appliqué. La logique générale de filtrage des robots pour d’autres jeux de données n’est pas exécutée par la plateforme d’expérience ou CJA. |
| Règles de traitement | Pour les jeux de données basés sur ADC, les règles de traitement sont toujours appliquées. |
| Rognage d’identité sur plusieurs périphériques | Les clients sont limités à des points de suture &quot;uniques&quot; des données via le service de  de, ou doivent actuellement appliquer cette logique aux données avant l’assimilation des données de la plateforme d’expérience. |

## Non pris en charge actuellement, mais planifié

| Fonctionnalité | Remarques |
| --- | --- |
| Détection des anomalies | Un soutien est prévu. |
| Analyse des contributions | Un soutien est prévu. |
| Segment IQ | Un soutien est prévu. |
| Publication de segments (envoi de segments de Workspace vers Experience Cloud) | Un soutien est prévu. |
| Autorisations utilisateur/ de de données | Tous les utilisateurs de CJA ont le même  de - cela signifie que tous les utilisateurs ont accès à toutes les connexions, à tous les de données, etc. En gros, tous les utilisateurs sont des utilisateurs de niveau administrateur dans CJA. Le soutien est prévu pour 2020. |
| Téléchargement CSV | Un soutien est prévu. |
| Rapports/Projets planifiés | Un soutien est prévu. |
| Alertes | Un soutien est prévu. |
| Calendriers personnalisés | Un soutien est prévu. |
| Canaux marketing | Un soutien est prévu. |
| Exportation PDF | Un soutien est prévu. |
| Accès à l&#39;API  | Prise en charge prévue - sera disponible uniquement avec API 2.0. |
| Dessin d’ID via le graphique de périphérique | Un soutien est prévu. |

## Support non encore planifié

| Fonctionnalité | Remarques |
| --- | --- |
| A4T | Le soutien n&#39;est pas encore prévu. |
| Chemin | Le soutien n&#39;est pas encore prévu. |
| Advertising Cloud | Le soutien n&#39;est pas encore prévu. |
| Créateur de rapports (module externe Excel) | Le soutien n&#39;est pas encore prévu. |
| Activity Map  | Le soutien n&#39;est pas encore prévu. |
| Créateur de règles de classification | Le soutien n&#39;est pas encore prévu. |
| Sources de données récapitulatives | Le soutien n&#39;est pas encore prévu. |
|  en temps réel | Le soutien n&#39;est pas encore prévu. |

## Ne sera jamais pris en charge

| Fonctionnalité | Remarques |
| --- | --- |
| Mesure Personnes à l’aide de la coopération entre plusieurs périphériques |  |
|  des rapports et analyses |  |
| Signets Rapports et analyses |  |
|  des rapports et analyses |  |
| du calendrier des rapports et analyses |  |
| Ad Hoc Analysis |  |
| Data Warehouse Création de rapports | Le service de Adobe Experience Platform constituera la nouvelle interface pour ces cas d’utilisation dans CJA. |
| Mobile Services |  |
| Flux de données |  |
