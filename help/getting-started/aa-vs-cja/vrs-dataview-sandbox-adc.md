---
title: Suites de rapports virtuelles, vues de données, sandbox AEP et connecteur source Analytics
description: Découvrez les environnements de création de rapports virtuels et les environnements sandbox.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
source-git-commit: 6603aed778980c37d69843f11f3ee64e64cd13b5
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 100%

---

# Suites de rapports virtuelles, vues de données, sandbox AEP et connecteur source Analytics

Adobe propose divers moyens de générer des environnements de création de rapports virtuels et des environnements sandbox. Il est utile de comprendre les similitudes et les différences entre les fonctionnalités suivantes et la manière dont ces fonctionnalités sont liées au [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) :

* Suites de rapports virtuelles Adobe Analytics
* Vues de données CJA
* Sandbox AEP

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
* Disponible en tant que source pour les flux de données dans AEP par le biais du connecteur source Analytics. Seules les suites de rapports complètes (non virtuelles) peuvent être utilisées avec le connecteur source Analytics.


## Vues de données CJA

Consultez l’[aperçu des vues des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=fr) pour en savoir plus.

Une vue de données :

* Peut reposer sur des filtres CJA.
* Peut s’appliquer de manière non destructive aux données historiques et nouvelles.
* Permet de créer une ou plusieurs vues virtuelles en plus d’une connexion CJA pour une utilisation par différentes équipes commerciales.
* Peut servir à contrôler l’accès à et traiter différents types de données pour différents utilisateurs dans CJA.
* Fournit des options performantes et non destructives pour transformer et améliorer les données entrantes dans CJA par le biais d’une connexion CJA.
* Repose sur les capacités de traitement de la période de rapport de CJA.
* Permet aux utilisateurs de créer une définition personnalisée de la « session ».
* S’applique au moment de l’exécution du rapport, comme pour l’évaluation des filtres. Ceci se produit _après_ que le connecteur source (Adobe Analytics ou autre) a écrit des données sur un jeu de données dans le lac de données AEP, et _après_ que les données ont été ingérées dans CJA par le biais d’une connexion CJA.
* Permet un nombre illimité de variables, bien que le traitement puisse limiter celles exposées aux utilisateurs.
* Permet d’attribuer un nom personnalisé aux conteneurs Événement, Session et Personne.
* Prend en charge les options de calendrier personnalisé.

Une vue de données ne permet pas de :

* Fournir un moyen direct de combiner des suites de rapports ou d’autres jeux de données. Au lieu de cela, les jeux de données sont combinés dans une connexion CJA. Les données combinées de la connexion CJA peuvent être utilisées dans toutes les vues de données reposant sur cette connexion.

## Sandbox AEP

Consultez l’[aperçu des sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=fr) pour en savoir plus.

Un sandbox AEP :

* Fournit un moyen de diviser une instance AEP unique en plusieurs environnements virtuels distincts (développement, test, étape, exploitation, etc.) pour favoriser le développement et l’évolution d’applications d’expérience digitale.
* Peut être considéré comme un conteneur regroupant toutes les données et applications d’un environnement donné.

Un sandbox AEP ne :

* Fournit pas de fonctions similaires à celles des suites de rapports virtuelles, des connexions CJA ou des vues de données.
* Combine pas des suites de rapports avec ou sans autres jeux de données à lui seul. Les jeux de données au sein d’un environnement de test peuvent toutefois être combinés dans une connexion CJA.

Notez que :

* Les données de différents sandbox ne peuvent pas être combinées dans CJA.
* Le connecteur source Analytics envoie les données de la suite de rapports _vers_ un sandbox donné. Chaque suite de rapports peut être configurée en tant que source pour un seul sandbox. Consultez la [documentation du connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) pour en savoir plus.
