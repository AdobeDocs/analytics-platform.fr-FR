---
title: Analyse des tendances
description: Mesurez l’interaction client au fil du temps.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: e42f04eaa06a761803e76b64a5a16674fb4af57d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Analyse des [!UICONTROL tendances] {#trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_trends_button"
>title="Tendances"
>abstract="Mesurez l’interaction client au fil du temps."

<!-- markdownlint-enable MD034 -->

L’analyse ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Tendances]** fournit des informations précieuses sur les performances de votre produit ou le comportement de vos utilisateurs et utilisatrices au fil du temps. L’axe horizontal de ce rapport est un intervalle de temps, tandis que l’axe vertical mesure les événements souhaités.


>[!VIDEO](https://video.tv.adobe.com/v/3421666/?quality=12&learn=on)

## Cas d’utilisation

Les cas d’utilisation de cette analyse sont les suivants :

* **Évaluer les performances du produit** : les tendances vous permettent d’évaluer les performances globales de votre produit sur une période donnée. En analysant des mesures telles que l’interaction client, l’adoption ou les taux de conversion, vous pouvez déterminer si les performances de votre produit s’améliorent, stagnent ou déclinent.
* **Adoption de fonctionnalités** : les tendances vous permettent de comprendre comment les utilisateurs et utilisatrices adoptent les nouvelles fonctionnalités ou mises à jour que vous publiez. Vous pouvez déterminer les fonctionnalités les plus populaires et celles qui doivent être améliorées. Ces informations vous permettent de prendre des décisions basées sur les données concernant les fonctionnalités autour desquelles prioriser vos efforts de développement.
* **Comportement des utilisateurs et utilisatrices** : les tendances peuvent fournir des informations sur le comportement des utilisateurs et utilisatrices au fil du temps. En examinant les actions spécifiques effectuées par les utilisateurs et utilisatrices, vous pouvez identifier des modèles sur lesquels les utilisateurs et utilisatrices risquent de décrocher. Vous pouvez combiner les informations de cette analyse avec [Entonnoir](funnel.md) pour obtenir encore plus d’informations sur le comportement.
* **Tests et expérimentation A/B** : si vous exécutez des tests A/B dans votre produit, vous pouvez utiliser les tendances pour évaluer quels tests sont les plus réussis au fil du temps.

## Interface

Consultez [Interface](../overview.md#interface) pour une vue d’ensemble de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Vue]** : basculez entre cette analyse et [Fréquence](frequency.md).
* **[!UICONTROL Événements et mesures]** : événements ou mesures que vous souhaitez mesurer. Chaque sélection est représentée sous la forme d’une série de graphiques et d’une ligne de tableau. Les événements et les mesures ne peuvent pas être combinés dans la requête ; une fois que vous avez effectué votre première sélection, les sélections de requête restantes doivent être du même type. Vous pouvez inclure un maximum de cinq sélections.
* **[!UICONTROL Compté comme]** : méthode de comptage à appliquer aux événements sélectionnés. <ul><li>**[!UICONTROL Options]** incluent [!UICONTROL Utilisateurs], [!UICONTROL Événements], [!UICONTROL Sessions], [!UICONTROL Pourcentage d’utilisateurs], [!UICONTROL Événements par session] et [!UICONTROL Événements par utilisateur].</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} Des options **[!UICONTROL B2B supplémentaires]** sont disponibles pour Customer Journey Analytics B2B edition : [!UICONTROL Comptes globaux], [!UICONTROL Comptes], [!UICONTROL Groupes d’achats], [!UICONTROL Opportunités], [!UICONTROL Pourcentage de comptes globaux], [!UICONTROL Pourcentage de comptes], [!UICONTROL Pourcentage de groupes d’achats], [!UICONTROL Pourcentage d’opportunités], [!UICONTROL Événements par compte global], [!UICONTROL Événements par compte], [!UICONTROL Événements par groupe d’achats] et [!UICONTROL Événements par opportunité].</li></ul>Les options Comptabilisé comme s’appliquent uniquement aux requêtes d’événement et sont supprimées pour les requêtes de mesure.
* **[!UICONTROL Segments]** : segments que vous souhaitez mesurer. Chaque segment sélectionné double le nombre de séries de graphiques et de lignes de tableau. Vous pouvez inclure un maximum de cinq segments.
* **[!UICONTROL Propriété de répartition]** : répartit les lignes de la série de graphiques et du tableau selon les valeurs de la propriété sélectionnée. Une seule propriété de répartition est prise en charge. Les 20 premières valeurs apparaissent dans le tableau, et jusqu’à dix valeurs peuvent être affichées dans le graphique. Vous pouvez masquer ou afficher une ligne dans le graphique en appuyant sur l’icône ![Icône afficher/masquer](../assets/hide-in-chart.png).

### Paramètres du graphique

L’analyse [!UICONTROL Tendances] propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : type de visualisation que vous souhaitez utiliser. Les options disponibles sont Ligne, Barres, Barres empilées et Aires empilées.

### Chevauchements

Ajoutez des données supplémentaires au graphique. Lorsque plusieurs séries sont visibles sur le graphique, les superpositions n’apparaissent que lorsque vous survolez le graphique.

* **[!UICONTROL Détection des anomalies]** : exécute la [détection des anomalies](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) sur l’analyse des tendances. Les valeurs aberrantes apparaissent sous la forme de points que vous pouvez survoler pour plus d’informations.
* **[!UICONTROL Incrustation de lignes de tendance]** : ajoute une courbe de tendance au graphique pour dépeindre un motif plus clair dans les données.
   * [!UICONTROL Linéaire] : crée une ligne de régression droite. Idéal pour les données linéaires simples qui augmentent ou diminuent à un taux constant. Équation : `y = a + b * x`
   * [!UICONTROL Logarithmique] : crée une ligne de régression courbe. Idéal pour les données qui augmentent ou diminuent rapidement, puis se stabilisent. Équation : `y = a + b * log(x)`
   * [!UICONTROL Moyenne glissante] : crée une courbe de tendance lisse basée sur un ensemble de moyennes. Connue également sous le nom de moyenne mobile, une moyenne glissante utilise un nombre de points de données (déterminé par votre sélection), calcule leur moyenne et utilise cette moyenne comme point dans la ligne. Par exemple, une moyenne glissante de 7 jours ou de 4 semaines. Les options de moyenne glissante disponibles dépendent de l’intervalle et de la période sélectionnés.

### Comparaison de temps

{{apply-time-comparison}}


### Période

Période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont Horaire, Quotidien, Hebdomadaire, Mensuel et Trimestriel. Une même période peut avoir différents intervalles qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse s’étendant sur trois jours avec une granularité quotidienne n’affiche que trois points de données, tandis qu’une analyse s’étendant sur trois jours avec une granularité horaire affiche 72 points de données.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les périodes personnalisées enregistrées précédemment sont disponibles pour votre commodité. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une période fixe.


<!--

## Example

See below for an example of the analysis.

![Trends compare](../assets/trends-compare.png)

-->