---
description: Découvrez comment résoudre les problèmes de configuration d’une visualisation de zone de travail de parcours.
title: Dépannage de la zone de travail de parcours
feature: Visualizations
role: User
exl-id: f0ac3752-9244-4d9e-807b-e6471e6aa55b
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '1290'
ht-degree: 1%

---

# Résolution des problèmes liés à la zone de travail de parcours

La visualisation de la zone de travail des Parcours vous permet d’analyser les parcours que vous fournissez à vos utilisateurs et clientes, et d’obtenir des informations détaillées à leur sujet.

Pour en savoir plus sur la zone de travail de Parcours, consultez la présentation de la zone de travail de Parcours [&#128279;](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) et [Configurer une visualisation de zone de travail de Parcours &#x200B;](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

Les informations suivantes peuvent vous aider à résoudre les problèmes liés aux résultats inattendus que vous pouvez voir, tels que les nœuds qui apparaissent plus tard dans le parcours et qui affichent un pourcentage ou un nombre plus élevé que les nœuds qui apparaissent plus tôt dans le parcours.

## Nœuds avec un pourcentage ou une valeur plus élevé que les nœuds précédents

Il est possible dans la zone de travail du Parcours pour les nœuds qui arrivent plus tard dans le parcours d’afficher un pourcentage ou un nombre plus élevé que pour les nœuds qui arrivent plus tôt dans le parcours.

En d’autres termes, contrairement aux visualisations Abandons , qui sont toujours en forme de funnel (avec une participation décroissante à chaque étape), les visualisations de la zone de travail du Parcours peuvent avoir une plus grande participation aux étapes ultérieures du parcours que dans les étapes précédentes.

Cela peut se produire dans les scénarios suivants :

* Lors de l’utilisation d’une mesure principale autre que Personnes ou Sessions

* Lorsque plusieurs chemins convergent en un seul nœud

### Le parcours utilise une mesure principale autre que Personnes ou Session

Étant donné que la zone de travail de Parcours vous permet d’utiliser n’importe quelle mesure comme mesure principale, il peut en résulter que les nœuds qui viennent plus tard dans le parcours affichent un pourcentage ou un nombre plus élevé que les nœuds qui viennent plus tôt dans le parcours.

![Parcours avec des nœuds avec un pourcentage plus élevé que le nœud précédent](assets/journey-canvas-higher-percentage.png)

Le parcours utilisé dans les scénarios suivants est configuré avec les paramètres suivants :

* **[!UICONTROL Personne]** est défini comme conteneur.

* **[!UICONTROL Événement]** est défini comme mesure principale

#### Scénario 1 : l’utilisateur A suit le chemin du parcours dans la première session. Au cours d’une session ultérieure, l’utilisateur reçoit un événement qui correspond uniquement à un nœud ultérieur.

Supposons que l’utilisateur A visite le site et effectue le parcours (nœud 1 : « Site de visite » > nœud 2 : « Afficher le produit A » > nœud 3 : « Extraire »). Comme l’utilisateur A disposait d’un événement qui correspondait à chaque nœud du parcours dans l’ordre, un événement est comptabilisé sur chaque nœud du parcours.

Supposons maintenant que l’utilisateur A revisite le site lors d’une session ultérieure. Comme l’utilisateur A a déjà terminé le parcours au cours d’une session précédente en suivant le chemin du parcours, cela signifie que chaque fois que l’utilisateur A dispose d’un événement qui correspond à un nœud du parcours, et ce, même si l’utilisateur A n’a pas suivi le chemin du parcours au cours de sa session en cours, un événement est comptabilisé sur le nœud approprié du parcours. Par exemple, si l’utilisateur A extrait, un événement est comptabilisé sur le nœud « Extraire ». Cela peut entraîner un pourcentage et un nombre plus élevés sur le nœud « Extraire » que sur le nœud précédent « Afficher le produit A ».

Dans cet exemple, le paramètre de conteneur du parcours « Personne » joue un rôle essentiel pour déterminer si l’événement sur le troisième nœud (« Extraire ») est comptabilisé lors de la session suivante.

Si le paramètre du conteneur avait été défini sur « Session », l’événement qui s’était produit uniquement sur le troisième nœud lors de la visite suivante n’aurait pas été comptabilisé dans le parcours, car les statistiques affichées dans le parcours seraient limitées à une seule session définie pour une personne donnée. Pour en savoir plus sur le paramètre de conteneur, consultez [Commencer à créer une visualisation de zone de travail de Parcours &#x200B;](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization) dans l’article [Configurer une visualisation de zone de travail de Parcours &#x200B;](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### Scénario 2 : l’utilisateur B sort du parcours

Supposons que l’utilisateur B visite le site et ne termine pas le parcours (visite le site, consulte le produit B, puis passe en caisse). Dans ce cas, un événement est comptabilisé pour le nœud de début du parcours, « Visite du site », mais un événement n’est pas comptabilisé pour les nœuds restants, et l’utilisateur B tombe en dehors du parcours. Même si l’utilisateur B a extrait, un événement n’est pas comptabilisé sur le troisième nœud (« Extraire »), car l’utilisateur B n’a pas terminé le parcours en affichant le produit A avant l’extraction.

En effet, les événements ne sont comptabilisés pour chaque nœud que lorsque les personnes suivent le « chemin d’accès final » du parcours. Cela signifie que les événements ne sont comptabilisés que si la personne a finalement passé d’un nœud à l’autre, quels que soient les événements qui se produisent entre les 2 nœuds.

### Le parcours comporte plusieurs chemins convergeant en un seul nœud

La zone de travail de parcours vous permet d’inclure plusieurs nœuds de début dans un seul parcours, ce qui entraîne plusieurs chemins d’accès. Ces chemins d’accès peuvent converger en un nœud commun, ce qui fait que les nœuds qui apparaissent plus tard dans le parcours affichent un pourcentage ou un nombre plus élevé que les nœuds qui apparaissent plus tôt dans le parcours.

![parcours avec plusieurs chemins convergeant en un seul nœud](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### Pourcentages de parcours

Bien que les nombres affichés sur chaque nœud d’un parcours restent constants, quelle que soit la valeur sélectionnée dans le champ **[!UICONTROL Valeur de pourcentage]**, les pourcentages eux-mêmes peuvent changer.

Les sections ci-dessous montrent comment les pourcentages peuvent changer pour le même parcours, selon l’option sélectionnée dans le champ **[!UICONTROL Valeur de pourcentage]** :

+++Pourcentage du nœud de départ

Les nœuds de ce parcours contiennent les statistiques suivantes lorsque le champ **[!UICONTROL Valeur de pourcentage]** est défini sur **[!UICONTROL Pourcentage du nœud de début]** :

![Parcours avec des nœuds avec un pourcentage plus élevé que le nœud précédent](assets/journey-canvas-higher-percentage.png)

| Nœud | Statistiques |
|---------|----------|
| Nœud 1 - « Visite du site » | Dans ce parcours, 354 147 événements se sont produits sur le site au cours de la période de création des rapports, comme indiqué dans le nœud de début du parcours, « Visiter le site ». |
| Nœud 2 - « Afficher le produit A » | Sur le nombre total d’événements affichés dans le nœud de démarrage, 14 % (48 394) d’entre eux correspondaient aux critères du deuxième nœud du parcours, « Afficher le produit A ». |
| Nœud 3 - « Extraire » | Sur le nombre total d’événements affichés dans le nœud de démarrage, 32 % (113 782) d’entre eux correspondaient aux critères du troisième nœud du parcours, « Extraction ». |

+++

+++Pourcentage du nœud précédent

Les nœuds de ce parcours contiennent les statistiques suivantes lorsque le champ **[!UICONTROL Valeur de pourcentage]** est défini sur **[!UICONTROL Pourcentage du nœud précédent]** :

![Parcours avec des nœuds avec un pourcentage plus élevé que le nœud précédent](assets/journey-canvas-percentage-previous.png)

| Nœud | Statistiques |
|---------|----------|
| Nœud 1 - « Visite du site » | Dans ce parcours, 354 147 événements se sont produits sur le site au cours de la période de création des rapports, comme indiqué dans le nœud de début du parcours, « Visiter le site ». |
| Nœud 2 - « Afficher le produit A » | Sur le nombre total d’événements affichés dans le nœud précédent, 14 % (48 394) d’entre eux correspondaient aux critères du deuxième nœud du parcours, « Afficher le produit A ». |
| Nœud 3 - « Extraire » | Sur le nombre total d’événements affichés dans le nœud précédent, plus de 100 % (113 782) d’entre eux correspondaient aux critères du troisième nœud du parcours, « Extraction ». |

+++

+++Pourcentage du total

Les nœuds de ce parcours contiennent les statistiques suivantes lorsque le champ **[!UICONTROL Valeur de pourcentage]** est défini sur **[!UICONTROL Pourcentage du total]** :

![Parcours avec des nœuds avec un pourcentage plus élevé que le nœud précédent](assets/journey-canvas-percentage-total.png)

| Nœud | Statistiques |
|---------|----------|
| Nœud 1 - « Visite du site » | Dans ce parcours, 354 147 événements se sont produits sur le site au cours de la période de création des rapports, comme indiqué dans le nœud de début du parcours, « Visiter le site ». |
| Nœud 2 - « Afficher le produit A » | Sur le nombre total d’événements, moins de 1 % (48 394) correspondaient aux critères du deuxième nœud du parcours, « Afficher le produit A ». |
| Nœud 3 - « Extraire » | Sur le nombre total d’événements, 1 % (113 782) correspondaient aux critères du troisième nœud du parcours, « Check out » (Extraire). |

+++

## Compatibilité entre la mesure du conteneur et la mesure principale

Vous pouvez configurer le conteneur de zone de travail par Parcours sur Personne (qui utilise la mesure Personnes) ou Session (qui utilise la mesure Sessions).

Veillez à choisir une mesure principale compatible avec la mesure de conteneur actuellement sélectionnée. La plupart des mesures sont compatibles avec les mesures de conteneur disponibles. Toutefois, certaines combinaisons de mesures de conteneur et de mesures principales doivent être évitées.

Par exemple, l’utilisation de Personne comme conteneur avec Session comme mesure principale peut entraîner des résultats inattendus.

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
