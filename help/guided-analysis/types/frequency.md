---
title: Mode Fréquence
description: Mesurer l’engagement par la fréquence d’utilisation.
feature: Guided Analysis
keywords: analytics du produit
source-git-commit: 77192426a58e1560abe91b904452b9cd46c862e9
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 3%

---

# [!UICONTROL Fréquence] view

La variable **[!UICONTROL Fréquence]** view groupe les données d’événement en fonction de la fréquence d’affichage d’un événement. L’axe vertical de ce rapport contient des compartiments représentant la fréquence de l’événement ou des événements consultés. L’axe horizontal mesure le nombre d’utilisateurs ou de sessions pour chaque compartiment.

![Capture d’écran de fréquence](../assets/frequency-stacked.png)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Engagement**: suivi de l’engagement des utilisateurs avec n’importe quel événement. Vous pouvez cliquer sur une barre horizontale pour l’enregistrer en tant que segment. Les segments pour les intervalles d’engagement faible peuvent vous aider à déterminer pourquoi les utilisateurs n’interagissent pas avec l’événement à la fréquence souhaitée. Les segments pour les intervalles d’engagement élevé peuvent vous aider à comprendre pourquoi les utilisateurs interagissent souvent avec l’événement. À partir de là, vous pouvez encourager d’autres utilisateurs à adopter un comportement similaire.
* **Fidélité de la clientèle**: définissez l’événement sur Commandes et la mesure sur Utilisateurs. Ce rapport vous permet de regrouper les utilisateurs selon le nombre de fois qu’ils ont effectué un achat sur votre site au cours de la période spécifiée.
* **Optimisation de la prise en charge**: l’affichage de ce rapport par nombre d’appels au service clientèle ou de cas ouverts peut vous donner des informations sur les utilisateurs qui rencontrent le plus de problèmes. Vous pouvez ensuite créer un segment afin de vous concentrer sur leur expérience afin d’identifier et de résoudre leurs problèmes.
* **Services d’inscriptions**: ce rapport est utile pour les organisations qui disposent de services d’abonnement. Les utilisateurs à faible engagement sont plus susceptibles de se produire. Vous pouvez donc consulter ce rapport afin d’analyser le comportement des utilisateurs à forte interaction. Comprendre le comportement des utilisateurs fortement engagés peut contribuer à encourager un comportement similaire pour les utilisateurs à faible interaction, ce qui les rend moins susceptibles d’annuler leur abonnement.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Événements]**: événements que vous souhaitez mesurer. Chaque événement sélectionné est représenté sous la forme d’un graphique distinct. Une ligne représentant l’événement de tendance est ajoutée au tableau. Vous pouvez inclure jusqu’à cinq événements.
* **[!UICONTROL Personnes]**: segments que vous souhaitez mesurer. Chaque segment sélectionné double le nombre de lignes du graphique et de lignes du tableau. Vous pouvez inclure jusqu’à cinq segments.

## Paramètres du graphique

La variable [!UICONTROL Fréquence] La vue propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Mesure]**: mesure que vous souhaitez mesurer. Les options incluent [!UICONTROL Utilisateurs] et [!UICONTROL Sessions].
* **[!UICONTROL Type de graphique]**: type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Barre horizontale] et [!UICONTROL Barre empilée].

## Paramètres du compartiment

Détermine la manière dont l’événement est classé en groupes.

* **[!UICONTROL Blocs automatiques]**: identifiez automatiquement la taille optimale du compartiment en fonction de la distribution des données.
* **[!UICONTROL Lots personnalisés]**: contrôlez la manière dont le rapport regroupe les données dans des compartiments.
   * [!UICONTROL De]: premier compartiment. La fréquence inférieure à cette valeur est exclue des rapports.
   * [!UICONTROL À]: la fréquence supérieure à cette valeur est regroupée dans le dernier intervalle.
   * [!UICONTROL Taille]: intervalle du compartiment.

## Appliquer la comparaison des temps

{{apply-time-comparison}}

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de tendances. Ce paramètre n’a aucune incidence sur les vues non de tendance telles que Fréquence.
* **[!UICONTROL Date]**: date de début et date de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
