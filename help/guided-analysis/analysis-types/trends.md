---
title: Tendances
description: Découvrir les tendances et les changements au fil du temps concernant l‘interaction client.
source-git-commit: 37699a674a190aa2f28125d5b39bb3c27ac88551
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 2%

---

# Tendances

{{release-limited-testing}}

Le **Tendances** [Type d’analyse](overview.md) fournit des informations précieuses sur les performances de votre produit ou le comportement de vos utilisateurs au fil du temps. L’axe horizontal de ce rapport est toujours une granularité temporelle, tandis que l’axe vertical mesure les événements de votre choix. Voici quelques cas pratiques de ce type d’analyse :

* **Évaluation des performances du produit**: Les tendances vous permettent d’évaluer les performances globales de votre produit au cours d’une période donnée. En analysant des mesures telles que l’engagement des utilisateurs, les taux de conversion ou les recettes, vous pouvez déterminer si les performances de votre produit s’améliorent, stagnent ou déclinent.
* **Adoption des fonctionnalités**: Les tendances vous permettent de comprendre comment les utilisateurs adoptent les nouvelles fonctionnalités ou mises à jour que vous publiez. Vous pouvez déterminer les fonctionnalités les plus populaires et celles qui nécessitent une amélioration. Ces informations vous permettent de prendre des décisions basées sur les données en fonction des fonctionnalités dont vous souhaitez hiérarchiser vos efforts de développement.
* **Comportement des utilisateurs**: Les tendances peuvent fournir des informations sur le comportement des utilisateurs au fil du temps. En examinant les actions spécifiques que les utilisateurs effectuent, vous pouvez identifier les modèles dans lesquels les utilisateurs peuvent abandonner. Vous pouvez combiner les insights de ce type d’analyse avec une [Entonnoir](funnel.md) pour plus d’informations sur le comportement.
* **Test A/B et expérimentation**: Si vous exécutez des tests A/B dans votre produit, vous pouvez utiliser les tendances pour déterminer les tests les plus performants au fil du temps.

[Capture d&#39;écran des tendances]

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **Événements**: Événements que vous souhaitez mesurer dans votre rapport. Chaque événement sélectionné ici est représenté sous la forme d’une ligne ou d’un ensemble de barres colorées, selon le type de graphique. Une ligne représentant l’événement de tendance est ajoutée au tableau. Vous pouvez inclure jusqu’à cinq événements.
* **Personnes**: Segments que vous souhaitez mesurer dans votre rapport. Chaque segment sélectionné ici double le nombre de lignes du graphique et de lignes du tableau. Chaque ensemble d’événements est représenté pour chaque segment. Vous pouvez inclure jusqu’à cinq segments.

## Types d’affichage

Les tendances offrent les types d’affichage suivants. Vous pouvez modifier le type de vue à partir du menu déroulant situé en haut à gauche du graphique.

* **Utilisation :** Mesurez l’engagement des utilisateurs au fil du temps.

## Paramètres du graphique

Les tendances offrent les paramètres de graphique suivants. Vous pouvez ajuster les paramètres du graphique à l’aide du menu entre le type d’affichage et le sélecteur de calendrier.

* **Mesure**: Mesure que vous souhaitez mesurer. Les options incluent Événements, Sessions, Utilisateurs, Événements par session et Événements par utilisateur.
* **Type de graphique**: Type de visualisation que vous souhaitez utiliser. Les options disponibles sont Ligne, Barre, Barre empilée et Zone empilée.

## Appliquer la comparaison des temps

Les tendances permettent de comparer la période actuelle à une période précédente. Si vous sélectionnez une option dans ce menu, chaque ligne reçoit une ligne pointillée de la même couleur. Cette ligne pointillée représente la même mesure dans la période précédente sélectionnée. Cette option double le nombre de lignes du graphique et de lignes du tableau.

Les options de comparaison de temps disponibles comprennent la période précédente, 13 semaines précédentes, 52 semaines précédentes et une période personnalisée. Si vous sélectionnez Période personnalisée, d’autres options s’affichent pour vous permettre de sélectionner le nombre et la granularité. Si vous sélectionnez Aucun, la comparaison de dates est supprimée.

## Période

Définit la période souhaitée. Ce paramètre comporte deux composants importants :

* **Intervalle**: Granularité de la date dans laquelle vous souhaitez afficher les données. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Une même période peut comporter des intervalles différents qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **Date**: Les dates de début et de fin. Des paramètres prédéfinis de période sont disponibles à des fins pratiques ou vous pouvez utiliser le sélecteur de calendrier pour définir la date exacte de votre choix.
