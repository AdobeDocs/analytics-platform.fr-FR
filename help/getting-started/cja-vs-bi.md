---
title: Comparer CJA aux solutions BI
description: Comparer Customer Journey Analytics aux solutions BI
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 955f4543a132126deee52b7dfe3398b742022069
workflow-type: ht
source-wordcount: '1609'
ht-degree: 100%

---


# Comparer CJA aux solutions BI

Avec l’accent mis actuellement sur l’expérience client, les marques nécessitent des solutions avancées pour mieux comprendre le parcours client holistique. La compréhension de ce parcours client complet vous permet d’analyser et d’obtenir des insights précieux sur la manière dont les canaux en ligne et hors ligne interagissent avec les clients et les clientes et mènent à une augmentation de la conversion, de la rétention et de la fidélité. Dans ce contexte, un parcours client peut être la commande en ligne directe d’un repas dans une chaîne alimentaire de sushis. Ou l’achat d’une nouvelle voiture, où le client ou la cliente associe la recherche en ligne avec des visites dans la salle d’exposition du concessionnaire, et un achat final en personne.

De nombreuses entreprises ont consolidé leurs données omnicanales dans un lac de données ou un entrepôt de données. Les outils de Business Intelligence (BI) sont utilisés en plus de ces entrepôts de données pour fournir les rapports, visualisations et insights dont l’entreprise a besoin pour comprendre le parcours client. Souvent, cette combinaison de solutions et d’outils est un objectif général par nature et par conception, et n’est pas axé explicitement sur le client. Customer Journey Analytics (CJA) se concentre sur l’autonomisation des responsables de l’expérience client, tels que les spécialistes du marketing, les analystes de données et les spécialistes des données. L’outil leur permet de visualiser le parcours client dans son contexte intégral, sur tous les canaux en temps réel et sans les limites que présentent de nombreux autres outils de BI.

Cette section de la documentation explique les différences fondamentales entre CJA et les outils de BI couramment utilisés, tout d’abord en examinant le workflow général utilisé pour atteindre l’objectif mentionné ci-dessus : comprendre le parcours client. Elle fournit ensuite de plus amples détails sur les différences de stockage, de collecte et d’interrogation des données entre les outils CJA et BI. Enfin, elle explique les différences de fonctionnalités de visualisation.

## Workflow BI traditionnel

Un obstacle fréquent aux analyses traditionnelles des parcours clients est le fait qu’elles ne sont pas axées sur le client ou la cliente. Chaque équipe collecte des données en silos, analysant et optimisant les expériences en fonction des données auxquelles elle a accès.

![Workflow BI standard](./assets/biworkflow.png)

Si vous souhaitez comprendre l’impact d’une campagne numérique spécifique sur une action hors ligne stockée dans un autre silo de données, envoyez une requête à la file d’attente de l’équipe de BI. L’équipe de BI écrit les requêtes nécessaires pour acquérir et transformer les données. Une fois les données brutes récupérées, l’équipe de BI crée la visualisation. Les données sont partagées avec vous à mesure que vous parcourez les insights et extrayez les données pour les activer dans d’autres systèmes.

Chacune de ces étapes peut prendre des heures, des jours ou même des semaines. S’il existe des questions ou des problèmes de suivi liés aux données interrogées, il peut s’écouler encore plus de temps avant que ces questions ne soient traitées et que le cycle se poursuive. Pour l’analyse, l’exploration et la compréhension continues du parcours client, ce processus est inefficace et non évolutif. En outre, les équipes de BI ne se contentent généralement pas de répondre aux questions liées au parcours client.

## CJA : Workflow démocratisé pour les données en ligne et hors ligne

CJA fournit un environnement permettant de connecter des données cross-canal en ligne et hors ligne au niveau global du client ou de la cliente dans le seul but de comprendre le parcours client. Il nécessite une configuration initiale pour [connecter](/help/connections/overview.md) et [définir des vues](/help/data-views/data-views.md) aux données que vous qualifiez comme pertinentes. Une fois ces données terminées, elles peuvent être analysées et explorées en permanence. Vous pouvez progressivement obtenir des insights sur les parcours client pour mieux les comprendre. En démocratisant les données combinées en ligne et hors ligne, vous pouvez répondre en quelques secondes aux questions liées au parcours client.

![Workflow CJA](./assets/cjaworkflow.png)

Vous pouvez utiliser CJA pour poser des questions à l’aide de l’environnement visuel Analysis Workspace et obtenir des insights presque instantanément. Les données et rapports cross-canal sont immédiatement disponibles, sans code SQL requis. D’autres requêtes et analyses peuvent être effectuées à l’aide d’un simple glisser-déposer dans l’interface utilisateur, avec des données entièrement corrélées. Vous pouvez continuer à poser des questions et à explorer progressivement les détails selon vos besoins. Vous pouvez ensuite agir immédiatement sur les insights que vous découvrez, comme partager des audiences pour l’activation et l’orchestration.

## Le puissant moteur de création de rapports de CJA

CJA utilise une architecture propriétaire puissante qui distribue l’analyse sur des centaines (voire des milliers) de serveurs afin d’afficher les données dans Analysis Workspace en quelques secondes. Voici quelques propriétés remarquables de cette architecture de traitement :

* **Optimisé pour les requêtes individuelles asociées aux clients et aux clients** : d’un point de vue technique, CJA stocke les données dans un moteur de création de rapports distribué qui fait largement appel à la mise en cache. Ce moteur est adapté aux requêtes réactives sur les données d’événement de niveau individuel et, de ce fait, parfaitement optimisé pour les requêtes associées aux clients et aux clientes. Le moteur de création de rapport stocke les données dans des indices bitmap orientés colonne qui permettent un calcul rapide et à la volée des mesures agrégées. Il dispose d’un moteur de filtrage complet qui permet une segmentation/analyse d’audience puissante. Et il offre une compréhension essentielle de la séquence parmi les points de données, ce qui est utile pour analyser le comportement entre ces points de données (l’ordre dans lequel les choses se sont produites) et pour assigner l’attribution à l’aide de différents modèles complexes.

* **Application rapide de chemins et de filtres complexes** : le moteur de création de rapports fonctionne sur des jeux de données hiérarchiques et partiellement ordonnés (par exemple, personne -> sessions -> évènements). Toutes les données d’un objet de niveau supérieur (profils individuels) résident sur un seul nœud de traitement pour des résultats précis. Ce découpage permet une application rapide de filtres et de chemins complexes. Les opérations complexes telles que la sessionnalisation, l’attribution, la persistance dynamique des attributs de données et les options de manipulation de données complexes sont exécutées à grande échelle avec un temps de création de rapports rapide. Dans le monde de la BI, ces types d’opérations nécessitent généralement la création de cubes OLAP pour chaque cas d’utilisation. Le moteur de création de rapports de CJA permet un accès illimité à l’ensemble du jeu de données sur chaque requête, ce qui se traduit par des données entièrement corrélées, sans qu’il soit nécessaire de procéder à un cubage préalable.

* **Requête efficace de flux de données complexes** : l’une des plus grandes différences du moteur de création de rapports comparé aux bases de données SQL et NoSQL traditionnelles est sa capacité à déterminer des prédicats en fonction des relations orientées séquence à un niveau fondamental. Ces opérations d’interrogation fondamentales peuvent examiner le flux d’enregistrement, qui est composé de nombreuses séquences entrelacées (et même imbriquées). Elles exécutent une requête sur tous ces flux de données entrelacés avec l’efficacité d’une seule opération de séquence contiguë.

* **Conçu pour répondre rapidement à des requêtes volumineuses** : le moteur de création de rapports n’a pas un objectif aussi général que les systèmes Big Data traditionnels. Cependant, il est spécialement conçu pour répondre aux requêtes qui s’étendent sur des millions (voire des milliards) d’enregistrements (données d’événement/événements d’expérience), généralement en moins d’une seconde. Contrairement à d’autres systèmes Big Data, il ne procède pas en échantillonnant les données ou en pré-calculant les réponses à toutes les questions qu’il pense que vous pourriez poser. Au lieu de cela, il est capable de calculer les réponses assez rapidement pour prendre en charge les cas d’utilisation des requêtes interactives. Cette conception spécifique du moteur de création de rapports de CJA facilite la disponibilité et la rapidité des données pour une analyse et une exploration continues, ce qui vous permet d’obtenir progressivement des insights et une compréhension des parcours clients.

* **Agit comme une solution de BI sans affichage** : lorsque vous définissez vos dimensions, mesures et filtres à un seul endroit, tout client CJA (y compris notre API publique CJA) peut accéder à ces composants. Ce processus extrait les requêtes complexes des utilisateurs finaux et utilisrices finales et garantit que les résultats sont les mêmes, quel que soit le client de création de rapports ou de visualisation que vous utilisez.

## Fonctionnalités de visualisation uniques de CJA

Le moteur de création de rapports est essentiel pour CJA. Il vous permet d’interagir progressivement avec toutes les données de parcours client dans ce moteur de création de rapports et d’agir sur ces données. CJA est fourni avec un vaste ensemble de composants qui vous permettent d’effectuer ces opérations visuellement et par glisser-déposer. Les outils de visualisation de BI vous permettent d’effectuer des recherches à l’intérieur des limites des données préparées par SQL (telles que définies par le service informatique). CJA vous permet de ventiler et de découper autant que vous le souhaitez, sans avoir à redemander au service informatique de créer une autre vue SQL.

« Progressivement » est ici un concept clé : contrairement à la plupart des visualisations dans les outils de BI, l’interface utilisateur visuelle par glisser-déposer de CJA vous permet de ventiler en continu vos données en fonction de vos besoins spécifiques : vous pouvez créer des requêtes visuelles de manière interactive à l’aide de mesures, dimensions, filtres (segments), calculs, chronologies, annotations et autres valeurs d’analyse pertinentes.

Ces composants de visualisation intègrent des fonctionnalités intelligentes telles que :

* Les **Fonctionnalités d’analyse virtuelle** par exemple les [Détection des anomalies](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) qui utilisent des algorithmes prédictifs et le machine learning pour fournir des informations sur les comportements inhabituels de vos données.

* Les **Fonctionnalités d’analyse avancées** qui sont spécifiquement axées sur les insights du parcours client, comme les [diagrammes de flux](/help/analysis-workspace/visualizations/c-flow/flow.md), l’[attribution IQ](/help/analysis-workspace/attribution/overview.md), les [diagrammes d’abandons](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), et les [ventilations de dimensions](/help/components/dimensions/t-breakdown-fa.md). Voici quelques exemples de visualisations prêtes à l’emploi :

   * [Analyse de la fidélisation client via des tableaux de cohortes/latence](/help/analysis-workspace/visualizations/cohort-table/cohort-use-cases.md), où vous glissez-déposez simplement des mesures/dimensions dans un créateur et où vous terminez en moins de 30 secondes,

   * Visualisations d’[abandon](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)/de [flux](/help/analysis-workspace/visualizations/c-flow/create-flow.md). S’installent en moins d’une minute.

   * Les [modèles d’attribution](/help/analysis-workspace/attribution/algorithmic.md) comme Première touche, Dernière touche, Participation, Atténuation temporelle et même les modèles personnalisés qui nécessitent quelques clics pour être configurés.

* La **Fonction de segmentation à chaque étape de votre exploration progressive** : chaque fois que vous le jugez utile, vous pouvez republier votre audience dans Experience Platform et, de là, vers l’une des destinations prises en charge.

* La **sessionnalisation** entièrement [personnalisable](/help/data-views/component-settings/persistence.md) : vous pouvez déterminer quand une session, dans le cadre d’un canal d’un parcours client, commence et se termine.

* Le **Traitement et la démocratisation** : les tableaux de bord créés dans CJA peuvent être :

   * [Modifiés](/help/analysis-workspace/curate-share/curate.md) par d’autres personnes de l’organisation pour l’exploration continue,
   * Exportés vers Excel à l’aide de [Report Builder](/help/report-builder/report-buider-overview.md) (un plug-in dédié),
   * [Partagés](/help/analysis-workspace/curate-share/share-projects.md) dans divers formats, notamment [PDF](/help/analysis-workspace/curate-share/download-send.md), [CSV](/help/analysis-workspace/curate-share/download-send.md) et par le biais d’une [application mobile dédiée](/help/mobile-app/home.md), avec les personnes intéressées par les rapports finaux et/ou les visualisations.

Il est difficile de comparer les fonctionnalités de visualisation de CJA à celles des outils de BI en raison de la variété des visualisations disponibles. Certains outils de BI disposent de visualisations plus avancées, mais CJA se concentre sur des visualisations interactives et interopérables du parcours client qui vous permettent de ventiler les données en quelques secondes sans avoir à « charger » pour chaque requête supplémentaire.


## Résumé

CJA diffère des outils de BI par la façon dont il intègre de manière transparente un moteur de création de rapports axé sur le parcours client hautement optimisé avec des outils et des composants conviviaux, dans l’optique d’exécuter des analyses et de créer des rapports et des visualisations avancées. Le tout depuis une seule interface utilisateur, sans avoir à passer d’un moteur de requête à un environnement de visualisation.

