---
title: Règles de traitement, VISTA et classifications par rapport à la préparation des données pour le connecteur source Analytics
description: En savoir plus sur la transformation des données à l’aide de règles de traitement et de VISTA par rapport à l’utilisation de la préparation des données
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 95%

---

# Règles de traitement, VISTA et classifications par rapport à la préparation des données 

Les [règles de traitement et les règles VISTA](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=fr) d’Adobe Analytics offrent un moyen de transformer et de manipuler les données transmises à la [collecte de données](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=fr) d’Adobe Analytics. Ces transformations se produisent dans le cadre du traitement des données par Adobe avant leur stockage à des fins de création de rapports et d’analyse dans Adobe Analytics.

La [préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) est un outil qui vous permet d’appliquer des mappages et des transformations reposant sur des lignes aux données ingérées dans [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=fr). Les données sont ensuite mises à la disposition des applications Experience Platform, notamment CJA et d’autres. La préparation des données est intégrée à de nombreux [connecteurs source](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=fr) de Platform ainsi qu’au [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr). Ce connecteur permet d’ingérer des données de suite de rapports d’Adobe Analytics dans Platform.

## Transformations supplémentaires au moyen de la préparation des données {#data-prep}

Les données collectées et stockées dans Adobe Analytics peuvent être transformées par des règles de traitement ou des règles VISTA, ou par les deux. Cependant, les suites de rapports qui sont après cela transférées vers Platform par le biais d’Analytics Source Connector peuvent être de nouveau transformées au moyen de la préparation de données. Cela peut être utile dans plusieurs buts :

* **Résoudre les différences de schémas entre les suites de rapports à utiliser dans CJA et/ou RTCDP**. Par exemple, supposons que la suite de rapports A définit `eVar1` comme un « terme de recherche » et que la suite de rapports B définit `eVar2` comme un « terme de recherche ». Vous pouvez utiliser la préparation de données pour mapper les deux eVars différentes dans un champ commun qui contient les données des deux eVars. Cela permet de [combiner des suites de rapports avec différents schémas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=fr) dans une [connexion CJA](/help/connections/overview.md) ou pour les utiliser dans la [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=fr).
* **Mapper des champs `eVars` à des noms à la signification sémantique**. `eVars` et `props` passant par le connecteur source Analytics sont mappées à des champs tels que _\_experience.analytics.customDimensions.eVars.eVar1_. La préparation des données peut servir à mapper les champs `eVar` et `prop` à de nouveaux champs aux noms plus significatifs pour vos utilisateurs ou correspondant à des noms provenant d’autres sources de données. (Cette opération peut également être effectuée d’autres façons, comment en modifiant le nom des champs dans une [vue de données CJA](/help/data-views/create-dataview.md).)
* **En général, transformer des données**. La préparation des données rassemble des centaines de fonctions de mappage qui peuvent être utilisées pour calculer de nouveaux champs en fonction des données passant par le connecteur source Analytics. Vous pouvez diviser les champs délimités en champs distincts. Vous pouvez combiner des champs. Vous pouvez manipuler des chaînes. Vous pouvez extraire des informations d’un champ en fonction d’expressions régulières, et bien plus encore.

## Préparation et classification des données {#classifications}

La préparation de données rejoint les [classifications](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=fr) dans certains cas.

Par exemple, dans un champ délimité, vous pouvez utiliser la préparation des données pour diviser ce champ en plusieurs champs individuels sans utiliser de classifications. En règle générale, les classifications sont un moyen d’ajouter des métadonnées à un champ en chargeant un fichier de recherche fourni en dehors du flux d’événements Analytics entrants.

Vous pouvez par exemple charger un fichier de classification qui regroupe les SKU en fonction de leur « taille », « marque », « couleur », etc. Une autre différence entre les classifications et la préparation de données réside dans le fait que les classifications s’appliquent à la fois aux données _historiques et futures_. Les mappages de la préparation de données, en revanche, s’appliquent aux données _futures_ à partir du moment où le mappage est créé.
