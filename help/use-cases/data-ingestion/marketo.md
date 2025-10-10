---
title: Rapport sur les données Marketo Engage
description: Découvrez comment créer des rapports sur les données Marketo Engage dans Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
source-git-commit: fedb1337b32e44fc00989bace6a4d1788043f55f
workflow-type: tm+mt
source-wordcount: '1059'
ht-degree: 13%

---

# Rapport sur les données Marketo Engage

Vous pouvez exploiter les jeux de données Marketo Engage disponibles dans Experience Platform pour fournir des solutions d’analyse et de création de rapports utiles aux spécialistes du marketing B2B. Créez ensuite des rapports sur ces jeux de données dans Customer Journey Analytics.

Gardez à l’esprit que :

* Le compte rendu des performances de Marketo Engage est idéal pour mesurer et optimiser les programmes marketing directement dans Marketo. Il est rapide, normatif et convivial pour les marketeurs.
* Customer Parcours Analytics offre une solution d’analyse personnalisable et beaucoup plus large pour les parcours clients qui s’étendent sur plusieurs canaux, produits et unités commerciales, y compris, mais sans s’y limiter, les données Marketo.

Voir [comparaison des rapports](#reporting-comparison) pour plus d’informations.

>[!NOTE]
>
>Vous pouvez envisager le [B2B edition Customer Journey Analytics](/help/getting-started/cja-b2b-edition.md) pour tirer le meilleur parti des données Marketo Engage. Vous pouvez combiner des jeux de données Marketo Engage avec des jeux de données de compte et de recherche. Et créer des rapports sur le niveau de compte et d’opportunité dans Customer Journey Analytics B2B edition.
>


Pour créer des rapports sur les données Marketo Engage dans Customer Journey Analytics :

+++ &#x200B;1. Mapper les champs de données source Marketo à leurs cibles XDM

Mappez les objets [Personnes](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo) et [Activités](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo) à leurs champs cibles de schéma XDM respectifs.

+++

+++ &#x200B;2. Ingestion de données Marketo dans Adobe Experience Platform

Utilisez le [connecteur Marketo Engage](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo) pour importer les données de Marketo dans Experience Platform et les tenir à jour à l’aide des applications connectées à Platform.

+++

+++ &#x200B;3. Configurer une connexion à ce jeu de données dans Customer Journey Analytics

Pour générer des rapports sur des jeux de données Experience Platform, vous devez d’abord établir une connexion entre les jeux de données dans Experience Platform et Customer Journey Analytics. Voir [Créer ou modifier une connexion](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-connections/create-connection).

+++


+++ &#x200B;4. Créer une ou plusieurs vues de données

Une [vue de données](/help/data-views/data-views.md) est un conteneur spécifique à Customer Journey Analytics qui vous permet de déterminer comment interpréter les données d’une connexion. Elle spécifie toutes les dimensions et mesures disponibles dans Analysis Workspace, soit dans le cas qui nous intéresse, les mesures et dimensions spécifiques à Marketo. Elle spécifie également les colonnes à partir desquelles ces dimensions et mesures obtiennent leurs données. Les vues de données sont définies en vue de la création de comptes rendus des performances dans Analysis Workspace.

+++ 

+++ &#x200B;5. Rapport dans Analysis Workspace

Voici un cas pratique que vous pouvez explorer : Combien de visites de pages web par prospect avez-vous eues en avril-juin 2020 ?

1. Ouvrez [Analytics Workspace](/help/analysis-workspace/home.md) et créez un projet.
Les clients disposant de la plateforme de données clients B2B/B2P peuvent effectuer une analyse de type B2C dans Customer Journey Analytics. Les objets B2B ne sont pas encore disponibles.

1. Créez un [segment](/help/components/segments/seg-create.md) pour les pages vues web comme suit - Type d’événement = web.webpagedetails.pageViews :

   ![Fenêtre de définition affichant l’événement et le type d’événement](../assets/marketo-filter.png)

1. Extrayez le segment que vous avez créé dans le tableau à structure libre - Pages vues web, puis extrayez la période Mois. Cette action permet d’obtenir les visites de pages web par prospect chaque mois :

   ![Tableau à structure libre présentant les événements par mois.](../assets/marketo-freeform.png)

1. Vous pouvez également extraire les dimensions suivantes : Clé de personne ou adresse e-mail professionnelle. Cette action vous donne les visites de pages web par prospect :

   ![Tableau à structure libre affichant les événements et workEmail.Address et les vues de page web.](../assets/marketo-freeform2.png)

Les données Marketo Engage dans Customer Journey Analytics peuvent différer de ce que vous voyez dans les rapports de Marketo Engage.

+++


## Comparaison des rapports

La comparaison suivante entre les rapports dans Customer Journey Analytics et Marketo Engage présente certaines différences importantes au niveau des fonctionnalités d’analyse, de la flexibilité, des sources de vérité et des cas d’utilisation.

### Customer Journey Analytics

Customer Journey Analytics est un outil d’analyse cross-canal avancé basé sur Adobe Experience Platform. Customer Journey Analytics est conçu pour les équipes d’entreprise qui ont besoin de rapports puissants, flexibles et personnalisables sur les sources de données numériques et hors ligne.

#### Fonctionnalités principales

* **Sources de données** : peut combiner plusieurs jeux de données (web, CRM, e-mail, centre d’appel, hors ligne, Marketo, etc.) pour la création de rapports à 360° sur le parcours client.
* **Analyse en libre-service** : espace de travail par glisser-déposer avec des tableaux de bord et des visualisations hautement interactifs et personnalisables.
* **Attribution avancée** : prend en charge des modèles d’attribution complexes, multipoint et personnalisés pour toutes les données connectées, et pas seulement les programmes marketing.
* **Analyse de l’audience et du cheminement** : segmentation profonde, analyse des cohortes et des chemins d’accès sur les parcours des acheteurs.
* **Informations exploitables** : permet une orchestration pilotée par les données (par exemple, renvoyer les informations aux moteurs de marketing ou de personnalisation).
* **À l’échelle de l’entreprise** : adapté aux organisations ayant besoin d’une gouvernance d’entreprise, de plusieurs marques et d’un volume de données élevé.

#### Cas d’utilisation standard de Customer Journey Analytics

* Mappage avancé du parcours client sur plusieurs canaux et points de contact.
* Segmentation et combinaison complexes des données en ligne et hors ligne.
* Tableaux de bord des indicateurs clés de performance personnalisés pour le reporting exécutif et opérationnel.
* Modélisation d’attribution holistique (au-delà du numérique ou de l’e-mail).


### Marketo Engage

Marketo Engage offre des rapports in-app axés sur les indicateurs clés de performance de l’automatisation marketing, la mesure des programmes et des campagnes et l’analyse de l’impact marketing. Tous ces rapports sont directement liés à l’activité dans Marketo.

#### Fonctionnalités principales

* **Analyse marketing native** : rapports standard pour l’e-mail, les pages de destination, les campagnes, les prospects, les opportunités, le pipeline et l’attribution des recettes (première, dernière, multicontact).
* **Module complémentaire Analyses BI avancées)** : faites glisser et déposez le créateur de rapports personnalisé (par glisser-déposer) pour analyser les données de programme/compte/prospect (voir Présentation récente des analyses BI avancées).
* **Tableaux de bord préconfigurés** : pour les performances de la campagne, l’efficacité des canaux, la contribution au pipeline/au chiffre d’affaires.
* **Analyse des programmes et des canaux** : attribution et retour sur investissement spécifiques aux parcours gérés par Marketo.
* **Orienté marketing** : axé sur les utilisateurs et utilisatrices qui ont besoin de transparence dans le funnel marketing : statistiques sur les e-mails, formulaires, campagnes intelligentes et impact sur le chiffre d’affaires.


#### Cas d’utilisation standard de Marketo Engage

* Suivez et optimisez les performances des e-mails, des programmes et des campagnes.
* Attribuer des pistes et un pipeline aux tactiques marketing.
* Surveillez les tendances d’engagement et les pistes de score.
* Partagez des informations avec les équipes de vente/marketing sans ressources d’ingénierie de données.
* Accédez à des rapports prêts à l’emploi et adaptés aux marketeurs.


Consultez ci-dessous un tableau de comparaison rapide des fonctionnalités de création de rapports entre Marketo Engage et Customer Journey Analytics :

| Fonctionnalité | Marketo Engage | Customer Journey Analytics |
|---|---|---|
| **Focus Principal** | Programme marketing et reporting centré sur la campagne. | Analyse et création de rapports holistiques, omnicanales, et parcours comportementaux. |
| **Sources de données** | Données générées dans et via Marketo Engage. | Combine des données issues de toutes les données compatibles avec Experience Platform, notamment Marketo, un site web, une application mobile, des canaux hors ligne, etc. |
| **Attribution** | Attribution unique et multipoint sur les données Marketo. | Attribution cross-canal personnalisée sur toutes les données disponibles dans la solution. |
| **Rapports personnalisés et flexibilité** | Advanced BI (module complémentaire) pour les séances approfondies sur les programmes et les comptes. | Très flexible dans la façon dont vous créez des espaces de travail, des tableaux de bord ou des rapports personnalisés à l’aide de toutes les données disponibles. |
| **Analyse de l’audience** | Filtrer et segmenter les listes de programmes, l’engagement et les listes intelligentes. | Visualisations riches en rôles et en parcours, cheminement des audiences et analyse du chevauchement des segments. |
| **Utilisateurs prévus** | Marketeurs, opérateurs marketing, intervenants dans la génération de la demande, agents des recettes. | Analystes, spécialistes des données, stratèges marketing, professionnels de l’expérience client. |
| **Déduplication des mesures** | Pour les rapports de performances des e-mails, les mesures sont automatiquement dédupliquées par l’identifiant du prospect, l’identifiant de campagne et l’identifiant de ressource de messagerie. Si plusieurs e-mails sont créés à partir de la même ressource e-mail et sont envoyés au même prospect à partir du même programme, ces e-mails ne seront comptabilisés que comme un seul. | Sans filtres et mesures supplémentaires appliqués, les données de rapport par e-mail sont signalées comme un nombre total de performances d’e-mail sans [déduplication des mesures](/help/data-views/component-settings/metric-deduplication.md). |

{style="table-layout:fixed"}
