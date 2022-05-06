---
title: Ingestion d’audiences AEP dans Customer Journey Analytics
description: Explique comment ingérer des audiences AEP dans Customer Journey Analytics pour une analyse plus approfondie.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 535095dc82680882d1a53076ea0655b1333b576b
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 1%

---

# Ingestion d’audiences AEP dans Customer Journey Analytics (CJA)

>[!NOTE]
>
>Ce sujet est en construction.

Ce cas d’utilisation explore une méthode manuelle intermédiaire pour amener les audiences Adobe Experience Platform (AEP) dans CJA. Ces audiences peuvent avoir été créées dans le créateur de segments AEP, Adobe Audience Manager ou d’autres outils et sont stockées dans Real-time Customer Profile (RTCP). Les audiences se composent d’un ensemble d’identifiants de profil, ainsi que des attributs/événements/etc. applicables. et nous voulons les importer dans CJA Workspace pour analyse.

## Conditions préalables

* Accès à Adobe Experience Platform (AEP), en particulier à Real-time Customer Profile.  Accès également à la création/gestion de schémas et de jeux de données AEP.
* Accès à AEP Query Service (et possibilité d’écrire du code SQL) ou à un autre outil pour effectuer quelques transformations légères
* Accès au Customer Journey Analytics (doit être un administrateur de produit CJA, afin de créer/modifier des connexions CJA et des vues de données)
* Possibilité d’utiliser les API Adobe (Segmentation, éventuellement d’autres)

## Étape 1 : Sélection d’une ou de plusieurs audiences dans Real-time Customer Profile {#audience}

Adobe Experience Platform [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr) (RTCP) vous permet d’obtenir une vue d’ensemble de chaque client en combinant des données issues de plusieurs canaux, notamment en ligne, hors ligne, CRM et tiers. Vous disposez probablement déjà d’audiences dans RTCP qui peuvent provenir de diverses sources. Sélectionnez une ou plusieurs audiences à ingérer dans CJA.

## Étape 2 : Création d’un jeu de données d’union de profil pour l’exportation

Pour exporter l’audience vers un jeu de données pouvant éventuellement être ajouté à une connexion dans CJA, vous devez créer un jeu de données dont le schéma est un profil. [Schéma d’union](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).
Les schémas d’union sont composés de plusieurs schémas qui partagent la même classe et qui ont été activés pour Profile. Le schéma d&#39;union permet de visualiser une fusion de tous les champs contenus dans les schémas partageant la même classe. Real-time Customer Profile utilise le schéma d’union pour créer une vue d’ensemble de chaque client.

## Étape 3 : Exportation d’une audience vers le jeu de données d’union de profil via un appel API {#export}

Avant de pouvoir importer une audience dans CJA, vous devez l’exporter vers un jeu de données AEP. Cette opération ne peut être effectuée qu’à l’aide de l’API Segmentation, et plus particulièrement avec la variable [Point de terminaison de l’API des tâches d’exportation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en). Vous pouvez créer une tâche d’exportation à l’aide de l’ID d’audience de votre choix et placer les résultats dans le jeu de données AEP d’union de profils que vous avez créé à l’étape 2.  Bien que vous puissiez exporter divers attributs/événements pour l’audience, vous n’avez qu’à exporter le champ d’identifiant de profil spécifique qui correspond au champ d’identifiant de personne utilisé dans la connexion CJA que vous allez utiliser (voir à l’étape 5 ci-dessous).

## Étape 4 : Editer la sortie de l&#39;export

Les résultats de la tâche d’exportation doivent être transformés en jeu de données Profile distinct pour être ingérés dans CJA.  Cette transformation peut être effectuée avec AEP Query Service, ou un autre outil de transformation de votre choix.  Nous n’avons besoin que de l’identifiant de profil (qui correspondra à l’identifiant de personne dans CJA) et d’un ou plusieurs identifiants d’audience pour créer des rapports dans CJA. Toutefois, la tâche d’exportation standard contient plus de données. Nous devons donc modifier cette sortie pour supprimer les données superflues et déplacer certains éléments.  En outre, vous devez d’abord créer un schéma/jeu de données avant d’y ajouter les données transformées.

Voici un exemple de sortie d’exportation dans le jeu de données d’union Profile, **before** toute modification :

![Sortie non normalisée](assets/export-unedited.png)

Prenez note des points suivants :

* L’ID d’audience est contenu sous `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* Le statut doit être &quot;réalisé&quot;, &quot;entré&quot;, mais pas &quot;sorti&quot;.

Il s’agit du format du jeu de données Profile que vous pouvez envoyer dans CJA.

![Sortie modifiée](assets/export-edited.png)

Voici les éléments de données qui doivent être présents :

* `_aresprodvalidation` champ de chaîne : Fait référence à votre ID d’organisation. Le vôtre sera différent.
* `personID` champ de chaîne : Il s’agit du champ de schéma XDM standard sur les jeux de données de profil pour identifier la personne. Utilisez l’identifiant de profil de l’exportation.
* `audienceMembershipId` champ de chaîne : ID d’audience de l’exportation.  REMARQUE : Ce champ peut être nommé comme bon vous semble (à partir de votre propre schéma).
* Ajoutez un nom convivial pour l’audience (`audienceMembershipIdName`), par exemple

   ![Nom d’audience convivial](assets/audience-name.png)

* Ajoutez d’autres métadonnées d’audience si vous le souhaitez.

## Étape 5 : Ajoutez ce jeu de données Profile à une connexion existante dans CJA (BG : vous pouvez en créer un nouveau, mais 99 % du temps, les clients souhaitent l’ajouter à une connexion existante où ils disposent déjà de leurs données ; les identifiants d’audience &quot;enrichissent&quot; simplement les données existantes dans CJA)

[Création d’une connexion](/help/connections/create-connection.md)

## Étape 6 : Modifier la vue de données CJA existante (ou en créer de nouvelles)

Ajouter `audienceMembershipId`, `audienceMembershipIdName` et `personID` dans la vue de données.

## Étape 7 : Rapport dans Workspace

Vous pouvez désormais créer des rapports sur `audienceMembershipId`, `audienceMembershipIdName` et `personID` dans Workspace.

## Remarques supplémentaires

* Vous devez effectuer ce processus à une cadence régulière, de sorte que les données d’audience soient constamment actualisées dans CJA.
* Vous pouvez importer plusieurs audiences dans une seule connexion CJA. Cela ajoute une complexité supplémentaire au processus, mais cela est possible. Pour que cela fonctionne, vous devez apporter quelques modifications au processus ci-dessus :
   1. Effectuez ce processus pour chaque audience souhaitée dans votre collection d’audiences dans RTCP.
   1. Lors de l’exécution des transformations de la sortie de la tâche d’exportation, vous devez créer une liste de `audienceMembershipId(s)`, car un seul ID de personne CJA peut appartenir à plusieurs audiences. À un moment donné, CJA prendra en charge des tableaux/tableaux d’objets dans les jeux de données de profil. Une fois ces éléments pris en charge, utilisez un tableau d’objets pour la variable `audienceMembershipId` ou `audienceMembershipIdName` sera la meilleure option. Dans l’intervalle, extrayez tous les identifiants d’audience actuels pour chaque identifiant de profil dans la sortie de la tâche d’exportation (avec le statut &quot;réalisé&quot; ou &quot;entré&quot;), et placez-les dans une chaîne de valeurs séparées par des virgules (c’est-à-dire, `<id1>,<id2>,...`).  S’il existe un ID d’audience avec le statut &quot;sortie&quot;, assurez-vous qu’il ne figure PAS dans la liste.  Si vous souhaitez conserver l’association de noms conviviaux avec l’identifiant, vous pouvez le joindre à la fin de chaque identifiant dans la liste (avec toute autre métadonnée).
   1. Dans votre vue de données, créez une dimension à l’aide de la transformation Sous-chaîne sur la `audienceMembershipId` pour convertir la chaîne de valeurs séparées par des virgules en tableau. REMARQUE : le tableau contient actuellement une limite de 10 valeurs.
   1. Vous pouvez maintenant créer un rapport sur cette nouvelle dimension. `audienceMembershipIds` dans l’espace de travail CJA.
