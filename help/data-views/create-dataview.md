---
title: Création d’une vue de données
description: Décrit comment créer un de données  à un jeu de données de plateforme dans Customer Journey Analytics (CJA).
translation-type: tm+mt
source-git-commit: d6101371fc9c055a73c7b7bcd1a8d6d6fdc13322

---


# Création d’une vue de données

Un  de données est similaire à une suite de rapports virtuelle dans Analytics en ce sens qu’il s’agit en quelque sorte d’un &quot;filtré&quot; des données. Vous pouvez créer différents de données pour la même connexion, avec des paramètres différents pour le délai d’expiration de la visite, l’attribution, etc. Vous pouvez créer plusieurs  de données pour un seul jeu de données. Par exemple, vous pouvez avoir un de données  où toutes les dimensions sont définies sur &quot;Dernière touche&quot; et, simultanément, un autre de données (basé sur le même jeu de données) avec toutes les dimensions définies sur &quot;Première touche&quot;.

Les projets de l’espace de travail dans les analyses de parcours du client reposent sur des  de données.

Cliquez [ici](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) pour une présentation vidéo.

## Condition requise

Avant de pouvoir créer des  de de données, vous devez [configurer une ou plusieurs connexions aux jeux de données de la plateforme] d’expérience](/help/connections/create-connection.md).

## Configurer les paramètres

1. Dans les analyses de parcours du client, accédez à l’ **[!UICONTROL Data Views]** onglet.

1. Cliquez sur **[!UICONTROL Add]** pour ajouter un de données et configurer ses paramètres.

   | Paramètre de session | Définition |
   |---|---|
   | Connexion | Ce champ associe le de données à la connexion que vous avez établie précédemment, qui contient le ou les [!UICONTROL Experience Platform] jeux de données. |
   | Nom | Attribuer un nom au de données est obligatoire. |
   | Description | Une description détaillée n’est pas obligatoire, mais recommandée. |
   | Balises Ajouter | Les balises vous permettent d’organiser vos  de données en . |
   | Fuseau horaire | Choisissez le fuseau horaire de votre  de données. |
   | Délai d’expiration de la session | Sélectionnez la définition de &quot;session&quot;. Le paramètre de délai d’expiration de session définit le niveau d’inactivité qu’un unique doit connaître avant le démarrage automatique d’une nouvelle session. Il est défini par défaut sur 30 minutes. Par exemple, si vous définissez le délai d’expiration de la session sur 45 minutes, un nouveau regroupement de session est créé pour chaque séquence d’accès collectée, séparé par 45 minutes d’inactivité. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   |  nouvelle session avec le  | Un nouveau de session  lorsqu’un  est déclenché, qu’une session ait expiré ou non. La nouvelle session comprend le  qui l’a démarré. De plus, vous pouvez utiliser plusieurs  pour  une session et une nouvelle session se déclenche si l’un de cestermes est observé dans les données. Ce paramètre aura un impact sur le nombre de visites, le  de segments Session (anciennement Visite) et la logique d’expiration des visites sur les dimensions. |
   | Ajouter des filtres | &quot;&quot; est le terme &quot;segments&quot; dans les analyses de parcours du client. Si vous souhaitez filtrer vos données, faites glisser le filtre approprié ici depuis le rail de gauche. Si vous ne sélectionnez pas de filtre, le  de données contiendra toutes vos données. |

1. Cliquez sur **[!UICONTROL Continue]**.

## Ajouter des composants

1. Il est maintenant temps d’ajouter des composants (dimensions, mesures) aux  de données (comme l’expérience de traitement dans les suites de rapports virtuelles). Notez que chacun des champs des jeux de données est maintenant traduit en dimensions ou en mesures. Faites glisser des dimensions et des mesures dans le panneau ou **[!UICONTROL Sélectionner tout** pour ajouter tous les composants.

   ![](assets/add-all-components.png)

1. Cliquez sur l’ **[!UICONTROL Add Components]** onglet pour ajouter des dimensions et des mesures au  de données.

   ![](assets/add-all-components2.png)

1. (Facultatif) Vous pouvez renommer un composant en un nom convivial ou modifier ses paramètres d’attribution en le sélectionnant et en modifiant ses paramètres. Notez que le nom sous-jacent est conservé. Pour plus d’informations, voir [Configuration des  de de données et attribution](/help/data-views/configure-dataviews.md).

1. La procédure suivante consiste à [spécifier les paramètres](/help/data-views/configure-dataviews.md)de composant et d’attribution.