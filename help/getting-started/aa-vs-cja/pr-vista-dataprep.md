---
title: Règles de traitement, VISTA et classifications par rapport à la préparation des données pour Analytics Source Connector
description: En savoir plus sur la transformation des données à l’aide de règles de traitement et de VISTA par rapport à l’utilisation de la préparation des données
source-git-commit: f6b8c5f1e8e82d0eb856b5cfed63b72c7ecfe3db
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 6%

---


# Règles de traitement, VISTA et classifications par rapport à la préparation des données

Adobe Analytics [règles de traitement et règles VISTA](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) fournir un moyen de transformer et de manipuler les données transmises à Adobe Analytics ; [collecte de données](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). Ces transformations se produisent dans le cadre du traitement des données par l’Adobe avant que les données ne soient stockées à des fins de création de rapports et d’analyse dans Adobe Analytics.

[Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) est un outil qui vous permet d’appliquer des mappages et des transformations basés sur des lignes aux données ingérées dans [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en). Par la suite, les données sont mises à la disposition des applications Experience Platform, y compris CJA et d’autres. La préparation des données est intégrée à la plupart des plateformes. [connecteurs source](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en), ainsi qu’avec la fonction [Connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr). Ce connecteur permet d’ingérer des données de suite de rapports d’Adobe Analytics vers Platform.

## Autres transformations à l’aide de la préparation des données {#data-prep}

Les données collectées et stockées dans Adobe Analytics peuvent être transformées par des règles de traitement ou des règles VISTA, ou les deux. Cependant, les suites de rapports qui sont ensuite transférées vers Platform via Analytics Source Connector peuvent être transformées à nouveau à l’aide de la préparation de données. Cela peut être souhaitable à plusieurs fins :

* **Résolution des différences de schémas entre les suites de rapports à utiliser dans CJA et/ou RTCDP**. Par exemple, supposons que la suite de rapports A définit `eVar1` comme &quot;Terme de recherche&quot; et la suite de rapports B définit `eVar2` comme &quot;Terme de recherche&quot;. Vous pouvez utiliser la préparation de données pour mapper les deux eVars différentes dans un champ commun qui contient les données des deux eVars. Cela permet de [combiner des suites de rapports avec différents schémas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) dans [Connexion CJA](/help/connections/overview.md) ou à utiliser dans [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=fr).
* **Mappage `eVars` des champs vers des noms sémantiquement significatifs ;**. `eVars` et `props` les connexions via Analytics Source Connector sont mappées à des champs tels que _\_experience.analytics.customDimensions.eVars.eVar1_. La préparation des données peut être utilisée pour mapper `eVar` et `prop` des champs vers de nouveaux champs dont les noms sont plus significatifs pour vos utilisateurs ou qui correspondent à des noms provenant d’autres sources de données. (Cela peut également être effectué par d’autres moyens, tels que le changement de nom des champs dans une [Vue des données CJA](/help/data-views/create-dataview.md).)
* **Généralisation de la transformation des données**. La préparation des données contient des centaines de fonctions de mappage qui peuvent être utilisées pour calculer et calculer de nouveaux champs en fonction des données provenant du connecteur source Analytics. Vous pouvez diviser les champs délimités en champs distincts. Vous pouvez combiner des champs. Vous pouvez manipuler des chaînes. Vous pouvez extraire des informations d’un champ en fonction d’expressions régulières, et bien plus encore.

## Préparation et classification des données {#classifications}

La préparation de données présente un croisement avec [classifications](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=fr) dans certaines situations.

Par exemple, dans un champ délimité, vous pouvez utiliser la prédisposition de données pour diviser ce champ en plusieurs champs individuels sans utiliser de classifications. En règle générale, les classifications sont un moyen d’ajouter des métadonnées à un champ en chargeant un fichier de recherche fourni en dehors du flux d’accès Analytics entrants.

Vous pouvez par exemple charger un fichier de classification qui regroupe les SKU en &quot;taille&quot;, &quot;marque&quot;, &quot;couleur&quot;, etc. Une autre différence entre les classifications et la préparation de données réside dans le fait que les classifications s’appliquent aux données. _historiquement et à l&#39;avenir_. Les mappages de préparation de données, en revanche, sont appliqués. _forward_ aux données à partir du moment où le mappage est créé.

