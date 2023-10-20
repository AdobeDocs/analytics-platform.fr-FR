---
title: Utiliser les données de suite de rapports Adobe Analytics dans Customer Journey Analytics
description: Comment configurer des suites de rapports Adobe Analytics pour une ingestion dans Adobe Experience Platform et Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: cb81422ed08420fe9a16c32ddd748c9569197b17
workflow-type: ht
source-wordcount: '878'
ht-degree: 100%

---

# Utiliser les données de suite de rapports Adobe Analytics dans Customer Journey Analytics

Les clients et clientes Adobe Analytics peuvent facilement tirer parti de leurs suites de rapports dans Adobe Experience Platform et Customer Journey Analytics à l’aide du [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). La discussion suivante explique comment procéder.

>[!IMPORTANT]
>
>Vous devez disposer du package **Sélectionner** afin d’effectuer une analyse des données sur plusieurs suites de rapports. Contactez votre administrateur ou administratrice si vous ne savez pas de quel package de Customer Journey Analytics vous disposez.

## Préparation

Avant de commencer à utiliser les suites de rapports Adobe Analytics dans Adobe Experience Platform et Customer Journey Analytics, il y a plusieurs choses que vous devriez envisager de faire pour préparer vos données et assurer un passage fluide vers Customer Journey Analytics. Pour plus d’informations, consultez la page suivante :

* [Passage d’Adobe Analytics à Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Configurer des suites de rapports pour l’ingestion dans Adobe Experience Platform et Customer Journey Analytics

Une fois vos données préparées, vous pouvez configurer les suites de rapports à utiliser dans Adobe Experience Platform et Customer Journey Analytics.

1. **Créez un flux de données pour chaque suite de rapports que vous souhaitez utiliser dans Adobe Experience Platform et Customer Journey Analytics.** Le [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr) est l’outil qui vous permet de [créer une connexion](/help/connections/create-connection.md) (ou flux de données) entre Adobe Analytics et Adobe Experience Platform. Vous utiliserez le connecteur source pour créer un flux de données pour chaque suite de rapports que vous souhaitez utiliser dans Adobe Experience Platform. Le flux de données crée une copie des données de votre suite de rapports dans laquelle le schéma a été converti en [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=fr) pour une consommation par les applications Adobe Experience Platform, y compris Customer Journey Analytics.<p>Chaque suite de rapports configurée avec un flux de données via le connecteur source est stockée en tant que jeu de données distinct dans le lac de données Adobe Experience Platform. 13 mois de données historiques de suite de rapports seront automatiquement inclus dans chaque flux de données et les nouvelles données seront transmises à Adobe Experience Platform de manière continue. (Notez qu’à compter du 26 avril 2023, le renvoi dans les sanbox hors production est limité à 3 mois.) Avec le connecteur source Analytics, vous n’avez pas besoin de créer le schéma à l’avance. Un schéma normalisé propre à Adobe Analytics est automatiquement créé. Toutefois, l’outil [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) d’Adobe Experience Platform peut être utilisé pour améliorer ce schéma avant que les données ne soient stockées dans le lac de données et mises à la disposition de Customer Journey Analytics. Notez que certains types de données sont exclus par le connecteur source et ne seront pas présents dans le jeu de données dans le lac de données Adobe Experience Platform. D’autres lignes peuvent être exclues entre le lac de données et Customer Journey Analytics. Pour plus de détails, voir [Comparer vos données Adobe Analytics aux données Customer Journey Analytics](/help/troubleshooting/compare.md).
1. **Utilisez la préparation de données pour vous aider à combiner des suites de rapports dans Customer Journey Analytics.** La préparation des données peut être utilisée pour de nombreux types de transformations des données. En outre, une utilisation courante pour les données Adobe Analytics consiste à résoudre les différences dans les mappages prop et/ou eVar entre plusieurs suites de rapports afin que les suites de rapports puissent être facilement combinées dans Customer Journey Analytics. Voir [combiner des suites de rapports avec différents schémas](/help/use-cases/aa-data/combine-report-suites.md) pour plus d’informations.
1. **Activez le groupement** si nécessaire. Lors de la combinaison de plusieurs jeux de données dans Customer Journey Analytics, les fonctionnalités de groupement d’identités peuvent aider à résoudre différents espaces de noms d’ID en un seul identifiant regroupé pour une vue unique du client ou de la cliente sur plusieurs appareils et canaux. Voir [Vue d’ensemble du groupage](../../stitching/overview.md) pour plus d’informations.
1. **Créez une ou plusieurs connexions à Customer Journey Analytics.** Une fois que les jeux de données de vos suites de rapports sont disponibles dans le lac de données d’Adobe Experience Platform, vous pouvez créer une ou plusieurs [connexions à Customer Journey Analytics](/help/connections/overview.md) pour importer ces jeux de données dans Customer Journey Analytics. Au sein d’une connexion, les données d’une suite de rapports peuvent être combinées à d’autres types de données, ce qui vous permet de créer une véritable vue cross-canal des expériences client.
1. **Créez une ou plusieurs vues de données de Customer Journey Analytics.** Une [vue de données](/help/data-views/data-views.md) est un conteneur spécifique à Customer Journey Analytics qui vous permet de déterminer comment interpréter les données d’une connexion dans Customer Journey Analytics. Les vues de données ont de nombreuses et puissantes [options de configuration](/help/data-views/create-dataview.md) pour personnaliser les données présentées à vos utilisateurs et utilisatrices dans [Analysis Workspace](/help/analysis-workspace/home.md).

## Comparaison entre Customer Journey Analytics et Adobe Analytics

Customer Journey Analytics et Adobe Analytics ont des points communs. Par exemple, Customer Journey Analytics et Adobe Analytics offrent tous deux la puissance d’Analysis Workspace pour une analyse libre et rapide. Cependant, comme Customer Journey Analytics est une application d’Adobe Experience Platform qui utilise Adobe Experience Platform pour l’ingestion de données, Customer Journey Analytics et Adobe Analytics diffèrent de plusieurs manières importantes. Les articles suivants sont utiles pour comprendre ces différences :

* [Comparer vos données Adobe Analytics avec les données Customer Journey Analytics](/help/troubleshooting/compare.md)
* [Prise en charge des fonctionnalités de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Comparer la terminologie des données d’Analytics transmises par le biais du connecteur source Analytics](/help/getting-started/aa-vs-cja/terminology.md)
* [Comparer le traitement des données dans les fonctionnalités de création de rapports d’Adobe Analytics et de Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Suites de rapports virtuelles, vues de données, sandbox Adobe Experience Platform et connecteur source Analytics](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Règles de traitement, VISTA et classifications par rapport à la préparation des données](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID et le connecteur source Analytics](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
