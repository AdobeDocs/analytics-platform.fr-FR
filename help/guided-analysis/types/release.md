---
title: Version
description: Comparer les performances sur des périodes égales avant et après le lancement.
feature: Guided Analysis
source-git-commit: aca4a5091c65d7243f79551be7cee615ba98bb26
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 4%

---

# Version

{{release-limited-testing}}

Le **Version** La vue présente une comparaison des performances des indicateurs clés avant et après une date donnée. L’axe horizontal de ce rapport est un intervalle de temps, tandis que l’axe vertical mesure les indicateurs clés souhaités. Une barre verticale au milieu du graphique représente la date que vous souhaitez comparer avant et après. Cette date représente généralement une modification notable du produit par rapport auquel vous souhaitez effectuer une mesure, telle qu’une mise à jour du produit ou un lancement de campagne.

![Version](../assets/release.png)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Évaluation globale des performances :** La comparaison d’indicateurs clés globaux, tels que les recettes, peut vous aider à déterminer si une version donnée a globalement réussi.
* **Adoption des fonctionnalités**: Si une mise à jour de produit est axée sur l’amélioration d’une certaine fonctionnalité, vous pouvez utiliser cette vue pour comparer directement l’utilisation de cette fonctionnalité avant et après la mise à jour du produit.
* **Détection des bogues**: Le suivi du nombre d’erreurs avant et après une version peut fournir un indicateur précoce des problèmes des clients. Si vous constatez une augmentation des erreurs immédiatement après une version, vous pouvez collaborer avec les équipes d’ingénierie ou de développement pour identifier et corriger le problème, afin d’éviter tout impact supplémentaire sur les clients.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **Indicateurs clés**: Événements que vous souhaitez mesurer par utilisateur. Chaque indicateur de clé sélectionné est représenté sous la forme d’une ligne colorée. Une ligne représentant l’événement est ajoutée au tableau. Vous pouvez inclure jusqu’à trois événements.
* **Facteurs**: Date que vous souhaitez comparer avant et après.
* **Personnes**: Le segment que vous souhaitez mesurer. Le segment sélectionné filtre vos données afin de se concentrer uniquement sur les individus qui correspondent à vos critères de segment.

## Paramètres du graphique

La vue Version propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **Mesure**: Mesure que vous souhaitez mesurer. Les options incluent [!UICONTROL Événements par utilisateur], [!UICONTROL Pourcentage d&#39;utilisateurs], [!UICONTROL Événements], [!UICONTROL Sessions], et [!UICONTROL Utilisateurs].
* **Type de graphique**: Type de visualisation que vous souhaitez utiliser. Les options comprennent Ligne.

## Période

La sélection des dates dans les rapports d’impact fonctionne différemment des autres types d’analyse, puisque le rapport se base sur la date spécifiée dans le rail de requête. Les options disponibles sont les suivantes :

* **Intervalle**: Granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont les suivantes : [!UICONTROL Quotidien], [!UICONTROL Hebdomadaire], [!UICONTROL Mensuel], et [!UICONTROL Trimestriel]. La modification de l’intervalle affecte les options disponibles pour les périodes Avant et Après.
* **Avant et après la période**: La durée d’analyse avant et après la date spécifiée dans le rail de requête. Les options disponibles dépendent de la variable [!UICONTROL Intervalle] sélection.
