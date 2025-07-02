---
description: Découvrez comment identifier les anomalies statistiques à l’aide de techniques de détection des anomalies.
title: Techniques Statistiques Utilisées Pour La Détection Des Anomalies
feature: Anomaly Detection
exl-id: 7165e7a1-a04f-450e-bffd-e329adac6903
role: User
source-git-commit: f3c9a000ae5baa19cb5a6cf0e0343de3a9685b56
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 67%

---

# Techniques statistiques

Dans Analysis Workspace, la détection des anomalies applique différentes techniques statistiques avancées afin de déterminer si une observation doit être considérée comme anormale.

Selon la granularité de date du rapport, trois différentes techniques statistiques sont utilisées, en particulier pour la détection des anomalies horaire, quotidienne, hebdomadaire ou mensuelle. Chacune de ces techniques statistiques est décrite ci-dessous.

## Détection des anomalies avec une granularité quotidienne

Dans les rapports avec une granularité quotidienne, l’algorithme prend en compte plusieurs facteurs importants afin de produire les résultats les plus exacts possible. Tout d’abord, l’algorithme détermine le type de modèle à appliquer en fonction des données disponibles pour lesquelles l’algorithme sélectionne l’une des deux classes : un modèle basé sur une série temporelle ou un modèle de détection des valeurs aberrantes (appelé segmentation fonctionnelle).

La sélection du modèle de série temporelle repose sur les combinaisons suivantes de type d’erreur, de tendance et de caractère saisonnier, comme décrit par [Hyndman et al. (2008)](https://idp.springer.com/authorize?response_type=cookie&client_id=springerlink&redirect_uri=https%3A%2F%2Flink.springer.com%2Fbook%2F10.1007%2F978-3-540-71918-2). Plus particulièrement, l’algorithme tente les combinaisons suivantes :

1. Erreur additive, aucune tendance, caractère saisonnier additif (ANA)
1. Erreur additive, tendance additive, caractère saisonnier additif (AAA)
1. Erreur multiplicative, aucune tendance, caractère saisonnier multiplicatif (MNM)
1. Erreur multiplicative, aucune tendance, caractère saisonnier additif (MNA)
1. Erreur additive, tendance additive, aucun caractère saisonnier (AAN)

L&#39;algorithme teste l&#39;adéquation de chacune de ces combinaisons en sélectionnant celle qui présente la meilleure erreur moyenne absolue en pourcentage (EMPA). Toutefois, si la MAPE du meilleur modèle de série temporelle est supérieure à 15 %, une segmentation fonctionnelle est appliquée. En règle générale, les données à haut degré de répétition (par exemple, semaine par semaine ou mois par mois) sont les mieux adaptées à un modèle de série temporelle.

Une fois le modèle sélectionné, l’algorithme adapte les résultats en fonction des jours fériés et du caractère saisonnier d’un exercice à l’autre. En ce qui concerne les jours fériés, l’algorithme vérifie si les jours fériés suivants sont présents dans la période de création de rapports :

* Jour du Souvenir (États-Unis)
* 4 juillet (États-Unis)
* Thanksgiving (États-Unis)
* Black Friday (États-Unis)
* Cyber Monday (États-Unis)
* 24-26 décembre
* Janvier 1
* 31 décembre

Ces jours fériés ont été choisis en fonction d’une analyse statistique approfondie de nombreux points de données de clients afin d’identifier les jours fériés les plus importants pour le plus grand nombre de groupes de tendances des clients. Bien que la liste ne soit certainement pas exhaustive pour tous les clients ou cycles économiques, l’application de jours fériés améliore considérablement les performances de l’algorithme dans son ensemble pour presque tous les jeux de données des clients.

Une fois le modèle sélectionné et les jours fériés identifiés dans la période de création des rapports, l’algorithme s’exécute comme suit :

1. Créez la période de référence des anomalies. Cette période de référence des anomalies comprend jusqu’à 35 jours avant la période de création des rapports, ainsi qu’une période correspondante un an auparavant. Tenez compte des jours bissextiles lorsque cela est nécessaire et incluez tous les jours fériés applicables qui peuvent avoir eu lieu un autre jour de l’année précédente.
1. Vérifie si les jours fériés de la période actuelle (à l’exclusion de l’année précédente) sont anormaux en fonction des données les plus récentes.
1. Si le jour férié dans la période actuelle est anormal, adapte la valeur attendue et l’intervalle de confiance du jour férié actuel étant donné le jour férié de l’année précédente (avec une marge de deux jours avant et après). La correction des jours fériés actuels repose sur l’erreur en pourcentage absolu de la moyenne la plus faible de :

   1. Effets additifs
   1. Effets multiplicatifs
   1. Différence d’une année sur l’autre

Dans l’exemple suivant, observez l’amélioration drastique des performances le jour de Noël et du Nouvel An :

![Graphiques en deux lignes présentant les changements de performances avec et sans les performances des vacances.](assets/anomaly_statistics.png)

## Détection des anomalies avec une granularité horaire

Pour les données horaires, on applique le même algorithme de série temporelle qu’avec l’algorithme de granularité quotidienne. Toutefois, il repose principalement sur deux modèles de tendance : un cycle de 24 heures ainsi qu’un cycle week-end/jour de semaine. Afin de capturer ces deux effets saisonniers, l’algorithme horaire crée deux modèles distincts (week-end et jour de semaine) en appliquant la même approche que celle décrite ci-dessus.

Le créneau de formation des tendances horaires repose sur un intervalle de recherche en amont de 336 heures.

## Détection des anomalies avec une granularité horaire ou mensuelle

Les tendances hebdomadaires et mensuelles diffèrent des tendances hebdomadaires ou quotidiennes déterminées avec une granularité quotidienne ou horaire, de sorte qu’un algorithme distinct est appliqué. Pour les tests hebdomadaires et mensuels, une approche de détection des valeurs aberrantes en deux étapes est connue sous le nom de test de déviation généralisée extrémiste et identifiée (DGSE). Ce test tient compte du nombre maximum d’anomalies attendues combiné à l’approche ajustée de diagrammes en boîte (méthode non paramétrique de détection des valeurs aberrantes) afin de déterminer le nombre maximum de valeurs aberrantes. Les deux étapes sont les suivantes :

1. Fonction ajustée de diagrammes en boîte : détermine le nombre maximum d’anomalies étant donné les données d’entrée.
1. Fonction GESD : appliquée aux données d’entrée avec le résultat de l’étape 1.

L’étape de détection des anomalies de saisonnalité des vacances et de la période YoY soustrait ensuite les données de l’année dernière des données de cette année. Il effectue ensuite une nouvelle itération sur les données à l’aide du processus en deux étapes ci-dessus pour vérifier que les anomalies sont appropriées pour la saison. Chacune de ces granularités de date utilise une recherche en amont de 15 périodes, y compris la période de création de rapports sélectionnée (15 mois ou 15 semaines) et une période correspondante un an auparavant pour la formation.
