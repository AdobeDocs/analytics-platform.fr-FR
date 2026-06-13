---
title: Rapports GA4 dans Customer Journey Analytics
description: Recherchez l’équivalent Customer Journey Analytics pour chaque section de rapport GA4.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: c2d8f4a1-7b3e-4c9f-a5d2-8e1b6c3f9072
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 3200
ht-degree: 0%

---


# Rapports GA4 dans Customer Journey Analytics

Utilisez cette page comme référence de recherche lorsque vous savez quel rapport GA4 vous consultez et que vous souhaitez recréer son équivalent approximatif dans Analysis Workspace. Les rapports sont organisés par sections de navigation de GA4. Pour les scénarios de création de rapports cross-canal avancés qui sont disponibles après la migration des données GA vers Customer Journey Analytics, voir [Rapport sur les données Google Analytics](/help/use-cases/third-party/ga/report.md).

## Temps réel

+++Temps réel

Le rapport en temps réel de GA4 montre l&#39;activité des 30 dernières minutes : les utilisateurs actifs, les événements déclenchés, où se trouvent les utilisateurs, ce qui entraîne le trafic et sur quelles pages ils se trouvent.

Customer Journey Analytics ne comporte pas de zone de rapports en temps réel distincte. Au lieu de cela, créez un panneau dans Analysis Workspace et activez le bouton (bascule) **[!UICONTROL Actualisation en temps réel]** (faisant partie du package **Ultimate**) afin que ses visualisations se mettent à jour chaque minute :

1. Créez un panneau [à structure libre](/help/analysis-workspace/c-panels/freeform-panel.md) (le bouton (bascule) fonctionne également sur les panneaux [Vierge](/help/analysis-workspace/c-panels/blank-panel.md), [Attribution](/help/analysis-workspace/c-panels/attribution.md) et [Élément suivant ou précédent](/help/analysis-workspace/c-panels/next-previous.md)) avec les dimensions et mesures que vous souhaitez surveiller. Pour refléter les cartes en temps réel de GA4, utilisez **[!UICONTROL Page]**, **[!UICONTROL Type d’événement]**, **[!UICONTROL Domaine référent]** ou **[!UICONTROL Pays]** comme dimension, avec **[!UICONTROL Sessions]** comme mesure.
2. Activez le bouton (bascule) **[!UICONTROL Actualisation en temps réel]** et choisissez une période comprise entre **[!UICONTROL 15 dernières minutes]** et **[!UICONTROL 24 dernières heures]**. Les données sont limitées à une fenêtre dynamique de 24 heures et le panneau s’actualise toutes les minutes pendant 30 minutes au maximum.

La création de rapports en temps réel favorise les données au niveau de l’événement et de la session, et ne peut pas utiliser le groupement. Préférez donc **[!UICONTROL Sessions]** à **[!UICONTROL Personnes]**. Voir [Utiliser les rapports en temps réel](/help/components/real-time/use-real-time.md) pour la procédure complète et [Présentation des rapports en temps réel](/help/components/real-time/real-time.md) pour les détails des droits et de la latence.

+++

## Acquisition

+++Acquisition des utilisateurs (première touche)

Le rapport d’acquisition d’utilisateurs de GA4 attribue chaque utilisateur au canal, à la source et au support qui l’ont amené sur votre site pour la première fois, à l’aide de l’attribution première touche.

Dans Analysis Workspace, appliquez un modèle d’attribution **[!UICONTROL Première touche]** à la dimension **[!UICONTROL Canal marketing]**. Les canaux marketing doivent être configurés avant utilisation. Voir [Création d’un champ dérivé de canal marketing](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md).

1. Faites glisser la dimension **[!UICONTROL Canal marketing]** dans un [[!UICONTROL tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Cliquez avec le bouton droit sur un en-tête de colonne de mesure et sélectionnez **[!UICONTROL Utiliser un modèle d’attribution autre que celui par défaut]**.
3. Sélectionnez **[!UICONTROL Première touche]** avec un intervalle de recherche en amont approprié à votre analyse.

Vous pouvez également utiliser le panneau [[!UICONTROL Attribution] ](/help/analysis-workspace/c-panels/attribution.md) pour une comparaison côte à côte des performances des canaux Première touche et Dernière touche.

+++

+++Acquisition du trafic (basée sur une session)

Le rapport d’acquisition du trafic de GA4 attribue chaque session au canal, à la source et au support qui l’a initiée, à l’aide de l’attribution basée sur la session. Vous pouvez le ventiler par groupe de canaux par défaut, source/média, référent ou campagne.

Dans Analysis Workspace, la dimension **[!UICONTROL Canal marketing]** avec le modèle d’attribution par défaut **[!UICONTROL Dernière touche]** fournit des rapports de canal basés sur la session :

1. Faites glisser la dimension **[!UICONTROL Canal marketing]** dans un [[!UICONTROL tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Faites glisser les mesures souhaitées le long de la mesure par défaut **[!UICONTROL Événements]**.

Les répartitions de GA4 correspondent à ces dimensions Customer Journey Analytics :

* **Canal** : **[!UICONTROL Canal marketing]**. Customer Journey Analytics ne comporte aucun regroupement de canaux intégré : définissez-les comme un [champ dérivé](/help/data-views/derived-fields/derived-fields.md) à l’aide du modèle de fonction **[!UICONTROL Canaux marketing]** ou transférez des règles depuis Adobe Analytics lors de l’utilisation du connecteur source Analytics (voir [Utiliser des dimensions de canal marketing](/help/use-cases/aa-data/marketing-channels.md)).
* **Source / medium et referrals** : **[!UICONTROL Domaine référent]** et **[!UICONTROL Type de référent]**.
* **Campaign** : les paramètres `utm_*` de GA4 ne sont pas collectés automatiquement. Chacun doit être mappé à un champ XDM lors de l’implémentation avant d’apparaître en tant que dimension. Si les valeurs de la campagne arrivent sous la forme d’un code de suivi, utilisez la dimension **[!UICONTROL Code de suivi]**.

+++

+++Chemins d’attribution et de conversion

Les rapports Attribution de GA4 (sous Advertising) montrent comment différents canaux contribuent aux conversions et permettent de comparer les modèles et d’analyser les chemins de conversion.

Dans Analysis Workspace, utilisez le panneau [[!UICONTROL Attribution] ](/help/analysis-workspace/c-panels/attribution.md) :

1. Sélectionnez l’icône Panneaux et faites glisser un panneau **[!UICONTROL Attribution]** sur la zone de travail.
2. Faites glisser la dimension **[!UICONTROL Canal marketing]** vers la zone **[!UICONTROL Ajouter Dimension]**.
3. Faites glisser votre mesure de conversion (par exemple, un événement d’achat) vers la zone **[!UICONTROL Ajouter une mesure]**.
4. Sélectionnez la **[!UICONTROL Version]**.

Le [!UICONTROL panneau Attribution] génère un tableau de comparaison des modèles et une visualisation [!UICONTROL Flux de canal] présentant les principaux chemins empruntés par les visiteurs et visiteuses avant la conversion. Sélectionnez **[!UICONTROL Ajouter un modèle]** pour comparer plusieurs modèles d’attribution simultanément.

+++

## Engagement

+++Pages et écrans

Le rapport Pages et écrans de GA4 affiche les mesures de performances des pages et des écrans d’applications individuels.

Dans Analysis Workspace, faites glisser la dimension **[!UICONTROL Page]** dans un [[!UICONTROL tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) et ajoutez les mesures de votre choix. Les mesures courantes comprennent **[!UICONTROL Sessions]**, **[!UICONTROL Personnes]**, **[!UICONTROL Taux de rebond]** et **[!UICONTROL Temps passé par session]**.

Pour regrouper des pages par structure de chemin d’URL (par exemple, `/blog/` ou `/products/`), utilisez la dimension **[!UICONTROL Section du site]** si votre implémentation la définit, ou créez un champ [dérivé](/help/data-views/derived-fields/derived-fields.md) qui analyse l’URL de page avec la fonction **[!UICONTROL Analyse d’URL]**. Si vous conservez un mappage page à section explicite, un [jeu de données de recherche](/help/connections/standard-lookups.md) peut fournir le regroupement à la place.

+++

+++Pages de destination

Le rapport de la page de destination de GA4 indique les pages sur lesquelles les utilisateurs arrivent lorsqu’ils commencent une session.

Dans Analysis Workspace, faites glisser la dimension **[!UICONTROL Page d’entrée]** dans un [[!UICONTROL tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). La mesure **[!UICONTROL Sessions]** est la plus pertinente pour cette dimension.

+++

+++Événements

Le rapport Événements de GA4 indique le nombre de déclenchements de chaque événement, avec des mesures au niveau de l’événement.

Dans GA4, les événements ont un nom et des paramètres facultatifs (par exemple, `video_play` d’événement avec le paramètre `video_title`). Dans Customer Journey Analytics, la dimension standard du nom de l’événement est **[!UICONTROL Type d’événement]** (provenant de l’`xdm.eventType`). Les paramètres d’événement sont mappés à d’autres champs XDM dont les noms dépendent de votre implémentation.

Faites glisser la dimension **[!UICONTROL Type d’événement]** dans un [[!UICONTROL tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) pour répertorier tous les types d’événement, avec la mesure **[!UICONTROL Événements]**.

+++

+++Événements clés (conversions)

Le rapport Événements clés de GA4 (anciennement Conversions) répertorie chaque événement clé par nom avec son nombre, les événements marqués comme étant critiques pour l’entreprise dans la configuration de propriété GA4.

Customer Journey Analytics ne comporte aucun indicateur « événement clé » ; chaque interaction étant un événement, il n’existe aucune liste prédéfinie de conversions à ouvrir.

Pour recréer la liste des conversions GA4 par nom, utilisez **segments en tant que lignes**. Un [[!UICONTROL tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ne peut pas placer une mesure à la position de la ligne, mais il peut y placer un segment :

1. Pour chaque conversion, créez un segment qui isole ses événements ; par exemple, un segment de portée événement où `xdm.eventType` est égal à `commerce.purchases`. Nommez chaque segment après la conversion qu’il représente (par exemple, **Achats**).
2. Faites glisser chaque segment de conversion dans la zone des lignes d’un [!UICONTROL tableau à structure libre], un par ligne.
3. Ajoutez la mesure **[!UICONTROL Événements]** comme colonne. Chaque ligne indique le nombre de conversions, reflétant la liste des événements clés de GA4. Utilisez **[!UICONTROL Personnes]** à la place pour compter les convertisseurs uniques.

Pour ajouter un taux de conversion, créez une mesure calculée (cliquez sur l’icône **+** près de la liste des mesures) définie comme une mesure de conversion divisée par **[!UICONTROL Sessions]** ou **[!UICONTROL Personnes]**.

Chaque conversion que vous isolez ici peut également être définie comme mesure réutilisable dans votre vue de données. Consultez l’entrée **Événements clés → Mesures d’événement personnalisé** sous [Mesures courantes](#common-metrics) pour savoir comment configurer cela.

+++

## Monétisation

+++Achats eCommerce

Le rapport d’achats e-commerce de GA4 affiche les données d’achat au niveau du produit, y compris les articles, le chiffre d’affaires et la quantité.

Dans Customer Journey Analytics, la création de rapports d’e-commerce utilise la dimension **[!UICONTROL Produit]** avec les mesures d’achat. Ce rapport nécessite que votre implémentation envoie des données commerciales XDM (telles que `xdm.commerce.purchases`, `xdm.commerce.order` et `xdm.productListItems`).

1. Faites glisser la dimension **[!UICONTROL Product]** dans un [[!UICONTROL tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Faites glisser des mesures d’e-commerce telles que **[!UICONTROL Commandes]**, **[!UICONTROL Chiffre d’affaires]** et **[!UICONTROL Unités]** avec la mesure par défaut **[!UICONTROL Événements]**.

+++

+++Parcours d’achat (funnel)

Le rapport parcours d’achat de GA4 montre comment les utilisateurs se déplacent dans votre funnel d’achat (par exemple, de l’ajout au panier pour commencer la commande à l’achat) et où ils déposent.

Dans Analysis Workspace, utilisez la visualisation [**[!UICONTROL Abandons]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) :

1. Sélectionnez l’icône Visualisations et faites glisser une visualisation **[!UICONTROL Abandons]** sur la zone de travail.
2. Recherchez la dimension **[!UICONTROL Page]** et développez-la pour afficher les valeurs de page individuelles.
3. Faites glisser la première étape de funnel (par exemple, une page produit) dans le premier emplacement **[!UICONTROL Ajouter un point de contact]**.
4. Continuez à ajouter des points de contact pour chaque étape.

La visualisation des abandons accepte n’importe quelle dimension, mesure ou segment comme point de contact, et pas seulement les pages. Elle correspond donc aux entonnoirs basés sur des événements de GA4 et s’étend aux séquences qui mélangent des événements, des pages et des segments.

+++

+++Promotions

Le rapport Promotions de GA4 montre comment les promotions internes (bannières, emplacements présentés) stimulent les interactions de produits.

Dans Customer Journey Analytics, les données de promotion requièrent la capture des impressions et des clics de promotion dans les champs de schéma XDM. Une fois collecté, créez un [[!UICONTROL tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) qui inclut la dimension du nom de la promotion avec les mesures d’impression et de clic. Contactez votre administrateur Customer Journey Analytics pour vérifier quelles données de promotion sont disponibles dans votre vue de données.

+++

+++Publicités de l’éditeur

Le rapport Publicités de l’éditeur de GA4 affiche les recettes publicitaires provenant de Google Ad Manager ou d’AdMob pour les propriétés monétisées par l’éditeur.

Customer Journey Analytics n’a pas d’intégration native de l’éditeur aux recettes publicitaires. Pour rapporter ces données, ingérez les chiffres d’affaires de votre plateforme de monétisation des annonces (Google Ad Manager ou AdMob, par exemple) dans Adobe Experience Platform sous la forme d’un jeu de données, à l’aide d’un connecteur source ou d’une ingestion de données directe. Une fois ingérées, les données sont disponibles pour la création de rapports dans Customer Journey Analytics.

+++

## Rétention

+++Présentation de la rétention

Le rapport Retention overview de GA4 combine plusieurs vues de rétention — utilisateurs nouveaux ou récurrents, et un graphique de cohortes indiquant le nombre d&#39;utilisateurs qui reviennent au fil du temps.

**Nouveaux utilisateurs et utilisateurs récurrents** : utilisez les segments **[!UICONTROL Première session]** et **[!UICONTROL Sessions récurrentes]** comme lignes dans un [[!UICONTROL tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) :

1. Faites glisser le segment **[!UICONTROL Première session]** du panneau Composants vers la zone de ligne du tableau, puis faites glisser le segment **[!UICONTROL Sessions récurrentes]** en dessous.
2. Ajoutez les mesures de votre choix à côté de la mesure par défaut **[!UICONTROL Événements]**.
3. Pour suivre les tendances dans le temps, faites glisser une visualisation [**[!UICONTROL Ligne]**](/help/analysis-workspace/visualizations/line.md) au-dessus du tableau, puis ctrl+clic (Windows) ou cmd+clic (Mac) sur chaque ligne pour mettre en surbrillance les deux segments.

**Rétention au fil du temps** : utilisez la visualisation [**[!UICONTROL Tableau de cohortes]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) :

1. Sélectionnez l’icône Visualisations et faites glisser un **[!UICONTROL Tableau de cohortes]** sur la zone de travail.
2. Faites glisser la mesure **[!UICONTROL Personnes]** dans les champs Critères d’inclusion et de retour, puis sélectionnez **[!UICONTROL Créer]**.

Le [!UICONTROL Tableau de cohorte] regroupe les personnes par période initiale et effectue le suivi du comportement des retours sur les périodes suivantes ; les critères d’inclusion, de retour et de granularité sont tous configurables.

+++

## Utilisateur

+++Détails démographiques

Le rapport Détails démographiques de GA4 couvre les caractéristiques des utilisateurs (âge, sexe et centres d’intérêt) (optimisé par les signaux Google, qui nécessite que les utilisateurs soient connectés à un compte Google avec la personnalisation activée), ainsi que leur localisation (pays, région, ville) et leur langue.

**Emplacement** mappe directement aux dimensions Customer Journey Analytics : utilisez la visualisation **[!UICONTROL Pays]**, **[!UICONTROL Régions]** ou **[!UICONTROL Villes]** dans un [[!UICONTROL Tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ou la visualisation [[!UICONTROL Map]](/help/analysis-workspace/visualizations/map.md) pour une vue géographique (faites glisser la mesure **[!UICONTROL Personnes]** dans l’emplacement **[!UICONTROL Ajouter la mesure]** et sélectionnez **[!UICONTROL Créer]**).

**âge, sexe et centres d’intérêt** nécessitent des données propriétaires. Si votre organisation collecte des données démographiques par le biais de systèmes de gestion de la relation client (CRM), de formulaires d’enregistrement ou d’enquêtes basées sur le consentement, ingérez-les en tant que [jeu de données de profil](/help/connections/create-connection.md#profile-dataset) et joignez-les aux données d’événement. Cette approche produit des données plus fiables que le modèle de signaux Google déduits de GA4, car elle utilise des attributs propriétaires consentis.

+++

+++Détails techniques

Le rapport Tech de GA4 affiche le navigateur, le système d’exploitation, la résolution d’écran et la catégorie d’appareils.

Dans Analysis Workspace, les dimensions suivantes sont mappées aux dimensions Tech de GA4, chacune provenant d’un champ XDM standard :

| Dimension technique de GA4 | Dimension Analysis Workspace | Champ XDM |
|---|---|---|
| Navigateur | **[!UICONTROL Navigateur]** | `xdm.environment.browserDetails.name` |
| Système d’exploitation | **[!UICONTROL Système d’exploitation]** | `xdm.environment.operatingSystem` |
| Résolution d’écran | **[!UICONTROL Résolution de l’écran]** | `xdm.device.screenWidth`, `xdm.device.screenHeight` |
| Catégorie d’appareil (mobile, bureau, tablette) | **[!UICONTROL Type d’appareil mobile]** | `xdm.device.type` |
| Modèle d’appareil | **[!UICONTROL Appareil mobile]** | `xdm.device.model` |

Faites glisser l’une de ces dimensions du panneau Composants vers un [[!UICONTROL tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).

>[!NOTE]
>
>Les navigateurs modernes ayant réduit le détail de la chaîne Agent-utilisateur, des valeurs complètes et précises dépendent de la collecte de [User-Agent Client Hints](https://experienceleague.adobe.com/en/docs/experience-platform/collection/use-cases/client-hints) dans votre configuration de Web SDK.

+++

## Explorer

+++Exploration sous forme libre

L’exploration de format libre de GA4 est un tableau en zone de travail vierge avec des lignes, des colonnes et des superpositions de graphiques facultatives configurables.

Analysis Workspace [**[!UICONTROL tableau à structure libre]**](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) est l’équivalent direct et la base de la plupart des projets Workspace. Faites glisser n’importe quelle dimension dans les lignes, n’importe quelle mesure dans les colonnes et n’importe quel segment dans la zone de dépôt de segments au-dessus du tableau.

Consultez [Prise en main d’Analysis Workspace](home.md#getting-started-in-analysis-workspace) pour le mappage terminologique entre GA4 Explorer et Workspace.

+++

+++exploration de funnel

L’exploration Funnel de GA4 définit une séquence d’étapes et mesure l’achèvement et le retour à chaque étape.

Dans Analysis Workspace, utilisez la visualisation [**[!UICONTROL Abandons]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) :

1. Sélectionnez l’icône Visualisations et faites glisser une visualisation **[!UICONTROL Abandons]** sur la zone de travail.
2. Faites glisser la dimension, la mesure ou le segment qui représente votre première étape dans le premier emplacement **[!UICONTROL Ajouter un point de contact]**.
3. Continuez à ajouter un point de contact pour chaque étape suivante de la séquence.

N’importe quelle dimension, mesure ou segment pouvant servir de point de contact, [!UICONTROL Abandon] correspond aux entonnoirs basés sur des événements de GA4 et s’étend aux séquences cross-canal qui mélangent des événements, des pages et des segments.

+++

+++Exploration des chemins

L’exploration du chemin de GA4 (Universal Analytics appelé ce flux d’utilisateurs) permet de visualiser les séquences de pages ou d’événements que les utilisateurs parcourent.

Dans Analysis Workspace, utilisez la visualisation [**[!UICONTROL Flux]**](/help/analysis-workspace/visualizations/c-flow/flow.md) :

1. Sélectionnez l’icône Visualisations et faites glisser une visualisation **[!UICONTROL Flux]** sur la zone de travail.
2. Faites glisser une valeur de la dimension sur laquelle vous souhaitez tracer le chemin (par exemple, une valeur **[!UICONTROL Page]** ou **[!UICONTROL Type d’événement]**) vers le centre du flux.
3. La visualisation montre ce que les utilisateurs et utilisatrices faisaient avant et après ce point.

La visualisation [!UICONTROL Flux] est interactive : sélectionnez n’importe quel nœud pour développer davantage les chemins d’accès dans les deux sens. N’importe quelle dimension peut être utilisée afin que vous puissiez suivre un chemin d’accès sur des pages, des événements, des canaux marketing ou des liens personnalisés.

+++

+++Chevauchement des segments

L’exploration du chevauchement des segments de GA4 montre comment plusieurs segments d’utilisateurs se coupent, visualisés sous la forme d’un diagramme de Venn.

Dans Analysis Workspace, utilisez la visualisation [**[!UICONTROL Venn]**](/help/analysis-workspace/visualizations/venn.md) :

1. Sélectionnez l’icône Visualisations et faites glisser une visualisation **[!UICONTROL Venn]** sur la zone de travail.
2. Faites glisser jusqu’à trois segments du panneau Composants vers la visualisation.

Le diagramme de Venn affiche les tailles d’intersection et le [[!UICONTROL tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) sous-jacent affiche les données sous-jacentes.

+++

+++Exploration des cohortes

L’exploration de cohortes de GA4 regroupe les utilisateurs et utilisatrices par une caractéristique partagée (généralement la date d’acquisition) et suit leur comportement au fil du temps.

Dans Analysis Workspace, utilisez la visualisation [**[!UICONTROL Tableau de cohorte]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) :

1. Sélectionnez l’icône Visualisations et faites glisser un **[!UICONTROL Tableau de cohortes]** sur la zone de travail.
2. Faites glisser la mesure **[!UICONTROL Personnes]** dans les champs Critères d’inclusion et de retour .
3. Sélectionnez la **[!UICONTROL Version]**.

Le [!UICONTROL Tableau de cohorte] regroupe les personnes par période initiale et effectue le suivi du comportement de retour sur les périodes suivantes. Par défaut, il cohorte à la date d’acquisition, mais les critères d’inclusion, de retour et de granularité sont tous configurables.

+++

+++Explorateur des utilisateurs

L’explorateur d’utilisateurs de GA4 affiche les utilisateurs individuels, leur historique de session et une chronologie des événements.

Customer Journey Analytics prend en charge l’analyse au niveau de la personne de deux manières :

* **Lorsque le groupement est activé** : créez une portée de segment pour une valeur d’ID de personne spécifique et appliquez-la à n’importe quel projet Workspace. Le conteneur **[!UICONTROL Personne]** isole l’activité regroupée de cet individu à travers les sessions et les canaux.
* **Données d’événement brutes** : utilisez **aperçus de jeux de données** dans l’interface utilisateur de Adobe Experience Platform pour examiner les enregistrements d’événement XDM bruts. Cette vue est utile pour la validation de l’implémentation et le débogage d’événements individuels.

+++

+++Durée de vie de l’utilisateur

L’exploration de la durée de vie de l’utilisateur de GA4 mesure la valeur cumulée et l’engagement de chaque utilisateur dans l’ensemble de sa relation avec votre entreprise, plutôt que dans une période fixe. Il associe des mesures de durée de vie historiques à des prédictions de machine learning pour Google pour la probabilité d’achat, la probabilité d’attrition et le chiffre d’affaires prévu.

Ils sont associés à Customer Journey Analytics en deux parties :

**Valeur de durée de vie historique** est réalisable en mode natif. Étant donné que Customer Journey Analytics établit des rapports sur votre fenêtre de conservation des données complète, vous pouvez définir une longue période et agréger le chiffre d’affaires et l’engagement cumulés de chaque personne au cours de cette recherche en amont. Avec le groupement ou un ID de personne persistant, le conteneur **[!UICONTROL Personne]** lie cette activité à une personne et les mesures calculées expriment la valeur par personne. Le résultat n’est pas une durée de vie illimitée, mais une recherche en amont longue et configurable qui en approche une.

La **valeur de durée de vie prédictive** n’est pas intégrée. Customer Journey Analytics n’a aucun modèle de probabilité d’achat, de perte de clientèle ou de chiffre d’affaires prévu intégré au produit. Pour utiliser des scores prédictifs, calculez-les en externe (par exemple, dans un workflow CRM ou de science des données) et importez-les dans Customer Journey Analytics en tant que jeu de données de profil, puis faites-les apparaître sous forme de dimensions ou de mesures. Adobe recommande de travailler avec un consultant en implémentation pour concevoir cette approche.

+++

## Mesures courantes

+++Utilisateurs actifs → Personnes

Le **utilisateurs actifs** de GA4 comptabilise les utilisateurs qui ont eu au moins une session engagée dans la période.

Dans Customer Journey Analytics, l’équivalent le plus proche est **[!UICONTROL Personnes]**, un nombre d’ID de personne uniques dans la période. [!UICONTROL Personnes] inclut toutes les personnes identifiées, quel que soit le niveau d’engagement. Il est donc généralement supérieur au nombre d’utilisateurs actifs de GA4 pour les sites avec un trafic passif important.

Pour une comparaison comportementale plus étroite, appliquez un [segment de sessions engagées](compare-data.md#engaged-sessions) pour étendre la mesure [!UICONTROL Personnes] aux utilisateurs qui répondent à vos critères d’engagement.

+++

+++Sessions engagées → Mesure calculée

GA4 **sessions engagées** compte les sessions qui ont duré 10 secondes ou plus, qui ont eu 2 pages vues ou plus ou qui incluaient au moins un événement clé.

Customer Journey Analytics ne comporte aucune mesure de sessions engagées intégrée : définissez-la comme un segment qui capture vos critères d’engagement, puis utilisez-la avec la mesure **[!UICONTROL Sessions]**. Consultez [Sessions engagées](compare-data.md#engaged-sessions) pour connaître l’approche recommandée et savoir comment en déduire un taux d’engagement.

+++

+++Taux d’engagement → Mesure calculée

Le **taux d’engagement** de GA4 correspond au pourcentage de sessions engagées : sessions engagées divisé par le nombre total de sessions.

Dans Customer Journey Analytics, créez-la en tant que mesure calculée à partir de votre définition des sessions engagées. Consultez [Sessions engagées](compare-data.md#engagement-rate) pour obtenir des instructions détaillées.

+++

+++Durée moyenne de l’engagement → Durée par session

Le **temps d’engagement moyen** de GA4 mesure le temps moyen pendant lequel le navigateur ou l’application était au premier plan lors des sessions engagées.

Dans Customer Journey Analytics, utilisez l’option **[!UICONTROL Durée de la session (secondes)]** qui mesure le temps écoulé entre le premier événement et le dernier événement d’une session. Ce composant inclut des périodes pendant lesquelles l’utilisateur n’a peut-être pas activement participé, de sorte que les valeurs peuvent différer de celles de la mesure GA4. Il s’agit de l’équivalent intégré le plus proche.

+++

+++Nombre d’événements → événements

Le **nombre d’événements** de GA4 correspond au nombre total d’enregistrements d’un événement.

Dans Customer Journey Analytics, la mesure équivalente est **[!UICONTROL Événements]** : le nombre total d’enregistrements d’événement dans le jeu de données pour la période sélectionnée et les segments appliqués.

+++

+++Sessions → Sessions

Les **Sessions** de GA4 et les **[!UICONTROL Sessions]** de Customer Journey Analytics mesurent toutes deux le nombre de sessions dans une période. Les nombres peuvent différer en raison de règles de définition de session différentes. Pour plus d’informations](compare-data.md#sessions) voir [Pourquoi les données GA4 et Customer Journey Analytics diffèrent-elles ?

+++

+++Nouveaux utilisateurs → segment Première session appliqué aux personnes

Le **Nouveaux utilisateurs** de GA4 comptabilise les utilisateurs qui ont eu leur toute première session dans la période sélectionnée.

Dans Analysis Workspace :

1. Recherchez le segment **[!UICONTROL Première session]** dans le panneau Composants .
2. Faites-le glisser dans la zone de dépôt des segments au-dessus de votre [[!UICONTROL tableau à structure libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
3. Utilisez la mesure **[!UICONTROL Personnes]** pour comptabiliser les nouvelles personnes uniques.

+++

+++Taux de rebond → Taux de rebond (avec mises en garde)

Le **taux de rebond** de GA4 correspond au pourcentage de sessions qui n’ont pas été engagées (moins de 10 secondes, aucun événement clé, moins de 2 pages vues). Il s’agit de l’inverse du taux d’engagement.

La mesure Customer Journey Analytics **[!UICONTROL Taux de rebond]** utilise une définition différente par défaut et est configurable par vue de données. Ces différences produisent des nombres sensiblement différents qui mesurent des comportements différents.

Pour obtenir une estimation du taux de rebond de GA4 dans Customer Journey Analytics, créez une mesure Taux d’engagement et inversez-la avec une seconde mesure calculée définie sur `1 - Engagement Rate`. Voir [Sessions engagées](compare-data.md#engagement-rate) pour la création détaillée.

Consultez [Pourquoi les données GA4 et Customer Journey Analytics diffèrent](compare-data.md#bounce-rate) pour une explication détaillée de la différence de définition.

+++

+++Événements clés → mesures d’événement personnalisé

Les **événements clés** de GA4 (anciennement appelés conversions) sont des événements désignés comme des résultats commerciaux importants dans la configuration des propriétés GA4.

Dans Customer Journey Analytics, une conversion est une mesure d’événement personnalisée configurée dans la vue de données. Tout événement XDM peut être exposé en tant que mesure et une mesure peut être définie pour s’incrémenter de manière conditionnelle sur une valeur de champ XDM (par exemple, une mesure **[!UICONTROL Achats]** qui s’incrémente lorsque `xdm.eventType` est égale à `commerce.purchases`). Recherchez la mesure appropriée par son libellé dans le panneau Composants d’Analysis Workspace ; le nom reflète la manière dont votre administrateur l’a configurée.

Pour reproduire le rapport Événements clés de GA4 *rapport* (une liste de chaque conversion avec son nombre), consultez l’entrée **Événements clés (conversions)** sous [Engagement](#engagement) sur cette page.

+++

>[!MORELIKETHIS]
>
>* [Rapport sur les données Google Analytics](/help/use-cases/third-party/ga/report.md)
