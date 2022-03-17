---
title: Guide de l’utilisateur CJA pour les utilisateurs d’Adobe Analytics
description: Eléments à prendre en compte du point de vue de l’utilisateur lorsque votre entreprise déplace les données d’Adobe Analytics vers Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: d5bdbfd0ac2a62ea5a55fbd381bf5453910ce0d1
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 26%

---


# Guide de l’utilisateur CJA pour les utilisateurs d’Adobe Analytics

Félicitations, votre entreprise commence à travailler en Customer Journey Analytics ! En tant qu’utilisateur d’Adobe Analytics, vous avez déjà un bon départ. En travaillant avec Customer Journey Analytics, vous remarquerez de grandes différences et quelques similitudes. Cette page vise à expliquer les choses qui n&#39;ont pas changé, ainsi que certaines des différences majeures. Nous vous indiquerons également comment obtenir plus d’informations sur les nouveaux concepts et d’autres étapes pour rendre votre parcours client plus facile et plus efficace.

## Ce qui n’a pas changé

De nombreux éléments que vous connaissez du côté des rapports n’ont pas changé. Vous pouvez continuer à utiliser la puissance d’Analysis Workspace pour analyser vos données, ainsi que les tableaux de bord Adobe Analytics et une nouvelle version du Report Builder. Workspace et tableaux de bord fonctionnent essentiellement de la même manière que dans Adobe Analytics traditionnel. Report Builder dispose d’une nouvelle interface et s’exécute désormais sur PC, ordinateurs Mac et version web d’Excel. Au niveau du reporting, ce qui est différent, c&#39;est que vous avez accès à beaucoup plus de données cross-canal à analyser. Voici un exemple de Workspace :

## Nouvelle architecture

Customer Journey Analytics récupère ses données à partir de Adobe Experience Platform. Experience Platform vous permet de centraliser et de normaliser les données et le contenu des clients à partir de n’importe quel système ou canal, et d’appliquer la science des données et l’apprentissage automatique afin d’améliorer la conception et la diffusion d’expériences personnalisées.

Les données client de la plate-forme sont stockées sous forme de jeux de données, qui se composent d’un schéma et de lots de données. Pour plus d’informations sur la plate-forme, voir [Présentation de l’architecture de la plate-forme Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Votre administrateur CJA établit des connexions aux données dans Platform et crée des vues de données dans ces connexions. Considérez les vues de données comme des suites de rapports virtuelles. Les vues de données constituent la base des rapports en Customer Journey Analytics.

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
