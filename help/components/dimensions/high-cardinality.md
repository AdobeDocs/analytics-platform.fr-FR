---
title: Dimensions de cardinalité élevée
description: Explique comment Customer Journey Analytics gère les dimensions avec de nombreuses valeurs uniques.
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 6%

---

# Dimensions de cardinalité élevée

Lors de l’utilisation d’une dimension qui contient de nombreuses valeurs uniques, le rapport résultant peut contenir trop d’éléments de dimension uniques à afficher ou à calculer. Les résultats sont tronqués en supprimant les éléments de dimension considérés comme les moins importants. Ces optimisations sont effectuées pour maintenir les performances du projet et du produit.

Lorsque vous demandez un rapport avec trop de valeurs uniques, Analysis Workspace affiche un indicateur dans l’en-tête de dimension indiquant que tous les éléments de dimension ne sont pas inclus. Par exemple, **[!UICONTROL Lignes : 1 à 50 de plus de 22 343 156]**. Le mot-clé **[!UICONTROL more than]** indique qu’une certaine optimisation a été appliquée au rapport pour renvoyer les éléments de dimension les plus importants.

![Tableau à structure libre dans Workspace présentant le mot-clé &quot;plus que&quot; pour afficher 1 à 50 de plus de 22 343 156](assets/high-cardinality.png)

## Détermination des éléments de dimension à afficher

Customer Journey Analytics traite les rapports au moment de leur exécution, en distribuant le jeu de données combiné à plusieurs serveurs. Les données par serveur de traitement sont regroupées par ID de personne, ce qui signifie qu’un seul serveur de traitement contient toutes les données pour une personne donnée. Une fois le traitement terminé, un serveur transmet son sous-ensemble de données traitées à un serveur d’agrégation. Tous les sous-ensembles de données traitées sont combinés et renvoyés sous la forme d’un rapport d’espace de travail.

Si un serveur individuel traite des données qui dépassent un seuil unique, il tronque les résultats avant de renvoyer le sous-ensemble de données traité. Les éléments de dimension tronqués sont déterminés en fonction de la mesure utilisée pour le tri.

Si la mesure de tri est une mesure calculée, le serveur utilise les mesures de la mesure calculée pour déterminer les éléments de dimension à tronquer. Les mesures calculées peuvent contenir plusieurs mesures d’une importance variable. Par conséquent, les résultats peuvent être moins précis. Par exemple, lors du calcul de &quot;Recettes par personne&quot;, le montant total des recettes et le nombre total de personnes sont renvoyés et regroupés avant d’effectuer la division. Par conséquent, chaque serveur de traitement individuel choisit les éléments à supprimer sans savoir comment leurs résultats affectent le tri global.

Bien que certains éléments de dimension individuels puissent ne pas figurer dans les rapports de cardinalité élevée, les totaux des colonnes sont exacts et non basés sur des données tronquées. La fonction &quot;Comptage distinct&quot; dans les mesures calculées n’est pas non plus affectée par les éléments de dimension tronqués.

## Bonnes pratiques relatives aux dimensions à forte cardinalité

La meilleure façon d’adapter les dimensions de cardinalité élevée consiste à limiter le nombre d’éléments de dimension traités par un rapport. Comme tous les rapports sont traités au moment où ils sont demandés, vous pouvez ajuster les paramètres des rapports pour obtenir des résultats immédiats. Adobe recommande l’une des optimisations suivantes pour les dimensions à cardinalité élevée :

* Utilisez un [filtre](/help/components/filters/create-filters.md). Les filtres s’appliquent au moment où chaque serveur traite un sous-ensemble de données.
* Utilisez une recherche. Les éléments de Dimension exclus du terme de recherche sont supprimés des résultats du rapport, ce qui rend plus probable l’affichage des éléments de dimension souhaités.
* Utilisez une dimension du jeu de données de recherche. Les dimensions des jeux de données de recherche combinent les éléments de dimension des jeux de données d’événement, ce qui limite le nombre de valeurs uniques retournées.
* Utilisez le paramètre de composant [Include/exclude](/help/data-views/component-settings/include-exclude-values.md) dans le gestionnaire de vues de données.
* Raccourcissez la période de la requête. Si de nombreuses valeurs uniques s’accumulent au fil du temps, le raccourcissement de la période du rapport Workspace peut limiter le nombre de valeurs uniques que les serveurs à traiter.
* Pensez à utiliser [l’exportation de table complète](/help/analysis-workspace/export/export-cloud.md) pour renvoyer toutes les lignes de la table.
