---
title: Affichage de l’utilisation
description: Mesurez l’engagement des utilisateurs au fil du temps.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Guided Analysis
keywords: analytics du produit
role: User
source-git-commit: 1d6a241766455a5da978b7e8401f1d7c0ba688d6
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 1%

---

# [!UICONTROL Utilisation] view

La variable **[!UICONTROL Utilisation]** La vue fournit des informations précieuses sur les performances de votre produit ou sur le comportement de vos utilisateurs au fil du temps. L’axe horizontal de ce rapport est un intervalle de temps, tandis que l’axe vertical mesure les événements de votre choix.

>[!VIDEO](https://video.tv.adobe.com/v/3421666/?learn=on)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Évaluation des performances du produit**: les tendances vous permettent d’évaluer les performances globales de votre produit au cours d’une période donnée. En analysant des mesures telles que l’engagement des utilisateurs, l’adoption ou les taux de conversion, vous pouvez déterminer si les performances de votre produit s’améliorent, stagnent ou déclinent.
* **Adoption des fonctionnalités**: les tendances vous permettent de comprendre comment les utilisateurs adoptent les nouvelles fonctionnalités ou mises à jour que vous publiez. Vous pouvez déterminer les fonctionnalités les plus populaires et celles qui nécessitent une amélioration. Ces informations vous permettent de prendre des décisions basées sur les données en fonction des fonctionnalités dont vous souhaitez hiérarchiser vos efforts de développement.
* **Comportement des utilisateurs**: les tendances peuvent fournir des informations sur le comportement des utilisateurs au fil du temps. En examinant les actions spécifiques que les utilisateurs effectuent, vous pouvez identifier les modèles dans lesquels les utilisateurs peuvent abandonner. Vous pouvez combiner les insights de cette vue avec [Friction](friction.md) pour plus d’informations sur le comportement.
* **Test A/B et expérimentation**: si vous exécutez des tests A/B dans votre produit, vous pouvez utiliser les tendances pour déterminer les tests les plus performants au fil du temps.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Événements et mesures]**: événements ou mesures à mesurer. Chaque sélection est représentée sous la forme d’une série de graphiques et d’une ligne de tableau. Les événements et les mesures ne peuvent pas être combinés dans la requête. Une fois votre première sélection effectuée, les sélections de requête restantes doivent être du même type. Vous pouvez inclure jusqu’à cinq sélections.
* **[!UICONTROL Compté comme]**: mesure que vous souhaitez mesurer. Les options incluent Événements, Sessions, Utilisateurs, Pourcentage d’utilisateurs, Événements par session et Événements par utilisateur. Les options Comptées comme ne s’appliquent qu’aux requêtes d’événement et sont supprimées pour les requêtes de mesure.
* **[!UICONTROL Segments]**: segments que vous souhaitez mesurer. Chaque segment sélectionné double le nombre de séries de graphiques et de lignes de tableau. Vous pouvez inclure jusqu’à cinq segments.
* **[!UICONTROL Propriété de ventilation]**: ventile la série de graphiques et les lignes du tableau en fonction des valeurs de la propriété sélectionnée. Une seule propriété de ventilation est prise en charge. Les 20 premières valeurs apparaissent dans le tableau et vous pouvez afficher jusqu’à dix valeurs dans le graphique. Vous pouvez masquer ou afficher une ligne du graphique en faisant basculer le ![Icône Afficher le masquage](../assets/hide-in-chart.png) Icône

## Paramètres du graphique

La variable [!UICONTROL Utilisation] La vue propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Type de graphique]**: type de visualisation que vous souhaitez utiliser. Les options disponibles sont Ligne, Barre, Barre empilée et Zone empilée.

## Chevauchements

Ajoutez des données additionnelles au graphique. Lorsque plusieurs séries sont visibles sur le graphique, les superpositions s’affichent uniquement lorsque vous survolez le graphique.

* **[!UICONTROL Détection des anomalies]**: exécutions [détection des anomalies](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) sur l’analyse des tendances. Les valeurs aberrantes apparaissent sous la forme de points que vous pouvez survoler avec la souris pour plus d’informations.
* **[!UICONTROL Superposition de tendance]**: ajoute une courbe de tendance au graphique, ce qui permet de représenter plus clairement un motif dans les données.
   * [!UICONTROL Linéaire]: crée une ligne de régression droite. Ce qui est préférable pour les données linéaires simples qui augmentent ou diminuent à un rythme régulier. Équation : `y = a + b * x`
   * [!UICONTROL Logarithmique]: crée une ligne de régression courbe. Ce qui est préférable pour les données qui augmentent ou diminuent rapidement, puis qui deviennent plus au niveau. Équation : `y = a + b * log(x)`
   * [!UICONTROL Moyenne glissante]: crée une courbe de tendance fluide basée sur un ensemble de moyennes. Connue également sous le nom de moyenne mobile, une moyenne glissante utilise un nombre spécifique de points de données précédents (déterminé par votre sélection), calcule leur moyenne et utilise la moyenne comme point dans la ligne. Par exemple, une moyenne mobile de sept jours ou de quatre semaines. Les options de moyenne glissante disponibles dépendent de l’intervalle et de la période sélectionnés.

## Comparaison de temps

{{apply-time-comparison}}

![Comparaison du temps d’utilisation](../assets/usage-compare.png)

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de tendances. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Une même période peut comporter des intervalles différents qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **[!UICONTROL Date]**: date de début et date de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
