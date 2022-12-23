---
title: Utiliser les données de suite de rapports Adobe Analytics dans Customer Journey Analytics
description: Comment configurer des suites de rapports Adobe Analytics pour l’ingestion dans AEP et CJA
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: ht
source-wordcount: '767'
ht-degree: 100%

---

# Utiliser les données de suite de rapports Adobe Analytics dans Customer Journey Analytics

Les clients Adobe Analytics peuvent facilement tirer parti de leurs suites de rapports dans Adobe Experience Platform et Customer Journey Analytics à l’aide du [Connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). La discussion suivante explique comment procéder.

## Préparation

Avant de commencer à utiliser les suites de rapports Adobe Analytics dans AEP et CJA, il y a plusieurs choses que vous devriez faire pour préparer vos données et assurer un passage sans encombres vers Customer Journey Analytics. Pour plus d’informations, consultez la page suivante :

* [Passage d’Adobe Analytics à Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Configurer des suites de rapports pour l’ingestion dans Adobe Experience Platform et CJA

Une fois vos données préparées, vous êtes prêt(e) à configurer des suites de rapports à utiliser dans AEP et CJA.

1. **Créez un flux de données pour chaque suite de rapports que vous souhaitez utiliser dans AEP et CJA.** Le [Connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr) est l’outil qui vous permet de [créer une connexion](/help/connections/create-connection.md) (ou flux de données) entre Adobe Analytics et AEP. Vous utiliserez le connecteur source pour créer un flux de données pour chaque suite de rapports que vous souhaitez utiliser dans AEP. Le flux de données crée une copie des données de votre suite de rapports dans laquelle le schéma a été converti en [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=fr) pour une consommation par les applications AEP, y compris CJA. Chaque suite de rapports configurée avec un flux de données via le connecteur source est stockée en tant que jeu de données distinct dans le lac de données AEP. 13 mois de données historiques de suite de rapports seront automatiquement inclus dans chaque flux de données et les nouvelles données seront transmises à AEP de manière continue. Avec le Connecteur source Analytics, vous n’avez pas besoin de créer le schéma à l’avance. Un schéma normalisé propre à Adobe Analytics est automatiquement créé. Toutefois, l’outil de [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) d’AEP peut être utilisé pour améliorer ce schéma avant que les données ne soient stockées dans le lac de données et mises à la disposition de CJA. Notez que certains types de données sont exclus par le connecteur source et ne seront pas présents dans le jeu de données dans le lac de données AEP. D’autres lignes peuvent être exclues entre le lac de données et CJA. Pour plus de détails, voir [Comparer vos données Adobe Analytics aux données CJA](/help/troubleshooting/compare.md).
1. **Utilisez la préparation de données pour vous aider à combiner des suites de rapports dans CJA.** La préparation des données peut être utilisée pour de nombreux types de transformation des données. En outre, une utilisation courante pour les données Adobe Analytics consiste à résoudre les différences dans les mappages prop et/ou eVar entre plusieurs suites de rapports afin que les suites de rapports puissent être facilement combinées dans CJA. Voir [combiner des suites de rapports avec différents schémas](/help/use-cases/aa-data/combine-report-suites.md) pour plus d’informations.
1. **Activez l’ Cross-Channel Analytics** si nécessaire. Lors de la combinaison de plusieurs jeux de données dans CJA, les fonctionnalités de groupement d’identités de l’ Cross-Channel Analytics peuvent aider à résoudre différents espaces de noms d’ID en un seul identifiant regroupé pour une vue unique du client sur plusieurs appareils et canaux. Voir [présentation de l’ Cross-Channel Analytics](/help/connections/cca/overview.md) pour plus d’informations.
1. **Créer une ou plusieurs connexions CJA.** Une fois que les jeux de données de vos suites de rapports sont disponibles dans le lac de données AEP, vous pouvez créer une ou plusieurs [Connexions CJA](/help/connections/overview.md) pour importer ces jeux de données dans CJA. Au sein d’une connexion, les données d’une suite de rapports peuvent être combinées à d’autres types de données, ce qui vous permet de créer une véritable vue cross-canal des expériences client.
1. **Créer une ou plusieurs vues de données CJA.** Une [vue de données](/help/data-views/data-views.md) est un conteneur spécifique à Customer Journey Analytics qui vous permet de déterminer comment interpréter les données d’une connexion CJA. Les vues de données ont de nombreuses et puissantes [options de configuration](/help/data-views/create-dataview.md) pour personnaliser les données présentées à vos utilisateurs et utilisatrices dans [Analysis Workspace](/help/analysis-workspace/home.md).

## Comparaison entre Customer Journey Analytics et Adobe Analytics

Customer Journey Analytics et Adobe Analytics ont des points communs. Par exemple, CJA et Adobe Analytics offrent tous deux la puissance d’Analysis Workspace pour une analyse libre et rapide. Toutefois, comme CJA est une application d’Adobe Experience Platform qui utilise AEP pour l’ingestion de données, CJA et Adobe Analytics diffèrent de plusieurs façons importantes. Les articles suivants sont utiles pour comprendre ces différences :

* [Comparer vos données Adobe Analytics aux données CJA](/help/troubleshooting/compare.md)
* [Prise en charge des fonctionnalités de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Comparez la terminologie des données d’Analytics transmises par le biais du connecteur source Analytics.](/help/getting-started/aa-vs-cja/terminology.md)
* [Comparaison du traitement des données dans les fonctionnalités de création de rapports d’Adobe Analytics et de CJA](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Suites de rapports virtuelles, vues de données, sandbox AEP et connecteur source Analytics](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Règles de traitement, VISTA et classifications par rapport à la préparation des données](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID et le connecteur source Analytics](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
