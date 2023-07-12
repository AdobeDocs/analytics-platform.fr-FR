---
title: Tendances de conversion
description: Effectuez le suivi des modifications du taux de conversion au fil du temps.
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 2%

---

# Tendances de conversion

{{release-limited-testing}}

Le **Tendances de conversion** le type d’affichage fournit une visualisation de tendance des taux de conversion au fil du temps. L’axe horizontal est toujours une granularité de date, tandis que l’axe vertical représente le taux de conversion. Utilisation de ce type de vue conjointement avec [Friction](friction.md) vous permet d’établir et d’affiner l’entonnoir souhaité. Vous pouvez ensuite utiliser ce type de vue pour afficher les taux de conversion de cet entonnoir au fil du temps. Les cas d’utilisation de ce type de vue sont les suivants :

* **Suivi des efforts d’optimisation**: Après avoir identifié les goulets d’étranglement clés que vous souhaitez améliorer à l’aide de [Friction](friction.md), vous pouvez utiliser ce type de vue pour suivre l’impact de ces optimisations sur le taux de conversion au fil du temps.
* **Évaluation des tests A/B**: Évaluer l’efficacité des tests A/B ou des expériences menées dans le contexte d’un entonnoir. En comparant les taux de conversion entre différentes variations, vous pouvez facilement déterminer les tests qui génèrent des taux de conversion plus élevés, ce qui entraîne des décisions basées sur les données autour des variations à mettre en oeuvre de manière permanente.
* **Évaluation de campagnes dans le temps**: Mesurez l’efficacité des campagnes marketing au fil du temps. Vous pouvez créer un segment qui se concentre sur les utilisateurs qui ont touché une campagne donnée et comparer leurs taux de conversion à d’autres campagnes. Vous pouvez également comparer les taux de conversion actuels à des campagnes similaires qui ont été exécutées dans le passé.

![Tendances de conversion](../assets/conversion-trends.png)

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **Étapes**: Points de contact de l’événement dont vous souhaitez effectuer le suivi. Chaque barre du graphique représente une étape. Vous pouvez inclure jusqu’à dix étapes.
* **Personnes**: Les segments que vous souhaitez comparer à l’entonnoir. Chaque segment sélectionné divise chaque étape en plusieurs barres. Chaque couleur représente un segment différent. Vous pouvez inclure jusqu’à trois segments.

## Paramètres du graphique

L’entonnoir propose les paramètres de graphique suivants. Vous pouvez ajuster les paramètres du graphique à l’aide du menu entre le type d’affichage et le sélecteur de calendrier.

* **Mesure**: Mesure que vous souhaitez mesurer. Les options incluent Sessions et Utilisateurs.
* **Type de graphique**: Type de visualisation que vous souhaitez utiliser. La seule option est Ligne.
* **Conversion à partir de**: Détermine le calcul du pourcentage d’une étape à l’autre. Les options incluent le calcul de la conversion à partir de la première étape ou de l’étape précédente.

## Appliquer la comparaison des temps

{{apply-time-comparison}}

![Comparaison des tendances de conversion](../assets/conversion-trends-compare.png)

## Période

Période souhaitée. Ce paramètre comporte deux composants importants :

* **Intervalle**: Granularité de la date dans laquelle vous souhaitez afficher les données. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Une même période peut comporter des intervalles différents qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **Date**: Les dates de début et de fin. Des paramètres prédéfinis de période sont disponibles à des fins pratiques ou vous pouvez utiliser le sélecteur de calendrier pour définir la date exacte de votre choix.
