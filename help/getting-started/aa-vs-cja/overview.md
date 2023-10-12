---
title: Comparaison à Adobe Analytics
description: Comparaison entre Customer Journey Analytics et Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: cb81422ed08420fe9a16c32ddd748c9569197b17
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 8%

---

# Comparaison à Adobe Analytics

Cette section de la documentation explique comment comparer et comprendre les différences entre Customer Journey Analytics et Adobe Analytics.

La différence fondamentale entre les deux solutions réside dans l’ampleur des données que vous pouvez prendre en compte lors de la création de vos rapports et analyses.

En Customer Journey Analytics, *any* la source de données peut faire partie des données que vous utilisez pour la création de rapports et l’analyse. Adobe Analytics est principalement destiné aux données en ligne collectées sur les sites web et les applications mobiles. Adobe Analytics offre des fonctionnalités d’importation de données provenant d’autres sources, mais l’objectif principal est de fournir plus de contexte aux données en ligne mentionnées précédemment.

## Collecte de données

Customer Journey Analytics s’appuie sur des données stockées dans des jeux de données Experience Platform. Vous disposez de plusieurs options pour collecter et ingérer des données dans ces jeux de données dans Experience Platform. Ces options sont décrites plus en détail dans la section [Présentation de Data Ingestion](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=en).

Adobe Analytics collecte finalement des données dans la solution elle-même. Encore une fois, vous disposez de plusieurs options pour collecter ces données, qui sont décrites plus en détail dans la section [Guide de mise en oeuvre Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=fr).

Vous pouvez utiliser les données de votre suite de rapports Adobe Analytics dans Customer Journey Analytics à l’aide de la variable [Connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr). Ce connecteur utilise les données collectées dans Adobe Analytics pour les ingérer dans Experience Platform, puis les utiliser dans Customer Journey Analytics. Voir [Utilisation des données de suite de rapports Adobe Analytics dans Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=fr) pour plus d’informations.


## Traitement des données

Avant de pouvoir créer des rapports sur les données, vous devez souvent traiter ces données pour vous assurer qu’elles peuvent être correctement utilisées à cette fin. Ce traitement des données peut avoir lieu au moment de la collecte et au moment de la création des rapports.

En règle générale, Customer Journey Analytics est conçu pour fonctionner avec les données collectées et stockées dans un jeu de données Experience Platform au moment du rapport. Customer Journey Analytics offre une puissante fonctionnalité de traitement de la période de rapport pour s’assurer que les données sont prêtes pour la création de rapports et l’analyse. Si vous devez mapper, transformer et valider des données avant qu’elles ne soient ingérées dans Experience Platform, vous pouvez utiliser la variable [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) de l’Experience Platform.

Dans Adobe Analytics, la plupart du traitement des données survient immédiatement après la collecte des données.

Voir [Comparaison du traitement des données dans Adobe Analytics et Customer Journey Analytics](data-processing-comparisons.md) et [Règles de traitement, VISTA et classifications par rapport à la préparation des données](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=fr) pour plus d’informations.


## Terminologie

Customer Journey Analytics offre une certaine flexibilité quant à la manière dont vous définissez des dimensions et des mesures, grâce à la flexibilité que les schémas basés sur le modèle de données d’expérience (XDM) sous-jacents offrent. Par exemple, lorsqu’Adobe Analytics utilise des visiteurs, des visites et des accès, Customer Journey Analytics utilise des personnes, des sessions et des événements comme concepts équivalents, mais vous pouvez modifier le nom à votre gré.

Voir [Comparaison de la terminologie pour les données Analytics transmises par le biais du connecteur source Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=en) pour plus d’informations sur les différences terminologiques.


## Environnements de création de rapports virtuels et environnements de test

Adobe Analytics a le concept de suites de rapports virtuelles qui vous permet de segmenter les données collectées et de contrôler l’accès à ces données segmentées.

Customer Journey Analytics a un concept similaire, appelé Vues de données. Les vues de données sont des conteneurs qui vous permettent de déterminer comment interpréter les données d’une connexion. Il offre la flexibilité ultime pour spécifier et configurer des dimensions et des mesures en vue de la préparation de vos rapports et analyses.

Experience Platform propose des environnements de test qui peuvent être considérés comme un conteneur contenant des données et des applications pour un environnement donné. La fonctionnalité d’un environnement de test n’est pas liée à une suite de rapports virtuelle Adobe Analytics ou à une vue de données de Customer Journey Analytics. Adobe Analytics lui-même n’a aucune dépendance ni relation avec les environnements de test Experience Platform. Customer Journey Analytics prend en charge les environnements de test Experience Platform, mais il y a quelques considérations importantes.

Voir [Suites de rapports virtuelles, vues de données, environnements de test Adobe Experience Platform et connecteur source Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=fr) pour plus d’informations.


## Identités

Customer Journey Analytics prend en charge les identités que vous définissez dans le cadre des schémas auxquels les jeux de données contenant vos données sont conformes. En tant que tels, les identités sont un concept fondamental Experience Platform utilisé par Customer Journey Analytics lors de la configuration d’un [connection](../../connections/overview.md) (en définissant l’ID de personne pour chaque jeu de données) et lors de l’application [groupement](../../stitching/overview.md) pour l’analyse cross-canal. L’identifiant Experience Cloud (ECID) est une identité importante utilisée par les SDK et l’API Experience Platform.

Adobe Analytics utilise un ensemble plus définitif de champs d’identité, comme l’Adobe Analytics ID (AAID). Lors de l’utilisation du connecteur source Analytics, ces champs d’identification Adobe Analytics reçoivent un traitement spécial. Voir [AAID, ECID, AACUSTOMID et le connecteur source Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) pour plus d’informations.


## Fonctionnalités

Vous trouverez un aperçu des fonctionnalités d’Adobe Analytics et de la prise en charge de ces fonctionnalités par Customer Journey Analytics à l’adresse [Prise en charge des fonctionnalités de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=en).





