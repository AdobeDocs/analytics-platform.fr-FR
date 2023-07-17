---
title: Vue de la croissance nette
description: Êtes-vous en train de gagner ou de perdre des utilisateurs et utilisatrices ?
feature: Guided Analysis
source-git-commit: 2b1e0ce53016634e0cb32f9256fa48e02f2a5323
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 1%

---

# Vue de la croissance nette

Le **Croissance nette** type d’affichage fournit des informations sur le taux auquel vous gagnez ou perdez des utilisateurs au cours d’une période spécifique. L’axe horizontal est un intervalle de temps, tandis que l’axe vertical est la mesure de la croissance.

Chaque point de données représente la croissance nette, qui est calculée à l’aide de la formule suivante :

`([New users] + [Return users]) / [Dormant users]`

Le résultat de cette formule est un ratio. Une croissance nette de `1` représente un équilibre; le produit a obtenu le même nombre d’utilisateurs qu’il a perdu. Une croissance nette supérieure à `1` représente une croissance positive; il y avait plus d’utilisateurs + récurrents que d’utilisateurs inactifs. De même, une croissance nette inférieure à `1` représente une perte; il y avait plus d’utilisateurs inactifs que de nouveaux utilisateurs + réguliers.

Semblable au [Principal](active.md) type d’affichage, les utilisateurs sont définis comme suit :

* **Nouveau**: L’utilisateur était principal pendant la période actuelle, mais pas auparavant. Découvrez jusqu’où l’analyse revient pour déterminer un nouvel utilisateur en pointant la souris sur &quot;[!UICONTROL Nouveaux utilisateurs]&quot; dans la légende du graphique. La période de recherche arrière est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **Retour**: L’utilisateur était principal dans la période actuelle et non principal dans la période précédente immédiatement, mais auparavant principal à un moment donné. Découvrez jusqu’où l’analyse revient pour déterminer un utilisateur récurrent en pointant la souris sur &quot;[!UICONTROL Utilisateurs récurrents]&quot; dans la légende du graphique. La période de recherche arrière est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **Dormant**: L’utilisateur était principal dans la période précédente immédiatement, mais n’est pas principal dans la période actuelle. Les utilisateurs inactifs ne sont pas pris en compte dans le nombre total d’utilisateurs principaux.
* Remarque : Les utilisateurs réguliers ne sont pas pris en compte dans ce calcul, car ils ne représentent aucun gain ni perte pour les utilisateurs.

![Croissance nette](../assets/net-growth.png)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Évaluation des performances**: Permet d’évaluer les performances globales de votre produit en termes d’acquisition de nouveaux utilisateurs. En suivant les tendances de croissance, vous pouvez mieux comprendre si votre produit attire et conserve les utilisateurs à un rythme souhaité.
* **Analyse des acquisitions d’utilisateurs**: Permet d’évaluer l’efficacité de vos stratégies d’acquisition d’utilisateurs. L’analyse des sources de croissance des utilisateurs, telles que les moteurs de recherche, les campagnes ou d’autres canaux marketing, vous permet d’identifier les sources de croissance les plus significatives afin que vous puissiez allouer les ressources en conséquence.
* **Analyse de la perte de clientèle**: La croissance nette inclut l&#39;attrition dans sa formule (utilisateurs inactifs). Vous pouvez évaluer l’intégrité globale de votre base d’utilisateurs au fil du temps. Si la croissance nette est constamment inférieure `1`, cela indique une forte attrition qui pourrait inciter à mettre en oeuvre des stratégies de rétention.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **Événements**: L’événement que vous souhaitez mesurer. Ce type de vue étant basé sur l’utilisateur, un utilisateur qui interagit avec l’événement une fois au cours de la période est comptabilisé comme un utilisateur principal. Vous pouvez inclure un événement dans une requête.
* **Personnes**: Le segment que vous souhaitez mesurer. Vous pouvez inclure un segment dans une requête.

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **Intervalle**: Granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Une même période peut comporter des intervalles différents qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **Date**: Les dates de début et de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
