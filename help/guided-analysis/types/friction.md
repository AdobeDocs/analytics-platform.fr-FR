---
title: Friction
description: Comparer les taux de conversion entre les étapes.
exl-id: f0ba3f00-bf1f-48db-8b6e-137460abf4f8
feature: Guided Analysis
source-git-commit: 164785f52990c43691c8e13c8fa80e3c201995f7
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 3%

---

# Friction

{{release-limited-testing}}

Le **Friction** La vue fournit une représentation visuelle d’un parcours utilisateur critique dans votre produit. L’axe horizontal représente chaque étape qu’un utilisateur doit franchir. L’axe vertical représente le pourcentage d’utilisateurs ou de sessions à chaque étape. Toutes les étapes doivent être effectuées dans l’ordre final, mais peuvent se produire à tout moment dans la fenêtre de création de rapports. Les cas d’utilisation de ce type de vue sont les suivants :

* **Analyse des conversions**: Vous pouvez analyser les conversions à chaque étape de l’entonnoir. En suivant le nombre d’utilisateurs qui passent d’une étape à l’autre, vous pouvez identifier les goulets d’étranglement présentant des taux de conversion inhabituels ou indésirables. Ces informations sont utiles pour comprendre où vous pouvez améliorer votre produit pour des résultats immédiats.
* **Optimisation de l’intégration**: Optimisez le processus d’intégration de votre produit en examinant le comportement des utilisateurs par rapport aux événements clés. Vous pouvez identifier les étapes que les utilisateurs rencontrent ou ne parviennent pas à accomplir.
* **Adoption et engagement des fonctionnalités**: Découvrez comment les utilisateurs interagissent avec des fonctionnalités spécifiques de votre produit. En analysant la progression des utilisateurs par le biais d’étapes liées aux fonctionnalités, vous pouvez évaluer les taux d’adoption des fonctionnalités et identifier les zones où les utilisateurs peuvent abandonner ou sous-utiliser certaines fonctionnalités. Vous pouvez ensuite utiliser ces informations pour vous concentrer sur les améliorations des fonctionnalités afin d’augmenter les taux d’adoption.
* **Évaluation de campagne**: Mesurez l’efficacité des campagnes marketing. Vous pouvez créer un segment qui se concentre sur les utilisateurs qui ont touché une campagne donnée et comparer leur processus de conversion à d’autres campagnes ou au sein de votre produit dans son ensemble.

![Friction](../assets/friction.png)

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **Étapes**: Points de contact de l’événement dont vous souhaitez effectuer le suivi. Chaque barre du graphique représente une étape. Vous pouvez inclure jusqu’à dix étapes.
* **Personnes**: Les segments que vous souhaitez comparer à l’entonnoir. Chaque segment sélectionné divise chaque étape en plusieurs barres. Chaque couleur représente un segment différent. Vous pouvez inclure jusqu’à trois segments.

## Paramètres du graphique

La vue Friction propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **Mesure**: Portée que vous souhaitez appliquer à l’entonnoir. Les options incluent Sessions et Utilisateurs. Lorsque vous sélectionnez des sessions, toutes les étapes doivent se produire au cours de la même session pour être comptabilisées. Si vous sélectionnez des utilisateurs, toutes les étapes doivent se produire dans la fenêtre de création de rapports sélectionnée pour le comptage.
* **Type de graphique**: Type de visualisation que vous souhaitez utiliser. Les options incluent les étapes.
* **Conversion à partir de**: Détermine le calcul du pourcentage d’une étape à l’autre. Les options incluent le calcul de la conversion à partir de la première étape ou de l’étape précédente.

## Appliquer la comparaison des temps

{{apply-time-comparison}}

![Comparaison du temps de fragment](../assets/friction-compare.png)

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **Intervalle**: Granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Ce paramètre n’a aucune incidence sur les vues qui n’ont pas de tendance, telles que Friction.
* **Date**: Les dates de début et de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.