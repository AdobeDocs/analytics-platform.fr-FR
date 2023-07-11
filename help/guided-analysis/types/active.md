---
title: Actif
description: Mesurer la croissance de la base d’utilisateurs et utilisatrices de votre produit.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
source-git-commit: 14c7aa342649afbe9923b0086947e5a0adeefff2
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 2%

---

# Actif

{{release-limited-testing}}

Le **Principal** type d’affichage fournit des informations sur la croissance et l’acquisition des utilisateurs au cours d’une période spécifique. L’axe horizontal est toujours une granularité temporelle, tandis que l’axe vertical est toujours une mesure des utilisateurs. Les utilisateurs sont analysés depuis le début de la période, répartis en quatre catégories :

* **Nouveau**: L’utilisateur était principal pendant le point de données actuel et n’a pas été affiché dans les points de données précédents. Survoler avec le curseur[!UICONTROL Nouveaux utilisateurs]&quot; dans la légende du graphique pour voir jusqu’où le rapport revient pour déterminer un nouvel utilisateur. Cette date est sélectionnée dynamiquement en fonction de la longueur et de la granularité de la période.
* **Répéter**: L’utilisateur apparaissait dans le point de données précédent immédiatement et dans le point de données actif.
* **Retour**: L’utilisateur n’apparaissait pas dans le point de données précédent immédiatement, mais n’est pas un nouvel utilisateur.
* **Dormant**: L’utilisateur n’apparaissait pas dans le point de données actif, mais dans le point de données précédent immédiatement. Les utilisateurs inactifs ne sont pas pris en compte dans le nombre total d’utilisateurs principaux.

Tous les utilisateurs principaux (nouveaux + répétition + retour) apparaissent sous la forme d’une nuance de teint au-dessus de l’axe horizontal, tandis que tous les utilisateurs inactifs apparaissent en orange sous l’axe horizontal.

Les cas d’utilisation de ce type de vue sont les suivants :

* **Rétention et perte de clientèle :** Fournit une visualisation claire des périodes de forte ou faible rétention des utilisateurs. La reconnaissance de ces périodes de rétention élevée ou faible peut vous aider à prendre des décisions sur les produits pour encourager la rétention élevée ou contribuer à réduire l’attrition.
* **Évaluation des campagnes**: L’affichage d’une campagne spécifique peut vous aider à comprendre non seulement le volume de trafic généré, mais également la manière dont la campagne a aidé les utilisateurs à rester engagés.
* **Analyse du cycle de vie des utilisateurs**: L’analyse de la principale croissance des utilisateurs tout au long du cycle de vie de l’utilisateur peut aider à identifier les étapes spécifiques où l’engagement de l’utilisateur diminue. Par exemple, s’il existe un taux élevé d’utilisateurs inactifs dans une phase d’intégration, cela peut indiquer des problèmes de convivialité ou la nécessité d’une meilleure orientation intégrée au produit.

[Capture d’écran de la croissance des utilisateurs]

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **Événements**: L’événement que vous souhaitez mesurer. Ce type d’affichage étant basé sur l’utilisateur, l’utilisateur peut toucher l’événement une seule fois dans la granularité de date définie pour être compté en tant qu’utilisateur principal. Vous ne pouvez inclure qu’un seul événement dans une requête.
* **Personnes**: Le segment que vous souhaitez mesurer. Vous ne pouvez inclure qu’un seul segment dans une requête.

## Paramètres du graphique

Ce type de vue propose les paramètres de graphique suivants. Vous pouvez ajuster les paramètres du graphique à l’aide du menu entre le type d’affichage et le sélecteur de calendrier.

* **Mesure**: Mesure que vous souhaitez mesurer. Les options disponibles sont Nombre d’utilisateurs et Pourcentage d’utilisateurs.
* **Type de graphique**: Type de visualisation que vous souhaitez utiliser. Les options disponibles sont Barre empilée et Zone empilée.

## Appliquer la comparaison des temps

{{apply-time-comparison}}

## Période

Période souhaitée. Ce paramètre comporte deux composants importants :

* **Intervalle**: Granularité de la date dans laquelle vous souhaitez afficher les données. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Une même période peut comporter des intervalles différents qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **Date**: Les dates de début et de fin. Des paramètres prédéfinis de période sont disponibles à des fins pratiques ou vous pouvez utiliser le sélecteur de calendrier pour définir la date exacte de votre choix.
