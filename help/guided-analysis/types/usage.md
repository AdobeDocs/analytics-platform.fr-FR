---
title: Utilisation
description: Mesurer l’interaction client au fil du temps.
exl-id: 1d103bd3-3e72-4c82-a534-c896f8433029
feature: Guided Analysis
source-git-commit: 81fe48ba9bdafa73e1bcd02e4016a2efa68ce1d1
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 3%

---

# Utilisation

{{release-limited-testing}}

Le **Utilisation** La vue fournit des informations précieuses sur les performances de votre produit ou le comportement de vos utilisateurs au fil du temps. L’axe horizontal de ce rapport est un intervalle de temps, tandis que l’axe vertical mesure les événements de votre choix. Les cas d’utilisation de ce type de vue sont les suivants :

* **Évaluation des performances du produit**: Les tendances vous permettent d’évaluer les performances globales de votre produit au cours d’une période donnée. En analysant des mesures telles que l’engagement des utilisateurs, l’adoption ou les taux de conversion, vous pouvez déterminer si les performances de votre produit s’améliorent, stagnent ou déclinent.
* **Adoption des fonctionnalités**: Les tendances vous permettent de comprendre comment les utilisateurs adoptent les nouvelles fonctionnalités ou mises à jour que vous publiez. Vous pouvez déterminer les fonctionnalités les plus populaires et celles qui nécessitent une amélioration. Ces informations vous permettent de prendre des décisions basées sur les données en fonction des fonctionnalités dont vous souhaitez hiérarchiser vos efforts de développement.
* **Comportement des utilisateurs**: Les tendances peuvent fournir des informations sur le comportement des utilisateurs au fil du temps. En examinant les actions spécifiques que les utilisateurs effectuent, vous pouvez identifier les modèles dans lesquels les utilisateurs peuvent abandonner. Vous pouvez combiner les insights de cette vue avec [Friction](friction.md) pour plus d’informations sur le comportement.
* **Test A/B et expérimentation**: Si vous exécutez des tests A/B dans votre produit, vous pouvez utiliser les tendances pour déterminer les tests les plus performants au fil du temps.

![Utilisation](../assets/usage.png)

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **Événements**: Événements que vous souhaitez mesurer. Chaque événement sélectionné est représenté sous la forme d’une ligne ou d’un ensemble de barres colorées, selon le type de graphique. Une ligne représentant l’événement de tendance est ajoutée au tableau. Vous pouvez inclure jusqu’à cinq événements.
* **Personnes**: Les segments que vous souhaitez mesurer. Chaque segment sélectionné double le nombre de lignes du graphique et de lignes du tableau. Vous pouvez inclure jusqu’à cinq segments.

## Paramètres du graphique

La vue Utilisation propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **Mesure**: Mesure que vous souhaitez mesurer. Les options incluent Événements, Sessions, Utilisateurs, Événements par session et Événements par utilisateur.
* **Type de graphique**: Type de visualisation que vous souhaitez utiliser. Les options disponibles sont Ligne, Barre, Barre empilée et Zone empilée.

## Appliquer la comparaison des temps

{{apply-time-comparison}}

![Comparaison du temps d’utilisation](../assets/usage-compare.png)

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **Intervalle**: Granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Une même période peut comporter des intervalles différents qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **Date**: Les dates de début et de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.