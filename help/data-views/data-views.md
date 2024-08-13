---
title: Présentation des vues de données
description: Une vue de données indique comment interpréter les éléments des données de la connexion du Customer Journey Analytics, tels que les mesures, les dimensions, les sessions, etc.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 0e4e4621abe02c022981e458282543908b2396c2
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 43%

---

# Présentation des vues de données

Une vue de données est un conteneur spécifique à Customer Journey Analytics qui vous permet de déterminer comment interpréter les données d’une [connexion](/help/connections/create-connection.md). Elle spécifie toutes les dimensions et mesures disponibles dans Analysis Workspace et les colonnes dont ces dimensions et mesures obtiennent leurs données. Les vues de données sont définies en vue de la création de comptes rendus des performances dans Analysis Workspace.

>[!NOTE]
>
>Les paramètres que vous sélectionnez ou modifiez dans une vue de données sont rétroactifs et non destructifs. En d’autres termes, ils ne modifient pas définitivement vos données sous-jacentes.

Vous pouvez créer différentes vues de données pour la même connexion, avec des ensembles de composants très différents (dimensions/mesures). Vous pouvez également créer des vues de données avec différents paramètres pour le délai d’expiration de la visite, l’attribution, etc. Par exemple, vous pouvez avoir une vue de données où toutes les dimensions sont définies sur [!UICONTROL Dernière touche] et, simultanément, une autre vue de données (basée sur le même jeu de données) où toutes les dimensions sont définies sur [!UICONTROL Première touche].

Les projets Espace de travail dans Customer Journey Analytics reposent sur des vues de données.

>[!IMPORTANT]
>
>Vous pouvez ajouter jusqu’à 5 000 mesures et 5 000 dimensions à une seule vue de données.

## Fonctionnalités des vues de données {#capabilities}

Les vues de données vous permettent de modifier directement les paramètres des éléments de schéma, sans devoir modifier le schéma dans Adobe Experience Platform ou procéder à une nouvelle mise en œuvre de votre environnement Customer Journey Analytics.

* Vous pouvez modifier un composant d’une mesure à une dimension et vice versa. Vous pouvez créer des mesures à partir de champs de chaîne ou des dimensions à partir de champs numériques. Cette fonctionnalité facilite votre vie, car vous n’avez pas à créer de champ numérique dans votre schéma XDM pour chaque mesure de votre choix. Au lieu de cela, vous pouvez simplement le créer directement dans la boîte de dialogue des vues de données. Voici quelques exemples :
   * **Créez une ou plusieurs dimensions et/ou une dimension à partir dʼun seul champ de schéma**. Cʼest une relation un-à-multiple. Par exemple, vous pouvez créer une ou plusieurs mesures Chiffre dʼaffaires et/ou une ou plusieurs dimensions Chiffre dʼaffaires à partir dʼun seul champ de schéma.
   * **Utilisez un champ de chaîne comme mesure** : lorsque vous renseignez un schéma dans Experience Platform avec un jeu de données, vous ne savez peut-être pas à lʼavance de quels éléments de schéma vous avez besoin. Par exemple, vous n’avez peut-être pas réalisé que vous aviez besoin d’une mesure pour *Erreurs sur une page*. Par conséquent, vous nʼavez pas créé dʼélément de schéma numérique à cet effet. En utilisant un élément de chaîne comme mesure, vous pouvez désormais utiliser les paramètres des vues de données pour spécifier qu’à chaque fois qu’une chaîne contient le mot `error`, elle peut être utilisée comme mesure.
   * **Utilisez un champ numérique comme dimension** : par exemple, si vous souhaitez extraire la mesure Recettes de la dimension Recettes, la dimension Recettes affichera chaque valeur comme élément de dimension. Et le nombre d’instances pour chaque élément de dimension en tant que mesure.

* Vous pouvez créer plusieurs mesures avec différents modèles d’attribution ou différents intervalles de recherche en amont à partir du même champ de schéma.

* Vous pouvez modifier l’identifiant d’un composant pour une compatibilité entre les vues de données. Lʼidentifiant (ID) de composant est utilisé par lʼAPI de création de rapports afin dʼidentifier une mesure ou une dimension spécifique. Comme vous pouvez créer arbitrairement de nombreuses mesures ou dimensions à partir d’un champ XDM, vous avez la possibilité de définir votre propre identifiant de composant. Par conséquent, une mesure que vous utilisez dans un projet Workspace peut être utilisée de manière compatible entre les vues de données (et l’API). Même si les mesures sont basées sur des champs totalement différents à partir de différentes connexions, vues de données ou d’un schéma différent dans XDM.

* Vous pouvez spécifier le nom convivial du composant qui apparaît dans Analysis Workspace. Par défaut, ce nom est hérité du nom dʼaffichage du schéma, mais vous pouvez désormais le remplacer pour cette vue de données spécifique.

* Vous pouvez afficher d’autres informations relatives aux schémas sur les composants. Par exemple :

   * de quel type de jeu de données (événement, profil, recherche, résumé) le composant provient,
   * le type de schéma (chaîne, entier, etc.) il provient de et
   * chemin d’accès au schéma (le champ XDM sur lequel il est basé).

* Vous pouvez baliser un composant pour faciliter sa recherche dans Workspace.

* Vous pouvez masquer un composant dans les rapports. Certains paramètres des mesures et des dimensions nécessitent une seconde mesure ou dimension pour la configuration (comme la déduplication des mesures ou des achats, par exemple). Le masquage d’un composant vous permet de définir un composant qui peut être utilisé dans les paramètres d’un autre composant sans être exposé dans les rapports.

* Vous pouvez appliquer une mise en forme à une mesure (décimal, heure, pourcentage ou devise, valeurs décimales, tendance à la hausse en vert ou rouge, options de devise, par exemple).

* Vous pouvez créer une mesure ou une dimension en fonction de certaines valeurs seulement du champ de schéma. Par exemple, si vous souhaitez une mesure Erreurs, vous pouvez créer une mesure à partir du champ nom de page, mais inclure uniquement les pages qui contiennent le mot `error`. La mesure Erreurs créée de cette manière prend en charge les filtres, peut être insérée dans les mesures calculées et fonctionne avec l’attribution, le flux, les abandons, etc.

* Pour les dimensions, vous pouvez inclure ou exclure automatiquement certaines valeurs dans un champ spécifique. Par exemple, si un développeur a envoyé une valeur incorrecte de `dev mistake` dans un champ, vous pouvez facilement l’exclure des rapports à l’aide d’une règle d’exclusion. La dimension se comporte comme si la mauvaise valeur n’avait jamais existé dans les données.

* Vous pouvez renommer vos conteneurs dans une vue de données et faire apparaître ces conteneurs renommés dans n’importe quel projet Workspace basé sur cette vue de données.

## Conditions préalables des vues de données {#prerequisites}

* Avant de pouvoir créer des vues de données, vous devez [configurer une ou plusieurs connexions aux jeux de données Experience Platform](/help/connections/create-connection.md).
* Pour créer ou gérer une vue de données, vous devez disposer dʼun [ensemble dʼautorisations dans Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-overview).
* Si vous utilisez le [connecteur source Adobe Analytics](/help/data-ingestion/analytics.md) ou si vous possédez des connaissances en arrière-plan Adobe Analytics, vous souhaiterez peut-être comprendre comment les champs de vos schémas et jeux de données se rapportent aux homologues Adobe Analytics. Pour en savoir plus, consultez [Mappages des champs Analytics ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics).

## Paramètres des vue de données que vous pouvez remplacer dans Espace de travail {#settings-override}

Certains paramètres des vues de données peuvent être modifiés dans Analysis Workspace au niveau du projet, dʼautres non.

* [!UICONTROL Intervalle de recherche en amont]
* Attribution de mesure
* Lʼaffichage ou non pour les utilisateurs de lʼélément de ligne [!UICONTROL Aucune valeur] dans un rapport

## Paramètres des vues de données que vous ne pouvez pas remplacer dans Espace de travail {#settings-no-override}

* [!UICONTROL Type de composant]
* Mise en forme des mesures
* Nom de la vue de données
* Attribution de dimension

## Supprimer des vues de données {#delete}

Si vous supprimez une vue de données dans [!UICONTROL Customer Journey Analytics], un message d’erreur indique que tout projet [!UICONTROL Workspace] qui dépend de cette vue de données supprimée ne fonctionne plus.

## Étapes suivantes

* [Création de vues de données](/help/data-views/create-dataview.md)
* [Cas dʼutilisation des vues de données](/help/use-cases/data-views/data-views-usecases.md)
