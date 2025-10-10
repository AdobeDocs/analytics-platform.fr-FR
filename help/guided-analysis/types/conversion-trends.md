---
title: Analyse des tendances de conversion
description: Suivez l’évolution des taux de conversion au fil du temps.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 100%

---

# Analyse des [!UICONTROL tendances de conversion] {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_conversiontrends_button"
>title="Tendances de conversion"
>abstract="Suivez l’évolution des taux de conversion au fil du temps."

<!-- markdownlint-enable MD034 -->


L’analyse ![Tendances de conversion](/help/assets/icons/ConversionTrends.svg) **[!UICONTROL Tendances de conversion]** fournit une visualisation des tendances des taux de conversion au fil du temps. L’axe horizontal est un intervalle de temps, tandis que l’axe vertical représente le taux de conversion.


>[!VIDEO](https://video.tv.adobe.com/v/3423486/?quality=12&learn=on&captions=fre_fr)


## Cas d’utilisation

Les cas d’utilisation de cette analyse sont les suivants :

* **Suivre les efforts d’optimisation** : après avoir identifié les goulets d’étranglement clés que vous souhaitez améliorer à l’aide de l’analyse [Entonnoir](funnel.md), vous pouvez utiliser cette analyse pour suivre l’impact de ces optimisations sur le taux de conversion au fil du temps.
* **Évaluation des tests A/B** : évaluez l’efficacité des tests A/B ou des expériences menées dans le contexte d’un entonnoir. En comparant les taux de conversion entre différentes variations, vous pouvez facilement déterminer quels tests offrent les taux de conversion les plus élevés, ce qui mène à des décisions pilotées par les données concernant les variations à implémenter de manière permanente.
* **Évaluation des campagnes au fil du temps** : mesurez l’efficacité des campagnes marketing au fil du temps. Vous pouvez créer un segment qui se concentre sur les utilisateurs et utilisatrices qui ont été en contact avec une campagne donnée et comparer leurs taux de conversion avec d’autres campagnes. Vous pouvez également comparer les taux de conversion actuels avec des campagnes similaires exécutées dans le passé.

## Interface

Consultez [Interface](../overview.md#interface) pour une vue d’ensemble de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Vue]** : basculez entre cette analyse et [Entonnoir](funnel.md).
* **[!UICONTROL Étapes]** : points de contact d’événement dont vous souhaitez effectuer le suivi. Chaque barre du graphique représente une étape. Vous pouvez inclure jusqu’à dix étapes.
* **[!UICONTROL Compté comme]** : méthode de comptage à appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Utilisateurs et utilisatrices] et [!UICONTROL Sessions].
* **[!UICONTROL Segments]** : segments sur lesquels vous souhaitez comparer l’entonnoir. Chaque segment sélectionné divise chaque étape en plusieurs barres. Chaque couleur représente un segment différent. Vous pouvez inclure jusqu’à trois segments.

### Paramètres du graphique

L’analyse [!UICONTROL Tendances de conversion] propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : type de visualisation que vous souhaitez utiliser. Les options comprennent [!UICONTROL Ligne].
* **[!UICONTROL Conversion de]** : détermine le calcul du pourcentage d’une étape à l’autre. Les options incluent le calcul de la conversion à partir de la [!UICONTROL Première étape] ou de l’[!UICONTROL Étape précédente].

>[!NOTE]
>
>La colonne **Moyenne** du tableau Analyse des tendances de conversion diffère de la colonne **Total** du tableau [Analyse en entonnoir](funnel.md). La première est une moyenne des colonnes de l’intervalle (par exemple, la moyenne des taux de conversion quotidiens), tandis que la seconde est un calcul agrégé sur l’ensemble de la période.

### Comparaison de temps

{{apply-time-comparison}}


### Période

Période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont Horaire, Quotidien, Hebdomadaire, Mensuel et Trimestriel. Une même période peut avoir des intervalles différents, ce qui affecte le nombre de points de données dans le graphique et le nombre de colonnes du tableau. Par exemple, l’affichage d’une analyse s’étendant sur trois jours avec une granularité quotidienne n’affiche que trois points de données, tandis qu’une analyse s’étendant sur trois jours avec une granularité horaire affiche 72 points de données.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les périodes personnalisées enregistrées précédemment sont disponibles pour votre commodité. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une période fixe.

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
