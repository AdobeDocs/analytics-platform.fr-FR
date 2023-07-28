---
title: Élément de dimension Traités des résultats
description: Explique l’élément de dimension "Résultats tronqués" et pourquoi il apparaît dans les rapports.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: f0fa126a23e6c99f89db82c91c98b6628d43a983
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 12%

---

# Élément de dimension Traités des résultats

Lors de l’utilisation d’une dimension qui contient de nombreuses valeurs uniques, les résultats du rapport peuvent être trop volumineux pour être traités.  Pour éviter des ralentissements dans l’ensemble du système, les résultats sont tronqués en supprimant les éléments jugés les moins importants.  Cela est indiqué sur un panneau à structure libre en ajoutant les mots &quot;plus que&quot; dans l’indicateur de pagination, par exemple &quot;Lignes : 1 à 400 de plus de 9 819 653&quot;.

Dans certains cas, comme le tri par une mesure calculée, il est impossible de déterminer les éléments de dimension les plus importants.  Dans ce cas, une icône d’avertissement est placée sur la mesure calculée expliquant ce problème et la liaison à [documentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/dimensions/high-cardinality.html?lang=en).

## Architecture de traitement des Customer Journey Analytics et valeurs uniques

Customer Journey Analytics traite les rapports au moment de leur exécution, en distribuant le jeu de données combiné à plusieurs serveurs. Les données dans chaque serveur de traitement sont regroupées par ID de personne, ce qui signifie qu’un seul serveur de traitement contient toutes les données concernant une personne spécifique. Une fois le traitement terminé, le serveur transmet son sous-ensemble de données traitées à un serveur d’agrégation. Tous les sous-ensembles de données traitées sont combinés et renvoyés sous la forme d’un rapport d’espace de travail.

Si un serveur individuel agrège un jeu de résultats qui dépasse un seuil de taille, il tronque les résultats avant de les renvoyer. Cette optimisation limite le trafic réseau et l’agrégation pour permettre des rapports rapides. Comme chaque serveur de traitement tronque les résultats avec uniquement la vue de ses propres données, il est possible que les éléments affichés dans Analysis Workspace aient des valeurs de mesure légèrement décalées.

Le serveur choisit les éléments de dimension à ignorer en fonction de la mesure utilisée pour le tri. Si la mesure de tri est une mesure calculée, le serveur utilise les mesures de la mesure calculée pour déterminer les éléments de dimension à tronquer. Les mesures calculées peuvent contenir plusieurs mesures d’une importance variable. Par conséquent, les résultats peuvent être moins précis. Par exemple, lors du calcul de &quot;Recettes par personne&quot;, le montant total des recettes et le nombre total de personnes sont renvoyés et regroupés avant d’effectuer la division. Par conséquent, chaque noeud choisit les éléments à supprimer sans savoir comment leurs résultats affectent le tri global.

## Différences avec &quot;Faible trafic&quot;

Dans les versions précédentes d’Adobe Analytics, une architecture de traitement différente était utilisée. Les données ont été traitées au moment de leur collecte. Les éléments de Dimension ont été placés sous &quot;Faible trafic&quot; après qu’une dimension ait atteint 500 000 valeurs uniques et qu’un filtrage plus agressif a été appliqué à un million de valeurs uniques. Le nombre de &quot;valeurs uniques&quot; a été réinitialisé au début de chaque mois calendaire. Les données traitées étaient permanentes, il n’y avait aucun moyen de retirer les données existantes de « Faible trafic ».

En Customer Journey Analytics, les éléments de dimension ne sont tronqués que si les résultats d’un rapport sont trop volumineux. Les données traitées ne sont pas permanentes, ce qui signifie que vous pouvez réduire ou éliminer la troncature en modifiant votre rapport.

## Réduction de l’élément de dimension &quot;Résultats tronqués&quot;

Si vous souhaitez réduire le nombre d’événements dans l’élément de dimension &quot;Résultats tronqués&quot;, Adobe recommande l’un des éléments suivants :

* Utilisez une [Filtrer](/help/components/filters/create-filters.md). Les filtres s’appliquent au moment où chaque serveur traite un sous-ensemble de données. La limitation du nombre de valeurs uniques renvoyées réduit l’élément de dimension &quot;Résultats tronqués&quot;.
* Utilisez une recherche. Si une recherche est utilisée, les éléments qui ne correspondent pas à la recherche sont supprimés des résultats du rapport, ce qui rend plus probable l’affichage des éléments de votre choix.
* Utilisez une dimension du jeu de données de recherche. Les dimensions des jeux de données de recherche combinent les éléments de dimension des jeux de données d’événement, ce qui limite le nombre de valeurs uniques retournées.
