---
description: Dans Analysis Workspace, la prévision utilise une série de techniques statistiques avancées pour déterminer les valeurs de prévision.
title: Techniques statistiques utilisées pour la prévision
feature: Visualizations
role: User
source-git-commit: 1bd24ee1163e4615bf5626c51aec9f167352f2f6
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 5%

---


# Techniques statistiques utilisées dans le service de prévision

Le service de prévision soutient actuellement Prophet et il a été démontré qu&#39;il fonctionne efficacement et de manière fiable pour la plupart des données. Prophet est un package de prévision open-source largement utilisé développé par Meta. Il décompose les données en composants tendances, saisonnalités et événements. Le modèle Prophète est efficace et s&#39;adapte bien à de nombreuses applications de prévision. En outre, le modèle fonctionne de manière robuste contre les valeurs aberrantes et les données manquantes.

À l’avenir, il est prévu de sélectionner des modèles basés sur l’heuristique, par exemple choisir le Processus gaussien approximatif en ligne pour les données en flux continu, ou NeuralProphet lorsque les utilisateurs spécifient la meilleure précision de prévision et peuvent tolérer un temps d’attente plus long.

Le service réduit automatiquement la taille des données lorsqu’il y a trop de points de données, afin de garantir un temps de réponse. Le temps de réponse cible est défini sur ~3 secondes. Actuellement, lorsque le nombre de points de données dépasse 5 500, les données de série temporelle sont sous-échantillonnées de manière adaptative, en fonction de la longueur des données. La sortie est convertie à nouveau à la fréquence des données d’origine, de sorte que le processus d’échantillonnage adaptatif n’affecte pas les expériences utilisateur.

Les effets de vacances sont pris en compte lorsque plusieurs années de données sont disponibles. Actuellement, la liste des jours fériés considérés est la suivante :

* Martin Luther King Day
* Presidents Day
* Jour du Souvenir (États-Unis)
* 4 juillet (États-Unis)
* Thanksgiving (États-Unis)
* Black Friday (États-Unis)
* Cyber Monday (États-Unis)
* Noël

Le service peut également supprimer une simple anomalie (valeurs aberrantes), par exemple en supprimant des points de données qui se trouvent en dehors de la plage six sigma. Cette option n’est pas activée par défaut, car on suppose que tous les points de données sont valides. Les anomalies peuvent avoir une influence négative sur la qualité du modèle, même si le modèle Prophète est résilient aux valeurs aberrantes en général.

Le service accepte les paramètres de saisonnalité spécifiés par l’utilisateur, par exemple la saisonnalité quotidienne et hebdomadaire. Sinon, le modèle sélectionne automatiquement le caractère saisonnier. En fonction de la granularité des données, le service utilise différentes longueurs de données historiques pour créer des modèles de prévision. Par exemple, pour les données quotidiennes, il extrait plus d’une année de données (si disponible). Pour les données horaires, il extrait huit semaines de données (si disponibles). L’extraction de données peut prendre du temps et entraîne parfois un temps d’attente plus long.

Les données historiques requises pour une granularité temporelle différente :

| Granularité | Données historiques requises |
|---|--:|
| Minute | 3 jours |
| Heure  | 2 semaines |
| Jour | 8 semaines |
| Semaine | 2 ans |
| Mois | 2 ans |
| Trimestre | 8 trimestres |
| Année | 8 ans |


Le résultat de la prévision pour chaque heure spécifiée s’accompagne d’un intervalle de prédiction (défini par les limites inférieure et supérieure), qui devrait contenir la valeur future observée 95 % du temps, souvent appelée intervalle de confiance. Il n&#39;y a pas de limite à ce que le service peut prévoir pour l&#39;avenir. Cependant, l’incertitude dans les prévisions augmente avec les dates plus lointaines, ce qui se traduit par un intervalle de prédiction plus large au fil du temps.

Le service ne fait aucune hypothèse sur les données utilisateur. Par exemple, le service ne suppose pas que les données sont non négatives. Cela signifie que les prédictions et/ou leurs limites peuvent être négatives, si les données présentent une forte tendance à la baisse, même si tous les points de données observés sont non négatifs.


## Références

1. Taylor, Sean J. et Benjamin Letham : *Prévision à grande échelle.* The American Statistician 72.1 (2018) : 37-45.
1. Triebe, Oskar et al.: *Neuralprophet : Prévision explicable à grande échelle.* arXiv preprint arXiv:2111.15397(2021).
1. Zhang et Arbor : *Détection des anomalies de série temporelle.* Demande de brevet américain #18/057883.

