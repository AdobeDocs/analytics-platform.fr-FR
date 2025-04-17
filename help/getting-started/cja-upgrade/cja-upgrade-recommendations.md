---
title: Mettre à niveau Adobe Analytics vers Customer Journey Analytics
description: Découvrez les étapes recommandées lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: dfc9ba843fbddc135c0f8160fb672adb36e9146f
workflow-type: tm+mt
source-wordcount: '3281'
ht-degree: 57%

---

# Mettre à niveau Adobe Analytics vers Customer Journey Analytics

Lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics, vous pouvez suivre les [étapes de mise à niveau recommandées](#recommended-upgrade-steps-for-most-organizations). Vous pouvez également suivre les [étapes de mise à niveau générées dynamiquement](#dynamically-generate-upgrade-steps-for-your-organization) en fonction des circonstances spécifiques à votre entreprise.

## Étapes de mise à niveau recommandées pour la plupart des organisations {#upgrade-process}

Le processus recommandé de mise à niveau d’Adobe Analytics vers Customer Journey Analytics est une nouvelle implémentation du SDK web Experience Platform, qui est la méthode de collecte de données préférée pour Customer Journey Analytics. En conjonction avec le SDK web, Adobe recommande également d’utiliser le connecteur source Analytics pour vous aider à effectuer la transition vers Customer Journey Analytics. Utilisez le connecteur source Analytics pour conserver les données Adobe Analytics historiques et comparer les données côte à côte.

Une fois que vous disposez de suffisamment de données historiques à l’aide de SDK web Experience Platform et que vous avez entièrement effectué la transition vers Customer Journey Analytics, le connecteur source Analytics peut être désactivé et le SDK web peut être utilisé exclusivement.

>[!NOTE]
>
>Si les étapes de mise à niveau décrites dans cette section ne sont pas pratiques pour votre entreprise, utilisez le Guide de mise à niveau de Customer Journey Analytics pour générer dynamiquement des étapes de mise à niveau adaptées aux circonstances uniques de votre entreprise. (Pour accéder au guide depuis Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Workspace]**, puis sélectionnez **[!UICONTROL Mettre à niveau vers Customer Journey Analytics]** dans le panneau de gauche. Suivez les instructions à l’écran.)

### Processus de mise à niveau recommandé de haut niveau {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Données historiques depuis Adobe Analytics"
>abstract="Intégrez vos données historiques de suite de rapports Adobe Analytics à Adobe Experience Platform et Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

1. **Implémenter le SDK web Experience Platform (pour la collecte de données en cours)**

   Une nouvelle implémentation du SDK web Experience Platform est le meilleur moyen de collecter des données pour Customer Journey Analytics. Cela offre les meilleures bases pour tirer parti au maximum de Customer Journey Analytics, car il s’agit de la méthode la plus performante, la plus simple et la plus durable pour implémenter Customer Journey Analytics.

   * Rapports et disponibilité des données hautement performants, grâce à Adobe Experience Platform conçu pour optimiser les cas d’utilisation de personnalisation en temps réel

   * Consolidation de l’implémentation de la collecte de données Adobe Experience Cloud avec les autres produits Experience Cloud (AJO, RTCDP, etc.)

   * Pas de dépendance à la nomenclature Adobe Analytics (prop, eVar, événement, etc.)

1. **Configurer le connecteur source Adobe Analytics (pour importer les données historiques)**

   Pour faciliter la transition vers l’utilisation du SDK web Experience Platform avec Customer Journey Analytics, Adobe recommande également d’utiliser le connecteur source Adobe Analytics. Vous pouvez ainsi conserver les données historiques et afficher les données de votre implémentation Adobe Analytics existante dans Customer Journey Analytics, côte à côte avec les données de votre nouvelle implémentation du SDK web Experience Platform.

   Le connecteur source Analytics vous permet d’effectuer les opérations suivantes :

   * Intégrez vos données historiques de suite de rapports Adobe Analytics à Adobe Experience Platform et Customer Journey Analytics.

     Vous pouvez laisser le connecteur source Analytics en cours d’exécution aussi longtemps que nécessaire pour conserver les données Adobe Analytics historiques.

   * Affichez les données collectées avec votre implémentation Adobe Analytics d’origine (AppMeasurement, l’extension Analytics ou l’extension SDK web) dans Customer Journey Analytics. Vous pouvez comparer ces données côte à côte avec celles de votre nouvelle implémentation du SDK web.

     Vous pouvez conserver le connecteur source Analytics en cours d’exécution jusqu’à ce que vous connaissiez et maîtrisiez les différences. <!--elaborate on what those differences are? -->

   Le connecteur source Analytics en tant qu’implémentation autonome n’est pas une méthode recommandée à long terme pour utiliser Customer Journey Analytics. Cela est dû à une latence élevée, à des schémas encombrés et complexes, à la dépendance à la nomenclature Adobe Analytics (prop, eVar, etc.) et à la difficulté à passer finalement du connecteur source Analytics à l’implémentation recommandée du SDK web.

### Étapes détaillées de mise à niveau recommandées

Les étapes suivantes décrivent le processus recommandé pour effectuer la mise à niveau d’Adobe Analytics vers Customer Journey Analytics.

Chaque étape fournit une explication générale d’un processus plus détaillé. Suivez le lien de chaque étape et effectuez les tâches associées, puis revenez à cette page et passez à l’étape suivante du processus.

1. [Planifiez l’architecture de votre schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Créez le schéma personnalisé souhaité dans Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Tenez compte des options suivantes lors de la création de votre schéma :

   * Si vous souhaitez intégrer Customer Journey Analytics à RTCDP, vous devez activer l’option **[!UICONTROL Profil]** sur votre schéma, comme décrit dans la section [Création d’un schéma XDM à utiliser avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md). Une fois cette option activée, lorsque les données sont ingérées dans des jeux de données basés sur ce schéma, ces données sont fusionnées dans le profil client en temps réel.

   * Si vous souhaitez inclure des données de médias en streaming, vous devez [configurer votre schéma pour ingérer et utiliser des données en streaming](/help/data-ingestion/streaming.md).

1. [Créez un jeu de données dans Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Facultatif) Si vous utilisez des données de classification dans Adobe Analytics, vous pouvez ajouter des données de classification à votre jeu de données dans Customer Journey Analytics.

   Pour ce faire, [créez un jeu de données de recherche pour chaque dimension contenant des données de classification](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Pour les implémentations d’Adobe Analytics utilisant AppMeasurement ou l’extension Analytics (balises), [créez un train de données dans Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Pour les implémentations d’Adobe Analytics utilisant le SDK Web, un flux de données existe déjà. Pour plus d’informations, voir [Configurer votre implémentation Adobe Analytics Web SDK existante pour envoyer des données à Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md).

1. [Ajoutez Adobe Experience Platform en tant que service à votre train de données](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Facultatif) Si vous souhaitez intégrer Customer Journey Analytics à Adobe Journey Optimizer, utilisez l’objet de personnalisation dans votre implémentation pour l’utiliser dans Adobe Journey Optimizer.

1. Développez la section qui décrit la manière dont vous souhaitez implémenter le SDK web Experience Platform pour votre implémentation Customer Journey Analytics, puis effectuez les étapes associées :

   +++Implémentation manuelle (fichier JS)

   1. [Ajoutez alloy.js à votre site](https://experienceleague.adobe.com/fr/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Remplissez un objet XDM et envoyez-le au train de données.

+++

   +++Balises

   1. [Créez une propriété de balise et ajoutez l’extension SDK web Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Ajouter l’extension SDK Web d’Adobe Experience Platform à votre propriété de balise](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [Implémentez la balise loader sur votre site](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Ajoutez une logique de collecte de données XDM à votre balise](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Utilisez l’API Edge Network pour envoyer des données au train de données souhaité.

+++

1. [Validez que votre implémentation du SDK web envoie des données à un jeu de données](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Créez une connexion dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Facultatif) Liez les données web aux données d’autres canaux, telles que les données du centre d’appel.

   Pour ce faire, ajoutez des jeux de données supplémentaires à votre connexion Customer Journey Analytics, comme décrit dans la section [Importer des données du centre d’appel et du web](/help/use-cases/cross-channel/call-center.md).

1. [Créez une vue de données dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Vérifiez que les données sont transmises à la vue de données dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. Dans votre environnement Adobe Analytics, [utilisez l’inventaire Analytics](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/analytics-inventory) pour obtenir une vue d’ensemble complète de votre environnement Adobe Analytics, y compris le nombre de projets et de composants, les suites de rapports, les utilisateurs, etc.

1. [Migrez des projets et des composants](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Facultatif) Si vous utilisez des canaux marketing dans Adobe Analytics, vous pouvez [créer un champ dérivé de canal marketing dans Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   Les champs dérivés constituent un aspect important des rapports en temps réel dans Customer Journey Analytics. Un champ dérivé vous permet de définir à la volée des manipulations de données (souvent complexes) par le biais d’un créateur de règles personnalisable.

   Les champs dérivés permettent de définir un champ de canal marketing dérivé qui détermine le canal marketing approprié en fonction d’une ou de plusieurs conditions (par exemple, le paramètre d’URL, l’URL de page ou le nom de page).

   Utilisez [le modèle de fonction des canaux marketing](/help/data-views/derived-fields/derived-fields.md#marketing-channels) dans les champs dérivés pour créer rapidement un champ dérivé pour les canaux marketing.

1. Comparez les données de votre ancienne implémentation dans Adobe Analytics aux données de la nouvelle implémentation dans Customer Journey Analytics. Vérifiez que vous comprenez bien les différences et la raison de leur existence. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Importez des données historiques depuis Adobe Analytics à l’aide du connecteur source Analytics :

   >[!NOTE]
   >
   >Suivez les étapes suivantes si vous n’avez pas créé de connecteur source Analytics auparavant.
   >
   >Si vous utilisez déjà le connecteur source Analytics avec Customer Journey Analytics, suivez les étapes de la section [Transition du connecteur source Analytics vers le SDK web pour Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Créer un schéma XDM pour le connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. Si vous ne disposez pas déjà d’un connecteur source Analytics, [créez le connecteur source Analytics et mappez les champs à votre schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      Ou

      Si vous disposez déjà d’un connecteur source Analytics, [mappez les champs du connecteur source à votre schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Ajoutez le jeu de données du connecteur source Analytics à la connexion](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. Planifiez l’intégration des utilisateurs et utilisatrices.

   Comme dans Adobe Analytics, Analysis Workspace est le principal outil de Customer Journey Analytics destiné aux utilisateurs et utilisatrices. Cependant, il existe des différences clés à connaître lors de l’utilisation d’Analysis Workspace dans Customer Journey Analytics.

   Donnez à vos utilisateurs et utilisatrices suffisamment de temps (3 à 6 mois) pour se familiariser avec les différences clés d’Analysis Workspace dans Customer Journey Analytics.

   Pour plus d’informations sur certaines différences clés entre Adobe Analytics et Customer Journey Analytics, voir le [Guide de l’utilisateur pour les utilisateurs et utilisatrices d’Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

1. Découvrez [la prise en charge des fonctionnalités dans Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). La plupart des fonctionnalités d’Adobe Analytics sont prises en charge dans Customer Journey Analytics et de nombreuses fonctionnalités supplémentaires sont disponibles dans Customer Journey Analytics.

1. Désactivez Adobe Analytics lorsque l’implémentation du SDK web Customer Journey Analytics est terminée et que vous êtes à l’aise avec les données que vous collectez.

   Adobe vous recommande de conserver votre environnement Adobe Analytics en cours d’exécution pendant un certain temps après l’implémentation de Customer Journey Analytics.

   Pour plus d’informations sur l’utilisation d’Adobe Analytics pendant et après une mise à niveau, ainsi que sur le moment suggéré pour désactiver Adobe Analytics, consultez [Évaluation de la durée pendant laquelle vous avez besoin d’Adobe Analytics après la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

## Générer de manière dynamique des étapes de mise à niveau pour votre organisation

Selon plusieurs facteurs, tels que les contraintes de calendrier et de ressources, les étapes de mise à niveau recommandées décrites dans la section [Présentation des étapes de mise à niveau recommandées](#recommended-upgrade-steps-for-most-organizations) peuvent ne pas être pratiques pour votre entreprise. Dans ce cas, vous pouvez générer dynamiquement des étapes de mise à niveau en fonction des circonstances spécifiques à votre entreprise. Le processus de génération de ces étapes varie selon que vous avez déjà accès à Customer Journey Analytics ou non.

### Pour les clients qui ont accès à Customer Journey Analytics

Pour générer dynamiquement des étapes de mise à niveau en fonction des spécificités de votre entreprise, procédez comme suit :

1. Complétez le Guide de mise à niveau de Customer Journey Analytics.

   Dans Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Workspace]**, puis sélectionnez **[!UICONTROL Mettre à niveau vers Customer Journey Analytics]** dans le panneau de gauche. Suivez les instructions à l’écran.

   Après avoir terminé ce guide de mise à niveau, vous recevez des instructions détaillées décrivant les étapes optimales de mise à niveau adaptées aux besoins de votre entreprise. Il s’agit des étapes de mise à niveau qui s’alignent le mieux sur votre environnement Adobe Analytics existant et vos objectifs pour Customer Journey Analytics. Les étapes de mise à niveau sont disponibles sous forme de lien partageable ou de fichier .csv téléchargeable.

1. Suivez les instructions étape par étape générées pour effectuer la mise à niveau vers Customer Journey Analytics.

### Pour les clients qui n’ont pas encore accès à Customer Journey Analytics

Pour générer dynamiquement des étapes de mise à niveau en fonction des spécificités de votre entreprise, procédez comme suit :

1. Contactez l’équipe chargée de votre compte Adobe pour obtenir le Guide de mise à niveau de Customer Journey Analytics.

   Votre équipe de compte Adobe peut vous guider tout au long du guide de mise à niveau et vous fournir un fichier .csv contenant les questions, vos réponses et les étapes de mise à niveau générées dynamiquement qui sont propres à votre entreprise.

   Avant de contacter l’équipe chargée de votre compte Adobe, familiarisez-vous avec les questions incluses dans le guide de mise à niveau de Customer Journey Analytics et déterminez vos réponses. Le Guide de mise à niveau de Customer Journey Analytics contient les questions suivantes et les réponses possibles :


   | Question | Réponses disponibles | Informations supplémentaires |
   |---------|----------|---------|
   | Sélectionnez l’option qui décrit votre mise en œuvre actuelle d’Adobe Analytics. Ces informations peuvent avoir une incidence sur les options de mise à niveau qui vous sont proposées lors de la mise à niveau vers Customer Journey Analytics. | Sélectionnez une option : <ul><li>**AppMeasurement:**<br/> Implémentation de JavaScript qui charge AppMeasurement.js sur une page et envoie des données à Adobe à l’aide de l’objet s (par exemple, s.eVar1).</li><li>**Extension Adobe Analytics (balises) :** <br/>implémentation de balises qui charge la collecte de données Adobe Experience Platform (anciennement appelée Launch). L’extension Adobe Analytics est installée sur la balise.</li><li>**Extension Experience Platform Web SDK (balises) : implémentation**<br/> balises qui charge la collecte de données Adobe Experience Platform (anciennement appelée Launch). L’extension SDK web est installée sur la balise.</li><li>**Experience Platform Web SDK (alloy.js) :** implémentation de JavaScript qui charge la bibliothèque Web SDK (alloy.js) sur une page et envoie des données à Adobe à l’aide d’une payload JSON.</li><li>**API Bulk Data Insertion :**<br/> implémentation qui utilise l’API d’insertion de données ou l’API d’insertion de données en bloc.</li><li>**Experience Platform Mobile SDK :**<br/> implémentation qui utilise Adobe Experience Platform Mobile SDK.</li><li>**AppMeasurement à l’aide d’un outil de gestion des balises tiers :**<br/> implémentation qui utilise un outil de gestion des balises tiers.</li><li>**Un produit autre qu’Adobe Analytics :**<br/> une implémentation qui collecte des données pour un produit autre qu’Adobe Analytics, tel que Google Analytics. La sélection de cette option désactive plusieurs options du guide de mise à niveau qui ne s’appliquent pas lors de la mise à niveau vers Customer Journey Analytics à partir d’un produit autre que Adobe Analytics. </li><li>**Je ne sais pas :**<br/> si vous n’êtes pas la personne qui gère votre implémentation, vous pouvez temporairement sélectionner cette option.</li></ul><p>Sélectionnez si applicable :<ul><li>**Notre mise en œuvre utilise actuellement le connecteur source Analytics :**<br/> Le connecteur source Analytics vous permet d’obtenir facilement de la valeur de Customer Journey Analytics, mais il vous faut payer pour Adobe Analytics et Customer Journey Analytics. Ce guide peut vous aider à passer à une mise en œuvre indépendante du SDK web.</li></ul></p> | <ul><li>[Découvrez votre implémentation Adobe Analytics et comment elle affecte votre mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[Transition du connecteur source Analytics vers Web SDK pour Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | La plupart des fonctionnalités d’Adobe Analytics sont facilement accessibles dans Customer Journey Analytics. Cependant, les fonctionnalités suivantes doivent être prises en compte lors du processus de mise à niveau. Sélectionnez celles que vous prévoyez d’utiliser. | Plusieurs réponses possibles :<ul><li>**Données historiques d’Adobe Analytics :**</br> Importez les données historiques de vos suites de rapports Adobe Analytics dans Adobe Experience Platform et Customer Journey Analytics.</li><li>**Composants et projets d’Adobe Analytics :**</br> Les composants d’Adobe Analytics incluent : les projets (avec les tableaux à structure libre et les visualisations associés), les segments et les mesures calculées.</li><li>**Superposition d’Activity Map et suivi des liens :**</br> extension de navigateur qui vous permet d’afficher les données de suivi des liens sous forme de superposition sur votre site.</li><li>**Données de classification :**</br> regroupez ou catégorisez les données en tant que dimensions distinctes.</li><li>**Canaux marketing :**</br> créez des règles qui catégorisent la manière dont les clients arrivent sur votre site.</li><li>**Data Warehouse:**</br> Exportez les données traitées d’Adobe Analytics au format tableur.</li><li>**Flux de données : **un remplacement exact des flux de données n’est pas encore disponible dans Customer Journey Analytics. Cependant, des fonctionnalités similaires peuvent être obtenues avec des fonctionnalités telles que l’exportation de table complète, l’exportation de jeux de données Platform, l’intégration de l’outil BI et l’API de création de rapports.</br></li><li>**Données de médias en flux continu :**</br> module complémentaire d’Adobe Analytics et de Customer Journey Analytics spécialisé dans la collecte de données multimédias, telles que l’audio, la vidéo ou le contenu en flux continu.</li></ul> | <ul><li>[Découvrez la prise en charge des fonctionnalités Adobe Analytics lors de la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | La plupart des nouvelles fonctionnalités sont déjà disponibles dans Customer Journey Analytics. Cependant, les fonctionnalités suivantes doivent être prises en compte lors du processus de mise à niveau. Sélectionnez celles que vous prévoyez d’utiliser. | Plusieurs réponses possibles :<ul><li>**Lier les données collectées aux données provenant d’autres sources (par exemple, les données du centre de contact) :**</br>(recommandé) Lier les données de diverses propriétés web, mobiles et hors ligne pour créer une vue unique et consolidée du comportement des clients. La possibilité de combiner des données d’analyse provenant d’autres canaux est le principal cas d’utilisation de Customer Journey Analytics.</li><li>**Regrouper les accès d’autres jeux de données à l’aide d’une dimension personnalisée :**<br/> Si l’un de vos jeux de données ne partage pas d’identifiant principal (tel qu’un Experience Cloud ID), vous pouvez toujours regrouper ces données à l’aide d’une autre dimension, telle que le nom d’utilisateur de connexion ou l’adresse e-mail.</li><li>**Intégration à Adobe Journey Optimizer :**<br/> permet d’offrir aux clients des expériences connectées, contextuelles et personnalisées.</li><li>**Intégration à Adobe Real-Time CDP:**<br/> Combiner des données de profil provenant de plusieurs sources pour générer des audiences et des segments en fonction des caractéristiques de l’utilisateur.</li><li>**Intégration à Adobe Target (A4T) :**<br/> Adobe recommande d’intégrer à Adobe Journey Optimizer pour les cas d’utilisation de la personnalisation. L’intégration à Adobe Target est possible, mais il s’agit d’une solution temporaire.</li><li>**Intégration à Adobe Audience Manager :**<br/> Adobe recommande d’intégrer à la plateforme de données clients en temps réel d’Adobe pour les cas d’utilisation basés sur l’audience. L’intégration à Audience Manager est possible, mais il s’agit d’une solution temporaire.</li></ul> | [Découvrez les fonctionnalités propres à Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | Sélectionnez la manière dont vous comptez utiliser Adobe Analytics et Customer Journey Analytics : | Sélectionnez une option : <ul><li>**J’ai l’intention de migrer complètement d’Adobe Analytics vers Customer Journey Analytics :**<br/>(Recommandé) Adobe vous recommande d’effectuer une transition complète d’Adobe Analytics vers Customer Journey Analytics. Pendant la période de transition, vous devez prévoir d’exécuter Adobe Analytics avec Customer Journey Analytics afin d’effectuer des comparaisons de données côte à côte. Lorsque les données vous conviennent, vous pouvez désactiver Adobe Analytics.</li><li>**J’ai l’intention de conserver les deux produits Analytics :**<br/>(Non recommandé) Si vous sélectionnez cette option, votre contrat avec Adobe comprend à la fois Adobe Analytics et Customer Journey Analytics, ce qui peut s’avérer plus coûteux pour votre organisation au fil du temps.</li></ul> | [Évaluer quand désactiver Adobe Analytics après la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | Sélectionnez la manière dont vous souhaitez configurer votre schéma Customer Journey Analytics : | Sélectionnez une option : <ul><li>**Je souhaite utiliser un schéma adapté à mon organisation :**</br>(Recommandé) La personnalisation de votre schéma permet à votre organisation de ne suivre que ce dont vous avez besoin et d’éviter la surcharge liée aux champs désordonnés et inutiles. Cette option inclut les groupes de champs ajoutés par le SDK web et les groupes de champs personnalisés pour votre organisation.</li><li>**Je souhaite utiliser le schéma Adobe Analytics par défaut :**</br>(Non recommandé) Le schéma Adobe Analytics contient plus d’un millier de champs, ce qui peut entraîner un schéma encombré et complexe. Votre entreprise serait forcée de continuer à adhérer au concept de props et d’eVars, qui est un concept hérité non utilisé dans Customer Journey Analytics. L’intégration à d’autres services Adobe Experience Platform est plus difficile.</li></ul> | [Choisissez votre schéma pour Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | Sélectionnez votre méthode préférée de mise en œuvre de Customer Journey Analytics : | <ul><li>**Implémentation manuelle (alloy.js) :**<br/> incluez la bibliothèque SDK Web (alloy.js) sur chaque page de votre site.</li><li>**Balises :**<br/>(Recommandé) Si vous n’utilisez pas encore de balises, installez le chargeur de balises sur votre site. Si vous utilisez déjà des balises, vous pouvez ajouter l’extension SDK web à votre propriété de balise. Cette option inclut les implémentations utilisant des balises dans les systèmes de collecte de données Adobe Experience Platform et de gestion des balises tiers.</li><li>**API :**<br/> utilisez l’API de collecte de données pour envoyer directement des données à un flux de données. Les types non authentifiés (client à serveur) et authentifiés (serveur à serveur) sont pris en charge.</li></ul> | [Découvrez les options d’implémentation de Web SDK lors de la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | (Facultatif) Sélectionnez une autre méthode de mise à niveau | <ul><li>**Utiliser uniquement le connecteur source Analytics :**<br/>(non recommandé) Vous pouvez utiliser le connecteur source Analytics comme seul chemin d’implémentation pour Customer Journey Analytics.<p>Cette option permet de gagner du temps d’implémentation en envoyant rapidement des données à Customer Journey Analytics. Elle présente toutefois diverses lacunes, telles qu’une latence plus élevée et la difficulté à quitter Adobe Analytics à l’avenir.</p></li><li>**Je souhaite utiliser ma logique AppMeasurement avec le SDK Web :**<br/> au lieu d’envoyer des données par le biais d’un objet XDM, envoyez toutes vos variables au format AppMeasurement via l’objet de données.<p>Cette option permet de gagner du temps d’implémentation en vous permettant de mapper votre logique AppMeasurement à XDM, plutôt que de renseigner entièrement un objet XDM. Cependant, cela introduit une complexité supplémentaire au fil du temps, car tout champ ajouté ultérieurement doit être mappé à XDM dans le train de données.</p></li><li>**Je souhaite envoyer ma couche de données à Adobe sans configuration supplémentaire :**<br/> Au lieu d’envoyer des données par le biais d’un objet XDM, vous pouvez envoyer l’ensemble de votre couche de données à Adobe par le biais de l’objet de données.<p>Cette option permet de gagner du temps d’implémentation en vous permettant de mapper votre couche de données à XDM, plutôt que de renseigner entièrement un objet XDM. Cependant, ce mappage représente une charge de travail importante, car il contient une quantité importante de données qu’Adobe ne peut pas interpréter facilement. Cette option introduit également une complexité supplémentaire au fil du temps, car tout champ ajouté ultérieurement à vos données doit être mappé à XDM dans le train de données.</p></li></ul> | <ul><li>[Alternative de mise à niveau : utilisez uniquement le connecteur source Analytics pour effectuer la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[Alternative de mise à niveau : utilisez la collecte de données AppMeasurement avec Experience Platform Web SDK et Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Alternative de mise à niveau : envoyez votre couche de données à Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   Après avoir terminé ce guide de mise à niveau avec l’équipe chargée de votre compte Adobe, vous recevrez un fichier .csv contenant les questions, vos réponses et les étapes de mise à niveau générées dynamiquement les mieux adaptées à votre environnement Adobe Analytics existant et à vos objectifs pour Customer Journey Analytics.

1. Suivez les instructions étape par étape générées dans le fichier .csv pour effectuer la mise à niveau vers Customer Journey Analytics.

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
