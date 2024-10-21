---
title: Analyse de l’entonnoir
description: Comparez les taux de conversion entre les étapes.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: f71abfb76a22171004a6f2a501c8ec70d8485478
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 2%

---

# Analyse [!UICONTROL Entonnoir]

L’analyse ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL Funnel ]**fournit une représentation visuelle d’un parcours utilisateur critique dans votre produit. L’axe horizontal représente chaque étape qu’un utilisateur doit franchir. L’axe vertical représente le pourcentage d’utilisateurs ou de sessions à chaque étape. Toutes les étapes doivent être effectuées dans l’ordre final, mais peuvent se produire à tout moment dans la fenêtre de création de rapports.

+++ Vidéo de démonstration

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?learn=on){width="90%"}

+++

![Comparaison de l’heure de l’entonnoir](../assets/funnel-compare.png)

## Cas d’utilisation

Voici quelques cas pratiques de cette analyse :

* **Analyse des conversions** : vous pouvez analyser les conversions à chaque étape de l’entonnoir, comme le passage en caisse au détail, l’inscription au compte, le flux d’abonnement ou tout autre parcours critique de votre expérience de produit. En suivant le nombre d’utilisateurs qui passent d’une étape à l’autre, vous pouvez identifier les goulets d’étranglement présentant des taux de conversion inhabituels ou indésirables. Ces informations sont utiles pour comprendre où vous pouvez améliorer votre parcours de produits pour des résultats immédiats.
* **Analyse de l’expérience** : vous pouvez comparer des taux de conversion sur un entonnoir qui comporte des étapes ou des étapes facultatives où une expérience A/B est en cours d’exécution. Ces informations peuvent vous aider à déterminer la variation de l’entonnoir qui génère le taux de conversion le plus élevé, afin que vous puissiez encourager plus d’utilisateurs à suivre ce chemin.
* **Optimisation de l’intégration** : optimisez le processus d’intégration de votre produit en examinant le comportement des utilisateurs par rapport aux événements clés. Vous pouvez identifier les étapes que les utilisateurs rencontrent ou ne parviennent pas à accomplir.
* **Adoption et engagement des fonctionnalités** : comprendre comment les utilisateurs interagissent avec des fonctionnalités spécifiques de votre produit. L’analyse de la progression des utilisateurs par le biais d’étapes liées aux fonctionnalités vous permet d’afficher les taux d’adoption et d’identifier les zones où les utilisateurs peuvent sous-utiliser certaines fonctionnalités. Vous pouvez ensuite utiliser ces informations pour vous concentrer sur les améliorations des fonctionnalités afin d’augmenter les taux d’adoption.
* **Efficacité des canaux marketing** : mesurez l’efficacité des canaux marketing. Vous pouvez créer un segment qui se concentre sur les utilisateurs qui ont interagi avec différents canaux marketing, tels que le référencement payant, l’affichage, le référencement naturel ou direct. Vous pouvez ensuite comparer leurs parcours pour déterminer quel canal génère les meilleurs résultats de produit.

## Interface

Voir [Interface](../overview.md#interface) pour un aperçu de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Afficher]** : basculez entre cette analyse et [Tendances de conversion](conversion-trends.md).
* **[!UICONTROL Steps]** : points de contact de l’événement dont vous souhaitez effectuer le suivi. Chaque barre du graphique représente une étape. Vous pouvez inclure jusqu’à dix étapes.
   * [!UICONTROL Comparer] : chaque étape fournit une option pour comparer plusieurs événements dans une seule étape de l’entonnoir, créant un &quot;entonnoir fourré&quot;. Cette fonctionnalité permet de comparer la friction de deux parcours côte à côte sans créer deux analyses distinctes. Elle est utile lorsqu’il existe des options d’étape ou qu’une expérience A/B est exécutée dans l’entonnoir. Consultez les tutoriels [Entonnoir](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel) dans le Customer Journey Analytics pour une vidéo qui explique comment comparer des entonnoirs.
* **[!UICONTROL Compté comme]** : la portée que vous souhaitez appliquer à l’entonnoir. Les options incluent [!UICONTROL Sessions] et [!UICONTROL Utilisateurs].
   * [!UICONTROL Sessions] : toutes les étapes doivent se produire au cours de la même session pour être comptabilisées.
   * [!UICONTROL Utilisateurs] : toutes les étapes doivent se produire dans la fenêtre de création de rapports sélectionnée pour être comptabilisées.
* **[!UICONTROL Segments]** : segments que vous souhaitez comparer à l’entonnoir. Chaque segment sélectionné divise chaque étape en plusieurs barres. Chaque couleur représente un segment différent. Vous pouvez inclure jusqu’à trois segments.

### Paramètres du graphique

L’analyse [!UICONTROL Entonnoir] offre les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Steps].
* **[!UICONTROL Conversion from]** : détermine le calcul du pourcentage d’une étape à l’autre. Les options incluent le calcul de la conversion à partir de la [!UICONTROL première étape] ou de l’ [!UICONTROL étape précédente].

### Comparaison de temps

{{apply-time-comparison}}



### Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de date selon laquelle vous souhaitez afficher les données de tendance. Ce paramètre n’a aucune incidence sur les analyses non de tendance telles que [Entonnoir](funnel.md).
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
