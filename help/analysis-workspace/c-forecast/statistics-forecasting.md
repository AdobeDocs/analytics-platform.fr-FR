---
description: Les prévisions dans Analysis Workspace utilisent une série de techniques statistiques avancées pour déterminer les valeurs des prévisions.
title: Techniques statistiques de la prévision
feature: Visualizations
role: User
exl-id: f042a6dd-6af5-4bdd-afc9-07546d8ded6e
source-git-commit: accd7300c2dd6224e4d154cb6e3889f564e07a1a
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 6%

---

# Techniques statistiques du service des prévisions

Le service de prévision prend actuellement en charge Prophète et s’est révélé efficace et fiable pour la plupart des données. Prophet est un ensemble de prévisions open source très utilisé développé par Meta. Il décompose les données en composants des tendances, des saisons et des événements. Le modèle Prophète est efficace et adapté à de nombreuses applications de prévision. En outre, le modèle fonctionne avec vigueur contre les valeurs aberrantes et les données manquantes.

À l’avenir, il est prévu de sélectionner des modèles en fonction de la méthode heuristique, par exemple sélectionner le processus Gaussien approximatif en ligne pour la diffusion de données en continu, ou NeuralProphet lorsque les utilisateurs spécifient la meilleure précision de prévision et peuvent tolérer un temps d’attente plus long.

Le service réduit automatiquement les données lorsqu’il y a trop de points de données, afin d’assurer le temps de réponse. Le temps de réponse de la cible est défini sur ~3 secondes. Actuellement, lorsque le nombre de points de données dépasse 5 500, les données de série temporelle sont sous-échantillonnées de manière adaptative, selon la longueur des données. La sortie est reconvertie à la fréquence de données d’origine, de sorte que le processus d’échantillonnage adaptatif n’affecte pas les expériences utilisateur.

Les effets des jours fériés sont pris en compte lorsque plusieurs années de données sont disponibles. Actuellement, la liste des jours fériés en question est la suivante :

* Journée Martin Luther King
* Journée des Présidents
* Jour du Souvenir (États-Unis)
* 4 juillet (États-Unis)
* Thanksgiving (États-Unis)
* Black Friday (États-Unis)
* Cyber Monday (États-Unis)
* Noël

Le service peut également effectuer une suppression simple d’anomalies (valeurs aberrantes), par exemple en supprimant des points de données situés en dehors de six plages de sigma. Cette option n’est pas activée par défaut, car tous les points de données sont considérés comme valides. Les anomalies peuvent avoir une influence négative sur la qualité du modèle, même si le modèle Prophète est résistant aux valeurs aberrantes en général.

Le service accepte les paramètres de caractère saisonnier spécifiés par l’utilisateur, par exemple le caractère saisonnier quotidien et hebdomadaire. Sinon, le modèle sélectionne automatiquement le caractère saisonnier. Pour une granularité de données différente, le service utilise différentes longueurs de données historiques pour créer des modèles de prévision. Par exemple, pour les données quotidiennes, il extrait plus d’une année de données (si disponible). Pour les données horaires, il extrait huit semaines de données (si disponibles). L’extraction de données peut prendre du temps et peut parfois entraîner un temps d’attente plus long.

Données historiques requises pour une granularité temporelle différente :

| Granularité | Données historiques requises |
|---|--:|
| Minute | 3 jours |
| Heure  | 2 semaines |
| Jour | 8 semaines |
| Semaine | 2 ans |
| Mois | 2 ans |
| Trimestre | 8 trimestres |
| Année | 8 ans |


Le résultat de la prévision pour chaque période spécifiée s’accompagne d’un intervalle de prédiction (défini par la limite inférieure et supérieure), qui devrait contenir la valeur future observée 95 % du temps, souvent appelée intervalle de confiance. Il n&#39;y a pas de limite à ce que le service peut prévoir dans l&#39;avenir. Cependant, l’incertitude des prévisions augmente avec les dates futures, ce qui se traduit par un intervalle de prédiction plus large au fil du temps.

Le service ne fait aucune supposition sur les données utilisateur. Par exemple, le service ne suppose pas que les données sont non négatives. Cela signifie que les prédictions et/ou leurs limites peuvent être négatives si les données présentent une forte tendance à la baisse, même si tous les points de données observés sont non négatifs.


## Références

1. Taylor, Sean J., et Benjamin Letham : *Prévisions à grande échelle.* Le statisticien américain 72.1 (2018) : 37-45.
1. Triebe, Oskar, et al.: *Neuralprophète : prévisions explicables à l’échelle.* arXiv, préimpression arXiv:2111.15397(2021).
1. Zhang et Arbour : *Détection des anomalies de série temporelle.* Demande de brevet américaine 18/057883.
