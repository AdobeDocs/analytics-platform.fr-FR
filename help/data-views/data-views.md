---
title: Qu’est-ce qu’une vue de données en Customer Journey Analytics ?
description: null
translation-type: tm+mt
source-git-commit: 0f116524c0c3937ddddce6b50b3d9f8519e9157f
workflow-type: tm+mt
source-wordcount: '1115'
ht-degree: 6%

---


# Qu’est-ce qu’une vue de données ?

Une vue de données se trouve au-dessus d’une [connexion](/help/connections/create-connection.md) Customer Journey Analytics (CJA). Une connexion combine un ou plusieurs jeux de données de Adobe Experience Platform et la connecte à la CJA. La vue de données indique comment interpréter les éléments des données de la connexion, tels que les mesures, les dimensions, les sessions, etc. Les vues de données sont définies en vue du rapports des données dans Workspace.

Si vous avez précédemment utilisé l’Adobe Analytics traditionnelle, une vue de données est similaire à une suite de rapports virtuelle en ce sens qu’il s’agit d’une vue &quot;filtrée&quot; des données.

Vous pouvez créer différentes vues de données pour la même connexion, avec des paramètres différents pour le délai d’expiration de la visite, l’attribution, etc... Vous pouvez également créer plusieurs vues de données pour un seul jeu de données. Par exemple, vous pouvez avoir une vue de données où toutes les dimensions sont définies sur [!UICONTROL Dernière touche] et, simultanément, une autre vue de données (basée sur le même jeu de données) avec toutes les dimensions définies sur [!UICONTROL Première touche].

Les projets Workspace dans Customer Journey Analytics reposent sur des vues de données.

## Quoi de neuf dans les vues de données ?

La dernière mise à jour des vues de données vous offre une plus grande flexibilité dans ce que vous pouvez faire avec les vues de données. Ces améliorations vous permettent de **modifier spontanément les paramètres des éléments de schéma dans les Vues de données, sans avoir à modifier le schéma de Adobe Experience Platform ou à réimplémenter votre environnement CJA**.

* **Vous pouvez changer un composant d’une mesure en Dimension et vice versa**. Vous pouvez créer des mesures à partir de champs de chaîne ou créer des dimensions à partir de champs numériques. Cela facilite votre vie en ce sens qu’il n’est pas nécessaire de créer un champ numérique dans votre schéma XDM pour chaque mesure souhaitée. Au lieu de cela, vous pouvez simplement la créer spontanément dans la boîte de dialogue des vues de données. En voici quelques exemples :
   * **Créez une ou plusieurs dimensions et/ou une dimension à partir d’un seul champ** de schéma. C&#39;est une relation de un à plusieurs. Par exemple, vous pouvez créer une ou plusieurs mesures Recettes et/ou une ou plusieurs dimensions Recettes à partir d’un seul champ de schéma.
   * **Utilisez un champ de chaîne comme mesure** : Lorsque vous renseignez un schéma en Experience Platform avec un jeu de données, vous ne savez peut-être pas à l’avance quels éléments de schéma vous avez besoin. Par exemple, vous n’avez peut-être pas réalisé que vous aviez besoin d’une mesure pour &quot;Erreurs sur une page&quot;. Par conséquent, vous n’avez pas créé d’élément de schéma numérique à cet effet. En utilisant un élément de chaîne comme mesure, vous pouvez maintenant utiliser les paramètres de vue de données pour spécifier que chaque fois qu&#39;une chaîne contient le mot &quot;erreur&quot;, elle peut être utilisée comme mesure.
   * **Utilisez un champ numérique comme dimension** : Par exemple, si vous souhaitez extraire la mesure Recettes de la dimension Recettes, la dimension Recettes affichera chaque valeur comme un élément de dimension (100 $, 175 $, 1 000 $, etc.) et le nombre d’instances pour chaque élément de dimension. Les recettes en tant que mesure se comporteraient comme elle l&#39;a toujours fait.

* **Vous pouvez créer plusieurs mesures avec différents modèles d’attribution ou avec différentes** fenêtres de recherche depuis le même champ de schéma.

* **Vous pouvez modifier l’ID d’un composant** , qui est utilisé pour la compatibilité entre vues de données. L’ID de composant est utilisé par l’API de rapports pour identifier une mesure ou une dimension spécifique. Comme vous pouvez créer arbitrairement de nombreuses mesures ou dimensions à partir d&#39;un champ XDM, nous vous offrons la possibilité de définir votre propre ID de composant. Par conséquent, une mesure que vous utilisez dans un projet Workspace peut être compatible entre les vues de données (et l’API), même si elles sont basées sur des champs totalement différents provenant de différentes connexions ou vues de données ou d’un schéma différent dans XDM.

* **Vous pouvez spécifier le nom du composant convivial qui apparaîtra dans Analysis Workspace**. Par défaut, ce nom est hérité du nom d’affichage du schéma, mais vous pouvez désormais le remplacer pour cette Vue de données spécifique. (C’est également ainsi que fonctionne la gestion des composants dans les suites de rapports virtuelles en Adobe Analytics traditionnel).

* **Vous pouvez vue d’autres informations relatives aux schémas sur les composants** , telles que : de quel type de jeu de données (événement, profil, recherche) il provient ; quel type de schéma (chaîne, entier, etc.) il est venu de; et son chemin de schéma (le champ XDM sur lequel il est basé).

* **Vous pouvez baliser un** composant pour faciliter sa recherche dans Workspace.

* **Vous pouvez masquer un composant dans le rapports**. Certains paramètres de mesures et de dimensions dans DV2 exigeaient une seconde mesure ou dimension pour la configuration (comme la déduplication de mesures ou la déduplication d’achat, par exemple). Cela vous permet de définir une mesure ou une dimension qui peut être utilisée dans les paramètres d’une autre mesure ou dimension sans être directement exposée au rapports (par exemple, un ID d’achat).

* **Vous pouvez appliquer une mise en forme à une mesure** , telle que l’affichage de la valeur décimale, de l’heure, du pourcentage ou de la devise ; en spécifiant les décimales ; présentant la tendance à la hausse comme verte ou rouge ; et spécification des options de devise.

* Vous pouvez **créer une mesure ou une dimension en fonction de certaines valeurs seulement du champ de schéma**. Par exemple, si vous souhaitez une mesure &quot;erreurs&quot;, vous pouvez créer une mesure à partir du champ de nom de page, mais inclure uniquement les pages qui contiennent le mot &quot;erreur&quot;. Les mesures d’erreurs créées à partir de ces données sont prises en charge par les filtres, insérées dans les mesures calculées et fonctionnent avec l’attribution, le flux, les abandons, etc.

* Pour les dimensions, vous pouvez **inclure ou exclure automatiquement certaines valeurs dans un champ spécifique**. Par exemple, si un développeur a envoyé une valeur incorrecte de `dev mistake` dans un champ, vous pouvez facilement l&#39;exclure du rapports à l&#39;aide d&#39;une règle d&#39;exclusion et se comporter comme s&#39;il n&#39;avait jamais existé dans les données.

* Vous pouvez **renommer vos conteneurs** dans une vue de données et faire en sorte que ces conteneurs soient renommés dans tout projet Workspace basé sur cette vue de données.

## Condition requise

* Avant de pouvoir créer des vues de données, vous devez [configurer une ou plusieurs connexions aux jeux de données Experience Platform](/help/connections/create-connection.md).
* Pour créer ou gérer une vue de données, vous devez disposer des autorisations suivantes dans Adobe Admin Console :

## Informations sur la vue d’un composant

Cliquez sur l’icône (i) info dans Workspace pour vue sur quel champ de schéma un composant est basé, ainsi que sur ses paramètres, tels qu’une description.

## Paramètres de Vue de données que vous pouvez remplacer dans Workspace

* Intervalle de recherche en amont
* Attribution de mesure
* Indique si les utilisateurs voient ou non la ligne &quot;Aucune valeur&quot; dans un rapport.

## Paramètres de Vue de données que vous ne pouvez pas remplacer dans Workspace

* Type de composant
* Formatage des mesures
* Nom de la vue de données
* Allocation de Dimension

## Aucune valeur

Vous pouvez décider comment appeler cette dimension Aucun/Aucune valeur/Non spécifié et si elle doit être visible par les utilisateurs dans le rapports. Toutefois, les administrateurs et les utilisateurs (pour les projets qu’ils possèdent) peuvent modifier le paramètre de visibilité dans Workspace.

## Supprimer des vues de données

Si vous supprimez une vue de données dans [!UICONTROL Customer Journey Analytics], un message d’erreur indique que tous les projets Workspace qui dépendent de cette vue de données supprimée cesseront de fonctionner.
