---
title: Comparaison à Adobe Analytics
description: Vue d’ensemble de la comparaison entre Customer Journey Analytics et Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
autotag-review: '2026-05-19T09:13:47.721Z'
TQID: 'https://experienceleague.adobe.com/MU9ywSyInHtsdzqvxO3yxTSY5bcDvdhnTUkhAgDHmZ4'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1f480cda20e0b2d54dd42b909bfa8bf8a2bc0c95
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 52%
---
# Comparaison à Adobe Analytics

Cette section de la documentation explique comment comparer et comprendre les différences entre Adobe Customer Journey Analytics et Adobe Analytics.

La différence fondamentale entre les deux solutions réside dans l’étendue des données que vous pouvez prendre en compte lors de la création de vos rapports et analyses.

Dans Customer Journey Analytics, *toute* source de données peut faire partie des données que vous utilisez pour la création de rapports et l’analyse. Adobe Analytics est principalement destiné aux données en ligne collectées à partir de sites web et d’applications mobiles. Adobe Analytics offre des fonctionnalités d’importation de données provenant d’autres sources, mais l’objectif principal de cette fonctionnalité est de fournir plus de contexte autour des données en ligne mentionnées précédemment.

## Collecte de données

Customer Journey Analytics s’appuie sur des données stockées dans des jeux de données Adobe Experience Platform. Vous disposez de plusieurs options pour collecter et ingérer des données depuis ces jeux de données dans Experience Platform. Ces options sont présentées dans la [présentation de Data Ingestion](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-data-ingestion/data-ingestion).

Adobe Analytics collecte les données au sein de la solution elle-même. Là encore, vous disposez de plusieurs options pour collecter ces données, qui sont détaillées dans le [Guide de mise en œuvre d’Adobe Analytics](https://experienceleague.adobe.com/fr/docs/analytics/implementation/home).

Vous pouvez utiliser les données de votre suite de rapports Adobe Analytics dans Customer Journey Analytics à l’aide du [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics?lang=fr). Ce connecteur ingère dans Experience Platform les données collectées dans Adobe Analytics. Vous pouvez ensuite créer une connexion à ce jeu de données dans Customer Journey Analytics. Voir [Utiliser les données de suite de rapports Adobe Analytics dans Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja) pour plus d’informations.

Les données de votre suite de rapports Adobe Analytics sont indépendantes des données stockées dans les jeux de données Adobe Experience Platform qui constituent votre connexion Customer Journey Analytics. Par conséquent, Adobe vous recommande d’évaluer les données de chaque plateforme séparément, plutôt que de vous attendre à ce que les deux plateformes reflètent les mêmes valeurs.

## Traitement des données

Avant de pouvoir créer des rapports sur les données, vous devez souvent traiter ces données pour vous assurer qu’elles peuvent être correctement utilisées pour la création des rapports. Le traitement des données peut avoir lieu au moment de la collecte et de la création des rapports.

En règle générale, Customer Journey Analytics est conçu pour fonctionner avec les données collectées et stockées dans les jeux de données Experience Platform au moment du rapport. Customer Journey Analytics offre une puissante fonctionnalité de traitement au moment de la création de rapports pour s’assurer que les données sont prêtes pour la création de rapports et l’analyse. [Les champs dérivés](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/derived-fields) et [les paramètres des composants](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/component-settings/overview) peuvent être modifiés et appliqués rétroactivement aux données historiques. Si vous devez mapper, transformer et valider des données avant leur ingestion dans Experience Platform, vous pouvez utiliser la fonctionnalité [Préparation de données](https://experienceleague.adobe.com/fr/docs/experience-platform/data-prep/home) d’Experience Platform.

Dans Adobe Analytics, la grande partie de ce traitement des données survient immédiatement après la collecte des données. Les règles des canaux marketing, les règles de traitement, la persistance d’eVar et d’autres logiques de post-traitement sont actuellement appliquées et sont permanentes dans la suite de rapports. Les modifications apportées à l’une de ces configurations n’affectent que les nouvelles données entrantes à partir de ce moment.

Voir [Comparer le traitement des données dans Adobe Analytics et Customer Journey Analytics](data-processing-comparisons.md) et [Règles de traitement, VISTA et classifications par rapport à la préparation des données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep) pour plus d’informations.


## Terminologie

Customer Journey Analytics offre une certaine flexibilité quant à la manière dont vous définissez des dimensions et des mesures, grâce à la flexibilité que les schémas basés sur le modèle de données d’expérience (XDM) sous-jacents offrent. Par exemple, lorsque Adobe Analytics utilise des visiteurs, des visites et des accès, Customer Journey Analytics utilise des personnes, des sessions et des événements (vous pouvez modifier le nom comme vous le souhaitez).

Voir [Comparer la terminologie pour les données Analytics transmises par le biais du connecteur source Analytics](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology) pour plus d’informations sur les différences terminologiques.


## Sandbox et environnements de création de rapports virtuelles

Adobe Analytics dispose du concept de suites de rapports virtuelles qui vous permet de segmenter les données collectées et de contrôler l’accès à ces données segmentées.

Customer Journey Analytics a un concept similaire, appelé vues de données. Les vues de données sont des conteneurs qui vous permettent de déterminer comment interpréter les données d’une connexion. Elles offrent la flexibilité ultime pour spécifier et configurer des dimensions et des mesures en vue de la préparation de vos rapports et analyses.

Experience Platform propose des sandbox qui fonctionnent comme un conteneur contenant des données et des applications pour un environnement donné. La fonctionnalité d’un sandbox n’est pas liée à une suite de rapports virtuelles Adobe Analytics ou à une vue de données de Customer Journey Analytics. Adobe Analytics lui-même n’a aucune dépendance ou relation avec les sandbox Experience Platform. Customer Journey Analytics prend en charge les sandbox Experience Platform, mais quelques considérations importantes sont à prendre en compte.

Voir [Suites de rapports virtuelles, vues de données, sandbox Adobe Experience Platform et connecteur source Analytics](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc) pour en savoir plus.


## Identités

Customer Journey Analytics prend en charge les identités que vous définissez dans le cadre des schémas auxquels les jeux de données contenant vos données sont conformes. En tant que telles, les identités sont un concept fondamental d’Experience Platform utilisé par Customer Journey Analytics lors de la configuration d’une [connexion](../../connections/overview.md) (en définissant l’ID de personne pour chaque jeu de données) et lors de l’application du [groupement](../../stitching/overview.md) pour l’analyse cross-canal. L’identité ECID est une identité importante utilisée par les SDK et l’API Experience Platform.

Adobe Analytics utilise un ensemble plus définitif de champs d’identité, comme l’ID Adobe Analytics (AAID). Lors de l’utilisation du connecteur source Analytics, ces champs d’identité Adobe Analytics font l’objet d’un traitement spécial. Voir [AAID, ECID, AACUSTOMID et le connecteur source Analytics](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc) pour plus d’informations.


## Dimensions de cardinalité élevée

Customer Journey Analytics stocke des valeurs de dimension entières. Il n’existe aucune limite au nombre de valeurs uniques qu’une dimension peut couvrir. En revanche, Adobe Analytics utilise des hachages 32 bits pour mapper les valeurs de dimension afin d’optimiser les rapports et le stockage. Ce comportement peut entraîner [collisions de hachage](https://experienceleague.adobe.com/fr/docs/analytics/implementation/validate/hash-collisions) dans les rapports. Adobe Analytics regroupe également les valeurs dans l’élément de ligne [Faible trafic](https://experienceleague.adobe.com/fr/docs/analytics/technotes/low-traffic) une fois le seuil limite unique atteint. Les segments utilisant ces dimensions peuvent afficher des incohérences entre les rapports Adobe Analytics et Customer Journey Analytics.

## Fonctionnalités prises en charge

Retrouvez une présentation des fonctionnalités d’Adobe Analytics et de la manière dont Customer Journey Analytics les prend en charge sur la page [Prise en charge des fonctionnalités de Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa).
