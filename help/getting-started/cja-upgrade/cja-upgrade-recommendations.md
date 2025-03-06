---
title: Chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: 967d8a957e722a080cd712ea7cf77f26660289da
workflow-type: tm+mt
source-wordcount: '1585'
ht-degree: 11%

---

# Mise à niveau d’Adobe Analytics vers Customer Journey Analytics

Lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics, vous pouvez suivre les [ étapes de mise à niveau recommandées ](#recommended-upgrade-steps-for-most-organizations). Vous pouvez également [générer dynamiquement des étapes de mise à niveau](#dynamically-generate-upgrade-steps-for-your-organization) en fonction des circonstances spécifiques à votre entreprise.

## Étapes de mise à niveau recommandées pour la plupart des organisations {#upgrade-process}

Le processus recommandé de mise à niveau d’Adobe Analytics vers Customer Journey Analytics est une nouvelle implémentation d’Experience Platform Web SDK, qui est la méthode de collecte de données préférée pour Customer Journey Analytics. En conjonction avec le Web SDK, Adobe recommande également d’utiliser le connecteur source Analytics pour vous aider à effectuer la transition vers Customer Journey Analytics. Utilisez le connecteur source Analytics pour conserver les données Adobe Analytics historiques et comparer les données côte à côte.

Une fois que vous disposez de suffisamment de données historiques à l’aide d’Experience Platform Web SDK et que vous avez entièrement effectué la transition vers Customer Journey Analytics, le connecteur source Analytics peut être désactivé et le SDK Web peut être utilisé exclusivement.

>[!NOTE]
>
>Si les étapes de mise à niveau décrites dans cette section ne sont pas pratiques pour votre entreprise, utilisez le questionnaire de mise à niveau [d’Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) pour générer dynamiquement des étapes de mise à niveau adaptées aux circonstances uniques de votre entreprise.

### Processus de mise à niveau recommandé de haut niveau {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Données historiques depuis Adobe Analytics"
>abstract="Intégrez vos données historiques de suite de rapports Adobe Analytics à Adobe Experience Platform et Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

1. **Implémenter Experience Platform Web SDK (pour la collecte de données en cours)**

   Une nouvelle mise en œuvre d’Experience Platform Web SDK est le meilleur moyen de collecter des données pour Customer Journey Analytics. Il offre les meilleures bases pour tirer le meilleur parti de Customer Journey Analytics, car il s’agit de la méthode la plus performante, la plus simple et la plus durable pour mettre en œuvre Customer Journey Analytics.

   * Rapports et disponibilité des données hautement performants, car Adobe Experience Platform est conçu pour alimenter les cas d’utilisation de la personnalisation en temps réel

   * Consolidation de l’implémentation de la collecte de données Adobe Experience Cloud avec les autres produits Experience Cloud (AJO, RTCDP, etc.)

   * Pas de dépendance à la nomenclature Adobe Analytics (prop, eVar, événement, etc.)

1. **Configurer le connecteur source Adobe Analytics (pour importer les données historiques)**

   Pour faciliter la transition vers l’utilisation d’Experience Platform Web SDK avec Customer Journey Analytics, Adobe recommande également d’utiliser le connecteur source Adobe Analytics. Vous pouvez ainsi conserver les données historiques et afficher les données de votre implémentation Adobe Analytics existante dans Customer Journey Analytics, côte à côte avec les données de votre nouvelle implémentation Experience Platform Web SDK.

   Le connecteur source Analytics vous permet d’effectuer les opérations suivantes :

   * Intégrez vos données historiques de suite de rapports Adobe Analytics à Adobe Experience Platform et Customer Journey Analytics.

     Vous pouvez laisser le connecteur source Analytics en cours d’exécution aussi longtemps que vous devez conserver les données Adobe Analytics historiques.

   * Affichez les données collectées avec votre implémentation Adobe Analytics d’origine (AppMeasurement, l’extension Analytics ou l’extension Web SDK) dans Customer Journey Analytics. Vous pouvez comparer ces données côte à côte avec celles de votre nouvelle implémentation de Web SDK.

     Vous pouvez conserver le connecteur source Analytics en cours d’exécution jusqu’à ce que vous connaissiez et maîtrisiez les différences. <!--elaborate on what those differences are? -->

   Le connecteur source Analytics en tant qu’implémentation autonome n’est pas une méthode recommandée à long terme pour utiliser Customer Journey Analytics. Cela est dû à une latence élevée, à des schémas encombrés et complexes, à la dépendance à la nomenclature Adobe Analytics (prop, eVar, etc.) et à la difficulté à passer finalement du connecteur source Analytics à l’implémentation recommandée de Web SDK.

### Étapes de mise à niveau recommandées détaillées

Les étapes suivantes décrivent le processus recommandé pour effectuer la mise à niveau d’Adobe Analytics vers Customer Journey Analytics.

Chaque étape fournit une explication générale d’un processus plus détaillé. Suivez le lien de chaque étape et effectuez les tâches associées, puis revenez à cette page et passez à l’étape suivante du processus.

1. [Planifiez l’architecture de votre schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Création du schéma personnalisé souhaité dans Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Tenez compte des options suivantes lors de la création de votre schéma :

   * Si vous souhaitez intégrer Customer Journey Analytics à RTCDP, vous devez activer l’option **[!UICONTROL Profile]** sur votre schéma, comme décrit dans la section [Création d’un schéma XDM à utiliser avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md). Lorsque cette option est activée, lorsque les données sont ingérées dans des jeux de données basés sur ce schéma, ces données sont fusionnées dans le profil client en temps réel.

   * Si vous souhaitez inclure des données de médias en flux continu, vous devez [configurer votre schéma pour ingérer et utiliser des données en flux continu](/help/data-ingestion/streaming.md).

1. [Créer un jeu de données dans Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Facultatif) Si vous utilisez des données de classification dans Adobe Analytics, vous pouvez ajouter des données de classification à votre jeu de données dans Customer Journey Analytics.

   Pour ce faire, [créez un jeu de données de recherche pour chaque dimension contenant des données de classification](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Pour les implémentations d’Adobe Analytics utilisant AppMeasurement ou l’extension Analytics (balises), [créez un flux de données dans Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Pour les implémentations d’Adobe Analytics utilisant le SDK Web, un flux de données existe déjà. Pour plus d’informations, voir [Configurer votre implémentation Adobe Analytics Web SDK existante pour envoyer des données à Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md).

1. [Ajoutez Adobe Experience Platform en tant que service à votre flux de données](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Facultatif) Si vous souhaitez intégrer Customer Journey Analytics à Adobe Journey Optimizer, utilisez l’objet de personnalisation dans votre implémentation pour l’utiliser dans Adobe Journey Optimizer.

1. Développez la section qui décrit la manière dont vous souhaitez implémenter Experience Platform Web SDK pour votre implémentation Customer Journey Analytics, puis effectuez les étapes associées :

   +++Implémentation manuelle (fichier JS)

   1. [Ajoutez alloy.js à votre site](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Renseignez un objet XDM et envoyez-le au flux de données.

+++

   +++Balises

   1. [Créez une propriété de balise et ajoutez l’extension Adobe Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Ajouter l’extension SDK Web d’Adobe Experience Platform à votre propriété de balise](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [Implémentez la balise de chargement sur votre site](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Ajoutez la logique de collecte de données XDM à votre balise](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Utilisez l’API Edge Network pour envoyer des données au flux de données souhaité.

+++

1. [Vérifiez que votre implémentation de Web SDK envoie des données à un jeu de données](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Créer une connexion dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Facultatif) Liez les données web aux données d’autres canaux, telles que les données du centre d’appels.

   Pour ce faire, ajoutez des jeux de données supplémentaires à votre connexion Customer Journey Analytics, comme décrit dans la section [Importer des données du centre d’appel et web](/help/use-cases/cross-channel/call-center.md).

1. [Créer une vue de données dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Vérifiez que les données sont transmises à la vue de données dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [Migration de projets et de composants](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Facultatif) Si vous utilisez des canaux marketing dans Adobe Analytics, vous pouvez [créer un champ dérivé de canal marketing dans Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   Les champs dérivés sont un aspect important des rapports en temps réel dans Customer Journey Analytics. Un champ dérivé vous permet de définir à la volée des manipulations de données (souvent complexes) par le biais d’un créateur de règles personnalisable.

   Les champs dérivés permettent de définir un champ de canal marketing dérivé qui détermine le canal marketing approprié en fonction d’une ou de plusieurs conditions (par exemple, le paramètre d’URL, l’URL de page ou le nom de page).

   Utilisez [le modèle de fonction Canaux marketing](/help/data-views/derived-fields/derived-fields.md#marketing-channels) dans les champs dérivés pour créer rapidement un champ dérivé pour les canaux marketing.

1. Comparez les données de l’ancienne mise en œuvre dans Adobe Analytics aux données de la nouvelle mise en œuvre dans Customer Journey Analytics. Vérifiez que vous comprenez bien les différences et la raison de leur existence. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Importez des données historiques depuis Adobe Analytics à l’aide du connecteur source Analytics :

   >[!NOTE]
   >
   >Procédez comme suit si vous n’avez pas créé de connecteur source Analytics auparavant.
   >
   >Si vous utilisez déjà le connecteur source Analytics avec Customer Journey Analytics, suivez les étapes de la section [Transition du connecteur source Analytics vers le SDK Web pour Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Créer un schéma XDM pour le connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. Si vous ne disposez pas déjà d’un connecteur source Analytics, [créez le connecteur source Analytics et mappez les champs à votre schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      Ou

      Si vous disposez déjà d’un connecteur source Analytics, [mappez les champs du connecteur source à votre schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Ajoutez le jeu de données du connecteur source Analytics à la connexion](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. Planifiez l’intégration des utilisateurs.

   Comme dans Adobe Analytics, Analysis Workspace est le principal outil de Customer Journey Analytics destiné aux utilisateurs et utilisatrices. Cependant, il existe des différences clés à connaître lors de l’utilisation d’Analysis Workspace dans Customer Journey Analytics.

   Donnez à vos utilisateurs et utilisatrices suffisamment de temps (3 à 6 mois) pour se familiariser avec les différences clés d’Analysis Workspace dans Customer Journey Analytics.

   Pour plus d’informations sur certaines différences clés entre Adobe Analytics et Customer Journey Analytics, voir le [Guide de l’utilisateur pour les utilisateurs et utilisatrices d’Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

1. En savoir plus sur [la prise en charge des fonctionnalités dans Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). La plupart des fonctionnalités d’Adobe Analytics sont prises en charge dans Customer Journey Analytics et de nombreuses fonctionnalités supplémentaires sont disponibles dans Customer Journey Analytics.

1. Désactivez Adobe Analytics lorsque l’implémentation de Customer Journey Analytics Web SDK est terminée et que vous êtes à l’aise avec les données que vous collectez.

   Adobe vous recommande de conserver votre environnement Adobe Analytics en cours d’exécution pendant un certain temps après l’implémentation de Customer Journey Analytics.

   Pour plus d’informations sur l’utilisation d’Adobe Analytics pendant et après une mise à niveau, ainsi que sur la durée suggérée de désactivation d’Adobe Analytics, voir [Évaluation de la durée pendant laquelle vous avez besoin d’Adobe Analytics après la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

## Générer de manière dynamique des étapes de mise à niveau pour votre organisation

Selon plusieurs facteurs, tels que les contraintes de calendrier et de ressources, les étapes de mise à niveau recommandées décrites dans la section [Présentation des étapes de mise à niveau recommandées](#1-understand-the-recommended-upgrade-steps) peuvent ne pas être pratiques pour votre entreprise.

Pour générer dynamiquement des étapes de mise à niveau en fonction des spécificités de votre entreprise :

1. Remplissez le questionnaire de mise à niveau d’[Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

   Après avoir rempli ce questionnaire, des instructions détaillées vous sont fournies, décrivant les étapes optimales de mise à niveau en fonction des besoins de votre entreprise. Il s’agit des étapes de mise à niveau qui s’alignent le mieux sur votre environnement Adobe Analytics existant et vos objectifs pour Customer Journey Analytics.

1. Suivez les instructions étape par étape générées pour effectuer la mise à niveau vers Customer Journey Analytics.

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
