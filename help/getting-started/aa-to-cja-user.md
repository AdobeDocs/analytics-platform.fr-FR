---
title: Guide de l’utilisateur CJA pour les utilisateurs d’Adobe Analytics
description: Eléments à prendre en compte du point de vue de l’utilisateur lorsque votre entreprise déplace les données d’Adobe Analytics vers Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 755e554e3eb362d6e7149e5d3a4fbbcddebdd14d
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 25%

---


# Guide de l’utilisateur CJA pour les utilisateurs d’Adobe Analytics

>[!NOTE]
>
>Cette page est en construction.

Félicitations, votre entreprise commence à travailler avec Customer Journey Analytics ! En tant qu’utilisateur familier avec Adobe Analytics, vous avez déjà un bon départ. En travaillant avec Customer Journey Analytics, vous remarquerez de grandes différences et quelques similitudes. Cette page vise à expliquer les choses qui n&#39;ont pas changé, ainsi que certaines des différences majeures. Nous vous indiquerons également comment obtenir plus d’informations sur les nouveaux concepts et d’autres étapes pour rendre votre parcours client plus facile et plus efficace.

## Ce qui n’a pas changé

De nombreux éléments que vous connaissez du côté des rapports n’ont pas changé.

* Vous pouvez toujours utiliser la puissance de [Analysis Workspace](/help/analysis-workspace/home.md) pour analyser vos données.
* Vous disposez également de la même version de [Tableaux de bord Adobe Analytics](/help/mobile-app/home.md) à votre disposition. Workspace et tableaux de bord fonctionnent de la même manière que dans Adobe Analytics traditionnel.
* [Report Builder](/help/report-builder/report-buider-overview.md) dispose d’une nouvelle interface et s’exécute désormais sur PC, Mac et la version web d’Excel.

En ce qui concerne les rapports, la différence est que vous avez accès à beaucoup plus de données cross-canal à analyser. Voici un exemple de certaines visualisations multicanaux qui incluent un certain nombre de sources de données cross-canal :

![visualisations multicanaux](assets/cross-channel.png)

## Nouvelle architecture

Customer Journey Analytics récupère ses données à partir de Adobe Experience Platform. Experience Platform vous permet de centraliser et de normaliser les données et le contenu des clients à partir de n’importe quel système ou canal, et d’appliquer la science des données et l’apprentissage automatique afin d’améliorer la conception et la diffusion d’expériences personnalisées.

Les données client de la plate-forme sont stockées sous forme de jeux de données, qui se composent d’un schéma et de lots de données. Pour plus d’informations sur la plate-forme, voir [Présentation de l’architecture de la plate-forme Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Votre administrateur CJA a établi [connexions](/help/connections/create-connection.md) aux jeux de données dans Platform. Ils ont ensuite construit [vues de données](/help/data-views/data-views.md) dans ces connexions. Considérez les vues de données comme des suites de rapports virtuelles. Les vues de données constituent la base des rapports en Customer Journey Analytics.

## Nouveaux concepts et terminologie

Plusieurs fonctionnalités de CJA ont été renommées et réarchitectées, par rapport à Adobe Analytics traditionnel, pour s’aligner sur les normes de l’industrie. La terminologie mise à jour inclut les segments, les suites de rapports virtuelles, les classifications, les attributs du client et les noms des conteneurs. Il n’existe plus de concepts familiers tels que les eVars et les props, ainsi que les limites qu’ils imposent.

### eVars et props

Les [!UICONTROL eVars], les [!UICONTROL props] et les [!UICONTROL événements] comme l’entend habituellement Adobe Analytics n’existent plus dans [!UICONTROL Customer Journey Analytics]. Vous disposez d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Ainsi, tous les paramètres d’attribution que vous appliquiez au cours du processus de collecte de données sont maintenant appliqués au moment de la requête.

### Les segments sont désormais &quot;Filtres&quot;

[!UICONTROL Customer Journey Analytics] n’utilise plus d’eVars, de props ou d’événements et utilise à la place n’importe quel schéma AEP. Cela signifie qu’aucun des segments existants n’est compatible avec [!UICONTROL Customer Journey Analytics]. En outre, les &quot;segments&quot; ont été renommés &quot;filtres&quot;.

Pour l’instant, vous ne pouvez pas partager/publier [!UICONTROL filtres] ([!UICONTROL segments]) de [!DNL Customer Journey Analytics] vers Profil unifié Experience Platform ou d’autres applications Experience Cloud. Cette fonctionnalité est en cours de développement.

### Mesures calculées

[!UICONTROL Customer Journey Analytics] n’utilise plus d’eVars, de props ou d’événements et utilise à la place n’importe quel schéma AEP. Cela signifie qu’aucune des mesures calculées existantes n’est compatible avec [!UICONTROL Customer Journey Analytics].

### Paramètres de persistance de session et de variable

[!UICONTROL Customer Journey Analytics] applique tous ces paramètres au moment du rapport. Ils se trouvent désormais dans les vues de données. Les modifications apportées à ces paramètres sont désormais rétroactives. Vous pouvez disposer de plusieurs versions en utilisant plusieurs vues de données !

### Les suites de rapports virtuelles sont désormais des &quot;vues de données&quot;



### Les classifications sont désormais des &quot;jeux de données de recherche&quot;

### Les attributs du client sont désormais des &quot;jeux de données de profil&quot;


### Les conteneurs d’accès sont désormais des conteneurs &quot;Événement&quot;.

### Les conteneurs Visite sont désormais des conteneurs &quot;Session&quot;.

### Les conteneurs Visiteur sont désormais des conteneurs &quot;Personne&quot;.

### `Uniques Exceeded`limitations

[!UICONTROL Customer Journey Analytics] n’a aucune limite de valeur unique, donc pas besoin de vous en soucier !
