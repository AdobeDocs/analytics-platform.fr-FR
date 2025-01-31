---
title: Analyse de l’entonnoir
description: Comparez les taux de conversion entre les étapes.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 3%

---

# Analyse de l’[!UICONTROL entonnoir] {#funnel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_funnel_button"
>title="Entonnoir"
>abstract="Comparez les taux de conversion entre les étapes."

<!-- markdownlint-enable MD034 -->

L’analyse ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL Funnel ]**fournit une représentation visuelle d’un parcours utilisateur critique dans votre produit. L’axe horizontal représente chaque étape qu’un utilisateur ou une utilisatrice doit franchir. L’axe vertical représente le pourcentage d’utilisateurs et d’utilisatrices ou de sessions à chaque étape. Toutes les étapes doivent être effectuées dans l’ordre souhaité, mais peuvent l’être à tout moment dans la fenêtre de création de rapports.

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?quality=12&learn=on){width="90%"}

## Cas d’utilisation

Les cas d’utilisation de cette analyse sont les suivants :

* **Analyse des conversions** : vous pouvez analyser les conversions à chaque étape de l’entonnoir, comme un passage en caisse au détail, une inscription à un compte, un flux d’abonnement ou tout autre parcours critique de votre expérience de produit. En suivant le nombre d’utilisateurs et d’utilisatrices qui passent d’une étape à l’autre, vous pouvez identifier les goulots d’étranglement qui présentent des taux de conversion inhabituels ou indésirables. Ces informations sont utiles pour savoir où améliorer votre parcours de produits et obtenir des résultats immédiats.
* **Analyse des expériences** : vous pouvez comparer les taux de conversion sur un entonnoir qui comporte des étapes facultatives où une expérience A/B est en cours d’exécution. Ces informations peuvent vous aider à déterminer quelle variation de l’entonnoir entraîne le taux de conversion le plus élevé, afin que vous puissiez encourager plus d’utilisateurs à emprunter cette voie.
* **Optimisation de l’intégration** : optimisez le processus d’intégration de votre produit en examinant le comportement des utilisateurs autour d’événements clés. Vous pouvez identifier les étapes avec lesquelles les utilisateurs ont du mal ou qu’ils ne terminent pas.
* **Adoption et engagement des fonctionnalités** : comprenez la manière dont les utilisateurs interagissent avec les fonctionnalités spécifiques de votre produit. L’analyse de la progression des utilisateurs et utilisatrices par le biais d’étapes liées aux fonctionnalités vous permet d’afficher les taux d’adoption et d’identifier les domaines dans lesquels les utilisateurs et utilisatrices peuvent sous-utiliser certaines fonctionnalités. Vous pouvez ensuite utiliser ces informations pour vous concentrer sur les améliorations des fonctionnalités afin d’augmenter les taux d’adoption.
* **Efficacité des canaux marketing** : mesurez l’efficacité des canaux marketing. Vous pouvez créer un segment qui se concentre sur les utilisateurs et utilisatrices qui ont interagi avec différents canaux marketing, tels que le référencement payant, l’affichage, le référencement naturel ou le ciblage direct. Vous pouvez ensuite comparer leurs parcours pour déterminer quel canal mène aux meilleurs résultats de produit.

## Interface

Voir [Interface](../overview.md#interface) pour une présentation de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Vue]** : basculer entre cette analyse et [Tendances de conversion](conversion-trends.md).
* **[!UICONTROL Étapes]** : points de contact d’événement dont vous souhaitez effectuer le suivi. Chaque barre du graphique représente une étape. Vous pouvez inclure jusqu’à dix étapes.
   * [!UICONTROL Comparer] : chaque étape fournit une option permettant de comparer plusieurs événements dans une seule étape d’entonnoir, créant un « entonnoir dupliqué ». Cette fonction vous permet de comparer le frottement de deux parcours côte à côte sans créer deux analyses distinctes. Cela s’avère utile lorsqu’il existe des options d’étape ou qu’une expérience A/B est en cours d’exécution dans l’entonnoir. Reportez-vous à la section [Entonnoir](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel) des tutoriels de Customer Journey Analytics pour visionner une vidéo expliquant comment comparer des entonnoirs.
* **[!UICONTROL Comptabilisée comme]** : la portée que vous souhaitez appliquer à l’entonnoir. Les options incluent [!UICONTROL Sessions] et [!UICONTROL Utilisateurs].
   * [!UICONTROL Sessions] : pour être comptabilisées, toutes les étapes doivent se produire au cours d’une même session.
   * [!UICONTROL Utilisateurs] : toutes les étapes doivent se produire dans la fenêtre de création de rapports sélectionnée pour être comptabilisées.
* **[!UICONTROL Segments]** : segments sur lesquels vous souhaitez comparer l’entonnoir. Chaque segment sélectionné divise chaque étape en plusieurs barres. Chaque couleur représente un segment différent. Vous pouvez inclure jusqu’à trois segments.

### Paramètres du graphique

L’analyse [!UICONTROL entonnoir] offre les paramètres de graphique suivants, qui peuvent être ajustés dans le menu au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : le type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Étapes].
* **[!UICONTROL Conversion de]** : détermine le calcul du pourcentage d’une étape à l’autre. Les options incluent le calcul de la conversion à partir de la [!UICONTROL Première étape] ou [!UICONTROL Étape précédente].

### Comparaison de temps

{{apply-time-comparison}}



### Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Ce paramètre n’a aucune incidence sur les analyses hors tendances telles que [Entonnoir](funnel.md).
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les périodes personnalisées enregistrées précédemment sont disponibles pour votre commodité. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une période fixe.

<!--
## Example

See below for an example of the analysis.

![Funnel time compare](../assets/funnel-compare.png)

-->
