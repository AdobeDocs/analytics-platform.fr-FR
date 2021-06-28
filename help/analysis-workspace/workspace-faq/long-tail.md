---
title: Élément de dimension Long Tail
description: Explique l’élément de dimension "Long Tail" et pourquoi il apparaît dans les rapports.
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: 8cee89a8ed656ad6376e64c8327aa7c94a937ce9
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Élément de dimension Long Tail

Si vous utilisez une dimension qui contient un grand nombre de valeurs uniques, vous pouvez parfois voir une valeur dans les rapports intitulée **[!UICONTROL Long Tail]**. Cet élément de dimension signifie que l’architecture de création de rapports utilisée par CJA contenait trop de valeurs uniques pour son traitement.

## Architecture de traitement CJA et valeurs uniques

CJA traite les rapports au moment de leur exécution, en distribuant le jeu de données combiné à un certain nombre de serveurs. Les données par serveur de traitement sont regroupées par ID de personne, ce qui signifie qu’un seul serveur de traitement contient toutes les données pour une personne donnée. Une fois le traitement terminé, il transmet son sous-ensemble de données traitées à un serveur d’agrégation. Tous les sous-ensembles de données traitées sont combinés et renvoyés sous la forme d’un rapport Workspace.

Si un serveur individuel qui traite un sous-ensemble de données rencontre plus de 500 000 éléments de dimension uniques, il renvoie les 500 000 premiers éléments de dimension de son propre sous-ensemble, puis renvoie le reste sous &quot;[!UICONTROL Long Tail]&quot;. L’élément de dimension &quot;[!UICONTROL Long Tail]&quot; affiché dans un rapport Workspace est le total agrégé des valeurs de chaque serveur de traitement individuel qui ont dépassé 500 000 valeurs uniques.

## Différences entre &quot;Long Tail&quot; et &quot;Low Traffic&quot;

Dans les versions précédentes d’Analytics, une architecture de traitement différente était utilisée. Les données ont été traitées au moment de leur collecte. Les éléments de Dimension ont été placés sous &quot;Faible trafic&quot; après qu’une dimension ait atteint 500 000 valeurs uniques et qu’un filtrage plus agressif a été appliqué à des valeurs uniques de 1M. Le nombre de valeurs uniques a été réinitialisé au début de chaque mois calendaire. Les données traitées étaient permanentes; il n’y avait aucun moyen de récupérer les données existantes du &quot;faible trafic&quot;.

Dans CJA, les éléments de dimension ne sont placés dans &quot;Long Tail&quot; que si un serveur de traitement individuel contient plus de 500 000 valeurs uniques. Les données traitées ne sont pas permanentes, ce qui signifie que vous pouvez réduire l’élément de dimension &quot;Long Tail&quot; en modifiant votre rapport.

## Réduction de l’élément de dimension &quot;Long Tail&quot;

Si vous souhaitez réduire l’élément de dimension &quot;Long Tail&quot;, Adobe recommande l’une des options suivantes :

* Utilisez un [filtre](/help/components/filters/create-filters.md). Les filtres s’appliquent au moment où chaque serveur traite un sous-ensemble de données. La limitation du nombre de valeurs uniques renvoyées réduit l’élément de dimension &quot;Long Tail&quot;.
* Utilisez une dimension de jeu de données de recherche. Les dimensions de jeu de données de recherche combinent des éléments de dimension de jeu de données d’événement, ce qui limite le nombre de valeurs uniques renvoyées.

Dans l’ensemble, il est difficile d’utiliser un rapport contenant plus de 500 000 éléments de dimension uniques. Si vous appliquez un filtre ou une dimension de jeu de données de recherche, vous pouvez réduire la présence de &quot;Long Tail&quot; tout en facilitant la consommation de votre rapport. Adobe prévoit d’améliorer cette expérience au fur et à mesure que CJA est développé.
