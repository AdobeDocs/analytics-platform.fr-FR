---
title: Première utilisation
description: Mesurer l’impact de la première utilisation des fonctionnalités sur les indicateurs clés.
feature: Guided Analysis
source-git-commit: 4121c199e4a5050d84f57c69d7fb1d7b05007fcd
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 3%

---

# [!UICONTROL Première utilisation] view

Le **[!UICONTROL Première utilisation]** La vue présente une comparaison des performances des indicateurs clés avant et après l’utilisation par un utilisateur d’une fonctionnalité de produit pour la première fois. L’axe horizontal de ce rapport est un intervalle de temps relatif avant et après l’événement, tandis que l’axe vertical mesure les indicateurs clés souhaités. Une barre verticale située au milieu du graphique représente le jour 0 lorsqu’une fonction est utilisée pour la première fois par un utilisateur donné. Comme les utilisateurs n’adoptent pas toujours les fonctionnalités le même jour et que vos déploiements peuvent se produire sur plusieurs jours, le jour 0 signifie quelque chose de différent pour chaque utilisateur.

Voir [!UICONTROL Première utilisation] vue en action

>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Nouvelle analyse des fonctionnalités**: Si vous lancez une nouvelle fonctionnalité dans votre produit, vous pouvez comparer les performances des indicateurs clés avant et après la première exposition des utilisateurs à cette nouvelle fonctionnalité.
* **Déploiements par phases**: Étant donné que l’analyse recherche la première utilisation de la fonctionnalité plutôt qu’une date fixe, cet affichage s’avère particulièrement utile si vous déployez vos fonctionnalités progressivement sur une période donnée.
* **Nouvelle analyse des versions de produit**: Si vous lancez une nouvelle version de votre produit, vous pouvez comparer les performances des indicateurs clés avant et après l’exposition initiale des utilisateurs à cette nouvelle version. Sélectionnez &quot;any event&quot; comme événement de première utilisation et filtrez-le sur votre propriété Version Number.
* **Améliorations des fonctionnalités existantes**: Si vous apportez des améliorations à une fonctionnalité existante de votre produit, vous pouvez comparer les performances des indicateurs clés avant et après que les utilisateurs aient été exposés à ces nouvelles améliorations pour la première fois. Vous pouvez effectuer cette analyse de plusieurs façons en fonction de l’instrumentation de votre fonction. 1) Sélectionnez un événement qui représente l’amélioration comme votre premier événement d’utilisation, et/ou 2) Sélectionnez la date à laquelle les modifications ont commencé à se déployer, et/ou 3) Segmentez l’analyse avec le groupe de personnes exposées aux améliorations.
* **Efficacité des campagnes**: Lorsqu’un utilisateur clique à partir d’une campagne donnée, vous pouvez comparer les indicateurs clés effectués avant et après l’interaction de l’utilisateur avec cette campagne.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Indicateurs clés]**: Événements que vous souhaitez mesurer par utilisateur. Chaque indicateur de clé sélectionné est représenté sous la forme d’une ligne colorée. Une ligne représentant l’événement est ajoutée au tableau. Vous pouvez inclure jusqu’à trois événements.
* **[!UICONTROL Facteurs]**: Ce point de vue comporte deux facteurs :
   * **[!UICONTROL Date]**: Jusqu’où vous souhaitez commencer à rechercher le premier événement d’utilisation qui s’est produit.
   * **[!UICONTROL Événement]**: L’événement dont vous souhaitez rechercher la première utilisation, pour centrer l’analyse.
* **[!UICONTROL Personnes]**: Le segment que vous souhaitez mesurer. Le segment sélectionné filtre vos données afin de se concentrer uniquement sur les individus qui correspondent à vos critères de segment.

## Paramètres du graphique

La vue Première utilisation offre les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Mesure]**: Mesure que vous souhaitez mesurer. Les options incluent [!UICONTROL Événements par utilisateur], [!UICONTROL Événements], [!UICONTROL Sessions], et [!UICONTROL Utilisateurs].
* **[!UICONTROL Type de graphique]**: Type de visualisation que vous souhaitez utiliser. Les options comprennent Ligne.

## Période

Les sélections de dates dans l’analyse d’impact fonctionnent différemment des autres types d’analyse, car l’analyse se concentre sur la date spécifiée dans le rail de requête. Les options disponibles sont les suivantes :

* **[!UICONTROL Intervalle]**: Granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont les suivantes : [!UICONTROL Quotidien], [!UICONTROL Hebdomadaire], [!UICONTROL Mensuel], et [!UICONTROL Trimestriel]. La modification de l’intervalle affecte les options disponibles pour les périodes Avant et Après.
* **[!UICONTROL Avant et après la période]**: La durée d’analyse avant et après le premier événement d’utilisation spécifié dans le rail de requête. Les options disponibles dépendent de la variable [!UICONTROL Intervalle] sélection.
