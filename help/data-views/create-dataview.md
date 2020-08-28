---
title: Création d’une vue de données
description: Décrit comment créer une vue de données pour un jeu de données Platform dans Customer Journey Analytics (CJA).
translation-type: ht
source-git-commit: de265170126c1a9fc1f66364a79a74ff487d0b71
workflow-type: ht
source-wordcount: '540'
ht-degree: 100%

---


# Création d’une vue de données

Une vue de données est similaire à une suite de rapports virtuelle dans Analytics car elle est en quelque sorte une vue « filtrée » des données. Vous pouvez créer différentes vues de données pour la même connexion, avec des paramètres différents pour le délai d’expiration de la visite, l’attribution, etc. Vous pouvez créer plusieurs vues de données pour un seul jeu de données. Par exemple, vous pouvez avoir une vue de données où toutes les dimensions sont définies sur « Dernière touche » et, simultanément, une autre vue de données (basée sur le même jeu de données) avec toutes les dimensions définies sur « Première touche ».

Les projets Workspace dans Customer Journey Analytics reposent sur des vues de données.

Cliquez [ici](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) pour une présentation vidéo.

## Condition requise

Avant de pouvoir créer des vues de données, vous devez [configurer une ou plusieurs connexions aux jeux de données Experience Platform](/help/connections/create-connection.md).

## Configurer les paramètres

1. Dans Customer Journey Analytics, accédez à l’onglet **[!UICONTROL Vues de données]**.

1. Cliquez sur **[!UICONTROL Ajouter]** pour ajouter une vue de données et configurer ses paramètres.

   | Paramètre de session | Définition |
   |---|---|
   | Connexion | Ce champ relie la vue de données à la connexion que vous avez établie précédemment, qui contient le ou les jeux de données [!UICONTROL Experience Platform]. |
   | Nom | Il est obligatoire d’attribuer un nom à la vue de données. |
   | Description | Une description détaillée n’est pas obligatoire, mais recommandée. |
   | Ajout de balises | Les balises vous permettent d’organiser vos vues de données en catégories. |
   | Fuseau horaire | Sélectionnez le fuseau horaire de votre vue de données. |
   | Délai d’expiration de la session | Sélectionnez votre définition d’une « session ». Le paramètre Délai de session définit le délai d’inactivité d’un visiteur unique avant qu’une nouvelle session ne soit lancée automatiquement. Par défaut, il est fixé à 30 minutes. Par exemple, si vous définissez le délai de session sur 45 minutes, un nouveau groupe de session est créé pour chaque séquence d’accès collectés, séparé par 45 minutes d’inactivité. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | Démarrer une nouvelle session avec un événement | Une nouvelle session démarre lorsqu’un événement est déclenché, qu’une session ait expiré ou non. La session nouvellement créée inclut l’événement à l’origine de son démarrage. De plus, vous pouvez utiliser plusieurs événements pour démarrer une session. Une nouvelle session se déclenche alors si l’un de ces événements est observé dans les données. Ce paramètre aura un impact sur le nombre de visites, sur le conteneur de segmentation des sessions (anciennement visites) et sur la logique d’expiration de visite pour les dimensions. |
   | Ajouter des filtres | Le terme « filtres » désigne les « segments » dans Customer Journey Analytics. Si vous souhaitez filtrer vos données, faites glisser le filtre approprié ici depuis le rail de gauche. Si vous ne sélectionnez pas de filtre, la vue de données contiendra toutes vos données. |

1. Cliquez sur **[!UICONTROL Continuer]**.

## Ajouter des composants

1. Il est maintenant temps d’ajouter des composants (dimensions, mesures) à la vue de données (comme l’expérience d’organisation dans les suites de rapports virtuelles). Notez que chacun des champs des jeux de données est maintenant traduit en dimensions ou en mesures. Faites glisser des dimensions et des mesures dans le panneau ou **[!UICONTROL Sélectionner tout]** pour ajouter tous les composants.

   ![](assets/add-all-components.png)

1. Cliquez sur l’onglet **[!UICONTROL Ajouter des composants]** pour ajouter des dimensions et des mesures à la vue de données.

   ![](assets/add-all-components2.png)

1. (Facultatif) Vous pouvez renommer un composant sous un nom convivial ou modifier ses paramètres d’attribution en le sélectionnant et en modifiant ses paramètres. Notez que le nom sous-jacent est conservé. Pour plus d’informations, voir [Configuration d’attribution et de vues de données](/help/data-views/configure-dataviews.md).

1. La procédure suivante consiste à [spécifier les paramètres de composant et d’attribution](/help/data-views/configure-dataviews.md).