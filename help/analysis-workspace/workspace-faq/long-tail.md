---
title: Valeur de dimension de longue traîne
description: Explique la valeur de dimension "Long Tail" et la raison pour laquelle elle apparaît dans le rapports.
translation-type: tm+mt
source-git-commit: 8f59697b2bb282a1057267131343229e12dd5111
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---


# Valeur de dimension de longue traîne

Si vous utilisez une dimension qui contient un grand nombre de valeurs uniques, vous pouvez parfois voir une valeur dans le rapports intitulée &quot;Long Tail&quot;. Cette valeur de dimension signifie que l’architecture de rapports CJA utilise trop de valeurs uniques pour être traitée.

## Architecture de traitement CJA et valeurs uniques

CJA traite les rapports au moment de leur exécution, distribuant le jeu de données combiné à plusieurs serveurs. Les données par serveur de traitement sont regroupées par ID de personne, ce qui signifie qu’un serveur de traitement unique contient toutes les données pour une personne donnée. Une fois le traitement terminé, il transmet son sous-ensemble de données traitées à un serveur d&#39;agrégation. Tous les sous-ensembles de données traitées sont combinés et renvoyés sous la forme d’un rapport Workspace.

Si un serveur individuel traitant un sous-ensemble de données rencontre plus de 500 000 valeurs de dimension uniques, il renvoie les 500 000 premières valeurs de dimension de son sous-ensemble, puis renvoie le reste sous &quot;Long Tail&quot;. La valeur de dimension &quot;Long Tail&quot; affichée dans un rapport Workspace correspond au total cumulé des valeurs de chaque serveur de traitement individuel qui dépassent 500 000 valeurs uniques.

## Différences entre &quot;Long Tail&quot; et &quot;Faible Trafic&quot;

Dans les versions précédentes d’Adobe Analytics, une architecture de traitement différente a été utilisée. Les données ont été traitées au moment de leur collecte. Les valeurs de dimension ont été placées sous &quot;Faible trafic&quot; après qu’une dimension ait atteint les valeurs uniques de 500 000 et appliqué un filtrage plus agressif à des valeurs uniques de 1M. Le nombre de valeurs uniques a été réinitialisé au début de chaque mois calendaire. Les données traitées étaient permanentes ; il n&#39;y avait aucun moyen d&#39;extraire les données existantes du &quot;faible trafic&quot;.

Dans CJA, les valeurs de dimension ne sont placées dans &quot;Long Tail&quot; que si un serveur de traitement individuel contient plus de 500 000 valeurs uniques. Les données traitées ne sont pas permanentes, ce qui signifie que vous pouvez réduire la valeur de dimension &quot;Long Tail&quot; en modifiant votre rapport.

## Réduire la valeur de dimension &quot;Long Tail&quot;

Si vous souhaitez réduire la valeur de dimension &quot;Long Tail&quot;, Adobe recommande l’une des méthodes suivantes :

* Utilisez un segment. Les segments s’appliquent au moment où chaque serveur traite un sous-ensemble de données. La limitation du nombre de valeurs uniques renvoyées réduit la valeur de dimension &quot;Long Tail&quot;.
* Utilisez une dimension de jeu de données de recherche. Les dimensions des jeux de données de recherche combinent les valeurs des jeux de données de événement, ce qui limite le nombre de valeurs uniques renvoyées.

Dans l’ensemble, il est difficile de consommer un rapport contenant plus de 500 000 valeurs de dimension uniques. Si vous appliquez un segment ou une dimension de jeu de données de recherche, vous pouvez réduire la présence de &quot;Long Tail&quot; tout en facilitant la consommation de votre rapport. Adobe prévoit améliorer cette expérience au fur et à mesure que la CJA sera développée.
