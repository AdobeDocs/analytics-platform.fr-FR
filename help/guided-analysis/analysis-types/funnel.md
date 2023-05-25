---
title: Entonnoir
description: Identifier les zones de friction à travers une séquence d’étapes.
source-git-commit: 9c4ee66d35182cb89678ae868ff35e364df361a9
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 3%

---

# Entonnoir

{{release-limited-testing}}

Le **Entonnoir** [Type d’analyse](overview.md) fournit une représentation visuelle d’un parcours utilisateur critique dans votre produit. L’axe horizontal représente chaque événement qu’un utilisateur doit toucher dans l’ordre. L’axe vertical représente le pourcentage d’utilisateurs ou de sessions qui ont touché chaque événement. Tous les points de contact doivent être définis dans l’ordre final, mais peuvent se produire à tout moment dans la fenêtre de création de rapports. Voici quelques cas pratiques de ce type d’analyse :

* **Analyse des conversions**: L’entonnoir vous permet d’analyser les conversions à chaque étape de l’entonnoir. En suivant le nombre d’utilisateurs qui passent d’une étape à l’autre, vous pouvez identifier les goulets d’étranglement présentant des taux de conversion inhabituels ou indésirables. Ces informations sont utiles pour comprendre où vous pouvez améliorer votre produit pour des résultats immédiats.
* **Optimisation de l’intégration**: L’entonnoir est utile pour optimiser le processus d’intégration de votre produit. En examinant le comportement des utilisateurs par rapport aux événements clés, vous pouvez identifier les étapes que les utilisateurs rencontrent ou ne parviennent pas à accomplir.
* **Adoption et engagement des fonctionnalités**: L’entonnoir vous aide à comprendre comment les utilisateurs interagissent avec des fonctionnalités spécifiques de votre produit. En analysant la progression des utilisateurs par le biais d’étapes liées aux fonctionnalités, vous pouvez évaluer les taux d’adoption des fonctionnalités et identifier les zones où les utilisateurs peuvent abandonner ou sous-utiliser certaines fonctionnalités. Vous pouvez ensuite utiliser ces informations pour vous concentrer sur les améliorations des fonctionnalités ou de l’interface utilisateur afin d’augmenter les taux d’adoption.
* **Évaluation de campagne**: L’entonnoir peut vous aider à mesurer l’efficacité des campagnes marketing. Vous pouvez créer un segment qui se concentre sur les utilisateurs qui ont touché une campagne donnée et comparer leur processus de conversion à d’autres campagnes ou au sein de votre produit dans son ensemble.

[Capture d’écran de l’entonnoir]

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **Étapes**: Points de contact de l’événement dont vous souhaitez effectuer le suivi. Chaque barre du graphique représente une étape. Vous pouvez inclure jusqu’à dix étapes.
* **Personnes**: Les segments que vous souhaitez comparer à l’entonnoir. Chaque segment sélectionné divise chaque étape en plusieurs barres. Chaque couleur représente un segment différent. Vous pouvez inclure jusqu’à trois segments.

## Types d’affichage

L’entonnoir offre les types de vue suivants. Vous pouvez modifier le type de vue à partir du menu déroulant situé en haut à gauche du graphique.

* **Friction**: Comparer les taux de conversion entre les étapes.

## Paramètres du graphique

L’entonnoir propose les paramètres de graphique suivants. Vous pouvez ajuster les paramètres du graphique à l’aide du menu entre le type d’affichage et le sélecteur de calendrier.

* **Mesure**: Mesure que vous souhaitez mesurer. Les options incluent Sessions et Utilisateurs.
* **Type de graphique**: Type de visualisation que vous souhaitez utiliser. La seule option est Etapes.
* **Conversion à partir de**: Détermine le calcul du pourcentage d’une étape à l’autre. Les options incluent le calcul de la conversion à partir de la première étape ou de l’étape précédente.

## Période

Les dates de début et de fin. Des paramètres prédéfinis de période sont disponibles à des fins pratiques ou vous pouvez utiliser le sélecteur de calendrier pour définir la date exacte de votre choix.
