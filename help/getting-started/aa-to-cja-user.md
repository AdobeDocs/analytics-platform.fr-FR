---
title: Guide de l’utilisateur pour les utilisateurs et utilisatrices d’Adobe Analytics
description: Éléments à prendre en compte du point de vue de l’utilisateur ou de l’utilisatrice lorsque votre entreprise déplace des données d’Adobe Analytics vers Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 9314aae4c62e5c7a21495beeea0a5d69c6e113a1
workflow-type: tm+mt
source-wordcount: '1455'
ht-degree: 95%

---

# Guide de l’utilisateur pour les utilisateurs et utilisatrices d’Adobe Analytics

Si votre organisation commence à utiliser Adobe Customer Journey Analytics, vous remarquerez sûrement des similitudes et des différences entre Adobe Analytics et Customer Journey Analytics. Cette page vise à expliquer ces différences pour aider votre organisation à s’adapter au nouveau workflow d’implémentation et de création de rapports. Cette page fournit aussi des ressources supplémentaires sur de nouveaux concepts et d’autres étapes pour faciliter et optimiser votre expérience en tant qu’analyste.

Plusieurs fonctionnalités de Customer Journey Analytics ont été renommées et repensées conformément aux normes du secteur. La terminologie a notamment subi quelques modifications au niveau des segments, des suites de rapports virtuelles, des classifications, des attributs client et des noms de conteneurs. Les limites des eVars et des props ont été remplacées par des dimensions et des métriques personnalisées flexibles.

## Éléments similaires

Toute la partie concernant les rapports n’a pas vraiment changé.

* Vous pouvez utiliser [Analysis Workspace](/help/analysis-workspace/home.md) pour analyser vos données. Workspace a le même mode de fonctionnement que sur la version standard d’Adobe Analytics.
* La même version des [tableaux de bord Adobe Analytics](/help/mobile-app/home.md) est disponible et fonctionne de la même manière, que ce soit avec Customer Journey Analytics ou Adobe Analytics.
* [Report Builder](/help/report-builder/report-buider-overview.md) a une nouvelle interface et fonctionne sur MS Windows, macOS et la version web d’Excel. (Avant cette version de Report Builder, vous ne pouviez pas l’utiliser sur Mac à moins de l’exécuter sur Vmware.) Cette version ne prend pas encore en charge les demandes de données AA traditionnelles.

## Modification des rapports

Vous avez accès à beaucoup plus de données cross-canal à analyser. Par exemple, vous pouvez créer un projet Workspace qui analyse les performances de plusieurs canaux, à condition que ces jeux de données soient ingérés par votre organisation et inclus dans les vues de données utilisées par Customer Journey Analytics (voir « Modification de l’architecture des données » ci-dessous).

![Vue Sources de données présentant des visualisations multicanal.](assets/cross-channel.png)

## Modification de l’architecture des données {#architecture}

Customer Journey Analytics récupère ses données à partir d’Adobe Experience Platform. Experience Platform vous permet de centraliser et de normaliser les données et le contenu des clients à partir de n’importe quel système ou canal et d’appliquer la science des données et le machine learning afin d’améliorer la conception et la diffusion d’expériences personnalisées.

Les données client d’Experience Platform sont stockées sous la forme de jeux de données, qui consistent en un [schéma](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=fr) et des lots de données. Pour plus d’informations sur la plateforme, voir [Présentation de l’architecture de la plateforme Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=fr).

Votre administrateur ou administratrice Customer Journey Analytics établit des [connexions](/help/connections/create-connection.md) aux jeux de données dans Experience Platform. et crée des [vues de données](/help/data-views/data-views.md) à l’aide de ces connexions. En termes de concept, les vues de données sont similaires aux suites de rapports virtuelles et sont à la base des rapports générés dans Customer Journey Analytics. Étant donné qu’Experience Platform exploite toutes les données pour les rapports, les suites de rapports n’existent plus en tant que conteneur de données.

Une connexion permet à votre administrateur ou administratrice Analytics d’intégrer des jeux de données d’Adobe Experience Platform dans Customer Journey Analytics, comme dans la vidéo suivante :

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

Adobe propose plusieurs façons d’importer des données dans Adobe Experience Platform, y compris les données des suites de rapports via le connecteur source Adobe Analytics ou le SDK Web. Les implémentations existantes de plusieurs suites de rapports peuvent être combinées au sein d’Experience Platform. Les connexions et les vues de données basées sur ces jeux peuvent combiner des données qui se trouvaient autrefois dans des suites de rapports distinctes.

## Modification du concept de suites de rapports virtuelles {#data-views}

Les [!UICONTROL vues de données] reprennent le concept même de suites de rapports virtuelles et l’étendent pour [contrôler plus intensément les données](/help/data-views/create-dataview.md) découlant des connexions. Ces modifications rendent les paramètres généraux tels que le fuseau horaire et les intervalles d’expiration de session configurables et rétroactifs. Les paramètres de variable individuels tels que l’attribution et l’expiration peuvent également être personnalisés au niveau du rapport ou de la vue de données. Ces réglages sont non destructifs et rétroactifs.

Notez que le sélecteur de la suite de rapports en haut à droite permet de choisir parmi les vues de données disponibles :

![sélecteur de la vue de données](assets/data-views.png)

Consultez [Cas dʼutilisation des vues de données](/help/use-cases/data-views/data-views-usecases.md) pour plus d’informations sur ce concept.

## Modification du concept des eVars et des props

Le concept des [!UICONTROL eVars], des [!UICONTROL props] et des [!UICONTROL événements] dans la version standard d’Adobe Analytics n’existe plus dans [!UICONTROL Customer Journey Analytics]. Dans Adobe Analytics, les eVars et les props stockent les descriptions du contenu, des clients, des campagnes, etc. et les événements comptabilisent des éléments tels que les revenus, les abonnements ou les prospects générés. Customer Journey Analytics conserve les deux types de données, et vous pouvez y accéder de la même manière : à partir du rail de gauche dans Analysis Workspace, sous Dimensions ou Métriques.

Un nombre illimité d’éléments de schéma est disponible dans Customer Journey Analytics, dont les dimensions, les métriques et les champs de liste. Ils sont mappés à un nombre illimité d’éléments de schéma, dont les dimensions, les métriques et les champs de liste au sein d’Experience Platform. Tous les paramètres de visite et d’attribution appliqués après le traitement des règles dans Adobe Analytics s’appliquent désormais au moment de la requête dans Customer Journey Analytics.

De par ce changement, il est possible qu’un seul champ de schéma soit utilisé à la fois comme dimension et comme métrique selon le suivi nécessaire.

## Modification du concept de segments

Bien que les segments ne soient pas techniquement migrés d’Adobe Analytics vers Customer Journey Analytics, vous pouvez utiliser l’outil de migration des composants pour recréer vos segments Adobe Analytics dans Customer Journey Analytics. Les segments sont recréés dans Customer Journey Analytics en fonction des dimensions et des mesures mappées. Pour plus d’informations, voir [Préparation à la migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=fr).

Bien que vous ne puissiez pas encore partager ou publier de [!UICONTROL filtres] ([!UICONTROL segments]) depuis [!DNL Customer Journey Analytics] vers le profil unifié Experience Platform, cette fonctionnalité est en cours de développement.

En plus du concept des segments, les conteneurs de segments ont eux aussi été mis à jour.

* **Les conteneurs d’accès sont désormais des conteneurs [!UICONTROL Événéments]**. Le conteneur [!UICONTROL Événement] vous permet de ventiler les informations sur les personnes en fonction d’événements individuels.
* **Les conteneurs Visiteur sont désormais des conteneurs [!UICONTROL Session]**. Le conteneur [!UICONTROL Session] permet dʼidentifier les interactions de pages, les campagnes ou les conversions pour une session spécifique.
* **Les conteneurs Visiteur sont désormais des conteneurs [!UICONTROL Personne]**. Le conteneur [!UICONTROL Personne] inclut chaque session et chaque événement pour une personne au cours dʼune période indiquée.

## Modification du concept des mesures calculées

Les mesures calculées portent le même nom entre Adobe Analytics et Customer Journey Analytics. Cependant, [!UICONTROL Customer Journey Analytics] n’utilise plus d’eVars, de props ou d’événements, mais des éléments de schéma Experience Platform. Au vu de ce changement majeur, aucune des métriques calculées existantes n’est compatible avec [!UICONTROL Customer Journey Analytics]. Si vous souhaitez déplacer des mesures calculées Adobe Analytics vers Customer Journey Analytics, regardez la vidéo suivante :

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## Modification des paramètres d’attribution et d’expiration des variables

[!UICONTROL Customer Journey Analytics] applique tous les paramètres de variable, y compris l’attribution et l’expiration, à la génération des rapports. Ces paramètres se trouvent désormais dans les [vues de données](/help/data-views/component-settings/persistence.md), et il est possible de modifier certains paramètres des variables (comme l’attribution) dans les projets Workspace.

Vous pouvez avoir plusieurs versions de la même variable au sein de la même vue de données. Par exemple, vous pouvez avoir une dimension Code de suivi qui expire après 30 jours et une autre qui expire à la fin d’une session. Ces deux dimensions Code de suivi utilisent les mêmes données source avec des paramètres d’attribution différents.

Vous pouvez également avoir plusieurs vues de données basées sur la même connexion. Par exemple, vous pouvez avoir une vue de données avec un délai d’expiration de session de 30 minutes et une autre avec un délai de 15 minutes. Les deux vues de données apparaissent dans le sélecteur en haut à droite pour faciliter la navigation entre elles.

## Modification du concept des classifications

Les « classifications » sont désormais appelées « jeux de données de recherche ». Les jeux de données de recherche sont utilisés pour rechercher des valeurs ou des clés trouvées dans vos données d’événement ou de profil. Vous pouvez, par exemple, charger des données de recherche qui font correspondre les identifiants numériques de vos données d’événement aux noms de produits. Consultez la section [Ajout de données au niveau du compte en tant que jeu de données de recherche](/help/use-cases/b2b/b2b.md) pour des cas pratiques.

## Modification du concept des attributs client

Les « attributs client » sont désormais appelés « jeux de données de profil ». Les jeux de données de profil contiennent des données qui sont appliquées à vos personnes, utilisateurs et utilisatrices ou clients et clientes dans les données [!UICONTROL Événement]. Cela permet, entre autres, de télécharger des données CRM sur vos clients. Vous pouvez sélectionner l’ID de personne à inclure. Chaque jeu de données défini dans [!DNL Experience Platform] dispose de son propre jeu d’un ou de plusieurs identifiants de personne.

## Modification de l’identification des visiteurs par Adobe

Customer Journey Analytics étend le concept d’identité au-delà des ECID pour inclure tout identifiant que vous souhaitez utiliser, y compris l’identifiant client, l’identifiant de cookie, les identifiants groupés, l’identifiant utilisateur, le code de suivi, etc. L’utilisation d’un identifiant d’espace de noms commun à tous les jeux de données ou l’utilisation du [groupement](../stitching/overview.md) permet de relier les personnes entre différents jeux de données. Tout utilisateur ou utilisatrice configurant un projet Workspace dans Customer Journey Analytics doit comprendre les identifiants utilisés dans les jeux de données. Regardez la vidéo suivante qui décrit l’utilisation des identités dans Customer Journey Analytics :

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Modification du concept des éléments de dimension à faible trafic

Dans la version standard d’Adobe Analytics, une variable qui reçoit trop de valeurs uniques finit par regrouper les éléments de dimension sous [!UICONTROL Faible trafic]. Customer Journey Analytics présente moins de limites pour les champs de cardinalité élevée. Les modifications apportées à l’architecture de création des rapports permettent à Analysis Workspace de créer des rapports sur de nombreux autres éléments de dimension uniques. Voir [Dimensions à cardinalité élevée](../components/dimensions/high-cardinality.md) pour plus d’informations sur la manière dont Customer Journey Analytics optimise les rapports pour les dimensions comportant de nombreuses valeurs uniques.
