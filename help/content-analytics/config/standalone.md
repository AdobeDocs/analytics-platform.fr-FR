---
title: Configuration de Content Analytics (autonome)
description: Vous guide tout au long des étapes requises pour configurer Content Analytics (autonome)
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 35d63b7d-f35a-4a88-ae14-96724d32a931
source-git-commit: 20ead546897ad517840f95a5ec4dcd7f830afe8c
workflow-type: tm+mt
source-wordcount: '2517'
ht-degree: 6%

---

# Configuration autonome

>[!IMPORTANT]
>
>Ce guide de configuration est destiné aux clients qui disposent d’une licence pour le package Adobe Content Analytics autonome. Le guide suppose que vous n’avez pas utilisé ou prévu d’utiliser Customer Journey Analytics ou toute autre application Experience Platform en dehors des fonctionnalités de Content Analytics. Voir [Configuration de Content Analytics](configuration.md) si vous souhaitez configurer et utiliser Content Analytics dans le cadre d’une implémentation Customer Journey Analytics existante.
>

Content Analytics est accordé sous licence en tant que produit autonome, mais la configuration se fait dans Experience Platform et Customer Journey Analytics. Ces plateformes fournissent l’infrastructure de collecte et d’analyse de données dont Content Analytics a besoin et qu’il utilise. Ce guide fournit toutes les instructions spécifiques dont vous avez besoin, même si vous découvrez Experience Platform et Customer Journey Analytics.

Avant de commencer la configuration de Content Analytics autonome, vous devez :

* Compréhension de base des concepts d’analyse web, connaissance des systèmes de gestion des balises et des bases de JavaScript.
* Planifiez 4 à 6 heures pour la configuration initiale, ainsi que du temps supplémentaire pour tester et valider la configuration.

## Terminologie

Ce guide utilise plusieurs termes techniques, issus d’Experience Platform et de Customer Journey Analytics, que vous ne connaissez peut-être pas. Vous trouverez ci-dessous une explication de ces termes (avec des liens de référence) dans le contexte de Content Analytics :

| Terme | Explication |
|---|---|
| **Schéma** | Un [schéma](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition) est un ensemble de règles qui représente et valide la structure et le format des données. À un niveau élevé, les schémas fournissent une définition abstraite d’un objet du monde réel, tel qu’un événement qui se produit sur un site web, comme un clic. Indiquez également les données à inclure dans chaque instance de cet objet. |
| **Jeu de données** | Un [jeu de données](https://experienceleague.adobe.com/fr/docs/experience-platform/catalog/datasets/overview) est une structure de stockage et de gestion pour une collection de données, généralement sous la forme d’un tableau, qui contient un schéma (des colonnes) et des champs (des lignes). Un jeu de données est semblable à une table de base de données où chaque ligne est un événement de votre site Web. |
| **Flux de données** | Un [flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/overview) représente la configuration côté serveur qui achemine les données de votre site web vers le jeu de données correct dans Adobe Experience Platform. Un flux de données fait office d’autoroute de données reliant votre site à votre espace de stockage. |
| **Balises** | Les [balises](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/home) d’Experience Platform représentent la nouvelle génération des fonctionnalités de gestion des balises d’Adobe. Les balises offrent aux clients un moyen simple de déployer et de gérer les balises d’analyse, de marketing et de publicité nécessaires pour offrir des expériences client pertinentes. Dans Content Analytics, le système de gestion des balises d’Adobe vous permet de déployer le code de suivi sur votre site web sans avoir à modifier chaque page de la même manière. La fonctionnalité Balises est similaire à la fonctionnalité que vous pouvez connaître du Gestionnaire de balises de Google. |
| **Sandbox** | Experience Platform fournit des [sandbox](https://experienceleague.adobe.com/fr/docs/experience-platform/sandbox/home) qui divisent une instance Experience Platform unique en environnements virtuels distincts pour favoriser le développement et l’évolution d’applications d’expérience digitale. Content Analytics utilise généralement le sandbox *de production*. |
| **Connexion** | [Connexions](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-connections/overview) définissez les jeux de données Experience Platform à ingérer. Une connexion définit le lien entre votre jeu de données (où les données sont stockées dans AEP) et Customer Journey Analytics (où vous les analysez). Une connexion rend les données collectées disponibles pour la création de rapports. |
| **Vue de données** | Une [vue de données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/data-views) est un conteneur qui vous permet de déterminer comment interpréter les données d’une connexion. Une vue de données spécifie toutes les dimensions et mesures pour lesquelles vous pouvez créer des rapports. Une vue de données est semblable à une configuration qui détermine les lignes et colonnes disponibles que vous pouvez utiliser dans votre analyse. |
| **Analysis Workspace** | [Analysis Workspace](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/home) est une interface de navigateur par glisser-déposer que vous utilisez pour créer vos rapports et analyses Content Analytics. |
| **Expérience** | Dans Content Analytics, une [expérience](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/content-analytics/content-analytics#terminology) fait référence à tout le contenu textuel d’une page web qui peut être capturé et analysé en fonction de l’URL de la page. |
| **Ressource** | Dans Content Analytics, une [ressource](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/content-analytics/content-analytics#terminology) est un élément de contenu individuel et unique, comme une image. |


## Présentation de la configuration

Cette configuration vous guide dans la configuration de toutes les applications requises pour disposer d’une implémentation Content Analytics **autonome** fonctionnelle. Vous pouvez diviser la configuration en trois phases, où chaque phase s’appuie sur la précédente :

**Phase 1** - [Préparation de votre environnement](#prepare-your-environment). Au cours de cette phase, vous devez configurer les autorisations utilisateur et vérifier votre infrastructure de données. Sans ces autorisations et cette structure de données appropriées, vous ne pouvez pas effectuer les étapes restantes. Les étapes impliquées sont les suivantes :

1. **Configurez le contrôle d’accès et les autorisations** pour prendre en charge la configuration et l’implémentation de Content Analytics.
1. **Configurer un schéma et un jeu de données** pour définir le modèle (schéma) des données à partir desquelles vous souhaitez collecter des informations d’analyse de contenu et l’emplacement de la collecte de ces données (jeu de données).

**Phase 2** - [Configurer la collecte de données](#configure-data-collection). Au cours de cette phase, vous créez le pipeline qui capture les données du contenu de votre site web. Ainsi, Content Analytics sait quel contenu les visiteurs et visiteuses interagissent avec votre contenu.

1. **Configurer un flux de données** pour configurer la manière dont les données collectées sont acheminées vers le jeu de données.
1. **Utiliser les balises de site web** pour configurer des règles et des éléments de données par rapport aux données de la couche de données sur le site web et pour vous assurer que les données sont envoyées au flux de données configuré.
1. **Déployer** dans un environnement de test **et valider** la collecte de données avant la publication dans un environnement de production.

**Phase 3** - [Configurer le reporting](#set-up-reporting). Au cours de cette phase, vous devez rendre les données collectées disponibles pour analyse dans les rapports. Vous pouvez ainsi obtenir les informations de performances de contenu que vous souhaitez obtenir à partir de Content Analytics.

1. **Configurer une connexion** à votre jeu de données.
1. **Configurer une vue de données** pour définir des mesures et des dimensions.
1. **Configuration et implémentation de Content Analytics**.
1. **Configurer un projet** pour créer des rapports et des visualisations Content Analytics.


## Préparation de votre environnement

Au cours de cette phase, vous devez configurer les autorisations utilisateur et vérifier votre infrastructure de données.

### Configuration du contrôle d’accès et des autorisations

Cette section documente l’accès dont vous avez besoin au produit, les profils de produit et les autorisations requises pour configurer et configurer un Content Analytics autonome. Bien que vous ne soyez intéressé que par les fonctionnalités de Content Analytics, vous avez toujours besoin d’un accès et d’autorisations pour d’autres produits Experience Platform afin que ces fonctionnalités fonctionnent correctement.

#### Contrôle d’accès

Le contrôle d’accès détermine si vous êtes autorisé à accéder à un produit Experience Platform.

Vous avez besoin d’un administrateur système ou d’un administrateur de produit pour vous ajouter en tant qu’administrateur d’un produit ou d’un profil de produit. Un administrateur de produit peut uniquement vous ajouter en tant qu’administrateur du produit administré (profil). Un administrateur système peut ajouter des administrateurs de produit à n’importe quel produit (profil).

>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Gérer les utilisateurs pour un profil de produit](https://video.tv.adobe.com/v/333860/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.


>[!ENDSHADEBOX]

Vous devez être un administrateur de produit pour les produits et profils de produit suivants pour Content Analytics autonome :

* Adobe Experience Platform
   * AEP-Default-All-Users (profil par défaut pour l’accès au sandbox de production)

* Collecte de données dʼAdobe Experience Platform
   * Tous les accès à la collecte de données par défaut

* Adobe Experience Platform Privacy Service 

* Customer Journey Analytics (Personnalisé)
   * Customer Journey Analytics (ou tout autre profil de produit configuré par défaut)

Vous définissez l’accès administrateur de produit via l’Admin Console :

1. Accédez à [Admin Console](https://adminconsole.adobe.com).
1. Sélectionnez **[!UICONTROL Produits]**.
1. Sélectionnez le produit spécifique.
1. Sélectionnez l’onglet **[!UICONTROL Administrateurs]**.
1. Sélectionnez **[!UICONTROL Ajouter un administrateur]** pour ajouter un administrateur au produit.
1. Saisissez un ou plusieurs noms d’utilisateur ou d’e-mail dans la boîte de dialogue **[!UICONTROL Ajouter des administrateurs de produit]**. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer.


Vous définissez l’accès administrateur de profil de produit via Admin Console :

1. Accédez à [Admin Console](https://adminconsole.adobe.com).
1. Sélectionnez **[!UICONTROL Produits]**.
1. Sélectionnez le produit spécifique. Vérifiez que vous disposez déjà d’un accès d’administrateur de produit.
1. Sélectionnez **[!UICONTROL Profils de produit]**.
1. Sélectionnez le profil de produit spécifique.
1. Sélectionnez l’onglet **[!UICONTROL Administrateurs]**.
1. Sélectionnez **[!UICONTROL Ajouter un administrateur]** pour ajouter un administrateur au profil de produit.
1. Saisissez un ou plusieurs noms d’utilisateur ou d’e-mail dans la boîte de dialogue **[!UICONTROL Ajouter des administrateurs de profil de produit]**. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer.


#### Autorisations

Les autorisations définissent ce que vous pouvez faire dans un produit une fois que vous avez accès au produit.

Vous définissez des autorisations pour Experience Platform dans l’interface [!UICONTROL Autorisations] et vous utilisez le contrôle d’accès basé sur les attributs. Pour Customer Journey Analytics, vous définissez des autorisations via [!UICONTROL Admin Console].

##### Experience Platform

L’interface [!UICONTROL Autorisations] d’Experience Platform repose sur la définition d’un rôle. Un rôle est un ensemble d’autorisations basées sur les ressources. Dans un nouvel environnement configuré, deux rôles par défaut sont disponibles : **[!UICONTROL Tous les accès de production par défaut]** et **[!UICONTROL Administrateurs de sandbox]**.

Pour Content Analytics, vous devez vérifier si les ressources suivantes et les autorisations associées sont ajoutées à ces rôles :

* Rôle Production All Access par défaut

   * Collecte de données
      * Afficher les trains de données
      * Gérer les trains de données

   * Data Management
      * Afficher des jeux de données
      * Gérer des jeux de données

   * Modélisation des données
      * Afficher des schémas
      * Gérer des schémas
      * Gestion des métadonnées d’identité


* Rôle Administrateurs Sandbox

   * Sandbox
      * Prod
      * (tout autre sandbox que vous souhaitez utiliser pour Content Analytics)

   * Sandbox Administration
      * Gérer les packages
      * Gérer les sandbox
      * Réinitialiser le sandbox
      * Afficher Sandbox


Dans l’interface Autorisations , vous pouvez vérifier les rôles et les autorisations associées. Et quels utilisateurs appartiennent au rôle.

1. Accédez à Experience Platform pour votre organisation.
1. Dans l’écran de bienvenue, dans **[!UICONTROL Accès rapide]**, sélectionnez **[!UICONTROL Afficher tout]**.
1. Activez l’épingle ![PinOn](/help/assets/icons/PinOn.svg) pour **[!UICONTROL Autorisations]** afin que **[!UICONTROL Autorisations]** soit disponible dans **[!UICONTROL Accès rapide]** pour une utilisation ultérieure.
1. Sélectionnez **[!UICONTROL Autorisations]**.
1. Sélectionnez ![&#x200B; Utilisateur &#x200B;](/help/assets/icons/User.svg) **[!UICONTROL Rôles]**.
1. Sélectionnez le rôle spécifique à vérifier (par exemple, **[!UICONTROL Tous les accès de production par défaut]**). Sélectionnez **[!UICONTROL Afficher tout]** pour afficher toutes les autorisations.
1. Dans l’écran **[!UICONTROL Détails]** :
   1. Vérifiez les **[!UICONTROL Ressources]** répertoriées dans **[!UICONTROL Autorisations]**.
   1. Vérifiez les noms des sandbox dans **[!UICONTROL Sandbox]**.

   Pour effectuer des mises à jour, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]**.
   1. Pour ajouter une ressource manquante, sélectionnez **[!UICONTROL Nom de la ressource]** ![Ajouter](/help/assets/icons/Add.svg) dans le rail de gauche **[!UICONTROL Ressources]** > **[!UICONTROL Adobe Experience Platform]**.
   1. Pour ajouter une autorisation manquante, sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) dans la ressource à laquelle il manque l’autorisation dans le panneau principal, puis sélectionnez l’autorisation manquante.

      ![&#x200B; Interface des autorisations &#x200B;](/help/content-analytics/assets/aep-permissions-ui.png)

   Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer toute mise à jour.

1. Sur l’écran Utilisateurs ou Groupes d’utilisateurs :
   1. Vérifiez que les utilisateurs ou groupes d’utilisateurs appropriés font partie de ce rôle.
      1. Sélectionnez ![UserAdd](/help/assets/icons/UserAdd.svg) Ajouter des utilisateurs dans Utilisateurs pour ajouter les utilisateurs individuels que vous avez définis dans Admin Console.
      1. Sélectionnez ![Ajouter](/help/assets/icons/Add.svg) Ajouter des groupes dans les groupes Utilisateurs pour ajouter les groupes d’utilisateurs que vous avez définis dans Admin Console.


##### Customer Journey Analytics

Customer Journey Analytics ne prend pas en charge le contrôle d’accès basé sur les attributs. Pour spécifier des autorisations, vous utilisez Admin Console.

Pour Content Analytics, vous devez vérifier si les autorisations de profil de produit Customer Journey Analytics suivantes sont incluses :

* Vues des données
   * Toutes les vues de données disponibles.

* Outils de création de rapports
   * Accès aux analyses guidées ?
   * Création des mesures calculées
   * Création de segment
   * Accès aux laboratoires ?
   * Création d’annotation
   * Création d’une audience ?
   * Vue Audience ?
   * Accès aux journaux d’audit
   * Partager les liens du projet avec tout le monde
   * Prévisions
   * Assistant IA : connaissances du produit
   * Agent Data Insights
   * Légendes intelligentes
   * Storytelling de données ?

* Outils des vues de données
   * Exportation de table complète ?
   * Extension CJA BI ?

Pour vérifier et mettre à jour ces autorisations pour Customer Journey Analytics :

1. Accédez à [Admin Console](https://adminconsole.adobe.com).
1. Sélectionnez **[!UICONTROL Produits]**.
1. Sélectionnez le produit **[!UICONTROL Customer Journey Analytics]**.
1. Sélectionnez **[!UICONTROL Profils de produit]**.
1. Sélectionnez le profil de produit configuré par défaut disponible pour Customer Journey Analytics. Par exemple : **[!UICONTROL Customer Journey Analytics]**.
1. Dans l’écran du profil de produit, sélectionnez **[!UICONTROL Autorisations]**.
1. Sélectionnez l’un des boutons ![Modifier](/help/assets/icons/Edit.svg) pour modifier les autorisations. Dans la boîte de dialogue **[!UICONTROL Modifier les autorisations pour Customer Journey Analytics]** :

   Interface utilisateur des autorisations CJA ![](../assets/cja-permissions-ui.png)

   1. Sélectionnez **[!UICONTROL Vues de données]** et activez **[!UICONTROL Inclusion automatique : activée]**. Ce bouton (bascule) garantit que toutes les vues de données font automatiquement partie des **[!UICONTROL éléments d’autorisation inclus]**.
   1. Sélectionnez **[!UICONTROL Outils de création de rapports]** et assurez-vous que toutes les autorisations répertoriées ci-dessus font partie des **[!UICONTROL Éléments d’autorisation inclus]**.
   1. Sélectionnez **[!UICONTROL Outils de vues de données]** et assurez-vous que toutes les autorisations répertoriées ci-dessus font partie des **[!UICONTROL Éléments d’autorisation inclus]**.

   Sélectionnez **[!UICONTROL Enregistrer]**.


### Configurer le schéma et le jeu de données

Pour collecter des données à partir de votre site web, sous réserve des informations Content Analytics, vous devez d’abord définir le type de données à collecter. Et aussi comment ces données sont stockées. Ces deux concepts sont expliqués dans la section [Configurer un schéma et un jeu de données](/help/data-ingestion/aepwebsdk.md#set-up-a-schema-and-dataset) du guide de démarrage rapide [Ingérer des données via le SDK Web Adobe Experience Platform](/help/data-ingestion/aepwebsdk.md).


## Configurer la collecte de données

Au cours de cette phase, vous créez le pipeline qui capture les données du contenu de votre site web.

### Configurer un flux de données

Vous avez défini les données à collecter et la manière de les stocker. L’étape suivante consiste à s’assurer que les données collectées sur votre site web sont acheminées vers le jeu de données . Vous devez configurer un flux de données, comme expliqué dans la section [Configurer un flux de données](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream) du guide de démarrage rapide [Ingérer des données via Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


### Utiliser des balises

Vous avez défini les données à collecter (schéma), comment stocker ces données (jeu de données) et comment les données collectées sur le site web sont acheminées vers le jeu de données (flux de données). L’étape suivante consiste à baliser votre site web pour configurer des règles et des éléments de données par rapport aux données de la couche de données sur votre site web. Le balisage de votre site web garantit que les données sont envoyées au flux de données configuré. Le balisage de votre site web à l’aide de balises est expliqué dans la section [Utiliser les balises](/help/data-ingestion/aepwebsdk.md#use-tags) du guide de démarrage rapide [Ingérer des données via le SDK web Adobe Experience Platform](/help/data-ingestion/aepwebsdk.md).


### Déployer et valider

Vous pouvez désormais déployer le code dans la version de développement du site Web dans la balise `<head>`. Une fois déployé, votre site web commence à collecter des données dans Adobe Experience Platform. Ces données sont ensuite soumises à Content Analytics.

Validez la mise en œuvre, corrigez-la si nécessaire, puis déployez-la dans l’environnement d’évaluation et de production à l’aide du processus de publication des balises


## Configurer des rapports

Au cours de cette phase, vous rendez les données collectées disponibles pour analyse dans les rapports.

### Configurer une connexion à votre jeu de données

Pour générer des rapports sur les données collectées et configurer ces données pour Content Analytics, vous devez configurer une connexion dans Customer Journey Analytics. La connexion se connecte au jeu de données qui contient les données collectées. La configuration d’une connexion est expliquée dans la section [Configurer une connexion](../../data-ingestion/aepwebsdk.md#set-up-a-connection) du guide de démarrage rapide [Ingérer des données via le SDK Web Adobe Experience Platform](/help/data-ingestion/aepwebsdk.md).


### Configurer une vue de données

La dernière étape avant de pouvoir configurer Content Analytics consiste à définir une vue de données. Une vue de données est un conteneur spécifique à Customer Journey Analytics qui vous permet de déterminer comment interpréter les données d’une connexion. Une vue de données vous permet de définir des mesures et des dimensions à partir des données d’un ou de plusieurs jeux de données auxquels Customer Journey Analytics est connecté. La configuration d’une vue de données est expliquée dans la section [Configurer une vue de données](/help/data-ingestion/aepwebsdk.md#set-up-a-data-view) du guide de démarrage rapide [Ingérer des données via Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


### Configurer Content Analytics

Tout est désormais en place pour configurer Content Analytics.

#### Configuration guidée

Utilisez l’assistant [configuration guidée](guided.md) et sélectionnez la vue de données que vous avez créée dans le cadre de l’étape [Configurer une vue de données](#set-up-a-data-view). Cette sélection garantit que Content Analytics est configuré et implémenté en plus des données que vous collectez sur votre site web.

Notez que l’assistant de configuration guidé configure les objets Content Analytics spécifiques supplémentaires suivants :

* **Jeu de données**, qui est configuré automatiquement pour les événements Content Analytics. Ce jeu de données utilise un schéma Content Analytics spécifique déjà créé et disponible.
* **Flux de données**, qui est configuré automatiquement pour diffuser des événements Content Analytics dans le jeu de données Content Analytics.
* **Propriété Tags**, configurée automatiquement et avec l’extension Content Analytics. Cette propriété Balises garantit que votre site web envoie des données Content Analytics au flux de données Content Analytics et au jeu de données Content Analytics.

  >[!IMPORTANT]
  >
  >Veillez à sélectionner l’option permettant de créer une propriété New Tags dans le cadre de l’étape [Collecte de données](guided.md#new-configuration-1) de l’assistant.
  >


#### Configuration manuelle

Pour implémenter Content Analytics pour votre site web, vous devez publier la propriété Content Analytics Tags [manuellement](manual.md).


### Configurer un projet

Configurez un projet dans Customer Journey Analytics pour créer vos [rapports et visualisations Content Analytics](/help/content-analytics/report/report.md). Vous pouvez également utiliser un modèle [Content Analytics](/help/content-analytics/report/report.md#template) pour commencer.
