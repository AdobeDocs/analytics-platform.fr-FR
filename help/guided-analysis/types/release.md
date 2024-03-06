---
title: Version
description: Comparez les performances sur des périodes égales avant et après le lancement.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: 240a17923b55479865affaafb098b56e32d083a3
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# [!UICONTROL Version] view

La variable **[!UICONTROL Version]** La vue présente une comparaison des performances des indicateurs clés avant et après une date donnée. L’axe horizontal de ce rapport est un intervalle de temps, tandis que l’axe vertical mesure les indicateurs clés souhaités. Une barre verticale au milieu du graphique représente la date que vous souhaitez comparer avant et après. Cette date représente généralement une modification notable du produit par rapport auquel vous souhaitez effectuer une mesure, telle qu’une mise à jour du produit ou un lancement de campagne.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?learn=on)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Évaluation globale des performances :** La comparaison d’indicateurs clés globaux, tels que les mesures d’engagement, peut vous aider à déterminer si une version donnée a globalement réussi.
* **Surveillance**: effectuez le suivi des mesures essentielles que vous prévoyez de rester inchangées lorsque des modifications sont apportées, telles que le temps de chargement ou le nombre de connexions. Utilisez ce type d’analyse pour les comparer avant et après une version afin de vous assurer qu’elles n’ont pas eu de conséquences inattendues.
* **Adoption des fonctionnalités**: si une mise à jour de produit est axée sur l’amélioration d’une certaine fonctionnalité, vous pouvez utiliser cette vue pour comparer directement l’utilisation de cette fonctionnalité avant et après la mise à jour du produit.
* **Détection des bogues**: le suivi du nombre d’erreurs avant et après une version peut fournir un indicateur précoce des problèmes des clients. Si vous constatez une augmentation des erreurs immédiatement après une version, vous pouvez collaborer avec les équipes d’ingénierie ou de développement pour identifier et corriger le problème, afin d’éviter tout impact supplémentaire sur les clients.

## Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Affichage]**: basculez entre ce type de vue et [Première utilisation](first-use.md).
* **[!UICONTROL Indicateurs clés]**: événements que vous souhaitez mesurer par utilisateur. Chaque indicateur de clé sélectionné est représenté sous la forme d’une ligne colorée. Une ligne représentant l’événement est ajoutée au tableau. Vous pouvez inclure jusqu’à trois événements.
* **[!UICONTROL Compté comme]**: méthode de comptage à appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Événements par utilisateur], [!UICONTROL Pourcentage d&#39;utilisateurs], [!UICONTROL Événements], [!UICONTROL Sessions], et [!UICONTROL Utilisateurs].
* **[!UICONTROL Facteurs]**: date que vous souhaitez comparer avant et après.
* **[!UICONTROL Segments]**: segment que vous souhaitez mesurer. Le segment sélectionné filtre vos données afin de se concentrer uniquement sur les individus qui correspondent à vos critères de segment.

## Paramètres du graphique

La vue Version propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Type de graphique]**: type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Ligne] et [!UICONTROL Barre].

## Période

La sélection des dates dans l’analyse d’impact fonctionne différemment des autres types d’analyse, puisque le rapport se base sur la date spécifiée dans le rail de requête. Les options disponibles sont les suivantes :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de tendances. Les options valides incluent : [!UICONTROL Qualité], [!UICONTROL Hebdomadaire], [!UICONTROL Mensuel], et [!UICONTROL Trimestriel]. La modification de l’intervalle affecte les options disponibles pour les périodes Avant et Après.
* **[!UICONTROL Avant et après la période]**: délai à analyser avant et après la date spécifiée dans le rail de requête. Les options disponibles dépendent du [!UICONTROL Intervalle] sélection.
