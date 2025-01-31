---
title: Analyse d’impact de la nouvelle version
description: Comparez les performances sur des périodes égales avant et après la version.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 10%

---

# Analyse d’[!UICONTROL impact de la nouvelle version] {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_releaseimpact_button"
>title="Impact de la version"
>abstract="Comparez les performances sur des périodes égales avant et après la version."

<!-- markdownlint-enable MD034 -->

L’analyse ![Version](/help/assets/icons/Release.svg) **[!UICONTROL Impact de la version]** présente une comparaison des performances des indicateurs clés avant et après une date donnée. L’axe horizontal de ce rapport est un intervalle de temps, tandis que l’axe vertical mesure les indicateurs clés souhaités. Une barre verticale située au milieu du graphique représente la date à laquelle vous souhaitez effectuer une comparaison, avant et après. Cette date représente généralement un changement notable du produit par rapport auquel vous souhaitez mesurer, tel qu’une mise à jour du produit ou un lancement de campagne.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?quality=12&learn=on)

## Cas d’utilisation

Les cas d’utilisation de cette analyse sont les suivants :

* **Évaluation globale des performances :** la comparaison d’indicateurs clés globaux, tels que les mesures d’engagement, peut vous aider à déterminer si une version donnée a globalement réussi.
* **Surveillance** : effectuez le suivi des mesures essentielles qui devraient rester fixes lorsque des modifications sont apportées, telles que le temps de chargement ou le nombre de connexions. Utilisez cette analyse pour les comparer avant et après une publication afin de vous assurer qu’elle n’a eu aucune conséquence inattendue.
* **Adoption des fonctionnalités** : si une mise à jour du produit se concentre sur l’amélioration d’une certaine fonctionnalité, vous pouvez utiliser cette analyse pour comparer directement l’utilisation de cette fonctionnalité avant et après la mise à jour du produit.
* **Détection des bogues** : le suivi du nombre d’erreurs avant et après une version peut fournir un indicateur précoce des problèmes client. Si vous constatez une augmentation du nombre d’erreurs immédiatement après une publication, vous pouvez collaborer avec les équipes d’ingénierie ou de développement pour identifier et corriger le problème, afin d’éviter tout impact supplémentaire sur les clients.

## Interface

Voir [Interface](../overview.md#interface) pour une présentation de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Vue]** : basculer entre cette analyse et [Impact de la première utilisation](first-use-impact.md).
* **[!UICONTROL Indicateurs clés]** : événements que vous souhaitez mesurer par utilisateur et utilisatrice. Chaque indicateur clé sélectionné est représenté sous la forme d’une ligne colorée. Une ligne représentant l’événement est ajoutée au tableau. Vous pouvez inclure jusqu’à trois événements.
* **[!UICONTROL Compté comme]** : méthode de comptage à appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Événements par utilisateur], [!UICONTROL Pourcentage d’utilisateurs], [!UICONTROL Événements], [!UICONTROL Sessions] et [!UICONTROL Utilisateurs].
* **[!UICONTROL Facteurs]** : date à comparer avant et après la date.
* **[!UICONTROL Segments]** : segment que vous souhaitez mesurer. Le segment sélectionné filtre vos données pour se concentrer uniquement sur les individus qui correspondent à vos critères de segment.

### Paramètres du graphique

L’analyse [!UICONTROL Impact des versions] propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : le type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Ligne] et [!UICONTROL Barre].

### Période

La sélection de la date dans l’analyse d’impact fonctionne différemment des autres analyses, puisque le rapport tourne autour de la date spécifiée dans le rail de requête. Les options disponibles sont les suivantes :

* **[!UICONTROL Intervalle]** : granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont les suivantes : [!UICONTROL Quotidien], [!UICONTROL Hebdomadaire], [!UICONTROL Mensuel] et [!UICONTROL Trimestriel]. La modification de l’intervalle affecte les options disponibles pour la période avant et après.
* **[!UICONTROL Période avant et après]** : durée de l’analyse avant et après la date spécifiée dans le rail de requête. Les options disponibles dépendent de la sélection de [!UICONTROL  Intervalle ].


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
