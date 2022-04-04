---
title: Présentation des vues de données
description: Une vue de données indique la manière dont vous souhaitez interpréter les éléments de données dans la connexion CJA, tels que les mesures, les dimensions, les sessions, etc.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 9f7b98084a7ec5d2abe89e00f0a6567cb271e80a
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 100%

---

# Présentation des vues de données

Une vue de données est un conteneur spécifique à Customer Journey Analytics qui vous permet de déterminer comment interpréter les données d’une [connexion](/help/connections/create-connection.md). Elle spécifie toutes les dimensions et mesures disponibles dans Analysis Workspace et les colonnes dont ces dimensions et mesures obtiennent leurs données. Les vues de données sont définies en vue de la création de comptes rendus des performances dans Analysis Workspace.

>[!NOTE]
>
>Les paramètres que vous sélectionnez ou modifiez dans une vue de données sont rétroactifs et non destructifs. En d’autres termes, ils ne modifient pas définitivement vos données sous-jacentes.

Vous pouvez créer différentes vues de données pour la même connexion, avec des ensembles de composants très différents (dimensions/mesures). Vous pouvez également créer des vues de données avec des paramètres différents pour le délai de visite, lʼattribution, etc. Par exemple, vous pouvez avoir une vue de données où toutes les dimensions sont définies sur [!UICONTROL Dernière touche] et, simultanément, une autre vue de données (basée sur le même jeu de données) où toutes les dimensions sont définies sur [!UICONTROL Première touche].

Les projets Espace de travail dans Customer Journey Analytics reposent sur des vues de données.

## Fonctionnalités des vues de données {#capabilities}

Les vues de données vous permettent de modifier directement les paramètres des éléments de schéma, sans devoir modifier le schéma dans Adobe Experience Platform ou procéder à une nouvelle mise en œuvre de votre environnement CJA.

* **Vous pouvez modifier un composant de mesure en dimension et vice versa**. Vous pouvez créer des mesures à partir de champs de chaîne ou des dimensions à partir de champs numériques. Cela vous facilite la vie, car il nʼest pas nécessaire de créer un champ numérique dans le schéma XDM pour chaque mesure souhaitée. Au lieu de cela, vous pouvez simplement le créer directement dans la boîte de dialogue des vues de données. Voici quelques exemples :
   * **Créez une ou plusieurs dimensions et/ou une dimension à partir dʼun seul champ de schéma**. Cʼest une relation un-à-multiple. Par exemple, vous pouvez créer une ou plusieurs mesures Chiffre dʼaffaires et/ou une ou plusieurs dimensions Chiffre dʼaffaires à partir dʼun seul champ de schéma.
   * **Utilisez un champ de chaîne comme mesure** : lorsque vous renseignez un schéma dans Experience Platform avec un jeu de données, vous ne savez peut-être pas à lʼavance de quels éléments de schéma vous avez besoin. Par exemple, vous nʼavez peut-être pas réalisé que vous aviez besoin dʼune mesure pour les « Erreurs sur une page ». Par conséquent, vous nʼavez pas créé dʼélément de schéma numérique à cet effet. En utilisant un élément de chaîne comme mesure, vous pouvez désormais utiliser les paramètres des vues de données pour indiquer que chaque fois quʼune chaîne contient le mot « erreur », elle peut être utilisée comme mesure.
   * **Utilisez un champ numérique comme dimension** : par exemple, si vous souhaitez extraire la mesure Chiffre dʼaffaires de la dimension Chiffre dʼaffaires, la dimension Chiffre dʼaffaires affichera chaque valeur en tant quʼélément de dimension (100 €, 175 €, 1 000 €, etc.) ainsi que le nombre dʼinstances pour chaque élément de dimension. La mesure Chiffre dʼaffaires se comporte alors comme elle lʼa toujours fait.

* **Vous pouvez créer plusieurs mesures avec différents modèles dʼattribution ou avec différents intervalles de recherche en amont** à partir du même champ de schéma.

* **Vous pouvez modifier lʼidentifiant dʼun composant** : cette fonctionnalité est utilisée pour la compatibilité entre les vues de données. Lʼidentifiant (ID) de composant est utilisé par lʼAPI de création de rapports afin dʼidentifier une mesure ou une dimension spécifique. Comme vous pouvez créer arbitrairement de nombreuses mesures ou dimensions à partir dʼun seul champ XDM, nous vous offrons la possibilité de définir votre propre ID de composant. Par conséquent, une mesure que vous utilisez dans un projet Espace de travail peut être compatible entre toutes les vues de données (et lʼAPI), même si celles-ci sont basées sur des champs totalement différents provenant de connexions ou de vues de données différentes ou dʼun schéma en XDM différent.

* **Vous pouvez définir un nom convivial pour le composant qui apparaîtra dans Analysis Workspace**. Par défaut, ce nom est hérité du nom dʼaffichage du schéma, mais vous pouvez désormais le remplacer pour cette vue de données spécifique.

* **Vous pouvez afficher plus dʼinformations relatives au schéma des composants**, telles que : le type de jeu de données (événement, profil, recherche) dont il provient, le type de schéma (chaîne, entier, etc.) dont il provient, ainsi que le chemin dʼaccès de son schéma (le champ XDM sur lequel il est basé).

* **Vous pouvez marquer un composant** pour faciliter sa recherche dans Espace de travail.

* **Vous pouvez masquer un composant dans le compte rendu des performances**. Certains paramètres des mesures et des dimensions nécessitent une seconde mesure ou dimension pour la configuration (comme la déduplication des mesures ou des achats, par exemple). Cela vous permet de définir une mesure ou une dimension qui peut être utilisée dans les paramètres dʼune autre mesure ou dimension sans être affichée directement dans le compte rendu des performances (par exemple, un identifiant dʼachat).

* **Vous pouvez appliquer une mise en forme à une mesure**, telle que lʼaffichage de la valeur décimale, de la durée, du pourcentage ou de la devise, la spécification du nombre de décimales, lʼaffichage de la tendance à la hausse en vert ou en rouge et la spécification des options de devise.

* Vous pouvez **créer une mesure ou une dimension basée sur seulement certaines des valeurs du champ de schéma**. Par exemple, si vous souhaitez une mesure « Erreurs », vous pouvez créer une mesure à partir du champ de nom de page, mais nʼinclure que les pages qui contiennent le mot « erreur ». La mesure Erreurs ainsi créée est prise en charge par des filtres, qui peuvent être insérés dans des mesures calculées, et fonctionne avec lʼattribution, le flux, les abandons, etc.

* Pour les dimensions, vous pouvez **automatiquement inclure ou exclure seulement certaines valeurs dans un champ spécifique**. Par exemple, si un développeur a envoyé une valeur incorrecte de `dev mistake` dans un champ, vous pouvez facilement lʼexclure du compte rendu des performances à lʼaide dʼune règle dʼexclusion, qui se comportera comme sʼil nʼavait jamais existé dans les données.

* Vous pouvez **renommer vos conteneurs** dans une vue de données et faire en sorte que ces conteneurs renommés apparaissent dans tout projet Espace de travail basé sur cette vue de données.

## Conditions préalables des vues de données {#prerequisites}

* Avant de pouvoir créer des vues de données, vous devez [configurer une ou plusieurs connexions aux jeux de données Experience Platform](/help/connections/create-connection.md).
* Pour créer ou gérer une vue de données, vous devez disposer dʼun [ensemble dʼautorisations dans Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr#admin-access-permissions).

## Paramètres des vue de données que vous pouvez remplacer dans Espace de travail {#settings-override}

Certains paramètres des vues de données peuvent être modifiés dans Analysis Workspace au niveau du projet, dʼautres non.

* [!UICONTROL Intervalle de recherche en amont]
* Attribution de mesure
* Lʼaffichage ou non pour les utilisateurs de lʼélément de ligne [!UICONTROL No Value] dans un rapport

## Paramètres des vues de données que vous ne pouvez pas remplacer dans Espace de travail {#settings-no-override}

* [!UICONTROL Type de composant]
* Mise en forme des mesures
* Nom de la vue de données
* Attribution de dimension

## Supprimer des vues de données {#delete}

Si vous supprimez une vue de données dans [!UICONTROL Customer Journey Analytics], un message dʼerreur indique que tous les projets [!UICONTROL Espace de travail] qui dépendent de cette vue de données supprimée ne fonctionneront plus.

## Étapes suivantes

* [Création de vues de données](/help/data-views/create-dataview.md)
* [Cas dʼutilisation des vues de données](/help/data-views/data-views-usecases.md)
