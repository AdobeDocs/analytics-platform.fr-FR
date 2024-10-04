---
description: Exemples lors de la configuration d’une visualisation de canevas de Parcours
title: Exemples de canevas de parcours
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: 2fc2bd660b017140b8dfa660cf71054af9efb87e
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 0%

---

# Dépannage du canevas de parcours

{{release-limited-testing}}

La visualisation du canevas de Parcours vous permet d’analyser et d’obtenir des informations détaillées sur les parcours que vous fournissez à vos utilisateurs et clients.

Pour en savoir plus sur le canevas de Parcours, voir [Présentation du canevas de Parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) et [Configuration d’une visualisation de canevas de Parcours](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

Les informations suivantes peuvent vous aider à résoudre les problèmes liés à des résultats inattendus, tels que les noeuds qui apparaissent plus tard dans le parcours et qui présentent un pourcentage ou un nombre plus élevé que les noeuds qui apparaissent plus tôt dans le parcours.

## Noeuds dont le pourcentage ou la valeur est plus élevé que les noeuds précédents

Il est possible, dans la zone de travail du Parcours, que les noeuds qui se trouvent plus tard dans le parcours affichent un pourcentage ou un nombre plus élevé que les noeuds qui se trouvent plus tôt dans le parcours.

En d’autres termes, contrairement aux visualisations Abandons, qui sont toujours en forme d’entonnoir (avec une participation diminuant à chaque étape), les visualisations du canevas de Parcours peuvent avoir une participation plus élevée aux étapes suivantes du parcours que lors des étapes précédentes.

Cela peut se produire dans les scénarios suivants :

* Lorsque vous utilisez une mesure principale autre que Personnes ou Sessions

* Lorsque plusieurs chemins d’accès convergent en un seul noeud

### Le parcours utilise une mesure principale autre que Personnes ou Session

Étant donné que le canevas de Parcours vous permet d’utiliser n’importe quelle mesure comme mesure principale, il peut en résulter que les noeuds qui apparaissent plus tard dans le parcours présentent un pourcentage ou un nombre plus élevé que les noeuds qui apparaissent plus tôt dans le parcours.

![Parcours avec des noeuds ayant un pourcentage plus élevé que le noeud précédent](assets/journey-canvas-higher-percentage.png)

Le parcours utilisé dans les scénarios suivants est configuré avec les paramètres suivants :

* **[!UICONTROL Person]** est défini comme conteneur

* **[!UICONTROL Event]** est défini comme mesure principale

#### Scénario 1 - L’utilisateur A suit le chemin d’accès au parcours de la première session, puis seulement les noeuds ultérieurs de la session suivante.

Supposons que l’utilisateur A consulte le site et effectue le parcours (Noeud 1 : &quot;Visite de site&quot; > Noeud 2 : &quot;Afficher le produit A&quot; > Noeud 3 : &quot;Extraction&quot;). Comme l’utilisateur A a terminé le parcours, un événement est comptabilisé sur chaque noeud du parcours.

Maintenant, supposons que l’utilisateur A consulte à nouveau le site au cours d’une session ultérieure. Comme l’utilisateur A a déjà terminé le parcours d’une session précédente en suivant le chemin du parcours, cela signifie que chaque fois que l’utilisateur A a un événement correspondant à n’importe quel noeud du parcours (même si l’utilisateur A n’a pas suivi le chemin du parcours dans sa session en cours), un événement est comptabilisé sur le noeud approprié du parcours. Par exemple, si l’utilisateur A extrait, un événement est comptabilisé sur le noeud &quot;Extraction&quot;. Cela peut se traduire par un pourcentage et un nombre plus élevés sur le noeud &quot;Extraction&quot; que sur le noeud précédent, &quot;Afficher le produit A&quot;.

Dans cet exemple, le paramètre de conteneur du parcours &quot;Personne&quot; joue un rôle essentiel pour déterminer que l’événement sur le troisième noeud (&quot;Extraction&quot;) est comptabilisé dans la session suivante.

Si le paramètre de conteneur avait été défini sur &quot;Session&quot;, l’événement qui s’est produit uniquement sur le troisième noeud lors de la visite suivante n’aurait pas été comptabilisé dans le parcours, car les statistiques affichées dans le parcours seraient limitées à une seule session définie pour une personne donnée. Pour en savoir plus sur le paramètre de conteneur, voir [Commencer la création d’une visualisation de canevas de Parcours](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization) dans l’article [Configurer une visualisation de canevas de Parcours](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### Scénario 2 - L’utilisateur B sort du parcours

Supposons que l’utilisateur B consulte le site et ne termine pas le parcours (visite le site, consulte le produit B, puis procède à l’extraction). Dans ce cas, un événement est comptabilisé pour le noeud de départ du parcours, &quot;Visite de site&quot;, mais il n’est pas comptabilisé pour les noeuds restants et l’utilisateur B est exclu du parcours. Même si l’utilisateur B a extrait les données, un événement n’est pas comptabilisé sur le troisième noeud (&quot;Extraction&quot;), car l’utilisateur B n’a pas terminé le parcours en affichant le produit A avant l’extraction.

Cela est dû au fait que les événements ne sont comptabilisés pour chaque noeud que lorsque les personnes suivent le &quot;chemin d’accès final&quot; du parcours, ce qui signifie que les événements ne sont comptabilisés que si la personne a fini par passer d’un noeud à l’autre, indépendamment des événements se produisant entre les 2 noeuds.

### Le parcours comporte plusieurs chemins convergeant en un seul noeud.

Le canevas de parcours vous permet d’inclure plusieurs noeuds de départ dans un seul parcours, ce qui entraîne plusieurs chemins d’accès. Ces chemins d’accès peuvent converger vers un noeud commun, ce qui entraîne des noeuds qui apparaissent plus tard dans le parcours indiquant un pourcentage ou un nombre plus élevé que les noeuds qui apparaissent plus tôt dans le parcours.

![Un parcours avec plusieurs chemins convergeant en un seul noeud](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### Pourcentages de parcours

Bien que les nombres affichés sur chaque noeud d’un parcours restent constants, indépendamment de ce qui est sélectionné dans le champ **[!UICONTROL Valeur en pourcentage]**, les pourcentages eux-mêmes peuvent changer.

Les sections suivantes montrent comment les pourcentages peuvent changer pour le même parcours, selon l’une des options suivantes sélectionnée dans le champ **[!UICONTROL Valeur en pourcentage]** :

+++Pourcentage du noeud de départ

Les noeuds de ce parcours contiennent les statistiques suivantes lorsque le champ **[!UICONTROL Valeur en pourcentage]** est défini sur **[!UICONTROL Pourcentage du noeud de départ]** :

![Parcours avec des noeuds ayant un pourcentage plus élevé que le noeud précédent](assets/journey-canvas-higher-percentage.png)

| Noeud | Statistiques |
|---------|----------|
| Noeud 1 - &quot;Visite de site&quot; | Dans ce parcours, le site comptait 354 147 événements dans la période du rapport, comme indiqué dans le noeud de départ du parcours, &quot;Visite de site&quot;. |
| Noeud 2 - &quot;Afficher le produit A&quot; | Sur le nombre total d’événements affichés dans le noeud de départ, 14 % (48 394) d’entre eux correspondaient aux critères du deuxième noeud du parcours, &quot;Afficher le produit A&quot;. |
| Noeud 3 - &quot;Extraction&quot; | Sur le nombre total d’événements affichés dans le noeud de départ, 32 % (113 782) d’entre eux correspondaient aux critères du troisième noeud du parcours, &quot;Extraction&quot;. |

+++

+++Pourcentage du noeud précédent

Les noeuds de ce parcours contiennent les statistiques suivantes lorsque le champ **[!UICONTROL Valeur en pourcentage]** est défini sur **[!UICONTROL Pourcentage du noeud précédent]** :

![Parcours avec des noeuds ayant un pourcentage plus élevé que le noeud précédent](assets/journey-canvas-percentage-previous.png)

| Noeud | Statistiques |
|---------|----------|
| Noeud 1 - &quot;Visite de site&quot; | Dans ce parcours, le site comptait 354 147 événements dans la période du rapport, comme indiqué dans le noeud de départ du parcours, &quot;Visite de site&quot;. |
| Noeud 2 - &quot;Afficher le produit A&quot; | Sur le nombre total d’événements affichés dans le noeud précédent, 14 % (48 394) d’entre eux correspondaient aux critères du deuxième noeud du parcours, &quot;Afficher le produit A&quot;. |
| Noeud 3 - &quot;Extraction&quot; | Sur le nombre total d’événements affichés dans le noeud précédent, plus de 100 % (113 782) d’entre eux correspondaient aux critères du troisième noeud du parcours, &quot;Extraire&quot;. |

+++

+++Pourcentage du total

Les noeuds de ce parcours contiennent les statistiques suivantes lorsque le champ **[!UICONTROL Valeur en pourcentage]** est défini sur **[!UICONTROL Pourcentage du total]** :

![Parcours avec des noeuds ayant un pourcentage plus élevé que le noeud précédent](assets/journey-canvas-percentage-total.png)

| Noeud | Statistiques |
|---------|----------|
| Noeud 1 - &quot;Visite de site&quot; | Dans ce parcours, le site comptait 354 147 événements dans la période du rapport, comme indiqué dans le noeud de départ du parcours, &quot;Visite de site&quot;. |
| Noeud 2 - &quot;Afficher le produit A&quot; | Sur le nombre total d’événements, moins de 1 % (48 394) d’entre eux correspondaient aux critères du deuxième noeud du parcours, &quot;Afficher le produit A&quot;. |
| Noeud 3 - &quot;Extraction&quot; | Sur le nombre total d’événements, 1 % (113 782) d’entre eux correspondaient aux critères du troisième noeud du parcours, &quot;Extraction&quot;. |

+++

## Compatibilité entre la mesure de conteneur et la mesure principale

Vous pouvez configurer le conteneur de canevas de Parcours pour qu’il soit Personne (qui utilise la mesure Personnes) ou Session (qui utilise la mesure Sessions).

Veillez à choisir une mesure principale compatible avec la mesure de conteneur actuellement sélectionnée. La plupart des mesures sont compatibles avec les mesures de conteneur disponibles. Cependant, certaines combinaisons de mesures de conteneur et de mesures principales doivent être évitées.

Par exemple, l’utilisation de Personne comme conteneur avec Session comme mesure principale peut entraîner des résultats inattendus.

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
