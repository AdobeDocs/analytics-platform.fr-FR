---
title: Chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 4%

---

# Mise à niveau d’Adobe Analytics vers Customer Journey Analytics

Avant de commencer la mise à niveau d’Adobe Analytics vers Customer Journey Analytics, vous devez d’abord connaître les étapes de mise à niveau recommandées.

Selon plusieurs facteurs, tels que la chronologie et les contraintes de ressources, les étapes de mise à niveau recommandées peuvent ne pas être pratiques pour votre entreprise. Une fois que vous avez compris les étapes de mise à niveau recommandées, remplissez le questionnaire pour générer dynamiquement des étapes de mise à niveau adaptées aux circonstances propres à votre entreprise.

## 1. Comprendre les étapes de mise à niveau recommandées

>[!NOTE]
>
>Les étapes de mise à niveau décrites dans cette section sont les étapes de mise à niveau recommandées que toute entreprise peut utiliser pour réussir la mise à niveau d’Adobe Analytics vers Customer Journey Analytics.
>
>Cependant, en fonction de plusieurs facteurs, tels que la chronologie et les contraintes de ressources, les étapes de mise à niveau recommandées peuvent ne pas être pratiques pour votre entreprise. Une fois que vous avez compris les étapes de mise à niveau recommandées, remplissez le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) pour générer dynamiquement des étapes de mise à niveau adaptées aux circonstances uniques de votre entreprise.

Les étapes recommandées lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics sont une nouvelle mise en oeuvre du SDK Web Experience Platform, qui est la méthode de collecte de données préférée de Customer Journey Analytics. Avec le SDK Web, Adobe recommande également d’utiliser le connecteur source Analytics afin de conserver les données Adobe Analytics historiques et d’effectuer une comparaison des données côte à côte.

Après la transition complète vers Customer Journey Analytics, le connecteur source Analytics peut être désactivé et le SDK web Experience Platform peut être utilisé exclusivement.

1. **Mise en oeuvre du SDK Web Experience Platform**

   Une nouvelle mise en oeuvre du SDK Web Experience Platform est le meilleur moyen de collecter des données pour Customer Journey Analytics. Il constitue la meilleure base pour tirer le meilleur parti du Customer Journey Analytics, car il s’agit de la méthode d’implémentation de Customer Journey Analytics la plus performante, la plus simple et la plus futée.

   * Rapports et disponibilité des données très performants, car Adobe Experience Platform est conçu pour optimiser les cas d’utilisation de la personnalisation en temps réel.

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

## 2. Générer dynamiquement les étapes de mise à niveau pour votre entreprise

Selon plusieurs facteurs, tels que la chronologie et les contraintes de ressources, les étapes de mise à niveau recommandées décrites dans la section [Comprendre les étapes de mise à niveau recommandées](#1-understand-the-recommended-upgrade-steps) peuvent ne pas être pratiques pour votre entreprise.

Pour afficher les étapes de mise à niveau générées dynamiquement en fonction des circonstances uniques de votre entreprise :

1. Renseignez le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

   Après avoir rempli ce questionnaire, des instructions étape par étape vous sont fournies, décrivant les étapes de mise à niveau optimales propres à votre entreprise. Il s’agit des étapes de mise à niveau qui correspondent le mieux à votre environnement Adobe Analytics existant et à vos objectifs pour Customer Journey Analytics.

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









