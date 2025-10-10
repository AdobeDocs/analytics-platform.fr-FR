---
title: Comparer le traitement des données dans les fonctionnalités de création de rapports d’Adobe Analytics et de Customer Journey Analytics
description: Comprendre les différences de traitement des données dans les différentes fonctionnalités de création de rapports
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: Basics
role: User
source-git-commit: 0e9dc47b80db142801a94dcbf31470d99a610949
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 64%

---

# Comparer le traitement des données dans Adobe Analytics et Customer Journey Analytics

Vous devez souvent traiter les données avant qu’elles ne soient utiles pour la création de rapports. Vous pouvez traiter ces données à plusieurs étapes du parcours, qui s’étend de la collecte de données à la génération de votre rapport ou visualisation.

Dans Adobe Analytics, la grande partie de ce traitement des données survient immédiatement après la collecte des données. Des fonctionnalités telles que les règles VISTA, les règles de traitement et les règles de traitement des canaux marketing sont disponibles pour prendre en charge ce **traitement au moment de la collecte**.
Les données sont ensuite stockées. Vous pouvez appliquer un traitement supplémentaire au moment du rapport. Vous pouvez notamment ventiler des dimensions, appliquer une segmentation ou sélectionner un modèle d’attribution différent. Ce **traitement au moment du rapport** survient à la volée.

Dans Adobe Analytics, le traitement au moment du rapport représente généralement une quantité de traitement inférieure à celle qui se produit au moment de la collecte.

![Traitement au moment de la collecte Adobe Analytics](../assets/aa-processing.png)

En revanche, Customer Journey Analytics est conçu pour nécessiter un traitement initial minimal de la collecte avant l’organisation et le stockage des données. L’architecture sous-jacente de Customer Journey Analytics est conçue pour fonctionner avec les données stockées au moment du rapport. Customer Journey Analytics offre sa puissante fonctionnalité de traitement de la période de rapport, et pas seulement dans Analysis Workspace. D’autres fonctionnalités de traitement de la période de rapport sont disponibles par le biais de la définition de [composants](/help/data-views/component-settings/overview.md) et [&#x200B; champs dérivés](/help/data-views/derived-fields/derived-fields.md) dans vos vues de données.

![Traitement au moment du rapport de Customer Journey Analytics](../assets/cja-processing.png)

Comprendre les différences de traitement des données dans les différentes fonctionnalités de création de rapports peut vous aider à comprendre quelles mesures sont disponibles à quel moment, et pourquoi elles peuvent être différentes.

Par exemple, la mesure *visites* est définie comme mesure dans Adobe Analytics au moment du traitement des données. Et *sessions* est calculé en tant que mesure dans Customer Journey Analytics au moment du rapport. Par conséquent, les deux mesures peuvent différer en fonction des règles de définition de session dans une vue de données Customer Journey Analytics.

En outre, les visites et les sessions en tant que mesures ne sont pas disponibles dans les jeux de données créés par le connecteur source Analytics. Vous devrez donc définir la session dans votre logique de requête pour effectuer des comparaisons.

## Terminologie {#terms}

Le tableau ci-dessous définit la terminologie des différents types de logiques de traitement appliqués à Adobe Analytics et Customer Journey Analytics :

| Terme | Définition | Remarques |
| --- | --- | --- |
| Traitement au moment de la collecte | Logique exécutée lors de la collecte et du traitement des données, avant leur stockage à des fins de création de rapports et d’analyse. | Cette logique est étroitement incluse aux données historiques et n’est généralement pas modifiable sans difficulté. |
| Traitement au moment du rapport | Logique exécutée au moment de l’exécution d’un rapport. | Cette logique peut être appliquée de manière non destructive aux données futures et historiques au moment de l’exécution du rapport. |
| Logique au niveau des accès | Logique appliquée ligne par ligne. | Exemples : règles de traitement, VISTA, certaines règles de canaux marketing. |
| Logique au niveau des visites | Logique appliquée au niveau des visites. | Exemples : définition de visite et de session. |
| Logique au niveau des visiteurs | Logique appliquée au niveau de la personne. | Exemple : groupement de plusieurs appareils/cross-canal des personnes. |
| Logique de segment | Évaluation des règles de segment pour les événements/visites/personnes (événement/session/personne). | Exemple : les personnes ayant acheté des chaussures rouges. |
| Mesures calculées | Évaluation des mesures personnalisées créées par le client. Les mesures calculées peuvent reposer sur des formules complexes, y compris des segments. | Par exemple, le nombre de personnes qui ont acheté des chaussures rouges. |
| Logique d’attribution | Logique calculant l’attribution. | Exemple : persistance de l’eVar. |
| Paramètres de composant | Application de personnalisations aux mesures ou aux dimensions, comme l’attribution, le comportement, le format, etc | Exemple : compartimentage de valeurs permettant de combiner les valeurs numériques en fonction d’une plage |
| Champs dérivés | Logique qui s’applique aux champs de schéma ou standard dans le cadre de la définition de composants dans une vue de données. | Exemple : création d’une nouvelle dimension de canal marketing |

{style="table-layout:auto"}

Adobe Analytics et maintenant Customer Journey Analytics ont amélioré leur flexibilité au fil des années, en permettant d’exécuter la logique des données au niveau des personnes, des visiteurs et des visiteuses au moment de l’exécution du rapport.

## Types de traitement des données {#types}

Les étapes de traitement des données effectuées par Adobe Analytics et Customer Journey Analytics et le timing de ces étapes varient d’une fonctionnalité à l’autre. Le tableau ci-dessous résume les types de traitement des données disponibles pour chaque fonctionnalité et le moment où le traitement des données est appliqué.

| Fonctionnalité | Appliqué au moment du traitement | Appliqué au moment du rapport | Non disponible | Remarques |
| --- | --- | --- | --- | --- |
| Création de rapports [Adobe Analytics](https://experienceleague.adobe.com/fr/docs/analytics)<br/>(sans inclure les fonctionnalités d’attribution avancées ni les suites de rapports virtuelles avec traitement de la période des rapports) | <ul><li>[Règles de traitement](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/c-processing-rules/processing-rules)</li><li>[Règles VISTA](https://experienceleague.adobe.com/fr/docs/analytics/technotes/terms)</li><li>[Règles des canaux marketing](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules) au niveau des accès</li><li>Règles des canaux marketing au niveau des visites (voir note)</li><li>Définition de visite</li><li>Logique d’attribution</li></ul> | <ul><li>Logique de segment</li><li>Mesures calculées</li></ul> | <ul><li>Analyses entre appareils (voir note)</li></ul> | <ul><li>Les analyses entre appareils nécessitent l’utilisation de suites de rapports virtuelles avec le traitement de la période de rapport.</li><li>Les « règles des canaux marketing au niveau des visites » incluent les éléments suivants : **Est la première page de la visite**, **Remplacer le canal Dernière touche**, et **Expiration du canal marketing**. (Voir la [documentation](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels).)</li></ul> |
| [Data Warehouse](https://experienceleague.adobe.com/fr/docs/analytics/export/data-warehouse/data-warehouse) Adobe Analytics | <ul><li>Règles de traitement</li><li>Règles VISTA</li><li>Règles des canaux marketing au niveau des accès</li><li>Règles des canaux marketing au niveau des visites</li><li>Définition de visite</li><li>Logique d’attribution</li></ul> | <ul><li>Logique de segment</li></ul> | <ul><li>Mesures calculées</li><li>Analyses entre appareils</li></ul> |     |
| [Flux de données](https://experienceleague.adobe.com/fr/docs/analytics/export/analytics-data-feed/data-feed-overview) Adobe Analytics | <ul><li>Règles de traitement</li><li>Règles VISTA</li><li>Règles des canaux marketing au niveau des accès</li><li>Règles des canaux marketing au niveau des visites</li><li>Définition de visite (champ visitnum)</li><li>Logique d’attribution (dans les colonnes « Post »)</li></ul> |   | <ul><li>Logique de segment</li><li>Mesures calculées</li><li>Analyses entre appareils</li></ul> | <ul><li>Les mappages d’ID pour certaines colonnes liées aux canaux marketing dans les flux de données ne sont pas inclus dans les flux de données. (Voir la [documentation sur les flux de données](https://experienceleague.adobe.com/fr/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference).)</li></ul> |
| [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) Adobe Analytics | <ul><li> Règles de traitement</li><li>Règles VISTA</li><ul> |   | <ul><li>Règles des canaux marketing au niveau des accès</li><li>Règles des canaux marketing au niveau des visites</li><li>Logique de visite</li><li>Logique d’attribution</li><li>Logique de segment</li><li>Mesures calculées</li><li>Analyses entre appareils</li></ul> |  |
| Adobe Analytics [fonctionnalités d’attribution avancées](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/attribution/overview) | <ul><li>Règles de traitement</li><li>Règles VISTA</li><li>Définition de visite (voir note)</li><li>Analyses entre appareils (voir note)</li></ul> | <ul><li>Règles des canaux marketing au niveau des accès (voir note)</li><li>Logique d’attribution des règles des canaux marketing au niveau des visites (voir note)</li><li>Logique de segment</li><li>Mesures calculées</li></ul> |  | <ul><li>Les analyses entre appareils nécessitent l’utilisation de suites de rapports virtuelles avec le traitement de la période de rapport.</li><li>Les fonctionnalités d’attribution avancées de Core Analytics utilisent des canaux marketing entièrement dérivés au moment du rapport (c’est-à-dire des valeurs moyennes dérivées).</li><li>Les fonctionnalités d’attribution avancées utilisent une définition de visite au moment du traitement, sauf lorsqu’elles sont utilisées dans une suite de rapports virtuelle de traitement de la période de rapport.</li></ul> |
| Suites de rapports virtuelles Adobe Analytics avec [traitement au moment de la création de rapports](https://experienceleague.adobe.com/fr/docs/analytics/components/virtual-report-suites/vrs-report-time-processing) | <ul><li>Règles de traitement</li><li>Règles VISTA</li><li>[Analyses entre appareils](https://experienceleague.adobe.com/fr/docs/analytics/components/cda/overview)</li></ul> | <ul><li>Définition de visite</li><li>Logique d’attribution</li><li>Logique de segment</li><li>Mesures calculées</li><li>Autres paramètres de traitement au moment de la création de rapports des suites de rapports virtuelles</li></ul> | <ul><li>Règles des canaux marketing au niveau des accès</li><li>Règles des canaux marketing au niveau des visites</li></ul> | <ul><li>Voir la [documentation](https://experienceleague.adobe.com/fr/docs/analytics/components/virtual-report-suites/vrs-report-time-processing) sur le traitement au moment de la création de rapports des suites de rapports virtuelles.</li></ul> |
| Jeu de données basé sur le [connecteur source Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/adobe-applications/analytics) dans le lac de données Adobe Experience Platform | <ul><li>Règles de traitement</li><li>Règles VISTA</li><li>Règles des canaux marketing au niveau des accès</li><li>Assemblage basé sur les champs (voir note)</li></ul> |   | <ul><li>[Règles des canaux marketing au niveau des visites](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels)</li><li>Logique de visite</li><li>Logique d’attribution</li><li>Logique de segment</li></ul> | <ul><li>Appliquer votre propre logique de segment et vos propres mesures calculées</li><li>L’assemblage basé sur les champs crée un jeu de données assemblé distinct en plus de celui créé par le connecteur source Analytics.</li></ul> |
| Création de rapports [Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-landing) | <ul><li>Mise en œuvre dans le cadre de la collecte de données Adobe Experience Platform</li></ul> | <ul><li>Définition de session</li><li>Paramètres de la [vue de données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/data-views)<li>Logique d’attribution</li><li>Mesures calculées</li><li>Logique de segment</li></ul> | <ul><li>Règles des canaux marketing au niveau des visites</li></ul> | <ul><li>Utilisez des jeux de données groupés pour tirer parti de l’analyse cross-canal.</li></ul> |

{style="table-layout:auto"}
