---
title: Élément de dimension Mot-clé à faible demande
description: Décrit l’élément de dimension « Mot-clé à faible demande » et pourquoi il apparaît dans les rapports.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '437'
ht-degree: 100%

---

# Élément de dimension Mot-clé à faible demande

Si vous utilisez une dimension qui contient un grand nombre de valeurs uniques, vous pouvez parfois voir une valeur dans les rapports nommée **[!UICONTROL Mot-clé à faible demande]**. Cet élément de dimension signifie que lʼarchitecture de rapport utilisée par CJA contenait trop de valeurs uniques pour le traitement.

## Architecture de traitement CJA et valeurs uniques

CJA traite les rapports au moment de leur exécution et distribue le jeu de données combiné à un certain nombre de serveurs. Les données dans chaque serveur de traitement sont regroupées par ID de personne, ce qui signifie qu’un seul serveur de traitement contient toutes les données concernant une personne spécifique. Une fois le traitement terminé, il transmet son sous-ensemble de données traitées à un serveur d’agrégation. Tous les sous-ensembles de données traitées sont combinés et renvoyés sous la forme d’un rapport d’espace de travail.

Si un serveur individuel traitant un sous-ensemble de données rencontre plus de 500 000 éléments de dimension uniques, il renvoie dʼabord les 500 000 premiers éléments de dimension de son propre sous-ensemble, puis renvoie les éléments restants sous lʼélément de dimension « [!UICONTROL Mot-clé à faible demande] ». Lʼélément de dimension « [!UICONTROL Mot-clé à faible demande] » affiché dans un rapport d’espace de travail représente le total agrégé des valeurs de chaque serveur de traitement individuel qui a dépassé 500 000 valeurs uniques.

## Différences entre « Mot-clé à faible demande » et « Faible trafic »

Dans les versions précédentes d’Analytics, une architecture de traitement différente était utilisée. Les données étaient traitées au moment de leur collecte. Les éléments de dimension étaient placés sous « Faible trafic » lorsquʼune dimension atteignait 500 000 valeurs uniques. De plus, un filtrage plus agressif était appliqué à partir de 1 million de valeurs uniques. Le nombre de valeurs uniques était réinitialisé au début de chaque mois civil. Les données traitées étaient permanentes, il n’y avait aucun moyen de retirer les données existantes de « Faible trafic ».

Dans CJA, les éléments de dimension ne sont placés dans « Mot-clé à faible demande » que si un serveur de traitement individuel contient plus de 500 000 valeurs uniques. Les données traitées ne sont pas permanentes, ce qui signifie que vous pouvez réduire le nombre de valeurs sous l’élément de dimension « Mot-clé à faible demande » en modifiant votre rapport.

## Réduction du nombre de valeurs sous l’élément de dimension « Mot-clé à faible demande »

Si vous souhaitez réduire le nombre de valeurs sous l’élément de dimension « Mot-clé à faible demande », Adobe vous recommande dʼeffectuer lʼune des opérations suivantes :

* Utilisez un [filtre](/help/components/filters/create-filters.md). Les filtres sont appliqués au moment où chaque serveur traite un sous-ensemble de données. En limitant le nombre de valeurs uniques quʼils renvoient, on réduit également le nombre de valeurs que contient lʼélément de dimension « Mot-clé à faible demande ».
* Utilisez une dimension du jeu de données de recherche. Les dimensions des jeux de données de recherche combinent les éléments de dimension des jeux de données d’événement, ce qui limite le nombre de valeurs uniques retournées.

Lʼanalyse dʼun rapport contenant plus de 500 000 éléments de dimension uniques nʼest pas une tâche aisée. Si vous appliquez un filtre ou une dimension du jeu de données de recherche, vous pouvez réduire la présence de lʼélément de dimension « Mot-clé à faible demande » tout en rendant votre rapport plus facile à consulter. Adobe prévoit dʼaméliorer cette expérience au fur et à mesure du développement de CJA.
