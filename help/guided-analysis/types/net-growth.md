---
title: Croissance nette
description: Gains et pertes de l’utilisateur du solde.
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 2%

---

# Croissance nette

{{release-limited-testing}}

Le **Croissance nette** type d’affichage fournit des informations sur le taux auquel vous acquérez ou perdez des utilisateurs au cours d’une période spécifique. L’axe horizontal est toujours une granularité temporelle, tandis que l’axe vertical est toujours la mesure de la croissance.

Chaque point de données représente la croissance nette de ce point de données, qui est calculée à l’aide de la formule suivante :

`([New users] + [Return users]) / [Dormant users]`

Semblable au [Principal](active.md) type d’affichage, les utilisateurs sont définis comme suit :

* **Nouveau**: L’utilisateur était principal pendant le point de données actuel et n’a pas été affiché dans les points de données précédents.
* **Retour**: L’utilisateur n’apparaissait pas dans le point de données précédent immédiatement, mais n’est pas un nouvel utilisateur.
* **Dormant**: L’utilisateur n’apparaissait pas dans le point de données actif, mais dans le point de données précédent immédiatement. Les utilisateurs inactifs ne sont pas pris en compte dans le nombre total d’utilisateurs principaux.

**Répéter** Les utilisateurs ne sont pas pris en compte dans ce calcul, car ils ne représentent aucune croissance ni perte.

Le résultat de cette formule est un ratio auquel votre base d’utilisateurs a augmenté ou diminué au cours de ce point de données. Une croissance nette de `1` représente un égal; le produit a obtenu le même nombre d’utilisateurs qu’il a perdu. Une croissance nette supérieure à `1` représente une croissance positive; il y avait plus d’utilisateurs nouveaux/récurrents que d’utilisateurs inactifs. De même, une croissance nette inférieure à `1` représente une perte d’utilisateurs principaux ; il y avait plus d’utilisateurs inactifs que d’utilisateurs nouveaux/récurrents.

Les cas d’utilisation de ce type de vue sont les suivants :

* **Analyse des acquisitions d’utilisateurs**: Permet d’évaluer l’efficacité de vos stratégies d’acquisition d’utilisateurs. L’analyse des sources de croissance des utilisateurs, telles que les moteurs de recherche, les campagnes ou d’autres canaux marketing, vous permet d’identifier les sources de croissance les plus significatives afin que vous puissiez allouer les ressources en conséquence.
* **Évaluation des performances**: Permet d’évaluer les performances globales de votre produit en termes d’acquisition de nouveaux utilisateurs. En suivant les tendances de croissance, vous pouvez mieux comprendre si votre produit attire et conserve les utilisateurs à un rythme souhaité.
* **Analyse de la perte de clientèle**: La croissance nette inclut l&#39;attrition dans sa formule (les utilisateurs inactifs). Vous pouvez évaluer l’intégrité globale de votre base d’utilisateurs au fil du temps. Si la croissance nette est constamment inférieure `1`, il indique un taux d’attrition élevé, ce qui vous invite à étudier les raisons de ce phénomène et à mettre en oeuvre des stratégies de rétention.

![Croissance nette](../assets/net-growth.png)

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **Événements**: L’événement que vous souhaitez mesurer. Comme ce type d’affichage est basé sur l’utilisateur, l’utilisateur peut toucher l’événement une seule fois dans la granularité de date définie afin de bénéficier de la croissance nette. Vous ne pouvez inclure qu’un seul événement dans une requête.
* **Personnes**: Le segment que vous souhaitez mesurer. Vous ne pouvez inclure qu’un seul segment dans une requête.

## Période

Période souhaitée. Ce paramètre comporte deux composants importants :

* **Intervalle**: Granularité de la date dans laquelle vous souhaitez afficher les données. Les options valides sont Quotidienne, Hebdomadaire, Mensuelle et Trimestrielle. Une même période peut comporter des intervalles différents qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **Date**: Les dates de début et de fin. Des paramètres prédéfinis de période sont disponibles à des fins pratiques ou vous pouvez utiliser le sélecteur de calendrier pour définir la date exacte de votre choix.
