---
title: Guide de l’utilisateur CJA pour les utilisateurs d’Adobe Analytics
description: Eléments à prendre en compte du point de vue de l’utilisateur lorsque votre entreprise déplace les données d’Adobe Analytics vers Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 3af757fd311d7a92e56aa9ce5939dc3db8dcf6fa
workflow-type: tm+mt
source-wordcount: '1051'
ht-degree: 18%

---

# Guide de l’utilisateur CJA pour les utilisateurs d’Adobe Analytics

Votre entreprise commence à employer Customer Journey Analytics. En tant qu’utilisateur familiarisé avec Adobe Analytics, vous avez déjà un bon départ. En travaillant avec Customer Journey Analytics, vous remarquerez quelques similitudes et de grandes différences. Cette page vise à expliquer les choses qui n&#39;ont pas changé, ainsi que certaines des différences majeures. Nous vous indiquerons également comment obtenir plus d’informations sur les nouveaux concepts et d’autres étapes pour rendre votre parcours client plus facile et plus efficace.

Plusieurs fonctionnalités de CJA ont été renommées et réarchitectées, par rapport à Adobe Analytics traditionnel, pour s’aligner sur les normes de l’industrie. La terminologie mise à jour inclut les segments, les suites de rapports virtuelles, les classifications, les attributs du client et les noms des conteneurs. Il n’existe plus de concepts familiers tels que les eVars et les props, ainsi que les limites qu’ils imposent.

## Ce qui n’a pas changé

De nombreux éléments que vous connaissez du côté des rapports n’ont pas changé.

* Vous pouvez toujours utiliser la puissance de [Analysis Workspace](/help/analysis-workspace/home.md) pour analyser vos données. Workspace fonctionne de la même manière que dans Adobe Analytics traditionnel.
* Vous disposez également de la même version de [Tableaux de bord Adobe Analytics](/help/mobile-app/home.md) à votre disposition. Les tableaux de bord (ou application Mobile) fonctionnent de la même manière que dans Adobe Analytics traditionnel.
* [Report Builder](/help/report-builder/report-buider-overview.md) dispose d’une nouvelle interface et s’exécute désormais sur PC, Mac et la version web d’Excel.

En ce qui concerne les rapports, **ce qui est différent** est que vous avez accès à beaucoup plus de données cross-canal à analyser. Voici un exemple de certaines visualisations qui incluent des sources de données cross-canal :

![visualisations multicanaux](assets/cross-channel.png)

## Nouvelle architecture {#architecture}

Customer Journey Analytics récupère ses données à partir de Adobe Experience Platform. Experience Platform vous permet de centraliser et de normaliser les données et le contenu des clients à partir de n’importe quel système ou canal, et d’appliquer la science des données et l’apprentissage automatique afin d’améliorer la conception et la diffusion d’expériences personnalisées.

Les données client de la plate-forme sont stockées sous forme de jeux de données, qui se composent d’un schéma et de lots de données. Pour plus d’informations sur la plate-forme, voir [Présentation de l’architecture de la plate-forme Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Votre administrateur CJA a établi [connexions](/help/connections/create-connection.md) aux jeux de données dans Platform. Ils ont ensuite construit [vues de données](/help/data-views/data-views.md) dans ces connexions. Considérez les vues de données comme des suites de rapports virtuelles. Les vues de données constituent la base des rapports en Customer Journey Analytics. Le concept de suite de rapports n’existe plus.

## Suites de rapports {#report-suites}

Les données de votre suite de rapports peuvent être importées en Experience Platform par le biais du connecteur source Adobe Analytics ou du SDK Web, en particulier si votre entreprise se trouve toujours sur la plateforme Adobe Analytics et que CJA/AEP est ajouté. Vous sources généralement des jeux de données spécifiques à une suite de rapports à l’aide du schéma Analytics.

## Les suites de rapports (virtuelles) sont désormais des &quot;vues de données&quot; {#data-views}

[!UICONTROL Vues des données] prenez le concept de suites de rapports virtuelles telles qu’elles existent aujourd’hui et développez-le en pour [activer des contrôles supplémentaires sur les données ;](/help/data-views/create-dataview.md) rendu disponible par les connexions. Cela rend configurables les intervalles de fuseau horaire et de délai d’expiration de session. Vous pouvez également appliquer dynamiquement des propriétés d’attribution et d’expiration pour des dimensions individuelles. Notez qu’elles sont appliquées rétroactivement sur toutes les données.

**Ce que vous devez faire**:

* Dans Workspace, le sélecteur de suite de rapports auquel vous êtes habitué vous permet désormais de choisir parmi les vues de données que votre administrateur a partagées avec vous :

   ![data-view-selector](assets/data-views.png)

* Familiarisez-vous avec les nombreuses [cas d’utilisation des vues de données](/help/data-views/data-views-usecases.md).

## eVars et props

Les [!UICONTROL eVars], les [!UICONTROL props] et les [!UICONTROL événements] comme l’entend habituellement Adobe Analytics n’existent plus dans [!UICONTROL Customer Journey Analytics]. Vous disposez d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Ainsi, tous les paramètres d’attribution que vous appliquiez au cours du processus de collecte de données sont maintenant appliqués au moment de la requête. Votre administrateur CJA a créé des vues de données

**Ce que vous devez faire**:

* Familiarisez-vous avec les nombreuses façons dont ces éléments de schéma peuvent être utilisés pour analyser en détail vos données.

## Les segments sont désormais &quot;Filtres&quot;

[!UICONTROL Customer Journey Analytics] n’utilise plus d’eVars, de props ou d’événements et utilise à la place n’importe quel schéma AEP. Cela signifie qu’aucun des segments existants n’est compatible avec [!UICONTROL Customer Journey Analytics]. En outre, les &quot;segments&quot; ont été renommés &quot;filtres&quot;.

Pour l’instant, vous ne pouvez pas partager/publier [!UICONTROL filtres] ([!UICONTROL segments]) de [!DNL Customer Journey Analytics] vers Profil unifié Experience Platform ou d’autres applications Experience Cloud. Cette fonctionnalité est en cours de développement.

**Ce que vous devez faire**:

* Si vous souhaitez déplacer des segments Adobe Analytics existants vers Customer Journey Analytics, affichez [cette vidéo](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=fr).
* Sinon, recréez les filtres dans Customer Journey Analytics.

## Mesures calculées

[!UICONTROL Customer Journey Analytics] n’utilise plus d’eVars, de props ou d’événements et utilise à la place n’importe quel schéma AEP. Cela signifie qu’aucune des mesures calculées existantes n’est compatible avec [!UICONTROL Customer Journey Analytics].

**Ce que vous devez faire**:

* Si vous souhaitez déplacer des mesures calculées Adobe Analytics vers Customer Journey Analytics, affichez [cette vidéo](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=fr).
* Sinon, recréez les mesures calculées dans Customer Journey Analytics.


## Données inter-suites de rapports

Les implémentations existantes de plusieurs jeux de données peuvent être combinées dans Experience Platform. Les connexions et les vues de données basées sur ces jeux de données peuvent combiner des données qui existaient auparavant dans des suites de rapports distinctes.

**Ce que vous devez faire**:

## Paramètres de persistance de session et de variable

[!UICONTROL Customer Journey Analytics] applique tous ces paramètres au moment du rapport. Ils se trouvent désormais dans [vues de données](/help/data-views/component-settings/persistence.md). Les modifications apportées à ces paramètres sont désormais rétroactives. Vous pouvez disposer de plusieurs versions en utilisant plusieurs vues de données !

**Ce que vous devez faire**:

## Les classifications sont désormais des &quot;jeux de données de recherche&quot;



## Les attributs du client sont désormais des &quot;jeux de données de profil&quot;


## Les conteneurs ont été renommés.

Vous spécifiez un conteneur pour [chaque vue de données que vous créez](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#containers).
* **Les conteneurs d’accès sont désormais des conteneurs &quot;Événement&quot;.**. Le conteneur [!UICONTROL Personne] inclut chaque session et événement pour les visiteurs au cours dʼune période indiquée.
* **Les conteneurs Visite sont désormais des conteneurs &quot;Session&quot;.**. Le conteneur [!UICONTROL Session] permet dʼidentifier les interactions de pages, les campagnes ou les conversions pour une session spécifique.
* **Les conteneurs Visiteur sont désormais [!UICONTROL Personne] conteneurs**. Le conteneur [!UICONTROL Personne] inclut chaque session et événement pour les visiteurs au cours dʼune période indiquée.

**Ce que vous devez faire**:

Vous avez la possibilité de renommer n’importe quel conteneur en fonction des besoins de votre entreprise.


## `Uniques Exceeded`limitations

[!UICONTROL Customer Journey Analytics] n’a aucune limite de valeur unique, donc pas besoin de vous en soucier !
