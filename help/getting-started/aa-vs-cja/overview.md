---
title: Comparaison à Adobe Analytics
description: Vue d’ensemble de la comparaison entre Customer Journey Analytics et Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 4cbf01d397e7f89e67ae20702790129478d45cce
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 73%

---

# Comparaison à Adobe Analytics

Cette section de la documentation explique comment comparer et comprendre les différences entre Adobe Customer Journey Analytics et Adobe Analytics.

La différence fondamentale entre les deux solutions réside dans l’étendue des données que vous pouvez prendre en compte lors de la création de vos rapports et analyses.

Dans Customer Journey Analytics, *toute* source de données peut faire partie des données que vous utilisez pour la création de rapports et l’analyse. Adobe Analytics est principalement destiné aux données en ligne collectées sur les sites web et les applications mobiles. Adobe Analytics offre des fonctionnalités d’importation de données provenant d’autres sources, mais l’objectif principal est de fournir plus de contexte sur les données en ligne mentionnées précédemment.

## Collecte de données

Customer Journey Analytics s’appuie sur des données stockées dans des jeux de données Adobe Experience Platform. Vous disposez de plusieurs options pour collecter et ingérer des données de ces jeux de données dans Experience Platform. Ces options sont décrites plus en détail dans la [vue d’ensemble de l’ingestion des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=fr).

Adobe Analytics collecte finalement des données dans la solution elle-même. Nous vous rappelons que vous disposez de plusieurs options pour collecter ces données, qui sont décrites plus en détail dans le [guide d’implémentation d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=fr).

Vous pouvez utiliser les données de votre suite de rapports Adobe Analytics dans Customer Journey Analytics à l’aide du [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr). Ce connecteur ingère dans Experience Platform les données collectées dans Adobe Analytics. Vous pouvez ensuite créer une connexion à ce jeu de données dans Customer Journey Analytics. Voir [Utiliser les données de suite de rapports Adobe Analytics dans Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=fr) pour plus d’informations.


## Traitement des données

Avant de pouvoir créer des rapports sur les données, vous devez souvent traiter ces données afin de vous assurer qu’elles peuvent être correctement utilisées pour la création de rapports. Le traitement des données peut avoir lieu au moment de la collecte et au moment de la création des rapports.

En règle générale, Customer Journey Analytics est conçu pour fonctionner avec les données collectées et stockées dans un jeu de données Experience Platform au moment de la création du rapport. Customer Journey Analytics offre une puissante fonctionnalité de traitement au moment de la création de rapports pour s’assurer que les données sont prêtes pour la création de rapports et l’analyse. Si vous devez mapper, transformer et valider des données avant qu’elles ne soient ingérées dans Experience Platform, vous pouvez utiliser la fonctionnalité [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) d’Experience Platform.

Dans Adobe Analytics, la grande partie de ce traitement des données survient immédiatement après la collecte des données.

Voir [Comparer le traitement des données dans Adobe Analytics et Customer Journey Analytics](data-processing-comparisons.md) et [Règles de traitement, VISTA et classifications par rapport à la préparation des données](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=fr) pour plus d’informations.


## Terminologie

Customer Journey Analytics offre une certaine flexibilité quant à la manière dont vous définissez des dimensions et des mesures, grâce à la flexibilité que les schémas basés sur le modèle de données d’expérience (XDM) sous-jacents offrent. Par exemple, lorsqu’Adobe Analytics utilise des visiteurs, des visites et des accès, Customer Journey Analytics utilise des personnes, des sessions et des événements comme concepts équivalents (vous pouvez modifier le nom selon vos besoins).

Voir [Comparer la terminologie pour les données Analytics transmises par le biais du connecteur source Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=fr) pour plus d’informations sur les différences terminologiques.


## Sandbox et environnements de création de rapports virtuelles

Adobe Analytics a le concept de suites de rapports virtuelles qui vous permet de segmenter les données collectées et de contrôler l’accès à ces données segmentées.

Customer Journey Analytics a un concept similaire, appelé vues de données. Les vues de données sont des conteneurs qui vous permettent de déterminer comment interpréter les données d’une connexion. Ils offrent la flexibilité ultime pour spécifier et configurer des dimensions et des mesures en vue de la préparation de vos rapports et analyses.

Experience Platform propose des sandbox qui peuvent être considérés comme un conteneur contenant des données et des applications pour un environnement donné. La fonctionnalité d’un sandbox n’est pas liée à une suite de rapports virtuelles Adobe Analytics ou à une vue de données de Customer Journey Analytics. Adobe Analytics n’a aucune dépendance ni relation avec les sandbox Experience Platform. Customer Journey Analytics prend en charge les environnements de test Experience Platform, mais il y a quelques considérations importantes.

Voir [Suites de rapports virtuelles, vues de données, sandbox Adobe Experience Platform et connecteur source Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=fr) pour en savoir plus.


## Identités

Customer Journey Analytics prend en charge les identités que vous définissez dans le cadre des schémas auxquels les jeux de données contenant vos données sont conformes. En tant que telles, les identités sont un concept fondamental d’Experience Platform utilisé par Customer Journey Analytics lors de la configuration d’une [connexion](../../connections/overview.md) (en définissant l’ID de personne pour chaque jeu de données) et lors de l’application du [groupement](../../stitching/overview.md) pour l’analyse cross-canal. L’identifiant Experience Cloud (ECID) est une identité importante utilisée par les SDK et l’API Experience Platform.

Adobe Analytics utilise un ensemble plus définitif de champs d’identité, comme l’ID Adobe Analytics (AAID). Lors de l’utilisation du connecteur source Analytics, ces champs d’identification Adobe Analytics reçoivent un traitement spécial. Voir [AAID, ECID, AACUSTOMID et le connecteur source Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=fr) pour plus d’informations.


## Fonctionnalités prises en charge

Vous trouverez une vue d’ensemble des fonctionnalités d’Adobe Analytics et de la prise en charge de ces fonctionnalités par Customer Journey Analytics dans la [Prise en charge des fonctionnalités de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=fr).





