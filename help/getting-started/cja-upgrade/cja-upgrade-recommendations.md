---
title: Chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ea16705e96047cbcf41e428d2018ea7c72b2afac
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 8%

---

# Mise à niveau d’Adobe Analytics vers Customer Journey Analytics

Avant de commencer la mise à niveau d’Adobe Analytics vers Customer Journey Analytics, vous devez d’abord connaître les étapes de mise à niveau recommandées.

>[!NOTE]
>
>Les étapes de mise à niveau décrites dans cette section sont les étapes de mise à niveau recommandées que toute organisation peut utiliser pour réussir la mise à niveau de Adobe Analytics vers Customer Journey Analytics.
>
>Toutefois, en fonction de plusieurs facteurs, tels que les contraintes de calendrier et de ressources, les étapes de mise à niveau recommandées peuvent ne pas être pratiques pour votre organisation. Dans ce cas, utilisez la [Adobe Analytics pour Customer Journey Analytics questionnaire](https://gigazelle.github.io/cja-ttv/) de mise à niveau afin de générer dynamiquement des étapes de mise à niveau adaptées aux circonstances uniques de votre organisation.

## Étapes de mise à niveau recommandées pour la plupart des organisations

Les étapes recommandées lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics sont une nouvelle mise en oeuvre du SDK Web Experience Platform, qui est la méthode de collecte de données préférée de Customer Journey Analytics. Avec le SDK Web, Adobe recommande également d’utiliser le connecteur source Analytics afin de conserver les données Adobe Analytics historiques et d’effectuer une comparaison des données côte à côte.

Après la transition complète vers Customer Journey Analytics, le connecteur source Analytics peut être désactivé et le SDK web Experience Platform peut être utilisé exclusivement.

### Processus de mise à niveau recommandée de haut niveau

1. **Implémentation du SDK Web Experience Platform**

   Une nouvelle mise en œuvre du SDK Web Experience Platform constitue le meilleur moyen de collecter des données pour Customer Journey Analytics. Il fournit la meilleure base pour tirer le meilleur parti de Customer Journey Analytics car c’est la méthode la plus performante, la plus simple et la plus pérenne pour la mise en œuvre de Customer Journey Analytics.

   * Rapports et disponibilité des données hautement performants, car Adobe Experience Platform est conçu pour alimenter les cas d’utilisation de personnalisation en temps réel

   * Consolidation de l’implémentation de la collecte de données Adobe Experience Cloud avec les autres produits Experience Cloud (AJO, RTCDP, etc.)

   * Pas de dépendance à la nomenclature Adobe Analytics (prop, eVar, événement, etc.)

1. **Configuration du connecteur source Adobe Analytics**

   Pour faciliter la transition vers l’utilisation du SDK Web Experience Platform avec Customer Journey Analytics, Adobe recommande également d’utiliser le connecteur source Adobe Analytics. Cela vous permet de conserver les données historiques et d’afficher les données de votre mise en oeuvre Adobe Analytics existante dans Customer Journey Analytics, côte à côte avec les données de votre nouvelle mise en oeuvre du SDK Web Experience Platform.

   Le connecteur source Analytics vous permet d’effectuer les opérations suivantes :

   * Insérez les données historiques de votre suite de rapports Adobe Analytics dans Adobe Experience Platform et Customer Journey Analytics.

     Vous pouvez conserver le connecteur source Analytics en cours d’exécution tant que vous devez conserver les données Adobe Analytics historiques.

   * Affichez les données collectées avec votre mise en oeuvre Adobe Analytics d’origine (AppMeasurement, extension Analytics ou extension SDK Web) dans Customer Journey Analytics. Vous pouvez comparer ces données côte à côte avec celles de votre nouvelle mise en oeuvre de SDK Web.

     Vous pouvez conserver le connecteur source Analytics en cours d’exécution jusqu’à ce que vous soyez familiarisé avec les différences. <!--elaborate on what those differences are? -->

   L’implémentation autonome du connecteur source Analytics n’est pas une méthode recommandée à long terme pour l’utilisation de Customer Journey Analytics. Cela est dû à une latence élevée, à des schémas encombrés et complexes, à la dépendance à la nomenclature Adobe Analytics (prop, eVar, etc.) et à la difficulté de passer finalement du connecteur source à l’implémentation recommandée du SDK Web.

### Étapes de mise à niveau recommandées détaillées

Les étapes suivantes décrivent le processus recommandé pour la mise à niveau de Adobe Analytics vers Customer Journey Analytics.

Selon l’environnement et les exigences uniques de votre entreprise, ces étapes recommandées peuvent ne pas convenir à votre entreprise. Dans ce cas, utilisez le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) pour générer dynamiquement des étapes de mise à niveau adaptées aux circonstances uniques de votre entreprise.

1. [Planifiez votre architecture de schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Créez le schéma personnalisé souhaité dans Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. [Créez un jeu de données dans Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. Développez la section qui décrit votre implémentation Adobe Analytics actuelle, puis effectuez les étapes associées :

   +++Pour les mises en œuvre Adobe Analytics à l’aide d’AppMeasurement

   1. [Créez un flux de données dans Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

   +++Pour les implémentations Adobe Analytics utilisant l’extension Analytics (balises)

   1. [Créez un flux de données dans Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

+++ Pour les mises en oeuvre Adobe Analytics à l’aide du SDK Web

   Aucune autre étape n’est requise.

+++

1. [Ajoutez Adobe Experience Platform en tant que service à votre flux de données ](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. Utilisez le tableau suivant pour identifier les fonctionnalités Adobe Analytics que vous souhaitez continuer à utiliser dans Customer Journey Analytics, puis utilisez les informations fournies pour apprendre à configurer ces fonctionnalités dans le cadre de la mise à niveau vers Customer Journey Analytics :

   | Fonctionnalité Adobe Analytics | Exigences d’implémentation pour le Customer Journey Analytics | Informations supplémentaires |
   |---------|----------|---------|
   | Données de classification | Créez un jeu de données de recherche pour chaque dimension contenant des données de classification. |  |
   | Canaux marketing | Créez un champ dérivé du canal marketing. |  |
   | Superposition d’Activity Map et suivi des liens | S.O. | Adobe travaille actuellement sur Activity Map prise en charge des superpositions pour Customer Journey Analytics. |
   | Flux de données | Aucune configuration requise pendant l’implémentation.<br/>[Découvrez les différentes options d’exportation dans Customer Journey Analytics](/help/analysis-workspace/export/export-project-overview.md). | Bien qu’un remplacement direct des flux de données ne soit pas encore disponible dans Customer Journey Analytics, vous pouvez exporter des rapports de Customer Journey Analytics d’Analysis Workspace pour les utiliser dans des outils tiers ou les combiner avec des données externes. |
   | Data Warehouse | Aucune configuration n’est requise pendant la mise en oeuvre.<br/>[Découvrez l’exportation de table complète en Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md). | L’exportation de tableau complet Customer Journey Analytics est l’évolution des rapports de Data Warehouse dans Adobe Analytics, avec de nombreuses nouvelles fonctionnalités souvent demandées qui ne sont pas disponibles dans Data Warehouse aujourd’hui. |
   | Données des médias en flux continu |  |  |

1. (Facultatif) Importez des données historiques d’Adobe Analytics à l’aide du connecteur source Analytics.

   Pour plus d’informations, voir [Utilisation d’un connecteur source](/help/data-ingestion/sources.md#use-a-source-connector) dans [Ingestion et utilisation de données à l’aide des connecteurs source](/help/data-ingestion/sources.md).

1. Utilisez le tableau suivant pour identifier les fonctionnalités de Customer Journey Analytics souhaitées, puis utilisez les informations fournies pour apprendre à configurer ces fonctionnalités dans le cadre de la mise à niveau vers Customer Journey Analytics :

   | Fonctionnalités Customer Journey Analytics souhaitées | Exigences d’implémentation pour le Customer Journey Analytics | Informations supplémentaires |
   |---------|----------|---------|
   | Liaison de données Web à des données provenant d’autres canaux, tels que les données de centre d’appels | Après avoir créé une connexion (comme décrit à une étape ultérieure), ajoutez des jeux de données supplémentaires à votre connexion dans Customer Journey Analytics. |  |
   | Intégration à RTCDP | Activation du profil dans votre schéma et création d’un jeu de données de profil à utiliser dans la plateforme RTCDP | Cela doit être effectué lors de la création de votre schéma XDM. |
   | Intégration à Adobe Journey Optimizer | Utilisez l’objet de personnalisation dans votre mise en œuvre pour l’utiliser dans Adobe Journey Optimizer |  |

1. Développez la section qui décrit votre implémentation Customer Journey Analytics souhaitée, puis effectuez les étapes associées :

   +++Mise en œuvre manuelle (fichier JS)

   1. [Ajoutez alloy.js à votre site](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

+++

   +++Balises

   1. [Créez une propriété de balise dans la collecte de données Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/quick-start#create-a-property).

+++

+++ API

   1. Utilisez l’API Edge Network pour envoyer des données à la banque de données souhaitée.

+++

1. [Créez une connexion en Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. [Créez une vue de données dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Validez que les données circulent dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [Migration de projets et de composants](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

1. Comparez les données de votre ancienne mise en oeuvre à celles de votre nouvelle mise en oeuvre et veillez à comprendre les différences et les raisons de leur existence.

1. Planification de l’intégration des utilisateurs.

   Comme dans Adobe Analytics, Analysis Workspace est le principal outil de Customer Journey Analytics destiné aux utilisateurs et utilisatrices. Cependant, il existe des différences clés à connaître lors de l’utilisation d’Analysis Workspace dans Customer Journey Analytics.

   Donnez à vos utilisateurs et utilisatrices suffisamment de temps (3 à 6 mois) pour se familiariser avec les différences clés d’Analysis Workspace dans Customer Journey Analytics.

   Pour plus d’informations sur certaines différences clés entre Adobe Analytics et Customer Journey Analytics, voir le [Guide de l’utilisateur pour les utilisateurs et utilisatrices d’Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

1. Désactivez la collecte de données d’AppMeasurement.

1. Désactivez le connecteur source Analytics.

   Avec l’implémentation du SDK Web Experience Platform, le connecteur source Analytics n’est nécessaire que pour les données Adobe Analytics historiques et pour comparer les données de votre implémentation d’origine à celles de votre nouvelle implémentation.

   Lorsque vous disposez de suffisamment de données historiques de votre nouvelle implémentation et que vous connaissez les différences de rapport dans Customer Journey Analytics, vous devez désactiver le connecteur source Analytics.

## Générer dynamiquement des étapes de mise à niveau pour votre organisation

Selon plusieurs facteurs, tels que la chronologie et les contraintes de ressources, les étapes de mise à niveau recommandées décrites dans la section [Comprendre les étapes de mise à niveau recommandées](#1-understand-the-recommended-upgrade-steps) peuvent ne pas être pratiques pour votre entreprise.

Pour générer dynamiquement des étapes de mise à niveau pour les circonstances uniques de votre entreprise :

1. Renseignez le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

   Après avoir rempli ce questionnaire, des instructions étape par étape vous sont fournies, décrivant les étapes de mise à niveau optimales qui sont propres aux besoins de votre entreprise. Il s’agit des étapes de mise à niveau qui correspondent le mieux à votre environnement Adobe Analytics existant et à vos objectifs pour Customer Journey Analytics.

1. Suivez les instructions détaillées générées pour effectuer la mise à niveau vers Customer Journey Analytics.

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->









