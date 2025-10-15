---
title: Analyse d’impact de la première utilisation
description: Mesurez l’impact de la première utilisation des fonctionnalités sur les indicateurs clés.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 100%

---

# Analyse d’[!UICONTROL impact de la première utilisation] {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_firstuseimpact_button"
>title="Impact de la première utilisation"
>abstract="Mesurez l’impact de la première utilisation des fonctionnalités sur les indicateurs clés."

<!-- markdownlint-enable MD034 -->

L’analyse ![FirstUse](/help/assets/icons/FirstUse.svg) **[!UICONTROL Impact de la première utilisation]** présente une comparaison des performances des indicateurs clés avant et après la première utilisation d’une fonctionnalité de produit par une personne. L’axe horizontal de ce rapport est un intervalle de temps relatif avant et après l’événement, tandis que l’axe vertical mesure les indicateurs clés souhaités. Une barre verticale située au milieu du graphique représente le jour 0 correspondant au moment où une fonctionnalité est utilisée pour la première fois par une personne donnée. Comme les utilisateurs et utilisatrices n’adoptent pas toujours les fonctionnalités le même jour et que vos déploiements peuvent potentiellement s’étendre sur plusieurs jours, le jour 0 peut avoir une signification différente pour chaque personne.


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?quality=12&learn=on)


## Cas d’utilisation

Les cas d’utilisation de cette analyse sont les suivants :

* **Analyse des nouvelles fonctionnalités** : si vous lancez une nouvelle fonctionnalité dans votre produit, vous pouvez comparer les performances des indicateurs clés avant et après la première exposition des utilisateurs et utilisatrices à cette nouvelle fonctionnalité.
* **Déploiements par phases** : comme l’analyse recherche la première utilisation de la fonctionnalité plutôt qu’une date fixe, cette analyse est utile si vous échelonnez le déploiement de vos fonctionnalités au fil du temps.
* **Analyse de la nouvelle version du produit** : si vous lancez une nouvelle version de votre produit, vous pouvez comparer les indicateurs clés obtenus avant et après la première exposition des utilisateurs et utilisatrices à cette nouvelle version. Sélectionnez « n’importe quel événement » comme événement de première utilisation et filtrez-le sur votre propriété Numéro de version.
* **Améliorations apportées aux fonctionnalités existantes** : si vous apportez des améliorations à une fonctionnalité existante de votre produit, vous pouvez comparer les indicateurs clés obtenus avant et après la première exposition des utilisateurs et utilisatrices à ces nouvelles améliorations. Vous pouvez effectuer cette analyse d’une ou plusieurs façons en fonction de votre instrumentation de fonctionnalités.
   * Sélectionner un événement représentant l’amélioration comme événement de première utilisation
   * Sélectionner la date de début du déploiement des modifications
   * Segmenter l’analyse en fonction du groupe de personnes exposées aux améliorations
* **Efficacité de la campagne** : lorsqu’un utilisateur ou une utilisatrice clique sur une campagne donnée, vous pouvez comparer les performances des indicateurs clés avant et après l’interaction de l’utilisateur ou de l’utilisatrice avec cette campagne.

## Interface

Consultez [Interface](../overview.md#interface) pour une vue d’ensemble de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Vue]** : basculez entre cette analyse et [Version](release-impact.md).
* **[!UICONTROL Indicateurs clés]** : événements que vous souhaitez mesurer par utilisateur et utilisatrice. Chaque indicateur clé sélectionné est représenté sous la forme d’une ligne colorée. Une ligne représentant l’événement est ajoutée au tableau. Vous pouvez inclure jusqu’à trois événements.
* **[!UICONTROL Compté comme]** : méthode de comptage à appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Événements par utilisateur ou utilisatrice], [!UICONTROL Événements], [!UICONTROL Sessions] et [!UICONTROL Utilisateurs et utilisatrices].
* **[!UICONTROL Facteurs]** : cette analyse comporte deux facteurs :
   * **[!UICONTROL Date]** : date à laquelle vous souhaitez commencer à rechercher le premier événement d’utilisation qui s’est produit.
   * **[!UICONTROL Événement]** : événement sur lequel vous souhaitez rechercher la première utilisation et sur lequel centrer l’analyse.
* **[!UICONTROL Segments]** : segments que vous souhaitez mesurer. Le segment sélectionné filtre vos données pour se concentrer uniquement sur les personnes qui correspondent à vos critères de segment. Un seul segment est pris en charge pour cette analyse.

### Paramètres du graphique

L’analyse [!UICONTROL Impact de la première utilisation] propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : type de visualisation que vous souhaitez utiliser. Ligne est une option disponible.

### Période

Les sélections de date dans l’analyse [!UICONTROL Impact de la première utilisation] fonctionnent différemment des autres analyses, car l’analyse tourne autour de la date spécifiée dans le rail de requête. Les options disponibles sont les suivantes :

* **[!UICONTROL Intervalle]** : granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont les suivantes : [!UICONTROL Quotidien], [!UICONTROL Hebdomadaire], [!UICONTROL Mensuel] et [!UICONTROL Trimestriel]. La modification de l’intervalle affecte les options disponibles pour la période avant et après.
* **[!UICONTROL Période avant et après]** : durée de l’analyse avant et après le premier événement d’utilisation spécifié dans le rail de requête. Les options disponibles dépendent de l’[!UICONTROL intervalle] sélectionné.

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
