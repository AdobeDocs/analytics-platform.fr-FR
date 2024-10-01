---
description: Exemples lors de la configuration d’une visualisation de canevas de Parcours
title: Exemples de canevas de parcours
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: 057c9f4a0e8fb163bfb23cea1870f949ad4ae1c0
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 1%

---

# Dépannage du canevas de parcours

{{release-limited-testing}}

La visualisation du canevas de Parcours vous permet d’analyser et d’obtenir des informations détaillées sur les parcours que vous fournissez à vos utilisateurs et clients.

Pour en savoir plus sur le canevas de Parcours, voir [Présentation du canevas de Parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) et [Configuration d’une visualisation de canevas de Parcours](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


## Compatibilité entre la mesure de conteneur et la mesure principale

Vous pouvez configurer le conteneur de canevas de Parcours pour qu’il soit Personne (qui utilise la mesure Personnes) ou Session (qui utilise la mesure Sessions).

Lorsque vous choisissez une mesure principale ou secondaire, veillez à choisir une mesure compatible avec la mesure de conteneur actuellement sélectionnée. La plupart des mesures sont compatibles avec les mesures de conteneur disponibles. Cependant, certaines combinaisons de mesures de conteneur et de mesures principales ou secondaires doivent être évitées.

Par exemple, si vous utilisez Personne comme conteneur avec Session comme mesure principale ou secondaire.


| Conteneur | Mesure Principal ou secondaire | Résultat |
|---------|----------|---------|
| Personnes | Session | Cette combinaison peut aboutir à des résultats inattendus. Plus précisément, le résultat de cette combinaison peut être |
| A2 | B2 | C2 |
| A3 | B3 | C3 |


## Pourcentages supérieurs à 100 %

Les configurations suivantes peuvent entraîner des noeuds affichant des pourcentages supérieurs à 100 % :

* Lorsque le champ **[!UICONTROL Valeur en pourcentage]** est défini sur **[!UICONTROL Pourcentage du total]**, et qu’une mesure principale est sélectionnée, ce qui génère moins de données pour le noeud de départ que sur les noeuds suivants.

  Par exemple, si Recettes est sélectionnée comme mesure principale et qu’aucune recette n’est réalisée sur la mesure principale, les recettes s’afficheront sur tous les noeuds où elles sont réalisées.


## Parcours qui n’a pas la forme d’entonnoir

Il est possible, dans la zone de travail du Parcours, que les noeuds qui se trouvent plus tard dans le parcours affichent un pourcentage ou un nombre plus élevé que les noeuds qui se trouvent plus tôt dans le parcours.

En d’autres termes, contrairement aux visualisations Abandons, qui sont toujours en forme d’entonnoir (avec une participation diminuant à chaque étape), les visualisations du canevas de Parcours peuvent avoir une participation plus élevée aux étapes suivantes du parcours.

Prenez un parcours avec les caractéristiques suivantes :

* Le parcours contient 3 noeuds : Noeud A —> Noeud B —> Noeud C

* Le champ **[!UICONTROL Valeur en pourcentage]** est défini sur **[!UICONTROL Pourcentage du total]**

* **[!UICONTROL Person]** est défini comme conteneur

* **[!UICONTROL Event]** est défini comme mesure principale

Dans ce scénario, supposons qu’un visiteur ait consulté le noeud A, le noeud B, puis le noeud C. Chacune de ces visites compte comme un événement unique sur chaque noeud, car elles ont été visitées dans l’ordre défini par le parcours.

Lors d’une visite ultérieure sur le site, le visiteur consulte uniquement le noeud C, ce qui entraîne un événement supplémentaire sur le noeud C.

Dans ce cas, les noeuds A et B affichent chacun 1 événement et 100 %, tandis que le noeud C affiche 2 événements et 200 %.

D’un autre côté, si Session était défini comme conteneur, les noeuds A, B et C afficheraient chacun 1 événement et 100 %, car la visite ultérieure sur le site où le visiteur a uniquement visité le noeud C n’aurait pas satisfait aux exigences de parcours, car les noeuds A et B n’ont pas été visités avant la visite du noeud C.
