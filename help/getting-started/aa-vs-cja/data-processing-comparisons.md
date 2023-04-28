---
title: Comparaison du traitement des données dans les fonctionnalités de création de rapports d’Adobe Analytics et de CJA
description: Comprendre les différences de traitement des données dans les différentes fonctionnalités de création de rapports
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
source-git-commit: 80d0b95f3bc3d785d9ca7e4b50aa1bd8440373c2
workflow-type: tm+mt
source-wordcount: '1012'
ht-degree: 91%

---

# Comparer le traitement des données dans Adobe Analytics et Customer Journey Analytics.

<!--

You often need the ability to process data before it is useful for reporting. You can process that data at several stages in the journey that spans from collecting data to generating your report or visualization.

In Adobe Analytics most of that processing of data occurs immediately after collecting the data. Functionalties like VISTA Rules, Processing Rules, Marketing Channels Processing Rules are available to support this **collection-time processing**. 
The data is then stored and at report time you can apply additional processing. For example, break down dimensions, apply segmentation, or  select a different attribution model. This **report-time processing** happens on the fly. 

In Adobe Analytics, report-time processing commonly represents a smaller amount of processing  than what happens at collection-time.

![Adobe Analytics collection-time processing](../assets/aa-processing.png)

In contrast, Customer Journey Analytics (CJA) is designed to require minimal upfront collection-time processing before data being is organized and stored. The underlying architecture of CJA is more designed to work with the stored data at report-time and offers its powerful report-time processing functionality not only in  Workspace but also, even more importantly, through the definition of components in your Data Views. 

![CJA report-time processing](../assets/cja-processing.png)

-->


Comprendre les différences de traitement des données dans les différentes fonctionnalités de création de rapports peut vous aider à comprendre quelles mesures sont disponibles à quel moment, et pourquoi elles peuvent être différentes.

Par exemple, puisque la mesure « visites » dans Adobe Analytics est définie au moment du traitement des données et que la mesure « sessions » dans CJA est calculée au moment du rapport, les deux mesures peuvent différer en fonction des règles utilisées pour la définition de session dans la vue de données CJA.

En outre, ni les visites, ni les sessions en tant que mesures ne sont disponibles dans les jeux de données créés par le connecteur source Analytics, ce qui vous obligerait donc à définir la session dans votre logique de requête pour effectuer des comparaisons.

## Terminologie {#terms}

Le tableau ci-dessous définit la terminologie des différents types de logiques de traitement appliqués à Adobe Analytics et CJA :

| Terme | Définition | Remarques |
| --- | --- | --- |
| Traitement de la collecte | Logique exécutée lorsque les données sont collectées et traitées, avant d’être stockées à des fins de création de rapports et d’analyse. | Cette logique est étroitement incluse aux données historiques et n’est généralement pas modifiable sans difficulté. |
| Traitement de la période de rapport | Logique exécutée au moment de l’exécution d’un rapport. | Cette logique peut être appliquée de manière non destructive aux données futures et historiques au moment de l’exécution du rapport. |
| Logique au niveau des accès | Logique appliquée ligne par ligne. | Exemples : règles de traitement, VISTA, certaines règles de canaux marketing. |
| Logique au niveau des visites | Logique appliquée au niveau des visites. | Exemples : définition de visite et de session. |
| Logique au niveau des visiteurs | Logique appliquée au niveau des visiteurs. | Exemple : connexité des visiteurs sur plusieurs appareils/canaux. |
| Logique de segment (filtre) | Évaluation des règles de segment (filtre) pour les accès/visites/visiteurs (événement/session/personne). | Exemple : les personnes ayant acheté des chaussures rouges. |
| Mesures calculées | Évaluation des mesures personnalisées créées par le client qui peuvent reposer sur des formules complexes, notamment des segments et des filtres. | Exemple : le nombre de personnes ayant acheté des chaussures rouges. |
| Logique d’attribution | Logique calculant l’attribution. | Exemple : persistance de l’eVar. |
| Paramètres de composant | Application de personnalisations à des mesures ou à des dimensions, comme l’attribution, le comportement, le format, etc. | Exemple : groupement de valeurs pour combiner des valeurs numériques basées sur une plage |
| Champs personnalisés | La logique s’applique au schéma ou aux champs standard dans le cadre de la définition des composants dans une vue de données. | Exemple : création d’une nouvelle dimension de canal marketing |

{style="table-layout:auto"}

Adobe Analytics et maintenant Customer Journey Analytics ont amélioré leur flexibilité au fil des années, en permettant d’exécuter la logique des données au niveau des visites et des visiteurs au moment de l’exécution du rapport.

## Types de traitement des données {#types}

Les étapes de traitement des données réalisées pour Adobe  et CJA et le moment d’exécution de ces étapes varient parmi les différentes fonctionnalités Analytics. Le tableau ci-dessous résume les types de traitement des données disponibles pour chaque fonctionnalité Analytics et le moment où le traitement des données est appliqué.

| Fonctionnalité | Appliqué au moment du traitement | Appliqué au moment du rapport | Non disponible | Remarques |
| --- | --- | --- | --- | --- |
| Création de rapports [Core AA](https://experienceleague.adobe.com/docs/analytics.html?lang=fr)<br/>(sans inclure les suites de rapports d’Attribution IQ ni les suites de rapports virtuelles avec traitement de la période des rapports) | <ul><li>[Règles de traitement](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=fr)</li><li>[Règles VISTA](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=fr)</li><li>[Règles des canaux marketing](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=fr) au niveau des accès</li><li>Règles des canaux marketing au niveau des visites (voir note)</li><li>Définition de visite</li><li>Logique d’attribution</li></ul> | <ul><li>Logique de segment</li><li>Mesures calculées</li></ul> | <ul><li>Analyses entre appareils (voir note)</li></ul> | <ul><li>Les analyses entre appareils nécessitent l’utilisation de suites de rapports virtuelles avec traitement de la période de rapport.</li><li>Les « règles des canaux marketing au niveau des visites » incluent les éléments suivants : **Est la première page de la visite**, **Remplacer le canal Dernière touche**, et **Expiration du canal marketing**. (Voir la [documentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=fr).)</li></ul> |
| [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=fr) pour Core AA | <ul><li>Règles de traitement</li><li>Règles VISTA</li><li>Règles des canaux marketing au niveau des accès</li><li>Règles des canaux marketing au niveau des visites</li><li>Définition de visite</li><li>Logique d’attribution</li></ul> | <ul><li>Logique de segment</li></ul> | <ul><li>Mesures calculées</li><li>Analyses entre appareils</li></ul> |  |
| [Flux de données](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=fr) pour Core AA | <ul><li>Règles de traitement</li><li>Règles VISTA</li><li>Règles des canaux marketing au niveau des accès</li><li>Règles des canaux marketing au niveau des visites</li><li>Définition de visite (champ visitnum)</li><li>Logique d’attribution (dans les colonnes « Post »)</li></ul> |  | <ul><li>Logique de segment</li><li>Mesures calculées</li><li>Analyses entre appareils</li></ul> | <ul><li>Les mappages d’ID pour certaines colonnes liées aux canaux marketing dans les flux de données ne sont pas inclus dans les flux de données. (Voir la [documentation sur les flux de données](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=fr).)</li></ul> |
| [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) pour Core AA | <ul><li> Règles de traitement</li><li>Règles VISTA</li><ul> |  | <ul><li>Règles des canaux marketing au niveau des accès</li><li>Règles des canaux marketing au niveau des visites</li><li>Logique de visite</li><li>Logique d’attribution</li><li>Logique de segment</li><li>Mesures calculées</li><li>Analyses entre appareils</li></ul> |  |
| [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=fr) pour Core AA | <ul><li>Règles de traitement</li><li>Règles VISTA</li><li>Définition de visite (voir note)</li><li>Analyses entre appareils (voir note)</li></ul> | <ul><li>Règles des canaux marketing au niveau des accès (voir note)</li><li>Logique d’attribution des règles des canaux marketing au niveau des visites (voir note)</li><li>Logique de segment</li><li>Mesures calculées</li></ul> |  | <ul><li>Les analyses entre appareils nécessitent l’utilisation de suites de rapports virtuelles avec traitement de la période de rapport.</li><li>Attribution IQ dans Core Analytics utilise des canaux marketing entièrement dérivés au moment du rapport (c’est-à-dire des valeurs moyennes dérivées).</li><li>Attribution IQ utilise une définition de visite au moment du traitement, sauf lorsqu’il est utilisé dans une suite de rapports virtuelle de traitement de la période de rapport.</li></ul> |
| Suites de rapports virtuelles Core AA avec [traitement de la période de rapport](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=fr) | <ul><li>Règles de traitement</li><li>Règles VISTA</li><li>[Analyses entre appareils](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=fr)</li></ul> | <ul><li>Définition de visite</li><li>Logique d’attribution</li><li>Logique de segment</li><li>Mesures calculées</li><li>Autres paramètres de traitement de la période de rapport des suites de rapports virtuelles</li></ul> | <ul><li>Règles des canaux marketing au niveau des accès</li><li>Règles des canaux marketing au niveau des visites</li></ul> | <ul><li>Voir la [documentation](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=fr) sur le traitement de la période de rapport des suites de rapport virtuelles.</li></ul> |
| Jeu de données reposant sur le [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr) dans le lac de données AEP | <ul><li>Règles de traitement</li><li>Règles VISTA</li><li>Règles des canaux marketing au niveau des accès</li><li>Assemblage basé sur les champs (voir note)</li></ul> |  | <ul><li>[Règles des canaux marketing au niveau des visites](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=fr)</li><li>Logique de visite</li><li>Logique d’attribution</li><li>Logique de filtre</li></ul> | <ul><li>Vous devez appliquer votre propre logique de filtre ainsi que vos propres mesures calculées.</li><li>L’assemblage basé sur les champs crée un jeu de données assemblé distinct en plus de celui créé par le connecteur source Analytics.</li></ul> |
| Création de rapports [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=fr) | <ul><li>Mise en oeuvre dans le cadre de la collecte de données Adobe Experience Platform</li></ul> | <ul><li>Définition de session</li><li>Paramètres de la [vue de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=fr)<li>Logique d’attribution</li><li>Mesures calculées</li><li>Logique de filtre</li></ul> | <ul><li>Règles des canaux marketing au niveau des visites</li></ul> | <ul><li>Vous devez utiliser un jeu de données assemblé pour tirer profit de l’assemblage basé sur les champs.</li></ul> |

{style="table-layout:auto"}
