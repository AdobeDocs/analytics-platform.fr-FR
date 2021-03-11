---
title: Présentation de l’Analyse cross-canal
description: Recomposer les identifiants de visiteurs de plusieurs jeux de données pour regrouper les visiteurs.
translation-type: tm+mt
source-git-commit: cc78a3941a4179be0dbf46055fea60df8e7e8b97
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 84%

---


# Présentation de l’Analyse cross-canal

**Journey IQ : Analyse cross-canal** est une fonctionnalité qui vous permet de recomposer l’ID de personne d’un jeu de données, ce qui permet une combinaison transparente de plusieurs jeux de données.  L’ACC examine les données utilisateur des sessions authentifiées et non authentifiées afin de générer un identifiant assemblé. Utiliser l’Analyse cross-canal vous permet de répondre à des questions telles que :

* Combien de personnes commencent leur expérience sur un canal, puis la terminent sur un autre ?
* Combien de personnes interagissent avec ma marque ? Combien de types de périphériques utilisent-elles ? Comment se superposent-elles ?
* À quelle fréquence les utilisateurs commencent-ils une tâche sur un périphérique mobile, puis passent-ils ensuite à un PC de bureau pour terminer la tâche ? Les clics publicitaires de campagne amenant à un périphérique conduisent-ils à une conversion ailleurs ?
* Comment ma compréhension de l’efficacité de la campagne change-t-elle si je prends en compte les trajets entre plusieurs périphériques ? Comment mon analyse d’entonnoir change-t-elle ?
* Quels sont les chemins les plus courants empruntés par les utilisateurs d’un périphérique à l’autre ? Où abandonnent-ils ? Où réussissent-ils ?
* En quoi le comportement des utilisateurs ayant plusieurs périphériques diffère-t-il de celui des utilisateurs disposant d’un seul périphérique ?

Lorsque vous combinez des jeux de données avec des identifiants de personne similaires, l’attribution est transférée sur plusieurs appareils et canaux. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur rencontre un problème avec sa commande, puis appelle votre équipe du service client pour l’aider à résoudre ce problème. Avec l’Analyse cross-canal, vous pouvez attribuer des événements du centre d’appel à la publicité sur laquelle ils ont cliqué à l’origine.

## Conditions préalables

>[!IMPORTANT]
>
>Si vous ne remplissez pas toutes les conditions préalables, vous risquez dʼêtre incapable de créer une connexion à l’ACC ou de ne pas obtenir de résultats satisfaisants lors de la combinaison de jeux de données.

Avant d’utiliser l’Analyse cross-canal, veillez à ce que votre organisation dispose des éléments suivants :

* Un jeu de données Adobe Experience Platform doit comporter deux colonnes qui permettent d’identifier les visiteurs :
   * Un **identifiant persistant**, un identifiant présent sur chaque ligne. Par exemple, un identifiant visiteur généré par une bibliothèque AppMeasurement Adobe Analytics.
   * Un **identifiant transitoire**, identifiant présent sur certaines lignes seulement. Par exemple, un nom d’utilisateur ou une adresse électronique chiffré une fois qu’un visiteur s’authentifie. Vous pouvez utiliser pratiquement n’importe quel identifiant, tant qu’il est présent au moins une fois sur le même événement qu’un identifiant persistant donné.
* Un autre jeu de données, tel que les données du centre d’appel, qui contient un identifiant transitoire sur chaque ligne. Cet identifiant de personne doit être formaté de la même manière que l’identifiant transitoire dans l’autre jeu de données.
* Cette fonctionnalité vous permet de réunir des jeux de données qui peuvent inclure la fusion de données utilisateur authentifiées et non authentifiées. Veillez à respecter les lois et réglementations en vigueur, y compris lʼobtention des autorisations dʼutilisateur final nécessaires, avant de fusionner des jeux de données.

## Limites

L’Analyse cross-canal est une fonctionnalité innovante et robuste, mais son utilisation a ses limites.

* Les capacités de recomposition de données actuelles sont limitées à une étape (identifiant persistant à identifiant transitoire). La recomposition de données à plusieurs étapes (par exemple, un identifiant persistant à un identifiant transitoire, puis à un autre identifiant transitoire) n’est pas prise en charge.
* Seuls les jeux de données dʼévénement sont pris en charge. D’autres jeux de données, tels que les jeux de données de recherche, ne sont pas pris en charge.
* Les mappages d’identifiants personnalisés utilisés dans votre organisation ne sont pas pris en charge.
* Le graphique Adobe Co-op et le graphique privé ne sont pas pris en charge.
* Analytics sur plusieurs Canaux ne transforme en rien le champ utilisé pour l’assemblage. L’assemblage basé sur les champs utilise la valeur du champ spécifié telle qu’elle existe dans le jeu de données désassemblé dans le lac de données. Par exemple, si le mot &quot;Bob&quot; apparaît parfois dans le champ et que le mot &quot;BOB&quot; apparaît, il s’agit de deux personnes distinctes.


## Activer l’Analyse cross-canal

Une fois que votre organisation a satisfait à toutes les conditions préalables et comprend ses limites, vous pouvez suivre ces étapes pour commencer à lʼutiliser dans CJA.

1. Importez les données de votre choix dans Adobe Experience Platform. Voir [Création d’un schéma](https://docs.adobe.com/content/help/fr-FR/experience-platform/xdm/tutorials/create-schema-ui.html) et [Envoi de données](https://docs.adobe.com/content/help/fr-FR/experience-platform/ingestion/home.html) dans la documentation Adobe Experience Platform.
1. Contactez votre gestionnaire de compte Adobe qui comprend les éléments suivants :
   * Demande d’activation de l’Analyse cross-canal
   * Identifiant du jeu de données pour le jeu dont vous souhaitez recomposer les données
   * Nom de colonne de l’identifiant persistant du jeu de données souhaité (identifiant qui apparaît sur chaque ligne)
   * Nom de colonne de l’identifiant transitoire pour le jeu de données souhaité (lien d’identifiant de personne entre les jeux de données)
   * Votre préférence en matière de fréquence de [relecture](replay.md) et de durée de période de recherche arrière. Les options incluent une relecture une fois par semaine avec une période de recherche arrière de 7 jours ou une relecture chaque jour avec une période de recherche arrière de 1 jour.
1. Le gestionnaire de compte d’Adobe travaillera avec l’ingénierie des Adobes pour activer les analyses multiCanaux à la réception de votre demande. Une fois activé, un nouveau jeu de données avec nouvelle clé contenant une nouvelle colonne d’ID de personne s’affiche dans Adobe Experience Platform. Votre gestionnaire de compte Adobe peut fournir le nouvel identifiant de jeu de données et le nom de colonne de l’identifiant de personne.
1. Lorsque l’Adobe est activé pour la première fois, il fournit un renvoi de données assemblées qui remonte au début du mois précédent (jusqu’à 60 jours). Pour ce renvoi, l’ID transitoire doit exister dans les données désassemblées à ce moment-là.
1. [Créez une connexion](../create-connection.md) dans CJA à l’aide du jeu de données qui vient d’être généré et de tous les autres jeux de données que vous souhaitez inclure. Choisissez l’identifiant de personne approprié pour chaque jeu de données.
1. [Créez une vue de données](/help/data-views/create-dataview.md) basée sur la connexion.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Une fois la vue de données configurée, Analysis dans CJA est comme toute autre analyse dans CJA, sauf que les données opèrent désormais entre canaux et appareils.
