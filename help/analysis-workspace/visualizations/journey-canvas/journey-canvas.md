---
description: Vue d’ensemble de la zone de travail du parcours
title: Zone de travail du parcours
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: c42858908aa8e73c5f3b622b9911ff9e9724f2dc
workflow-type: tm+mt
source-wordcount: '1318'
ht-degree: 2%

---

# Vue d’ensemble de la zone de travail du parcours

{{release-limited-testing}}

La visualisation du canevas de Parcours vous permet d’analyser et d’obtenir des informations détaillées sur les parcours que vous fournissez à vos utilisateurs et clients. Il vous permet de définir un parcours à partir de zéro ou d’en afficher un à partir de Journey Optimizer, puis de voir comment les gens ont quitté le parcours (sont tombés) ou ont continué à le traverser (sont passés par).

Vous pouvez [créer des analyses des parcours utilisateur](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) en utilisant n’importe quelle combinaison d’événements, d’éléments de dimension, de filtres et de plages de dates pour créer des noeuds de parcours. Connectez les noeuds pour créer le flux du parcours et incluez plusieurs chemins et points de décision. Faites glisser des noeuds sur la zone de travail pour réorganiser les événements et les conditions du parcours. Mises à jour des données en temps réel lorsque vous effectuez des modifications.

## Principales fonctionnalités

Les principales fonctionnalités de la visualisation du canevas de Parcours sont les suivantes :

* Analyse approfondie des abandons et des abandons qui prend en charge les parcours utilisateur les plus complexes.

* Zone de travail pour mapper et visualiser les différents points d’entrée, noeuds et chemins d’accès d’un parcours utilisateur.

* Effectuez un glisser-déposer des interactions pour ajouter des composants à la zone de travail et pour repositionner les noeuds existants.

* La possibilité de créer des analyses des parcours utilisateur dans la zone de travail du Parcours ou de les créer automatiquement en fonction des parcours Journey Optimizer.

## Informations potentielles

Vous trouverez ci-dessous quelques exemples des types de canevas de Parcours d’informations que vous pouvez fournir. Vous pouvez choisir si ces informations sont basées sur toutes les personnes dans la vue de données, toutes les personnes qui ont démarré le parcours ou toutes les personnes du noeud précédent du parcours.

**Fallthrough**

* Nombre et pourcentage de personnes ayant terminé le parcours (arrivées au noeud de fin)

* Le nombre et le pourcentage de personnes arrivant à un point (noeud) donné du parcours

* L’étape la plus courante qui s’est produite après ou avant un point donné (noeud) du parcours

**Abandon**

* Points (noeuds) du parcours où les personnes sont le plus souvent tombées du parcours (jamais arrivées à l’un des noeuds suivants immédiats)

**Autre**

* Données additionnelles pour tout noeud du parcours (en ajoutant une dimension de ventilation pour le noeud)


## Sélection entre le canevas de Parcours et les visualisations Abandons

Les visualisations du canevas de parcours sont similaires aux [visualisations des abandons](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), dans la mesure où les deux visualisations indiquent où les personnes ont quitté (abandonné) une séquence prédéfinie de pages et ont poursuivi leur visite (passant par une séquence de pages).

Cependant, il existe des différences importantes.

### Comprendre les différences

Le tableau suivant présente les types d’analyses pris en charge dans la visualisation du canevas de Parcours et la visualisation Abandons :

| Fonction | Visualisation du canevas de parcours | Visualisation des abandons |
|---------|----------|---------|
| Parcours linéaires | Oui | Oui |
| Parcours non linéaires avec plusieurs points d’entrée et chemins | Oui | Non |
| parcours Adobe Journey Optimizer | Oui | Non |
| Mesure primaire | Toute mesure, y compris les mesures calculées | Peut utiliser uniquement les mesures Session ou Utilisateur |
| Mesure secondaire | Oui<p>Toute mesure, y compris les mesures calculées</p> | Non |
| Comparaison de filtres | Non | Oui<p>Comparaison d’un [nombre illimité de filtres](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md#compare-filters-in-fallout)</p> |

### Choisir la visualisation à utiliser

Avant d’utiliser le canevas de Parcours ou Abandon, veillez à [ comprendre les différences entre les deux ](#understand-the-differences).

Si votre analyse des abandons n’implique qu’un parcours linéaire qui ne comporte qu’un seul début et une seule fin connus, envisagez d’utiliser une [visualisation des abandons](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) comme option plus simple pour ces parcours d’utilisateurs plus simples.

Le canevas de parcours est essentiel pour l’analyse des abandons impliquant des parcours avec plusieurs points d’entrée et chemins, ou pour l’analyse des parcours créés dans Journey Optimizer.

## Analyse des parcours Journey Optimizer

>[!NOTE]
>
>Si votre entreprise n’a pas accès à Journey Optimizer, vous pouvez toujours [créer des analyses dans la zone de travail du Parcours](#build-analyses-in-customer-journey-analytics).

L’analyse des parcours Journey Optimizer dans le canevas de Parcours fournit des informations détaillées et exploitables sur la manière dont les utilisateurs interagissent avec un parcours.

Lorsque vous analysez un parcours Journey Optimizer dans un canevas de Parcours, le parcours s’affiche avec le même ordre, la même séquence et la même structure que dans Journey Optimizer. Si vous pouvez apporter des modifications à un parcours dans la zone de travail du Parcours, les [ modifications ne sont plus synchronisées à partir de Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas).

### Avantages de l’analyse des parcours Journey Optimizer avec le canevas de Parcours

Le canevas de parcours fournit une analyse approfondie et approfondie qui n’est pas possible dans Journey Optimizer.

L’utilisation d’un canevas de Parcours pour analyser les parcours créés dans Journey Optimizer présente divers avantages :

* Créez des événements à l’aide de n’importe quelle dimension, mesure, filtre ou période de Customer Journey Analytics.

  Dans Journey Optimizer, un utilisateur technique doit créer un événement avant de pouvoir l’ajouter à un parcours.

* Créez des audiences basées sur un noeud personnalisé que vous créez (lance le créateur d’audiences du Customer Journey Analytics).

  Dans Journey Optimizer, vous pouvez créer des audiences uniquement pour les activités prédéfinies.

* Analyse des abandons et des abandons

* Ventilation des événements avec n’importe quelle dimension

* Combiner des événements

* Connexion à des événements

* Renommer et supprimer des événements

* Beaucoup plus

### Synchronisation entre Journey Optimizer et le canevas de Parcours

Après avoir créé une analyse d’un parcours Journey Optimizer dans la zone de travail de Parcours, les données se synchronisent dans une seule direction, de Journey Optimizer à la zone de travail de Parcours. Cela signifie que les modifications apportées à un parcours dans la zone de travail du Parcours ne sont jamais répercutées dans Journey Optimizer.

En outre, les modifications apportées à un parcours dans Journey Optimizer ne sont synchronisées avec la zone de travail de Parcours que si le parcours n’a pas été modifié dans la zone de travail de Parcours. Après avoir modifié un parcours dans la zone de travail de Parcours, les modifications apportées au parcours dans Journey Optimizer ne sont pas répercutées dans la zone de travail de Parcours. Pour voir les modifications répercutées dans la zone de travail du Parcours, vous pouvez supprimer et [recréer le parcours dans la zone de travail du Parcours](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Différences après la modification d’un parcours dans la zone de travail du Parcours {#differences-after-modifying}

Après avoir modifié un parcours Journey Optimizer dans la zone de travail du Parcours, des modifications peuvent se produire dans le traitement des données, les fonctionnalités disponibles et le comportement de synchronisation.

Si vous apportez une modification importante à un parcours Journey Optimizer dans le canevas de Parcours, des modifications peuvent se produire dans le traitement des données, les fonctionnalités disponibles et le comportement de synchronisation. Une modification importante comprend l’une des options suivantes :

* Ajout ou suppression d’un noeud

* Ajout ou suppression d’une flèche entre les noeuds

* Modification des composants sur un noeud

Si vous apportez d’autres modifications à un parcours Journey Optimizer dans la zone de travail du Parcours, par exemple en faisant glisser un noeud ou en ajoutant une ventilation, les différences décrites dans les sections suivantes ne s’appliquent pas.

>[!NOTE]
>
>Pour rétablir l’état d’origine du parcours, vous pouvez appuyer sur Ctrl+z après avoir effectué votre première modification dans la zone de travail du Parcours. Vous pouvez également supprimer et [recréer le parcours dans la zone de travail du Parcours](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### Différences de traitement des données

Après avoir modifié un parcours Journey Optimizer dans la zone de travail du Parcours, vous remarquerez peut-être des modifications apportées à vos données si votre parcours contient des mesures qui ne comportent pas de modèles d’attribution par défaut.

En effet, contrairement à Journey Optimizer, le canevas de Parcours vous permet d’appliquer plusieurs dimensions dans un seul parcours. Cette fonctionnalité signifie que l’ [attribution de mesure](/help/data-views/component-settings/attribution.md) n’est pas prise en charge.

#### Différences de fonctionnalités

Une fois que vous avez modifié un parcours Journey Optimizer dans la zone de travail de Parcours, les fonctionnalités suivantes peuvent changer, selon vos modifications :

* Les valeurs affichées dans le champ [!UICONTROL **Type de noeud**] changent.

* Les options disponibles dans le champ déroulant [!UICONTROL **Paramètres de la flèche**] changent.

Pour plus d’informations sur ces champs, voir [Configuration des paramètres](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

#### Différences de synchronisation

Les modifications apportées à un parcours dans Journey Optimizer ne sont synchronisées avec la zone de travail de Parcours que si le parcours n’a pas été modifié dans la zone de travail de Parcours.

Après avoir modifié un parcours Journey Optimizer dans la zone de travail de Parcours, les modifications apportées au parcours dans Journey Optimizer ne sont pas répercutées dans la zone de travail de Parcours. Pour voir les modifications répercutées dans la zone de travail du Parcours, vous pouvez supprimer et [recréer le parcours dans la zone de travail du Parcours](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Différences de terminologie entre Journey Optimizer et Customer Journey Analytics

Certains termes qui signifient une chose dans Journey Optimizer signifient autre chose en Customer Journey Analytics. Lors de l’utilisation du canevas de Parcours, les termes du Customer Journey Analytics sont utilisés.

| Terme | Zone de travail du parcours | Journey Optimizer |
|---------|----------|---------|
| **Événement** | L’une des mesures standard disponibles en Customer Journey Analytics. Cette mesure comptabilise des éléments tels que les recettes, les abonnements ou les pistes générées. | Catégorie d’activités qui déclenche un parcours personnalisé, tel qu’un achat en ligne. |

### Analyse d’un parcours Journey Optimizer dans le canevas de Parcours

Pour plus d’informations sur l’analyse d’un parcours Journey Optimizer dans la zone de travail de Parcours, voir [Configuration d’une visualisation de zone de travail de Parcours](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Créer des analyses dans le canevas de Parcours

Vous pouvez créer des analyses dans un canevas de Parcours basées sur des dimensions ou des mesures disponibles dans Analysis Workspace. Vous pouvez également analyser les parcours créés dans Journey Optimizer. Pour plus d’informations, voir [Configuration d’une visualisation de canevas de Parcours](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).
