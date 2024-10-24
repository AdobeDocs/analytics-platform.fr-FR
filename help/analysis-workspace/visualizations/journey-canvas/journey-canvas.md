---
description: Vue d’ensemble de la zone de travail du parcours
title: Zone de travail du parcours
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 820251833eae9fed1574a0010f726b0ba6e12cd1
workflow-type: tm+mt
source-wordcount: '1654'
ht-degree: 1%

---

# Vue d’ensemble de la zone de travail du parcours

La visualisation du canevas de Parcours vous permet d’analyser et d’obtenir des informations détaillées sur les parcours que vous fournissez à vos utilisateurs et clients. Il vous permet de définir un parcours à partir de zéro ou d’en afficher un à partir de Journey Optimizer, puis de voir comment les gens ont quitté le parcours (sont tombés) ou ont continué à le traverser (sont passés par).

Vous pouvez [créer des analyses des parcours utilisateur](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) en utilisant n’importe quelle combinaison d’événements, d’éléments de dimension, de filtres et de plages de dates pour créer des noeuds de parcours. Connectez les noeuds pour créer le flux du parcours et incluez plusieurs chemins et points de décision. Faites glisser des noeuds sur la zone de travail pour réorganiser les événements et les conditions du parcours. Mises à jour des données en temps réel lorsque vous effectuez des modifications.

[Les noeuds sont connectés](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) en tant que &quot;chemin d’accès final&quot;, ce qui signifie que les visiteurs sont comptabilisés tant qu’ils passent finalement d’un noeud à l’autre, indépendamment des événements se produisant entre les 2 noeuds. Le temps alloué aux utilisateurs pour se déplacer le long du chemin est déterminé par le paramètre du conteneur.

![Canevas de Parcours](assets/journey-canvas.png)

## Principales fonctionnalités

Les principales fonctionnalités de la visualisation du canevas de Parcours sont les suivantes :

* Analyse approfondie des abandons et des abandons qui prend en charge les parcours utilisateur les plus complexes.

* Zone de travail pour mapper et visualiser les différents points d’entrée, noeuds et chemins d’accès d’un parcours utilisateur.

* Effectuez un glisser-déposer des interactions pour ajouter des composants à la zone de travail et pour repositionner les noeuds existants.

* La possibilité de créer des analyses des parcours utilisateur dans la zone de travail du Parcours ou de les créer automatiquement en fonction des parcours Journey Optimizer.

## Informations potentielles

Le canevas de parcours fournit des informations exploitables pour les parcours les plus complexes.

### Chemin avec le taux de conversion le plus élevé {#conversion-rate-caption}

L’aperçu le plus visible dans le canevas de Parcours s’affiche sous la forme d’une légende en haut du canevas lui-même.

Cette légende résume les chemins d’accès du parcours présentant le taux de conversion le plus élevé.

Lorsque le parcours contient plusieurs noeuds de départ, la légende ressemble à ceci :

![Légende d’informations sur le canevas de Parcours](assets/journey-canvas-caption.png)

Lorsque le parcours contient un seul noeud de départ, la légende se présente comme suit :

![Parcours de la légende du détail du canevas à un seul noeud de démarrage](assets/journey-canvas-caption-singlestart.png)

Tenez compte des points suivants lors de l’interprétation de cette légende :

* Un _chemin_ est défini comme un noeud de départ connecté par des flèches à un noeud de fin, avec un nombre indéfini de noeuds connectés entre eux.

* Le calcul du taux de conversion dépend du type de parcours (le nombre de noeuds de début et de fin contenus dans le parcours, et si les chemins d’accès se croisent entre eux).

  Le tableau suivant décrit le mode de calcul des taux de conversion en fonction du type de parcours :

  | Type de parcours | Calcul du taux de conversion | Exemple |
  |---------|----------|---------|
  | **Un noeud de départ unique et un noeud de fin unique** | Le taux de conversion est calculé en divisant le nombre du noeud final par celui du noeud de départ. | ![Parcours avec plusieurs démarrages qui convergent vers un noeud commun](assets/journey-canvas-single-path.png) |
  | **Un noeud de départ unique et plusieurs noeuds de fin** | Le taux de conversion est calculé en recherchant le noeud final dont le nombre est le plus élevé et en le divisant par celui du noeud de départ. | ![Parcours avec plusieurs démarrages qui convergent vers un noeud commun](assets/journey-canvas-singlestart-multiend.png) |
  | **Plusieurs chemins autonomes, chaque chemin contenant un seul noeud de départ et un seul noeud de fin** | Le taux de conversion est calculé en divisant le nombre du noeud final par celui du noeud de départ. Le chemin présentant le taux de conversion le plus élevé est décrit dans la légende. | ![Parcours avec plusieurs démarrages qui convergent vers un noeud commun](assets/journey-canvas-multi-start-separate.png) |
  | **Plusieurs noeuds de départ qui à tout moment dans le parcours convergent vers un noeud commun** | Le taux de conversion est calculé en recherchant le noeud final dont le numéro est le plus élevé et en divisant ce nombre par celui du noeud de départ dont le numéro est le plus petit. | ![Parcours avec plusieurs démarrages qui convergent vers un noeud commun](assets/journey-canvas-multi-start-converge.png) |

### Abandons, abandons, etc.

Vous trouverez ci-dessous quelques exemples d’autres informations que le canevas de Parcours peut vous aider à fournir. Vous pouvez choisir si ces informations sont basées sur toutes les personnes dans la vue de données, toutes les personnes qui ont démarré le parcours ou toutes les personnes du noeud précédent du parcours.

#### Diminution

* Nombre et pourcentage de personnes ayant terminé le parcours (arrivées au noeud de fin)

* Le nombre et le pourcentage de personnes arrivant à un noeud donné du parcours

* L’étape la plus courante qui a suivi ou précédant un noeud donné du parcours

#### Abandon

* Les noeuds du parcours où les personnes sont le plus souvent tombées du parcours (ne sont jamais arrivées à l’un des noeuds suivants immédiats).

#### Données additionnelles pour chaque noeud

* Ajoutez une dimension de ventilation sur n’importe quel noeud du parcours pour afficher des données supplémentaires pour ce noeud spécifique.

## Sélection entre les visualisations Zone de travail de Parcours, Abandons ou Flux

La visualisation du canevas de Parcours présente des similitudes avec la [visualisation Abandons](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) et la [visualisation Flux](/help/analysis-workspace/visualizations/c-flow/flow.md), mais présente des différences importantes.

### Comprendre les différences

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Quand utiliser le canevas de Parcours

Le canevas de parcours est essentiel pour :

* Analyse des abandons impliquant des parcours avec plusieurs points d’entrée et chemins.

* Parcours non linéaires avec plusieurs chemins et points d’entrée, avec une séquence prédéfinie de pages.

* Analyses exploratoires ad hoc basées sur un parcours prédéfini.

* Analyse qui nécessite une mesure principale autre que Session, Personne ou Occurrences.

* Analyse plus approfondie des parcours issus de Adobe Journey Optimizer.

Utilisez [le tableau ci-dessus](#understand-the-differences) pour comprendre les différences entre les visualisations Zone de travail du Parcours, Abandons et Flux.

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

Après avoir modifié un parcours Journey Optimizer dans la zone de travail du Parcours, les options disponibles dans le champ déroulant [!UICONTROL **Paramètres de la flèche**] changent en fonction de vos modifications. Pour plus d’informations, voir [Configuration des paramètres](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

Le champ [!UICONTROL **Type de noeud**] est disponible uniquement dans Journey Optimizer. Elle n’est pas disponible lors de l’affichage d’un parcours Journey Optimizer dans la zone de travail du Parcours, que vous ayez apporté des modifications au parcours dans la zone de travail du Parcours ou non.

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
