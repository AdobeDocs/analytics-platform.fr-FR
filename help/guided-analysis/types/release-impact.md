---
title: Analyse d’impact de la nouvelle version
description: Comparez les performances sur des périodes égales avant et après le lancement.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: 7ccc9f28acf08fb49d86005abb7fbb648a1564ce
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 5%

---

# [!UICONTROL Analyse d’impact sur les versions]

L’analyse ![Impact sur les versions](/help/assets/icons/Release.svg) **[!UICONTROL présente une comparaison des indicateurs clés effectués avant et après une date donnée.]** L’axe horizontal de ce rapport est un intervalle de temps, tandis que l’axe vertical mesure les indicateurs clés souhaités. Une barre verticale au milieu du graphique représente la date que vous souhaitez comparer avant et après. Cette date représente généralement une modification notable du produit par rapport auquel vous souhaitez effectuer une mesure, telle qu’une mise à jour du produit ou un lancement de campagne.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?learn=on)

## Cas d’utilisation

Voici quelques cas pratiques de cette analyse :

* **Évaluation globale des performances :** La comparaison d’indicateurs clés globaux, tels que les mesures d’engagement, peut vous aider à déterminer si une version donnée a globalement réussi.
* **Surveillance** : effectuez le suivi des mesures vitales que vous prévoyez de rester inchangées lorsque des modifications sont apportées, telles que le temps de chargement ou le nombre de connexions. Utilisez cette analyse pour les comparer avant et après une version afin de vous assurer qu’elle n’a eu aucune conséquence imprévue.
* **adoption des fonctionnalités** : si une mise à jour de produit est axée sur l’amélioration d’une certaine fonctionnalité, vous pouvez utiliser cette analyse pour comparer directement l’utilisation de cette fonctionnalité avant et après la mise à jour du produit.
* **Détection des bogues** : le suivi du nombre d’erreurs avant et après une version peut fournir un indicateur précoce des problèmes des clients. Si vous constatez une augmentation des erreurs immédiatement après une version, vous pouvez collaborer avec les équipes d’ingénierie ou de développement pour identifier et corriger le problème, afin d’éviter tout impact supplémentaire sur les clients.

## Interface

Voir [Interface](../overview.md#interface) pour un aperçu de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Vue]** : basculez entre cette analyse et [Première utilisation impact](first-use-impact.md).
* **[!UICONTROL Indicateurs clés]** : événements que vous souhaitez mesurer par utilisateur. Chaque indicateur de clé sélectionné est représenté sous la forme d’une ligne colorée. Une ligne représentant l’événement est ajoutée au tableau. Vous pouvez inclure jusqu’à trois événements.
* **[!UICONTROL Compté comme]** : méthode de comptage que vous souhaitez appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Événements par utilisateur], [!UICONTROL Pourcentage d&#39;utilisateurs], [!UICONTROL Événements], [!UICONTROL Sessions] et [!UICONTROL Utilisateurs].
* **[!UICONTROL Facteurs]** : date à comparer avant et après.
* **[!UICONTROL Segments]** : segment que vous souhaitez mesurer. Le segment sélectionné filtre vos données afin de se concentrer uniquement sur les individus qui correspondent à vos critères de segment.

### Paramètres du graphique

L’analyse [!UICONTROL Impact sur les versions] offre les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Line] et [!UICONTROL Bar].

### Période

La sélection des dates dans l’analyse d’impact fonctionne différemment des autres analyses, puisque le rapport tourne autour de la date spécifiée dans le rail de requête. Les options disponibles sont les suivantes :

* **[!UICONTROL Intervalle]** : granularité de date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont les suivantes : [!UICONTROL Quotidien], [!UICONTROL Hebdomadaire], [!UICONTROL Mensuel] et [!UICONTROL Trimestriel]. La modification de l’intervalle affecte les options disponibles pour les périodes Avant et Après.
* **[!UICONTROL Avant et après la période]** : durée d’analyse avant et après la date spécifiée dans le rail de requête. Les options disponibles dépendent de la sélection [!UICONTROL Intervalle] .


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
