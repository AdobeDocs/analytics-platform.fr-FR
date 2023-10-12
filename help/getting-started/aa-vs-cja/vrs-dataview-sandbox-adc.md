---
title: Suites de rapports virtuelles, vues de données, environnements de test Adobe Experience Platform et connecteur source Analytics
description: Découvrez les environnements de création de rapports virtuels et les environnements sandbox.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
feature: Basics
source-git-commit: cb81422ed08420fe9a16c32ddd748c9569197b17
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 90%

---

# Suites de rapports virtuelles, vues de données, environnements de test Adobe Experience Platform et connecteur source Analytics

Adobe propose divers moyens de générer des environnements de création de rapports virtuels et des environnements sandbox. Il est utile de comprendre les similitudes et les différences entre les fonctionnalités suivantes et la manière dont ces fonctionnalités sont liées au [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) :

* Suites de rapports virtuels Adobe Analytics
* Vues de données de Customer Journey Analytics
* Sandbox Adobe Experience Platform

## Suites de rapports virtuels Adobe Analytics

Consultez l’[aperçu des suites de rapports virtuelles](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=fr) pour en savoir plus.

Une suite de rapports virtuelle :

* Peut reposer sur des segments Adobe Analytics.
* Peut s’appliquer de manière non destructive aux données historiques et nouvelles.
* Permet de créer une ou plusieurs vues virtuelles en plus d’une suite de rapports Adobe Analytics pour une utilisation par différentes équipes commerciales.
* Peut servir à contrôler l’accès à et traiter différents types de données pour différents utilisateurs dans Adobe Analytics.
* Offre des possibilités facultatives de [traitement de la période de rapport](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=fr) pour Adobe Analytics. Dans ce cas, une suite de rapports virtuelle peut être utilisée pour créer une définition personnalisée pour &quot;visite&quot;.
* S’applique au moment de l’exécution du rapport, comme pour l’évaluation des segments. Ceci se produit _après_ la collecte et le stockage des données dans Adobe Analytics.
* Est requise pour l’[analyse entre appareils](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=fr) dans Adobe Analytics.
* Dispose du même nombre de variables à utiliser comme suite de rapports Analytics standard (250 eVars, 250 props, 1 000 événements), bien que le traitement des suites de rapports virtuelles puisse limiter les variables qui sont exposées aux utilisateurs.
* Prend en charge les options de calendrier personnalisé.

Une suite de rapports virtuelle n’est pas :

* Un moyen de combiner les suites de rapports.
* Disponible dans Adobe Analytics Data Warehouse.
* Disponible en tant que source pour les flux de données dans Adobe Experience Platform par le biais du connecteur source Analytics. Seules les suites de rapports complets (non virtuels) peuvent être utilisées avec le connecteur source Analytics.


## Vues de données de Customer Journey Analytics

Consultez l’[aperçu des vues des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=fr) pour en savoir plus.

Une vue de données :

* Peut être basée sur des filtres de Customer Journey Analytics.
* Peut s’appliquer de manière non destructive aux données historiques et nouvelles.
* Permet de créer une ou plusieurs vues virtuelles en plus d’une connexion Customer Journey Analytics pour une utilisation par différentes équipes commerciales.
* Peut servir à contrôler l’accès à et traiter différents types de données pour différents utilisateurs et utilisatrices dans Customer Journey Analytics.
* Fournit de puissantes options non destructives pour transformer et améliorer les données entrant dans Customer Journey Analytics par le biais d’une connexion de Customer Journey Analytics.
* Dépend des fonctionnalités de traitement au moment du rapport de Customer Journey Analytics.
* Permet aux utilisateurs de créer une définition personnalisée de la « session ».
* S’applique au moment de l’exécution du rapport, comme pour l’évaluation des filtres. Ceci se produit _après_ que le connecteur source (Adobe Analytics ou autre) a écrit des données sur un jeu de données dans le lac de données Adobe Experience Platform, et _après_ que les données ont été ingérées dans Customer Journey Analytics par le biais d’une connexion Customer Journey Analytics.
* Permet un nombre illimité de variables, bien que le traitement puisse limiter celles exposées aux utilisateurs.
* Permet d’attribuer un nom personnalisé aux conteneurs Événement, Session et Personne.
* Prend en charge les options de calendrier personnalisé.

Une vue de données ne permet pas de :

* Fournir un moyen direct de combiner des suites de rapports ou d’autres jeux de données. Au lieu de cela, les jeux de données sont combinés dans une connexion Customer Journey Analytics. Les données combinées de la connexion Customer Journey Analytics peuvent être utilisées dans toutes les vues de données reposant sur cette connexion.

## Sandbox Adobe Experience Platform

Consultez la [vue d’ensemble des sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=fr) pour en savoir plus.

Un sandbox Adobe Experience Platform :

* Fournit un moyen de diviser une instance Adobe Experience Platform unique en plusieurs environnements virtuels distincts (développement, test, évaluation, production, etc.) pour favoriser le développement et l’évolution d’applications d’expérience digitale.
* Peut être considéré comme un conteneur regroupant toutes les données et applications d’un environnement donné.

Un sandbox Adobe Experience Platform ne :

* Fournit pas de fonctions similaires à celles des suites de rapports virtuelles, des connexions Customer Journey Analytics ou des vues de données.
* Combine pas des suites de rapports avec ou sans autres jeux de données à lui seul. Les jeux de données au sein d’un sandbox peuvent toutefois être combinés dans une connexion Customer Journey Analytics.

Notez que :

* Les données de différents sandbox ne peuvent pas être combinées dans Customer Journey Analytics.
* Le connecteur source Analytics envoie les données de la suite de rapports _vers_ un sandbox donné. Chaque suite de rapports peut être configurée en tant que source pour un seul sandbox. Consultez la [documentation du connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) pour en savoir plus.
