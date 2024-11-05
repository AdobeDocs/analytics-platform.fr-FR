---
title: Analyse des fréquences
description: Mesurez l’engagement par la fréquence d’utilisation.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 7%

---

# Analyse de la [!UICONTROL fréquence] {#frequency}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_frequency_button"
>title="Fréquence"
>abstract="Afficher la répartition de l’activité des personnes ayant une utilisation récurrente pour des événements spécifiques."

<!-- markdownlint-enable MD034 -->

L’analyse ![Fréquence](/help/assets/icons/Histogram.svg) **[!UICONTROL Fréquence]** regroupe les données d’événement selon la fréquence à laquelle les événements se produisent dans votre produit. L’axe vertical de cette analyse contient des intervalles qui représentent la fréquence de l’événement. L’axe horizontal mesure le nombre d’utilisateurs ou de sessions pour chaque compartiment.

>[!VIDEO](https://video.tv.adobe.com/v/3428089/?learn=on)

## Cas d’utilisation

Voici quelques cas pratiques de cette analyse :

* **Engagement** : effectuez le suivi de l’engagement des utilisateurs avec tout événement de votre produit. Vous pouvez cliquer sur n’importe quelle partie du graphique à barres pour l’enregistrer en tant que segment. Les segments pour les intervalles d’engagement faible peuvent vous aider à déterminer pourquoi les utilisateurs n’interagissent pas avec l’événement à la fréquence souhaitée. Les segments pour les intervalles d’engagement élevé peuvent vous aider à comprendre pourquoi les utilisateurs interagissent souvent avec l’événement. À partir de là, vous pouvez encourager d’autres utilisateurs à adopter un comportement similaire.
* **Fidélité de la clientèle** : définissez l’événement sur Commandes et la mesure sur Utilisateurs. Cette analyse vous permet de regrouper les utilisateurs selon le nombre de fois où ils ont effectué un achat sur votre site au cours de la période spécifiée.
* **Optimisation de l’assistance** : affichez le nombre d’appels de l’assistance ou de cas ouverts par utilisateur pour découvrir quels utilisateurs rencontrent le plus de problèmes. Vous pouvez ensuite créer un segment afin de vous concentrer sur leur expérience afin d’identifier et de résoudre leurs problèmes.
* **Services d’abonnement** : les utilisateurs avec un faible engagement sont plus susceptibles de se produire. Comprendre le comportement des utilisateurs fortement engagés peut contribuer à encourager un comportement similaire pour les utilisateurs à faible interaction, ce qui les rend moins susceptibles d’annuler leur abonnement.

## Interface

Voir [Interface](../overview.md#interface) pour un aperçu de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Affichage]** : basculez entre cette analyse et [Tendances](trends.md).
* **[!UICONTROL Événements]** : événements que vous souhaitez mesurer. Chaque événement sélectionné est représenté sous la forme d’un graphique distinct. Une ligne représentant l’événement de tendance est ajoutée au tableau. Vous pouvez inclure jusqu’à cinq événements.
* **[!UICONTROL Compté comme]** : méthode de comptage que vous souhaitez appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Utilisateurs], [!UICONTROL Sessions], [!UICONTROL Pourcentage d&#39;utilisateurs] et [!UICONTROL Pourcentage de sessions]. Le dénominateur des mesures en pourcentage de cette analyse est les utilisateurs ou les sessions qui ont effectué les événements sélectionnés, et non tous les utilisateurs actifs du produit.
* **[!UICONTROL Segments]** : segments que vous souhaitez mesurer. Chaque segment sélectionné double le nombre de barres du graphique et de lignes du tableau. Vous pouvez inclure jusqu’à cinq segments.

### Paramètres du graphique

L’analyse [!UICONTROL Fréquence] offre les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Barre horizontale] et [!UICONTROL Barre empilée].

### Paramètres du compartiment

Détermine la manière dont l’événement est classé en groupes (intervalles). Dans la vue de tableau de tendance, les utilisateurs sont regroupés selon la fréquence d’utilisation totale et dans chaque intervalle, ce qui signifie qu’un utilisateur peut compter dans différents intervalles.

* **[!UICONTROL Compartiments automatiques]** : identifiez automatiquement la taille optimale du compartiment en fonction de la distribution des données.
* **[!UICONTROL Lockets personnalisés]** : personnalisez la manière dont les données sont regroupées en compartiments.
   * [!UICONTROL De] : premier compartiment. La fréquence inférieure à cette valeur est exclue des rapports.
   * [!UICONTROL To] : la fréquence supérieure à cette valeur est regroupée dans le dernier compartiment.
   * [!UICONTROL Size] : intervalle du compartiment.

### Comparaison de temps

{{apply-time-comparison}}

### Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de date selon laquelle vous souhaitez afficher les données de tendance. Le graphique et le tableau présentent des données agrégées par défaut, avec la possibilité de développer le tableau en vue de tendances. Dans la vue de tendance, les utilisateurs sont regroupés en fonction de la fréquence d’utilisation au total et dans chaque intervalle, ce qui signifie qu’un utilisateur peut être comptabilisé dans différents intervalles.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.


<!--
## Example

See below foran example of the analysis.

![Frequency](../assets/frequency.png)

-->
