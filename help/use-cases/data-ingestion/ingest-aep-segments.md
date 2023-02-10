---
title: Ingestion d’audiences AEP dans Customer Journey Analytics
description: Explique comment ingérer des audiences AEP dans Customer Journey Analytics pour une analyse plus approfondie.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 04aaf9ae9f720255c97c9dc148953b5b9d6967ae
workflow-type: ht
source-wordcount: '937'
ht-degree: 100%

---

# Ingestion d’audiences AEP dans Customer Journey Analytics (CJA)

Ce cas pratique explore une méthode manuelle intermédiaire pour amener les audiences Adobe Experience Platform (AEP) dans CJA. Ces audiences peuvent avoir été créées dans le créateur de segments AEP, Adobe Audience Manager ou d’autres outils et sont stockées dans le profil client en temps réel. Les audiences se composent d’un ensemble d’identifiants de profil, ainsi que des attributs/événements/etc. applicables, et nous voulons les importer dans CJA Workspace pour analyse.

## Conditions préalables

* Accédez Adobe Experience Platform (AEP), en particulier au profil client en temps réel.
* Accédez à AEP pour créer/gérer des schémas et des jeux de données AEP.
* Accédez à AEP Query Service (et à la fonctionnalité d’écriture de code SQL) ou à un autre outil pour effectuer des transformations légères.
* Accédez à Customer Journey Analytics. Vous devez être un administrateur de produit CJA pour créer/modifier des connexions CJA et des vues de données.
* Possibilité d’utiliser les API Adobe (Segmentation, éventuellement d’autres)

## Étape 1 : Sélection d’une ou de plusieurs audiences dans le profil client en temps réel {#audience}

Le [profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr) d’Adobe Experience Platform vous permet d’obtenir une vue d’ensemble de chaque client en combinant des données issues de plusieurs canaux, notamment des données en ligne, hors ligne, CRM et tierces.

Vous disposez probablement déjà d’audiences dans RTCP qui peuvent provenir de différentes sources. Sélectionnez une ou plusieurs audiences à ingérer dans CJA.

## Étape 2 : Création d’un jeu de données d’union de profil pour l’exportation

Pour exporter l’audience vers un jeu de données pouvant éventuellement être ajouté à une connexion dans CJA, vous devez créer un jeu de données dont le schéma est [Schéma d’union](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=fr#understanding-union-schemas) Profil.

Les schémas d’union sont composés de plusieurs schémas qui partagent la même classe et qui ont été activés pour Profile. Le schéma d’union permet de visualiser une fusion de tous les champs contenus dans les schémas partageant la même classe. Le profil client en temps réel utilise le schéma d’union pour créer une vue d’ensemble de chaque client.

## Étape 3 : Exportation d’une audience vers le jeu de données Union Profil via un appel API {#export}

Avant de pouvoir importer une audience dans CJA, vous devez l’exporter vers un jeu de données AEP. Cette opération ne peut être effectuée qu’à l’aide de l’API Segmentation, et plus particulièrement avec le [Point d’entrée de l’API des tâches d’exportation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=fr).

Vous pouvez créer une tâche d’exportation à l’aide de l’ID d’audience de votre choix et placer les résultats dans le jeu de données AEP Union Profil que vous avez créé à l’étape 2. Bien que vous puissiez exporter divers attributs/événements pour l’audience, vous n’avez qu’à exporter le champ d’identifiant de profil spécifique qui correspond au champ d’identifiant de personne utilisé dans la connexion CJA que vous allez utiliser (voir à l’étape 5 ci-dessous).

## Étape 4 : Modifier la sortie de l’exportation

Les résultats de la tâche d’exportation doivent être transformés en jeu de données Profil distinct pour être ingérés dans CJA. Cette transformation peut se faire avec [AEP Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=fr) ou un autre outil de transformation de votre choix. Nous n’avons besoin que de l’ID de profil (qui correspondra à l’ID de personne dans CJA) et d’un ou plusieurs identifiants d’audience pour créer des rapports dans CJA.

Toutefois, la tâche d’exportation standard contient plus de données. Nous devons donc modifier cette sortie pour supprimer les données superflues et déplacer certains éléments. En outre, vous devez d’abord créer un schéma/jeu de données avant d’y ajouter les données transformées.

Voici un exemple de sortie d’exportation dans le jeu de données Union Profil, **avant** toute modification :

![Sortie non modifiée](../assets/export-unedited.png)

Prenez note des points suivants :

* L’ID d’audience est contenu sous `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* Le statut doit être « réalisé » ou « entré », mais pas « sorti ».

Il s’agit du format du jeu de données Profil que vous pouvez envoyer dans CJA.

![Sortie modifiée](../assets/export-edited.png)

Voici les éléments de données qui doivent être présents :

* champ de chaîne `_aresprodvalidation` : fait référence à votre ID d’organisation. Le vôtre sera différent.
* Champ de chaîne `personID` : il s’agit du champ de schéma XDM standard sur les jeux de données Profil pour identifier la personne. Utilisez l’ID de profil de l’exportation.
* Champ de chaîne `audienceMembershipId` : ID d’audience de l’exportation. REMARQUE : ce champ peut être nommé comme vous le souhaitez (à partir de votre propre schéma).
* Ajoutez un nom convivial pour l’audience (`audienceMembershipIdName`), par exemple

   ![Nom d’audience convivial](../assets/audience-name.png)

* Ajoutez d’autres métadonnées d’audience si vous le souhaitez.

## Étape 5 : Ajouter ce jeu de données Profil à une connexion existante dans CJA

Vous pouvez [créer une connexion](/help/connections/create-connection.md), mais la plupart des clients souhaitent ajouter le jeu de données Profil à une connexion existante. Les ID d’audience « enrichissent » les données existantes dans CJA.

## Étape 6 : Modifier la vue de données CJA existante (ou en créer une nouvelle)

Ajouter `audienceMembershipId`, `audienceMembershipIdName` et `personID` dans la vue de données.

## Étape 7 : Rapport dans Workspace

Vous pouvez désormais créer des rapports sur `audienceMembershipId`, `audienceMembershipIdName` et `personID` dans Workspace.

## Remarques supplémentaires

* Vous devez effectuer ce processus régulièrement, de sorte que les données d’audience soient constamment actualisées dans CJA.
* Vous pouvez importer plusieurs audiences dans une seule connexion CJA. Cela ajoute une complexité supplémentaire au processus, mais c’est possible. Pour que cela fonctionne, vous devez apporter quelques modifications au processus ci-dessus :
   1. Effectuez ce processus pour chaque audience souhaitée dans votre collection d’audiences dans RTCP.
   1. CJA prend en charge les tableaux/tableaux d’objets dans les jeux de données de profil. Utilisation d’un [tableau d’objets](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/object-arrays.html?lang=fr) pour audienceMembershipId ou audienceMembershipIdName est la meilleure option.
   1. Dans votre vue de données, créez une dimension à l’aide de la transformation Sous-chaîne sur le champ `audienceMembershipId` pour convertir la chaîne de valeurs séparées par des virgules en tableau. REMARQUE : le tableau contient actuellement une limite de 10 valeurs.
   1. Vous pouvez maintenant créer un rapport sur cette nouvelle dimension. `audienceMembershipIds` dans l’espace de travail CJA.
