---
title: Ingestion d’audiences AEP dans Customer Journey Analytics
description: Explique comment ingérer des audiences AEP dans Customer Journey Analytics pour une analyse plus approfondie.
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: cd1d639ad698c188c506881b2b17103b0a3559f2
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 2%

---


# Ingestion d’audiences AEP dans Customer Journey Analytics (CJA)

(Brandon, fyi, &quot;Profil unifié&quot; est un terme obsolète de &quot;Profil client en temps réel&quot;, selon le directeur de documentation de l’AEP. Vous ne trouverez aucun document dans l’ensemble de documents AEP.)

Ce cas d’utilisation explore une méthode manuelle intermédiaire pour amener les audiences Adobe Experience Platform (AEP) dans CJA. Ces audiences peuvent avoir été créées dans le créateur de segments AEP, Adobe Audience Manager ou d’autres outils et sont stockées dans Real-time Customer Profile (RTCP). Les audiences se composent de listes d’ID de personne, d’ID de profil, etc. et nous voulons les importer dans CJA Workspace pour analyse.

## Conditions préalables

* Accès à Adobe Experience Platform (AEP), en particulier à Real-time Customer Profile.
* Accès au Customer Journey Analytics
* Possibilité d’écrire du code personnalisé ?
* Quoi d&#39;autre.

## Étape 1 : Sélection d’une ou de plusieurs audiences dans Real-time Customer Profile {#audience}

Adobe Experience Platform [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr) (RTCP) vous permet d’obtenir une vue d’ensemble de chaque client en combinant des données issues de plusieurs canaux, notamment en ligne, hors ligne, CRM et tiers. Vous disposez probablement déjà d’audiences dans RTCP qui peuvent provenir de diverses sources. Sélectionnez une ou plusieurs audiences.

## Étape 2 : Création d’un jeu de données d’union de profil pour l’exportation

Pour exporter l’audience vers un jeu de données qui peut ensuite établir une connexion à CJA, vous devez créer un jeu de données dont le schéma est un profil. [Schéma d’union](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).
Les schémas d’union sont composés de plusieurs schémas qui partagent la même classe et qui ont été activés pour Profile. Le schéma d&#39;union permet de visualiser une fusion de tous les champs contenus dans les schémas partageant la même classe. Real-time Customer Profile utilise le schéma d’union pour créer une vue d’ensemble de chaque client.

## Étape 3 : Exportation d’une audience vers un jeu de données via un appel API {#export}

Avant de pouvoir importer une audience dans CJA, vous devez l’exporter vers un jeu de données dans AEP. Cette opération ne peut être effectuée qu’à l’aide de l’API Segmentation, et plus particulièrement avec la variable [Point de terminaison de l’API des tâches d’exportation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en). Vous pouvez créer une tâche d’exportation et placer les résultats dans le jeu de données AEP d’union de profils que vous avez créé à l’étape 2.

## Étape 4 : Editer la sortie de l&#39;export

Lors de la création de la tâche d’exportation pour une audience, nous n’avons besoin que de l’ID de personne et de l’ID d’audience pour créer des rapports dans CJA. Toutefois, la tâche d’exportation standard contient plus de données. Nous devons donc modifier cette sortie pour supprimer les données superflues.

Voici un exemple de sortie d’exportation dans le jeu de données d’union Profile, **before** toute modification :

![Sortie non normalisée](assets/export-unedited.png)

Prenez note des points suivants :

* L’ID d’audience est contenu sous `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* Le statut doit être &quot;réalisé&quot;, &quot;entré&quot;, mais pas &quot;sorti&quot;. Remplacez &quot;exited&quot; par &quot;blank&quot;.

Il s’agit du format du jeu de données Profile que vous pouvez envoyer dans CJA.

![Sortie modifiée](assets/export-edited.png)

Voici les éléments de données qui doivent être présents :

* `_aresprodvalidation`: Fait référence à votre ID d’organisation. Le vôtre sera différent.
* `personID`: Dans ce cas, un nom convivial
* `audienceMembershipIdList` champ de chaîne : ID d’audience
* Ajoutez un nom convivial pour l’audience (`audienceMembershipIdName`), par exemple

   ![Nom d’audience convivial](assets/audience-name)

## Étape 5 : Création d’une connexion dans CJA à ce jeu de données Profile

[Création d’une connexion](/help/connections/create-connection.md)

## Étape 6 : Création d’une vue de données

Ajouter `audienceMembershipIdName` et `personID` dans la vue de données.

## Étape 7 : Rapport dans Workspace

Vous pouvez désormais créer des rapports sur `audienceMembershipIdName` et `personID` dans Workspace.
La capture d&#39;écran serait géniale.

Pour ce faire :

écrivez d’autres étapes pour lorsque vous traitez avec des personnes qui appartiennent à plusieurs audiences.




