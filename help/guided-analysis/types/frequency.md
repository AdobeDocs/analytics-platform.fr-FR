---
title: Analyse de la fréquence
description: Mesurez l’engagement par la fréquence d’utilisation.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 100%

---

# Analyse de la [!UICONTROL fréquence] {#frequency}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_frequency_button"
>title="Fréquence"
>abstract="Afficher la répartition de l’activité des personnes ayant une utilisation récurrente pour des événements spécifiques."

<!-- markdownlint-enable MD034 -->

L’analyse ![Fréquence](/help/assets/icons/Histogram.svg) **[!UICONTROL Fréquence]** regroupe les données d’événement en fonction de la fréquence des événements dans votre produit. L’axe vertical de cette analyse contient des compartiments qui représentent la fréquence de l’événement. L’axe horizontal mesure le nombre d’utilisateurs et utilisatrices ou de sessions pour chaque compartiment.

>[!VIDEO](https://video.tv.adobe.com/v/3435804/?quality=12&learn=on&captions=fre_fr)

## Cas d’utilisation

Les cas d’utilisation de cette analyse sont les suivants :

* **Engagement** : suivez l’engagement des utilisateurs et utilisatrices envers n’importe quel événement de votre produit. Vous pouvez cliquer sur n’importe quelle partie du graphique à barres pour l’enregistrer en tant que segment. Les segments pour les compartiments à faible engagement peuvent vous aider à déterminer pourquoi les utilisateurs et utilisatrices n’interagissent pas avec l’événement à la fréquence souhaitée. Les segments pour les compartiments à engagement élevé peuvent vous aider à comprendre pourquoi les utilisateurs et utilisatrices interagissent souvent avec l’événement. À partir de là, vous pouvez encourager d’autres utilisateurs et utilisatrices à adopter un comportement similaire.
* **Fidélisation des clientes** : définissez l’événement sur Commandes et la mesure sur Utilisateurs et utilisatrices. Cette analyse vous permet de regrouper les utilisateurs et utilisatrices en fonction du nombre de fois qu’ils ont effectué un achat sur votre site au cours de la période spécifiée.
* **Optimisation de l’assistance** : affichez le nombre d’appels d’assistance ou de cas ouverts par personne pour déterminer les utilisateurs et utilisatrices qui rencontrent le plus de problèmes. Vous pouvez ensuite créer un segment afin de vous concentrer sur leur expérience et de les aider à identifier et résoudre leurs problèmes.
* **Services d’abonnement** : les utilisateurs et utilisatrices peu engagés sont plus susceptibles de faire l’objet de l’attrition. Comprendre le comportement des utilisateurs et utilisatrices à fort engagement peut contribuer à encourager un comportement similaire chez les utilisateurs et utilisatrices à faible engagement, ce qui les rend moins susceptibles d’annuler leur abonnement.

## Interface

Consultez [Interface](../overview.md#interface) pour une vue d’ensemble de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Vue]** : basculez entre cette analyse et les [Tendances](trends.md).
* **[!UICONTROL Événements]** : événements que vous souhaitez mesurer. Chaque événement sélectionné est représenté sous la forme d’un graphique distinct. Une ligne représentant l’événement de tendance est ajoutée au tableau. Vous pouvez inclure un maximum de cinq événements.
* **[!UICONTROL Compté comme]** : méthode de comptage à appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Utilisateurs et utilisatrices], [!UICONTROL Sessions], [!UICONTROL Pourcentage d’utilisateurs et d’utilisatrices] et [!UICONTROL Pourcentage de sessions]. Le dénominateur des mesures basées sur un pourcentage dans cette analyse est constitué des utilisateurs et utilisatrices ou des sessions qui ont réalisé les événements sélectionnés, et non de tous les utilisateurs et utilisatrices actifs du produit.
* **[!UICONTROL Segments]** : segments que vous souhaitez mesurer. Chaque segment sélectionné double le nombre de barres dans le graphique et de lignes dans le tableau. Vous pouvez inclure un maximum de cinq segments.

### Paramètres du graphique

L’analyse [!UICONTROL Fréquence] propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Barres horizontales] et [!UICONTROL Barres empilées].

### Paramètres du compartiment

Détermine la manière dont l’événement est classé dans des groupes (compartiments). Dans la vue Tableau de tendances, les utilisateurs et utilisatrices sont regroupés en fonction de la fréquence d’utilisation au total et dans chaque intervalle, ce qui signifie qu’une personne peut être comptabilisée dans différents regroupements à différents intervalles.

* **[!UICONTROL Compartiments automatiques]** : identifiez automatiquement la taille optimale des compartiments en fonction de la distribution des données.
* **[!UICONTROL Compartiments personnalisés]** : personnalisez la manière dont les données sont regroupées dans des compartiments.
   * [!UICONTROL De] : premier compartiment. Une fréquence inférieure à cette valeur est exclue de la création de rapports.
   * [!UICONTROL À] : les fréquences supérieures à cette valeur sont regroupées dans le dernier compartiment.
   * [!UICONTROL Taille] : intervalle du compartiment.

### Comparaison de temps

{{apply-time-comparison}}

### Période

Période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Le graphique et le tableau affichent des données agrégées par défaut, avec la possibilité de développer le tableau pour obtenir une vue de tendance. Dans la vue de tendance, les utilisateurs et utilisatrices sont regroupés en fonction de la fréquence d’utilisation au total et dans chaque intervalle, ce qui signifie qu’une personne peut être comptabilisée dans différents compartiments à différents intervalles.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les périodes personnalisées enregistrées précédemment sont disponibles pour votre commodité. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une période fixe.


<!--
## Example

See below foran example of the analysis.

![Frequency](../assets/frequency.png)

-->
