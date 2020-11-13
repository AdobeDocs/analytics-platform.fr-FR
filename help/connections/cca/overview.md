---
title: Présentation d’Analytics sur plusieurs canaux
description: Recopier les identifiants de visiteur de plusieurs jeux de données pour regrouper les visiteurs.
translation-type: tm+mt
source-git-commit: b57895d037f8db3ffc418312b95fc43dd0280dc9
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 19%

---


# Présentation d’Analytics sur plusieurs canaux

**QI du voyage : L’** analyse entre canaux est une fonctionnalité qui vous permet de recréer l’identifiant personnel d’un jeu de données, ce qui permet une combinaison transparente de plusieurs jeux de données. Le CCA examine les données utilisateur des sessions authentifiées et non authentifiées afin de générer un identifiant assemblé. Grâce à Analytics sur plusieurs canaux, vous pouvez répondre à des questions telles que :

* Combien de personnes commencent leur expérience dans un canal, puis la terminent dans un autre ?
* Combien de personnes interagissent avec ma marque ? Combien de types de périphériques utilisent-elles ? Comment se superposent-elles ?
* À quelle fréquence les utilisateurs commencent-ils une tâche sur un périphérique mobile, puis passent-ils ensuite à un PC de bureau pour terminer la tâche ? Les clics publicitaires de campagne amenant à un périphérique conduisent-ils à une conversion ailleurs ?
* Comment ma compréhension de l’efficacité de la campagne change-t-elle si je prends en compte les trajets entre plusieurs périphériques ? Comment mon analyse d’entonnoir change-t-elle ?
* Quels sont les chemins les plus courants empruntés par les utilisateurs d’un périphérique à l’autre ? Où abandonnent-ils ? Où réussissent-ils ?
* En quoi le comportement des utilisateurs ayant plusieurs périphériques diffère-t-il de celui des utilisateurs disposant d’un seul périphérique ?

Lorsque vous combinez des jeux de données avec des identifiants de personne similaires, l’attribution est transférée sur plusieurs périphériques et canaux. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur rencontre un problème avec sa commande, puis envoie à votre équipe du service à la clientèle un appel pour l’aider à résoudre ce problème. Avec Analytics sur plusieurs canaux, vous pouvez attribuer des événements du centre d’appels à la publicité sur laquelle ils ont cliqué à l’origine.

## Conditions préalables

>[!IMPORTANT]
>
>Si vous ne remplissez pas toutes les conditions préalables, vous risquez d&#39;être incapable de créer une connexion à l&#39;ACC ou de ne pas obtenir de résultats satisfaisants lors de la combinaison de jeux de données.

Avant d’utiliser Analytics sur plusieurs canaux, veillez à ce que votre entreprise soit préparée avec les éléments suivants :

* Un jeu de données de Adobe Experience Platform doit comporter deux colonnes qui permettent d&#39;identifier les visiteurs :
   * ID **persistant**, identifiant présent sur chaque ligne. Par exemple, un ID de visiteur généré par une bibliothèque Adobe Analytics AppMeasurement.
   * Un **identifiant transitoire**, identifiant présent sur certaines lignes seulement. Par exemple, un nom d’utilisateur ou une adresse électronique haché une fois qu’un visiteur s’authentifie. Vous pouvez utiliser pratiquement n’importe quel identifiant, tant qu’il est présent au moins une fois sur le même événement qu’un identifiant persistant donné.
* Un autre jeu de données, tel que les données du centre d’appels, qui contient un identifiant transitoire sur chaque ligne. Cet ID de personne doit être formaté de la même manière que l’ID transitoire dans l’autre jeu de données.
* Cette fonctionnalité vous permet de réunir des jeux de données qui peuvent inclure la fusion de données utilisateur authentifiées et non authentifiées. Veillez à respecter les lois et réglementations en vigueur, y compris l&#39;obtention des autorisations d&#39;utilisateur final nécessaires, avant de fusionner des jeux de données.

## Limites

Analytics sur plusieurs canaux est une fonctionnalité innovante et robuste, mais son utilisation est limitée.

* Les capacités de saisie actuelles sont limitées à une étape (ID persistant à ID transitoire). Le référencement à plusieurs étapes (par exemple, un ID persistant à un ID transitoire, puis à un autre ID transitoire) n’est pas pris en charge.
* Seuls les jeux de données de événement sont pris en charge. D’autres jeux de données, tels que les jeux de données de recherche, ne sont pas pris en charge.
* Les mappages d’ID personnalisés utilisés dans votre organisation ne sont pas pris en charge.
* Le graphique Adobe Co-op et le graphique privé ne sont pas pris en charge.

## Activer les analyses entre canaux

Une fois que votre organisation a satisfait à toutes les conditions préalables et comprend ses limites, vous pouvez suivre ces étapes pour début en l’utilisant dans CJA.

1. Importez les données de votre choix dans Adobe Experience Platform. Voir [Création d’un schéma](https://docs.adobe.com/content/help/fr-FR/experience-platform/xdm/tutorials/create-schema-ui.html) et [Envoi de données](https://docs.adobe.com/content/help/fr-FR/experience-platform/ingestion/home.html) dans la documentation Adobe Experience Platform.
1. Contactez votre gestionnaire de compte d’Adobe qui comprend les éléments suivants :
   * Demande d’activation des analyses entre canaux
   * ID du jeu de données pour le jeu de données que vous souhaitez recadrer
   * Nom de colonne de l’identifiant persistant du jeu de données souhaité (identifiant qui apparaît sur chaque ligne).
   * Nom de colonne de l’ID transitoire pour le jeu de données souhaité (lien d’identificateur de personne entre les jeux de données)
   * Vous préférez la fréquence [replay](replay.md) et la longueur de recherche. Les options incluent une relecture une fois par semaine avec une fenêtre de recherche en amont de 7 jours ou une relecture chaque jour avec une fenêtre de recherche en amont de 1 jour.
1. Le gestionnaire de compte d’Adobe active les analyses inter-canaux à la réception de votre demande. Une fois activé, un nouveau jeu de données avec nouvelle clé apparaît dans Adobe Experience Platform et contient une nouvelle colonne d’identification de personne. Votre gestionnaire de compte d’Adobe peut fournir le nouvel ID de jeu de données et le nom de colonne de l’ID de personne.
1. [Créez une ](../create-connection.md) connexion dans CJA à l’aide du jeu de données nouvellement généré et de tous les autres jeux de données que vous souhaitez inclure. Choisissez l’ID de personne approprié pour chaque jeu de données.
1. [Créez une ](/help/data-views/create-dataview.md) vue de données basée sur la connexion.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Une fois la vue de données configurée, l&#39;Analyse dans la CJA est comme toute autre analyse dans la CJA, sauf maintenant que les données opèrent entre canaux et appareils.
