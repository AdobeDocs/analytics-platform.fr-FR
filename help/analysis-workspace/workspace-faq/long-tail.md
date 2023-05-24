---
title: Élément de dimension Mot-clé à faible demande
description: Décrit l’élément de dimension « Mot-clé à faible demande » et pourquoi il apparaît dans les rapports.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 31%

---

# Élément de dimension de longue durée

Lors de l’utilisation d’une dimension contenant un grand nombre de valeurs uniques, un avertissement indiquant **[!UICONTROL Résultats tronqués]**.  Cela signifie que l’architecture de rapports utilisée par CJA contenait trop de valeurs uniques pour qu’elle soit traitée efficacement. En conséquence. il a supprimé les éléments qu’il jugeait les moins importants.

## Architecture de traitement CJA et valeurs uniques

CJA traite les rapports au moment de leur exécution et distribue le jeu de données combiné à un certain nombre de serveurs. Les données dans chaque serveur de traitement sont regroupées par ID de personne, ce qui signifie qu’un seul serveur de traitement contient toutes les données concernant une personne spécifique. Une fois le traitement terminé, le serveur transmet son sous-ensemble de données traitées à un serveur d’agrégation. Tous les sous-ensembles de données traitées sont combinés et renvoyés sous la forme d’un rapport d’espace de travail.

Si un serveur individuel agrège un jeu de résultats qui dépasse un seuil de taille, il tronquera les résultats avant de les renvoyer. Cela permet de maintenir le trafic et l’agrégation du réseau dans les limites pour permettre des rapports rapides.  Dans la mesure où il tronque les résultats avec uniquement la vue de ses propres données, il est possible (bien que peu probable) que les éléments affichés dans Analysis Workspace aient des valeurs de mesure incorrectes.

Le serveur choisit les éléments à ignorer en fonction de la mesure utilisée pour le tri.  S’il s’agit d’une mesure calculée, il n’est peut-être pas évident de savoir comment la trier. Les résultats peuvent donc être moins précis.  Par exemple, lors du calcul de &quot;Recettes par personne&quot;, le montant total des recettes et le nombre total de personnes sont renvoyés et regroupés avant d’effectuer la division. Par conséquent, chaque noeud choisit généralement les éléments à supprimer, sans vraiment savoir comment leurs résultats affecteront le tri global.

## Différences entre « Mot-clé à faible demande » et « Faible trafic »

Dans les versions précédentes d’Adobe Analytics, une architecture de traitement différente était utilisée. Les données étaient traitées au moment de leur collecte. Les éléments de dimension étaient placés sous « Faible trafic » lorsquʼune dimension atteignait 500 000 valeurs uniques. De plus, un filtrage plus agressif était appliqué à partir de 1 million de valeurs uniques. Le nombre de &quot;valeurs uniques&quot; a été réinitialisé au début de chaque mois calendaire. Les données traitées étaient permanentes, il n’y avait aucun moyen de retirer les données existantes de « Faible trafic ».

Dans CJA, les éléments de dimension ne sont tronqués que si les résultats d’un rapport sont trop volumineux. Les données traitées ne sont pas permanentes, ce qui signifie que vous pouvez réduire ou éliminer la troncature en modifiant votre rapport.

## Réduction du nombre de valeurs sous l’élément de dimension « Mot-clé à faible demande »

Si vous souhaitez réduire la troncation de &quot;Long Tail&quot;, Adobe recommande l’une des méthodes suivantes :

* Utilisez un [filtre](/help/components/filters/create-filters.md). Les filtres sont appliqués au moment où chaque serveur traite un sous-ensemble de données. La limitation du nombre de valeurs uniques qu’elles renvoient réduit la troncation &quot;Long Tail&quot;.
* Utilisez une recherche. Si une recherche est utilisée, les éléments qui ne correspondent pas à la recherche sont tronqués en premier, ce qui rend plus probable l’affichage des éléments souhaités.
* Utilisez une dimension du jeu de données de recherche. Les dimensions des jeux de données de recherche combinent les éléments de dimension des jeux de données d’événement, ce qui limite le nombre de valeurs uniques retournées.

Dans l’ensemble, il est difficile d’utiliser un rapport qui contient trop d’éléments de dimension uniques. Si vous appliquez un filtre ou une dimension de jeu de données de recherche, vous pouvez réduire la troncature &quot;Long Tail&quot; tout en simplifiant la consommation de votre rapport.
