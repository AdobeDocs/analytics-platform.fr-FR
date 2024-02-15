---
title: Première utilisation vue
description: Mesurez l’impact de la première utilisation de fonctionnalités sur les indicateurs clés.
feature: Guided Analysis
keywords: analytics du produit
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: de78569389f5a9d74603870e72b4f3871ef4aa92
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 1%

---

# [!UICONTROL Première utilisation] view

La variable **[!UICONTROL Première utilisation]** La vue présente une comparaison des performances des indicateurs clés avant et après l’utilisation par un utilisateur d’une fonctionnalité de produit pour la première fois. L’axe horizontal de ce rapport est un intervalle de temps relatif avant et après l’événement, tandis que l’axe vertical mesure les indicateurs clés souhaités. Une barre verticale située au milieu du graphique représente le jour 0 lorsqu’une fonction est utilisée pour la première fois par un utilisateur donné. Comme les utilisateurs n’adoptent pas toujours les fonctionnalités le même jour et que vos déploiements peuvent éventuellement se produire sur plusieurs jours, le jour 0 peut signifier quelque chose de différent pour chaque utilisateur.

>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Nouvelle analyse des fonctionnalités**: si vous lancez une nouvelle fonctionnalité dans votre produit, vous pouvez comparer les performances des indicateurs clés avant et après la première exposition des utilisateurs à cette nouvelle fonctionnalité.
* **Déploiements par phases**: dans la mesure où l’analyse recherche la première utilisation de la fonctionnalité plutôt qu’une date fixe, cet affichage s’avère utile si vous mettez progressivement le déploiement de vos fonctionnalités au fil du temps.
* **Nouvelle analyse des versions de produit**: si vous lancez une nouvelle version de votre produit, vous pouvez comparer les performances des indicateurs clés avant et après l’exposition initiale des utilisateurs à cette nouvelle version. Sélectionnez &quot;any event&quot; comme événement de première utilisation et filtrez-le sur votre propriété Version Number.
* **Améliorations des fonctionnalités existantes**: si vous apportez des améliorations à une fonctionnalité existante de votre produit, vous pouvez comparer les performances des indicateurs clés avant et après que les utilisateurs aient été exposés à ces nouvelles améliorations pour la première fois. Vous pouvez effectuer cette analyse d’une ou de plusieurs façons en fonction de l’instrumentation de votre fonction.
   * Sélectionnez un événement représentant l’amélioration comme événement de première utilisation.
   * Sélectionnez la date à laquelle les modifications ont commencé à se déployer.
   * Segmenter l’analyse avec le groupe de personnes exposées aux améliorations
* **Efficacité des campagnes**: lorsqu’un utilisateur clique à partir d’une campagne donnée, vous pouvez comparer les indicateurs clés effectués avant et après l’interaction de l’utilisateur avec cette campagne.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Affichage]**: basculez entre ce type de vue et [Version](release.md).
* **[!UICONTROL Indicateurs clés]**: événements que vous souhaitez mesurer par utilisateur. Chaque indicateur de clé sélectionné est représenté sous la forme d’une ligne colorée. Une ligne représentant l’événement est ajoutée au tableau. Vous pouvez inclure jusqu’à trois événements.
* **[!UICONTROL Compté comme]**: mesure que vous souhaitez mesurer. Les options incluent [!UICONTROL Événements par utilisateur], [!UICONTROL Événements], [!UICONTROL Sessions], et [!UICONTROL Utilisateurs].
* **[!UICONTROL Facteurs]**: ce mode comporte deux facteurs :
   * **[!UICONTROL Date]**: date à laquelle vous souhaitez commencer à rechercher le premier événement d’utilisation qui s’est produit.
   * **[!UICONTROL Événement]**: événement pour lequel vous souhaitez rechercher la première utilisation, afin de centrer l’analyse.
* **[!UICONTROL Segments]**: segment que vous souhaitez mesurer. Le segment sélectionné filtre vos données afin de se concentrer uniquement sur les individus qui correspondent à vos critères de segment. Un seul segment est pris en charge pour ce type de vue.

## Paramètres du graphique

La vue Première utilisation offre les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Type de graphique]**: type de visualisation que vous souhaitez utiliser. Les options comprennent Ligne.

## Période

Les sélections de dates dans l’analyse d’impact fonctionnent différemment des autres types d’analyse, car l’analyse se concentre sur la date spécifiée dans le rail de requête. Les options disponibles sont les suivantes :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de tendances. Les options valides incluent : [!UICONTROL Qualité], [!UICONTROL Hebdomadaire], [!UICONTROL Mensuel], et [!UICONTROL Trimestriel]. La modification de l’intervalle affecte les options disponibles pour les périodes Avant et Après.
* **[!UICONTROL Avant et après la période]**: durée d’analyse avant et après le premier événement d’utilisation spécifié dans le rail de requête. Les options disponibles dépendent du [!UICONTROL Intervalle] sélection.
