---
title: Suites de rapports virtuelles, vues de données, environnements de test Adobe Experience Platform et connecteur source Analytics
description: Découvrez les environnements de création de rapports virtuels et les environnements sandbox.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
feature: CJA Basics
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 62%

---

# Suites de rapports virtuelles, vues de données, environnements de test Adobe Experience Platform et connecteur source Analytics

Adobe propose divers moyens de générer des environnements de création de rapports virtuels et des environnements sandbox. Il est utile de comprendre les similitudes et les différences entre les fonctionnalités suivantes et la manière dont ces fonctionnalités sont liées au [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) :

* Suites de rapports virtuelles Adobe Analytics
* Vues des données du Customer Journey Analytics
* Environnements de test Adobe Experience Platform

## Suites de rapports virtuelles Adobe Analytics

Consultez l’[aperçu des suites de rapports virtuelles](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=fr) pour en savoir plus.

Une suite de rapports virtuelle :

* Peut reposer sur des segments Adobe Analytics.
* Peut s’appliquer de manière non destructive aux données historiques et nouvelles.
* Permet de créer une ou plusieurs vues virtuelles en plus d’une suite de rapports Adobe Analytics pour une utilisation par différentes équipes commerciales.
* Peut servir à contrôler l’accès à et traiter différents types de données pour différents utilisateurs dans Adobe Analytics.
* Offre des possibilités facultatives de [traitement de la période de rapport](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=fr) pour Adobe Analytics. Dans ce cas, une suite de rapports virtuelle peut être utilisée pour créer une définition personnalisée de la « visite ».
* S’applique au moment de l’exécution du rapport, comme pour l’évaluation des segments. Ceci se produit _après_ la collecte et le stockage des données dans Adobe Analytics.
* Est requise pour l’[analyse entre appareils](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=fr) dans Adobe Analytics.
* Dispose du même nombre de variables à utiliser en tant que suite de rapports Analytics standard (250 eVars, 250 props, 1 000 événements), bien que le traitement des suites de rapports virtuelles puisse limiter les variables exposées aux utilisateurs.
* Prend en charge les options de calendrier personnalisé.

Une suite de rapports virtuelle n’est pas :

* Un moyen de combiner les suites de rapports.
* Disponible dans Adobe Analytics Data Warehouse.
* Disponible comme source pour les flux de données dans Adobe Experience Platform via Analytics Source Connector. Seules les suites de rapports complètes (non virtuelles) peuvent être utilisées avec le connecteur source Analytics.


## Vues des données du Customer Journey Analytics

Consultez l’[aperçu des vues des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=fr) pour en savoir plus.

Une vue de données :

* Peut être basé sur des filtres de Customer Journey Analytics.
* Peut s’appliquer de manière non destructive aux données historiques et nouvelles.
* Permet de créer une ou plusieurs vues virtuelles au-dessus d’une connexion de Customer Journey Analytics, utilisables par différentes équipes commerciales.
* Peut être utilisé pour contrôler l’accès à et traiter différents types de données pour différents utilisateurs dans Customer Journey Analytics.
* Fournit de puissantes options non destructives pour transformer et améliorer les données qui entrent dans le Customer Journey Analytics par le biais d’une connexion de Customer Journey Analytics.
* Dépend des fonctionnalités de traitement de la période de rapport de Customer Journey Analytics.
* Permet aux utilisateurs de créer une définition personnalisée de la « session ».
* S’applique au moment de l’exécution du rapport, comme pour l’évaluation des filtres. Ceci est _after_ le connecteur source (Adobe Analytics ou autre) a écrit des données dans un jeu de données du lac de données Adobe Experience Platform, et _after_ les données ont été ingérées dans Customer Journey Analytics via une connexion de Customer Journey Analytics.
* Permet un nombre illimité de variables, bien que le traitement puisse limiter celles exposées aux utilisateurs.
* Permet d’attribuer un nom personnalisé aux conteneurs Événement, Session et Personne.
* Prend en charge les options de calendrier personnalisé.

Une vue de données ne permet pas de :

* Fournir un moyen direct de combiner des suites de rapports ou d’autres jeux de données. Au lieu de cela, les jeux de données sont combinés avec dans une connexion de Customer Journey Analytics. Les données combinées issues de la connexion du Customer Journey Analytics peuvent être utilisées dans toutes les vues de données basées sur cette connexion.

## Environnements de test Adobe Experience Platform

Consultez l’[aperçu des sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=fr) pour en savoir plus.

Un environnement de test Adobe Experience Platform :

* Fournit un moyen de partitionner une instance Adobe Experience Platform unique en environnements virtuels distincts (développement, test, évaluation, production, etc.) pour favoriser le développement et l’évolution d’applications d’expérience digitale.
* Peut être considéré comme un conteneur regroupant toutes les données et applications d’un environnement donné.

Un environnement de test Adobe Experience Platform ne permet pas :

* Fournissez des fonctions similaires aux suites de rapports virtuelles, aux connexions de Customer Journey Analytics ou aux vues de données.
* Combine pas des suites de rapports avec ou sans autres jeux de données à lui seul. Toutefois, les jeux de données d’un environnement de test peuvent être combinés au sein d’une connexion de Customer Journey Analytics.

Notez que :

* Les données de différents environnements de test ne peuvent pas être combinées dans Customer Journey Analytics.
* Le connecteur source Analytics envoie les données de la suite de rapports _vers_ un sandbox donné. Chaque suite de rapports peut être configurée en tant que source pour un seul sandbox. Consultez la [documentation du connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) pour en savoir plus.
