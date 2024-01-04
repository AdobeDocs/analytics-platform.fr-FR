---
title: Ingestion d’audiences Adobe Experience Platform dans Customer Journey Analytics
description: Explique comment ingérer des audiences Adobe Experience Platform dans Customer Journey Analytics pour une analyse plus approfondie.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 50%

---

# Ingestion d’audiences Adobe Experience Platform dans Adobe Customer Journey Analytics

Ce cas d’utilisation explore une méthode manuelle intermédiaire pour amener les audiences Adobe Experience Platform (Adobe Experience Platform) dans Customer Journey Analytics. Ces audiences peuvent avoir été créées dans le créateur de segments de Adobe Experience Platform, Adobe Audience Manager ou d’autres outils et sont stockées dans Real-time Customer Profile (RTCP). Les audiences se composent d’un ensemble d’identifiants de profil, ainsi que des attributs/événements/etc. applicables, et nous voulons les importer dans Customer Journey Analytics Workspace pour analyse.

## Conditions préalables

* Accès à Adobe Experience Platform (Adobe Experience Platform), en particulier à Real-time Customer Profile.
* Accès pour créer/gérer des schémas et des jeux de données Adobe Experience Platform.
* Accès à Adobe Experience Platform Query Service (et possibilité d’écrire du code SQL) ou à un autre outil pour effectuer des transformations légères.
* Accédez à Customer Journey Analytics. Vous devez être un administrateur de produit Customer Journey Analytics pour créer/modifier des connexions de Customer Journey Analytics et des vues de données.
* Possibilité d’utiliser les API Adobe (Segmentation, éventuellement d’autres)

## Étape 1 : Sélection d’une ou de plusieurs audiences dans le profil client en temps réel {#audience}

Le [profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr) d’Adobe Experience Platform vous permet d’obtenir une vue d’ensemble de chaque client en combinant des données issues de plusieurs canaux, notamment des données en ligne, hors ligne, CRM et tierces.

Vous disposez probablement déjà d’audiences dans RTCP qui peuvent provenir de différentes sources. Sélectionnez une ou plusieurs audiences à ingérer dans Customer Journey Analytics.

## Étape 2 : Création d’un jeu de données d’union de profil pour l’exportation

Pour exporter l’audience vers un jeu de données pouvant éventuellement être ajouté à une connexion dans Customer Journey Analytics, vous devez créer un jeu de données dont le schéma est un profil. [Schéma d’union](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=fr#understanding-union-schemas).

Les schémas d’union sont composés de plusieurs schémas qui partagent la même classe et qui ont été activés pour Profile. Le schéma d’union permet de visualiser une fusion de tous les champs contenus dans les schémas partageant la même classe. Le profil client en temps réel utilise le schéma d’union pour créer une vue d’ensemble de chaque client.

## Étape 3 : Exportation d’une audience vers le jeu de données Union Profil via un appel API {#export}

Avant d’importer une audience dans Customer Journey Analytics, vous devez l’exporter vers un jeu de données Adobe Experience Platform. Cette opération ne peut être effectuée qu’à l’aide de l’API Segmentation, et plus particulièrement avec le [Point d’entrée de l’API des tâches d’exportation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=fr).

Vous pouvez créer une tâche d’exportation à l’aide de l’ID d’audience de votre choix et placer les résultats dans le jeu de données Adobe Experience Platform d’union de profils que vous avez créé à l’étape 2. Bien que vous puissiez exporter divers attributs/événements pour l’audience, il vous suffit d’exporter le champ d’identifiant de profil spécifique qui correspond au champ d’identifiant de personne utilisé dans la connexion du Customer Journey Analytics que vous allez utiliser (voir à l’étape 5 ci-dessous).

## Étape 4 : Modifier la sortie de l’exportation

Les résultats de la tâche d’exportation doivent être transformés en jeu de données Profile distinct pour être ingérés dans Customer Journey Analytics.  Cette transformation peut se faire avec [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=fr)ou un autre outil de transformation de votre choix. Nous n’avons besoin que de l’identifiant de profil (qui correspondra à l’identifiant de personne en Customer Journey Analytics) et d’un ou plusieurs identifiants d’audience pour créer des rapports dans Customer Journey Analytics.

Toutefois, la tâche d’exportation standard contient plus de données. Nous devons donc modifier cette sortie pour supprimer les données superflues et déplacer certains éléments. En outre, vous devez d’abord créer un schéma/jeu de données avant d’y ajouter les données transformées.

Voici un exemple de sortie d’exportation dans le jeu de données Union Profil, **avant** toute modification :

![Sortie non modifiée](../assets/export-unedited.png)

Prenez note des points suivants :

* L’ID d’audience est contenu sous `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* Le statut doit être « réalisé » ou « entré », mais pas « sorti ».

Il s’agit du format du jeu de données Profile que vous pouvez envoyer dans Customer Journey Analytics.

![Sortie modifiée](../assets/export-edited.png)

Voici les éléments de données qui doivent être présents :

* champ de chaîne `_aresprodvalidation` : fait référence à votre ID d’organisation. Le vôtre sera différent.
* Champ de chaîne `personID` : il s’agit du champ de schéma XDM standard sur les jeux de données Profil pour identifier la personne. Utilisez l’ID de profil de l’exportation.
* Champ de chaîne `audienceMembershipId` : ID d’audience de l’exportation. REMARQUE : ce champ peut être nommé comme vous le souhaitez (à partir de votre propre schéma).
* Ajoutez un nom convivial pour l’audience (`audienceMembershipIdName`), par exemple

  ![Nom d’audience convivial](../assets/audience-name.png)

* Ajoutez d’autres métadonnées d’audience si vous le souhaitez.

## Étape 5 : Ajout de ce jeu de données Profile à une connexion existante dans Customer Journey Analytics

Vous pouvez [créer une connexion](/help/connections/create-connection.md), mais la plupart des clients souhaitent ajouter le jeu de données Profil à une connexion existante. Les identifiants d’audience &quot;enrichissent&quot; les données existantes en Customer Journey Analytics.

## Étape 6 : modifier la vue de données de Customer Journey Analytics existante (ou créer)

Ajouter `audienceMembershipId`, `audienceMembershipIdName` et `personID` dans la vue de données.

## Étape 7 : Rapport dans Workspace

Vous pouvez désormais créer des rapports sur `audienceMembershipId`, `audienceMembershipIdName` et `personID` dans Workspace.

## Remarques supplémentaires

* Vous devez effectuer ce processus régulièrement, de sorte que les données d’audience soient constamment actualisées dans Customer Journey Analytics.
* Vous pouvez importer plusieurs audiences au sein d’une même connexion de Customer Journey Analytics. Cela ajoute une complexité supplémentaire au processus, mais c’est possible. Pour que cela fonctionne, vous devez apporter quelques modifications au processus ci-dessus :
   1. Effectuez ce processus pour chaque audience souhaitée dans votre collection d’audiences dans RTCP.
   1. Customer Journey Analytics prend en charge les tableaux/tableaux d’objets dans les jeux de données de profil. Utilisation d’un [tableau d’objets](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html?lang=fr) pour audienceMembershipId ou audienceMembershipIdName est la meilleure option.
   1. Dans votre vue de données, créez une dimension à l’aide de la transformation Sous-chaîne sur le champ `audienceMembershipId` pour convertir la chaîne de valeurs séparées par des virgules en tableau. REMARQUE : le tableau contient actuellement une limite de 10 valeurs.
   1. Vous pouvez maintenant créer un rapport sur cette nouvelle dimension. `audienceMembershipIds` dans Customer Journey Analytics Workspace.
