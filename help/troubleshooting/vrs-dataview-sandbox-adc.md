---
source-git-commit: 7c3bbe2829c83406b2e6824e509c34459ae00f94
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 8%

---
# Suites de rapports virtuelles, vues de données, environnements de test AEP et connecteur source Analytics

Adobe offre divers moyens de créer des environnements de création de rapports virtuels et des environnements de test. Il est utile de comprendre les similitudes et les différences entre les fonctionnalités suivantes et la manière dont ces fonctionnalités sont liées à la fonction [Connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr):

* Suites de rapports virtuelles Adobe Analytics
* Vues des données CJA
* Environnements de test AEP

## Suites de rapports virtuelles Adobe Analytics

Pour plus d’informations, voir : [Suites de rapports virtuelles - Aperçu](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=fr).

Une suite de rapports virtuelle :

* Peut être basé sur des segments Adobe Analytics.
* Peut être appliqué de manière non destructive aux données historiques et nouvelles.
* Permet de créer une ou plusieurs vues virtuelles au-dessus d’une suite de rapports Adobe Analytics pour une utilisation par différentes équipes commerciales.
* Peut être utilisé pour contrôler l’accès à et traiter différents types de données pour différents utilisateurs dans Adobe Analytics.
* Fournit des options facultatives [traitement de la période de rapport](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) fonctionnalités pour Adobe Analytics. Dans ce cas, une suite de rapports virtuelle peut être utilisée pour créer une définition personnalisée pour &quot;visite&quot;.
* S’applique au moment de l’exécution du rapport, comme pour l’évaluation des segments. Ceci est _after_ les données ont été collectées et stockées dans Adobe Analytics.
* Est requis pour [Analyses entre appareils](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=fr) dans Adobe Analytics.
* Dispose du même nombre de variables à utiliser comme suite de rapports Analytics standard (250 eVars, 250 props, 1 000 événements), bien que le traitement des suites de rapports virtuelles puisse limiter les variables qui sont exposées aux utilisateurs.
* Prend en charge les options de calendrier personnalisé.

Une suite de rapports virtuelle n’est (ne) pas :

* Fournir un moyen de combiner les suites de rapports.
* Disponible dans Adobe Analytics Data Warehouse.
* Disponible comme source pour les flux de données dans AEP via Analytics Source Connector. Seules les suites de rapports complètes (non virtuelles) peuvent être utilisées avec Analytics Source Connector.


## Vues des données CJA

Pour plus d’informations, voir : [Présentation des vues des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=fr).

Une vue de données :

* Peut être basé sur des filtres CJA.
* Peuvent être appliquées aux données historiques et nouvelles de manière non destructive.
* Permet de créer une ou plusieurs vues virtuelles au-dessus d’une connexion CJA pour une utilisation par différentes équipes commerciales.
* Peut être utilisé pour contrôler l’accès à et traiter différents types de données pour différents utilisateurs dans CJA.
* Fournit de puissantes options non destructives pour transformer et améliorer les données qui entrent dans CJA par le biais d’une connexion CJA.
* repose sur les fonctionnalités de traitement de la période de rapport de CJA.
* Permet aux utilisateurs de créer une définition personnalisée pour la &quot;session&quot;.
* S’applique au moment de l’exécution du rapport, comme pour l’évaluation des filtres. Ceci est _after_ le connecteur source (Adobe Analytics ou autre) a écrit des données sur un jeu de données dans le lac de données AEP, et _after_ les données ont été ingérées dans CJA via une connexion CJA.
* Permet un nombre illimité de variables, bien que le traitement puisse limiter les variables exposées aux utilisateurs.
* Permet d’attribuer un nom personnalisé aux conteneurs Événement, Session et Personne.
* Prend en charge les options de calendrier personnalisé.

Une vue de données ne permet pas :

* Fournissez directement un moyen de combiner des suites de rapports ou d’autres jeux de données. Au lieu de cela, les jeux de données sont combinés avec dans une connexion CJA. Les données combinées de la connexion CJA peuvent être utilisées dans toutes les vues de données basées sur cette connexion.

## Environnements de test AEP

Pour plus d’informations, voir : [Présentation des environnements de test](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=fr).

Un environnement de test AEP :

* Fournit un moyen de partitionner une instance AEP unique en environnements virtuels distincts (développement, test, évaluation, production, etc.) pour favoriser le développement et l’évolution d’applications d’expérience numérique.
* Peut être considéré comme un conteneur contenant toutes les données et applications d’un environnement donné.

Un environnement de test AEP ne :

* Fournissez des fonctions similaires comme des suites de rapports virtuelles, des connexions CJA ou des vues de données.
* À elle seule, combinez des suites de rapports avec ou sans autres jeux de données. Cependant, les jeux de données d’un environnement de test peuvent être combinés dans une connexion CJA.

En outre :

* Les données de différents environnements de test ne peuvent pas être combinées dans CJA.
* Le connecteur source Analytics envoie les données de la suite de rapports. _into_ un environnement de test spécifique. Chaque suite de rapports peut être configurée comme source pour un seul environnement de test. Voir [Documentation du connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) pour plus d’informations.