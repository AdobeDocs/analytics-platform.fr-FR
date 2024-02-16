---
title: Mode Fréquence
description: Mesurez l’engagement par fréquence d’utilisation.
feature: Guided Analysis
keywords: analytics du produit
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
source-git-commit: e448f6ddbff2673abbd2920aacf41d4268f3ce07
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 1%

---

# [!UICONTROL Fréquence] view

La variable **[!UICONTROL Fréquence]** La vue groupe les données d’événement selon la fréquence à laquelle des événements se produisent dans votre produit. L’axe vertical de cette vue contient des intervalles qui représentent la fréquence de l’événement. L’axe horizontal mesure le nombre d’utilisateurs ou de sessions pour chaque compartiment.

![Capture d’écran de fréquence](../assets/frequency-stacked.png)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Engagement**: déterminez l’engagement des utilisateurs dans n’importe quel événement de votre produit. Vous pouvez cliquer sur n’importe quelle partie du graphique à barres pour l’enregistrer en tant que segment. Les segments pour les intervalles d’engagement faible peuvent vous aider à déterminer pourquoi les utilisateurs n’interagissent pas avec l’événement à la fréquence souhaitée. Les segments pour les intervalles d’engagement élevé peuvent vous aider à comprendre pourquoi les utilisateurs interagissent souvent avec l’événement. À partir de là, vous pouvez encourager d’autres utilisateurs à adopter un comportement similaire.
* **Fidélité de la clientèle**: définissez l’événement sur Commandes et la mesure sur Utilisateurs. Cette vue vous permet de regrouper les utilisateurs selon le nombre de fois où ils ont effectué un achat sur votre site au cours de la période spécifiée.
* **Optimisation de la prise en charge**: affichez le nombre d’appels d’assistance ou de cas ouverts par l’utilisateur pour mieux comprendre quels utilisateurs rencontrent le plus de problèmes. Vous pouvez ensuite créer un segment afin de vous concentrer sur leur expérience afin d’identifier et de résoudre leurs problèmes.
* **Services d’inscriptions**: les utilisateurs avec un faible engagement sont plus susceptibles de se produire. Comprendre le comportement des utilisateurs fortement engagés peut contribuer à encourager un comportement similaire pour les utilisateurs à faible interaction, ce qui les rend moins susceptibles d’annuler leur abonnement.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Affichage]**: basculez entre ce type de vue et [Utilisation](usage.md).
* **[!UICONTROL Événements]**: événements que vous souhaitez mesurer. Chaque événement sélectionné est représenté sous la forme d’un graphique distinct. Une ligne représentant l’événement de tendance est ajoutée au tableau. Vous pouvez inclure jusqu’à cinq événements.
* **[!UICONTROL Compté comme]**: méthode de comptage à appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Utilisateurs],  [!UICONTROL Sessions],  [!UICONTROL Pourcentage d&#39;utilisateurs] et  [!UICONTROL Pourcentage de sessions]. Le dénominateur des mesures en pourcentage dans cette vue est les utilisateurs ou les sessions qui ont effectué les événements sélectionnés, et non tous les utilisateurs actifs du produit.
* **[!UICONTROL Segments]**: segments que vous souhaitez mesurer. Chaque segment sélectionné double le nombre de barres du graphique et de lignes du tableau. Vous pouvez inclure jusqu’à cinq segments.

## Paramètres du graphique

La variable [!UICONTROL Fréquence] La vue propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Type de graphique]**: type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Barre horizontale] et [!UICONTROL Barre empilée].

## Paramètres du compartiment

Détermine la manière dont l’événement est classé en groupes.

* **[!UICONTROL Blocs automatiques]**: identifiez automatiquement la taille optimale du compartiment en fonction de la distribution des données.
* **[!UICONTROL Lots personnalisés]**: personnalisez la manière dont les données sont regroupées en compartiments.
   * [!UICONTROL De]: premier compartiment. La fréquence inférieure à cette valeur est exclue des rapports.
   * [!UICONTROL À]: la fréquence supérieure à cette valeur est regroupée dans le dernier intervalle.
   * [!UICONTROL Taille]: intervalle du compartiment.

## Comparaison de temps

{{apply-time-comparison}}

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de tendance. Ce paramètre n’a aucune incidence sur les vues non de tendance telles que Fréquence.
* **[!UICONTROL Date]**: date de début et date de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
