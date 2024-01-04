---
title: Vue Friction
description: Comparer les taux de conversion entre les étapes.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Guided Analysis
keywords: analytics du produit
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 1%

---

# [!UICONTROL Friction] view

La variable **[!UICONTROL Friction]** La vue fournit une représentation visuelle d’un parcours utilisateur critique dans votre produit. L’axe horizontal représente chaque étape qu’un utilisateur doit franchir. L’axe vertical représente le pourcentage d’utilisateurs ou de sessions à chaque étape. Toutes les étapes doivent être effectuées dans l’ordre final, mais peuvent se produire à tout moment dans la fenêtre de création de rapports.

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?learn=on)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Analyse des conversions**: vous pouvez analyser les conversions à chaque étape de l’entonnoir. En suivant le nombre d’utilisateurs qui passent d’une étape à l’autre, vous pouvez identifier les goulets d’étranglement présentant des taux de conversion inhabituels ou indésirables. Ces informations sont utiles pour comprendre où vous pouvez améliorer votre produit pour des résultats immédiats.
* **Optimisation de l’intégration**: optimisez le processus d’intégration de votre produit en examinant le comportement des utilisateurs par rapport aux événements clés. Vous pouvez identifier les étapes que les utilisateurs rencontrent ou ne parviennent pas à accomplir.
* **Adoption et engagement des fonctionnalités**: comprendre comment les utilisateurs interagissent avec des fonctionnalités spécifiques de votre produit. En analysant la progression des utilisateurs par le biais d’étapes liées aux fonctionnalités, vous pouvez évaluer les taux d’adoption des fonctionnalités et identifier les zones où les utilisateurs peuvent abandonner ou sous-utiliser certaines fonctionnalités. Vous pouvez ensuite utiliser ces informations pour vous concentrer sur les améliorations des fonctionnalités afin d’augmenter les taux d’adoption.
* **Évaluation de campagne**: mesurez l’efficacité des campagnes marketing. Vous pouvez créer un segment qui se concentre sur les utilisateurs qui ont touché une campagne donnée et comparer leur processus de conversion à d’autres campagnes ou au sein de votre produit dans son ensemble.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Étapes]**: points de contact de l’événement dont vous souhaitez effectuer le suivi. Chaque barre du graphique représente une étape. Vous pouvez inclure jusqu’à dix étapes.
* **[!UICONTROL Personnes]**: segments que vous souhaitez comparer à l’entonnoir. Chaque segment sélectionné divise chaque étape en plusieurs barres. Chaque couleur représente un segment différent. Vous pouvez inclure jusqu’à trois segments.

## Paramètres du graphique

La vue Friction propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Mesure]**: la portée que vous souhaitez appliquer à l’entonnoir. Les options incluent Sessions et Utilisateurs. Lorsque vous sélectionnez des sessions, toutes les étapes doivent se produire au cours de la même session pour être comptabilisées. Si vous sélectionnez des utilisateurs, toutes les étapes doivent se produire dans la fenêtre de création de rapports sélectionnée pour le comptage.
* **[!UICONTROL Type de graphique]**: type de visualisation que vous souhaitez utiliser. Les options incluent les étapes.
* **[!UICONTROL Conversion depuis]**: détermine le calcul du pourcentage d’une étape à l’autre. Les options incluent le calcul de la conversion à partir de la première étape ou de l’étape précédente.

## Appliquer la comparaison des temps

{{apply-time-comparison}}

![Comparaison du temps de fragment](../assets/friction-compare.png)

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de tendances. Ce paramètre n’a aucune incidence sur les vues qui n’ont pas de tendance, telles que Friction.
* **[!UICONTROL Date]**: date de début et date de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
