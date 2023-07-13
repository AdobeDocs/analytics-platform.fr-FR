---
title: Élément de dimension Traduit par les résultats
description: Explique l’élément de dimension "Résultats tronqués" et pourquoi il apparaît dans les rapports.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: cf3c451cbefa7d6f9d5ea326c69fc2e5944881ff
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 13%

---

# Élément de dimension Traduit par les résultats

Lors de l’utilisation d’une dimension qui contient de nombreuses valeurs uniques, un rapport peut renvoyer un élément de dimension intitulé **[!UICONTROL Résultats tronqués]**. Cet élément de dimension signifie que le rapport demandé contenait trop de valeurs uniques pour être traité efficacement. Par conséquent, elle supprime les éléments jugés les moins importants.

## Architecture de traitement des Customer Journey Analytics et valeurs uniques

Customer Journey Analytics traite les rapports au moment de leur exécution, en distribuant le jeu de données combiné à plusieurs serveurs. Les données dans chaque serveur de traitement sont regroupées par ID de personne, ce qui signifie qu’un seul serveur de traitement contient toutes les données concernant une personne spécifique. Une fois le traitement terminé, le serveur transmet son sous-ensemble de données traitées à un serveur d’agrégation. Tous les sous-ensembles de données traitées sont combinés et renvoyés sous la forme d’un rapport d’espace de travail.

Si un serveur individuel agrège un jeu de résultats qui dépasse un seuil de taille, il tronque les résultats avant de les renvoyer. Cette optimisation limite le trafic réseau et l’agrégation pour permettre des rapports rapides. Comme chaque serveur de traitement tronque les résultats avec uniquement la vue de ses propres données, il est possible que les éléments affichés dans Analysis Workspace aient des valeurs de mesure légèrement décalées.

Le serveur choisit les éléments de dimension à ignorer en fonction de la mesure utilisée pour le tri. Si la mesure de tri est une mesure calculée, le serveur utilise les mesures de la mesure calculée pour déterminer les éléments de dimension à tronquer. Les mesures calculées peuvent contenir plusieurs mesures d’une importance variable. Par conséquent, les résultats peuvent être moins précis. Par exemple, lors du calcul de &quot;Recettes par personne&quot;, le montant total des recettes et le nombre total de personnes sont renvoyés et regroupés avant d’effectuer la division. Par conséquent, chaque noeud choisit les éléments à supprimer sans savoir comment leurs résultats affectent le tri global.

## Différences entre &quot;Résultats tronqués&quot; et &quot;Faible trafic&quot;

Dans les versions précédentes d’Adobe Analytics, une architecture de traitement différente était utilisée. Les données ont été traitées au moment de leur collecte. Les éléments de Dimension ont été placés sous &quot;Faible trafic&quot; après qu’une dimension ait atteint 500 000 valeurs uniques et qu’un filtrage plus agressif a été appliqué à un million de valeurs uniques. Le nombre de &quot;valeurs uniques&quot; a été réinitialisé au début de chaque mois calendaire. Les données traitées étaient permanentes, il n’y avait aucun moyen de retirer les données existantes de « Faible trafic ».

En Customer Journey Analytics, les éléments de dimension ne sont tronqués que si les résultats d’un rapport sont trop volumineux. Les données traitées ne sont pas permanentes, ce qui signifie que vous pouvez réduire ou éliminer la troncature en modifiant votre rapport.

## Réduction de l’élément de dimension &quot;Résultats tronqués&quot;

Si vous souhaitez réduire le nombre d’événements dans l’élément de dimension &quot;Résultats tronqués&quot;, Adobe recommande l’un des éléments suivants :

* Utilisez une [Filtrer](/help/components/filters/create-filters.md). Les filtres s’appliquent au moment où chaque serveur traite un sous-ensemble de données. La limitation du nombre de valeurs uniques renvoyées réduit l’élément de dimension &quot;Résultats tronqués&quot;.
* Utilisez une recherche. Si une recherche est utilisée, les éléments qui ne correspondent pas à la recherche sont supprimés des résultats du rapport, ce qui rend plus probable l’affichage des éléments de votre choix.
* Utilisez une dimension du jeu de données de recherche. Les dimensions des jeux de données de recherche combinent les éléments de dimension des jeux de données d’événement, ce qui limite le nombre de valeurs uniques retournées.
