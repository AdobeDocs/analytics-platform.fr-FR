---
description: Découvrez comment utiliser la visualisation de la zone de travail des Parcours dans Analysis Workspace pour analyser les parcours utilisateur, les abandons et les conversions à chemins multiples.
title: Résolution des problèmes liés à la zone de travail de parcours
feature: Visualizations
role: User
exl-id: f0ac3752-9244-4d9e-807b-e6471e6aa55b
autotag-review: '2026-05-19T08:43:53.628Z'
TQID: 'https://experienceleague.adobe.com/E0LdSu06SM3c1ZBnOcIz352mqIkTN7dXfH9qC1BM-4g'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: d00e9f03-e50b-4162-b143-0c0817c937c2id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 1303
ht-degree: 93%

---

# Résolution des problèmes liés à la zone de travail de parcours

La visualisation Zone de travail de parcours vous permet d’analyser les parcours que vous fournissez à vos utilisateurs et utilisatrices et à votre clientèle, et d’obtenir des informations détaillées à leur sujet.

Pour en savoir plus sur la zone de travail de parcours, consultez [Vue d’ensemble de la zone de travail de parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) et [Configurer une visualisation de la zone de travail de parcours](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

Les informations suivantes peuvent vous aider à résoudre les problèmes liés à des résultats inattendus, tels que des nœuds situés plus loin dans le parcours affichant un pourcentage ou un nombre plus élevé que ceux situés plus tôt dans le parcours.

## Nœuds avec un pourcentage ou une valeur plus élevé(e) que les nœuds précédents

Il est possible, dans le parcours de zone de travail, que des nœuds qui viennent plus tard dans le parcours affichent un pourcentage ou un nombre plus élevé que ceux qui viennent plus tôt.

En d’autres termes, contrairement aux visualisations des abandons, qui ont toujours une forme d’entonnoir (avec une participation décroissante à chaque étape), les visualisations de la zone de travail de parcours peuvent présenter une participation plus élevée aux étapes ultérieures du parcours qu’aux étapes précédentes.

Cela peut se produire dans les scénarios suivants :

* Lors de l’utilisation d’une mesure principale autre que Personnes ou Sessions

* Lorsque plusieurs chemins convergent en un seul nœud

### Le parcours utilise une mesure principale autre que Personnes ou Sessions

Étant donné que la zone de travail de parcours vous permet d’utiliser n’importe quelle mesure comme mesure principale, des nœuds situés plus tard dans le parcours peuvent afficher un pourcentage ou un nombre plus élevé que des nœuds situés plus tôt dans le parcours.

![Parcours avec des nœuds affichant un pourcentage plus élevé que le nœud précédent](assets/journey-canvas-higher-percentage.png)

Le parcours utilisé dans les scénarios suivants est configuré avec les paramètres ci-après :

* **[!UICONTROL Personne]** est défini comme conteneur.

* **[!UICONTROL Événement]** est défini comme mesure principale.

#### Scénario 1 : la personne A suit le chemin du parcours dans la première session. Au cours d’une session ultérieure, la personne reçoit un événement qui correspond uniquement à un nœud ultérieur.

Supposons que la personne A visite le site et effectue le parcours (nœud 1 : « Consulter le site » > nœud 2 : « Afficher le produit A » > nœud 3 : « Payer »). Comme la personne A avait un événement qui correspondait à chaque nœud du parcours dans l’ordre, un événement est comptabilisé sur chaque nœud du parcours.

Supposons maintenant que la personne A revisite le site lors d’une session ultérieure. Comme la personne A a déjà complété le parcours lors d’une session précédente en suivant le chemin du parcours, cela signifie que chaque fois que la personne A a un événement correspondant à un nœud du parcours, et même même si elle n’a pas suivi le chemin du parcours lors de sa session actuelle, un événement est comptabilisé sur le nœud correspondant du parcours. Par exemple, si la personne A effectue le paiement, un événement est comptabilisé sur le nœud « Payer ». Cela peut entraîner un pourcentage et un nombre plus élevés sur le nœud « Payer » que sur le nœud précédent « Afficher le produit A ».

Dans cet exemple, le paramètre de conteneur du parcours « Personne » joue un rôle essentiel pour déterminer si l’événement sur le troisième nœud (« payer ») est comptabilisé lors de la session suivante.

Si le paramètre du conteneur avait été défini sur « Session », l’événement qui s’était produit uniquement sur le troisième nœud lors de la visite suivante n’aurait pas été comptabilisé dans le parcours, car les statistiques affichées dans le parcours seraient limitées à une seule session définie pour une personne donnée. Pour en savoir plus sur le paramètre de conteneur, consultez [Commencer à créer une visualisation de zone de travail de Parcours ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization) dans l’article [Configurer une visualisation de zone de travail de Parcours ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### Scénario 2 : la personne B sort du parcours.

Supposons que la personne B visite le site et ne termine pas le parcours (visite le site, consulte le produit B, puis effectue le paiement). Dans ce cas, un événement est comptabilisé pour le nœud de départ du parcours, « Consulter le site », mais un événement n’est pas comptabilisé pour les nœuds restants, et la personne B sort du parcours. Même si la personne B a effectué le paiement, un événement n’est pas comptabilisé sur le troisième nœud (« Extraire »), car la personne B n’a pas terminé le parcours en affichant le produit A avant le paiement.

Cela s’explique par le fait que les événements ne sont comptabilisés pour chaque nœud que lorsque les personnes suivent le « chemin final » du parcours. Cela signifie que les événements ne sont comptabilisés que si la personne a finalement passé d’un nœud à l’autre, quels que soient les événements qui se produisent entre les deux nœuds.

### Le parcours comporte plusieurs chemins convergeant en un seul nœud.

La zone de travail de parcours vous permet d’inclure plusieurs nœuds de départ dans un seul parcours, ce qui entraîne plusieurs chemins d’accès. Ces chemins d’accès peuvent converger en un nœud commun. Ainsi, les nœuds qui apparaissent plus tard dans le parcours affichent un pourcentage ou un nombre plus élevé que les nœuds qui apparaissent plus tôt dans le parcours.

![Parcours avec plusieurs chemins convergeant en un seul nœud](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### Pourcentages de parcours

Bien que les nombres affichés sur chaque nœud d’un parcours restent constants, quelle que soit la valeur sélectionnée dans le champ **[!UICONTROL Valeur de pourcentage]**, les pourcentages eux-mêmes peuvent changer.

Les sections ci-dessous montrent comment les pourcentages peuvent changer pour le même parcours, selon l’option sélectionnée dans le champ **[!UICONTROL Valeur de pourcentage]** :

+++Pourcentage du nœud de départ

Les nœuds de ce parcours contiennent les statistiques suivantes lorsque le champ **[!UICONTROL Valeur de pourcentage]** est défini sur **[!UICONTROL Pourcentage du nœud de départ]** :

![Parcours avec des nœuds ayant un pourcentage plus élevé que le nœud précédent](assets/journey-canvas-higher-percentage.png)

| Nœud | Statistiques |
|---------|----------|
| Nœud 1 - « Consulter le site » | Dans ce parcours, 354 147 événements se sont produits sur le site au cours de la période de reporting, comme indiqué dans le nœud de début du parcours, « Consulter le site ». |
| Nœud 2 - « Afficher le produit A » | Sur le nombre total d’événements affichés dans le nœud de départ, 14 % (48 394) d’entre eux correspondaient aux critères du deuxième nœud du parcours, « Afficher le produit A ». |
| Nœud 3 - « Payer » | Sur le nombre total d’événements affichés dans le nœud de démarrage, 32 % (113 782) d’entre eux correspondaient aux critères du troisième nœud du parcours, « Payer ». |

+++

+++Pourcentage du nœud précédent

Les nœuds de ce parcours contiennent les statistiques suivantes lorsque le champ **[!UICONTROL Valeur de pourcentage]** est défini sur **[!UICONTROL Pourcentage du nœud précédent]** :

![Parcours avec des nœuds ayant un pourcentage plus élevé que le nœud précédent](assets/journey-canvas-percentage-previous.png)

| Nœud | Statistiques |
|---------|----------|
| Nœud 1 - « Consulter le site » | Dans ce parcours, 354 147 événements se sont produits sur le site au cours de la période de reporting, comme indiqué dans le nœud de début du parcours, « Consulter le site ». |
| Nœud 2 - « Afficher le produit A » | Sur le nombre total d’événements affichés dans le nœud précédent, 14 % (48 394) d’entre eux correspondaient aux critères du deuxième nœud du parcours, « Afficher le produit A ». |
| Nœud 3 - « Payer » | Sur le nombre total d’événements affichés dans le nœud précédent, plus de 100 % (113 782) d’entre eux correspondaient aux critères du troisième nœud du parcours, « Payer ». |

+++

+++Pourcentage du total

Les nœuds de ce parcours contiennent les statistiques suivantes lorsque le champ **[!UICONTROL Valeur de pourcentage]** est défini sur **[!UICONTROL Pourcentage du total]** :

![Parcours avec des nœuds ayant un pourcentage plus élevé que le nœud précédent](assets/journey-canvas-percentage-total.png)

| Nœud | Statistiques |
|---------|----------|
| Nœud 1 - « Consulter le site » | Dans ce parcours, 354 147 événements se sont produits sur le site au cours de la période de reporting, comme indiqué dans le nœud de début du parcours, « Consulter le site ». |
| Nœud 2 - « Afficher le produit A » | Sur le nombre total d’événements, moins de 1 % (48 394) correspondaient aux critères du deuxième nœud du parcours, « Afficher le produit A ». |
| Nœud 3 - « Payer » | Sur le nombre total d’événements, 1 % (113 782) correspondaient aux critères du troisième nœud du parcours, « Payer ». |

+++

## Compatibilité entre la mesure du conteneur et la mesure principale

Vous pouvez configurer le conteneur de la zone de travail de parcours sur Personne (qui utilise la mesure Personnes) ou Session (qui utilise la mesure Sessions).

Veillez à choisir une mesure principale compatible avec la mesure de conteneur actuellement sélectionnée. La plupart des mesures sont compatibles avec les mesures de conteneur disponibles. Toutefois, certaines combinaisons de mesures de conteneur et de mesures principales doivent être évitées.

Par exemple, l’utilisation de Personne comme conteneur avec Session comme mesure principale peut entraîner des résultats inattendus.

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
