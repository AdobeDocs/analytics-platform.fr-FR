---
title: Analyse de la rétention
description: Mesurez le nombre de personnes qui continuent à utiliser votre produit.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '1259'
ht-degree: 3%

---

# Analyse de la rétention {#retention}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_retention_button"
>title="Rétention"
>abstract="Mesurez le nombre de personnes qui continuent à utiliser votre produit."

<!-- markdownlint-enable MD034 -->

L’analyse ![Rétention](/help/assets/icons/Retention.svg) **[!UICONTROL Rétention]** mesure la manière dont les utilisateurs continuent à utiliser votre produit au fil du temps, ce qui peut vous aider à comprendre son adéquation au marché. L’analyse comptabilise les utilisateurs en fonction de deux événements importants :

* Événement de début : événement utilisé pour qualifier les utilisateurs en vue de leur inclusion dans votre analyse.
* Événement de retour : un ou plusieurs événements qu’un utilisateur doit interagir avec pour être comptabilisé comme un utilisateur récurrent dans votre analyse.

Dans cette analyse, l’axe X du graphique représente le temps écoulé depuis l’événement de début initial d’un utilisateur et l’axe Y représente le pourcentage d’utilisateurs qui interagissent avec un ou plusieurs événements de retour. Vous pouvez afficher à la fois la rétention et l’attrition sur plusieurs durées, et les durées affichées peuvent être personnalisées à l’aide des paramètres de requête. Sous le graphique, un tableau fournit des données agrégées avec la possibilité d’afficher des cohortes individuelles, c’est-à-dire un groupe de personnes qui ont effectué l’événement de début à la même date.

>[!VIDEO](https://video.tv.adobe.com/v/3430503/?quality=12&learn=on)


## Cas d’utilisation

Les cas d’utilisation de cette analyse sont les suivants :

* **Analyse des cohortes** : regroupez les utilisateurs en cohortes en fonction des actions qu’ils entreprennent, telles que les inscriptions ou les achats. Vous pouvez comparer la rétention de ces groupes et déterminer comment améliorer l’expérience utilisateur de chaque groupe.
* **Ajustement du marché du produit** : Mesurez l’utilisation régulière de votre produit et visualisez-le sous la forme de courbes de rétention. Une rétention plus importante signifie une meilleure adéquation au marché du produit, et l’aplatissement de votre courbe indique le temps nécessaire pour atteindre votre adéquation. Affichez cette analyse à un niveau global ou répartissez-la par fonctionnalité de produit individuelle pour obtenir des informations plus précises.
* **Analyse des services d’abonnement** : si votre produit utilise un abonnement ou un autre type de modèle de chiffre d’affaires récurrent, vous pouvez voir le pourcentage d’utilisateurs qui tirent le meilleur parti de votre produit. Vous pouvez identifier certaines qualités et certains comportements dont ces utilisateurs font preuve.
* **Interaction client** : évaluez la manière dont certains types d’utilisateurs interagissent avec votre produit et comparez côte à côte la fréquence à laquelle ils reviennent. Un segment donné avec une rétention plus faible que les autres peut vous donner des informations sur l’amélioration des expériences potentiellement inférieures à la moyenne qu’ils peuvent avoir.

## Interface

Voir [Interface](../overview.md#interface) pour une présentation de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Événement de début]** : critères d’événement qu’un utilisateur doit respecter pour pouvoir être inclus dans votre analyse. Les utilisateurs qui interagissent avec l’événement de début sont comptabilisés dans la colonne « Utilisateurs » du tableau. Cet événement sert de dénominateur pour les taux de rétention affichés. Un événement est pris en charge et des filtres de propriété peuvent être appliqués selon les besoins. Par défaut, les événements de début et de retour sont liés, ce qui signifie qu’un utilisateur doit effectuer l’événement sélectionné une seule fois pour être inclus dans la cohorte, puis une nouvelle fois pour être comptabilisé comme un utilisateur récurrent. Sous le menu Plus , vous pouvez annuler le lien des événements de début et de retour si vous souhaitez que l’action de retour soit différente de l’action d’inclusion.
* **[!UICONTROL Événements renvoyés]** : critères d’événement qu’un utilisateur doit respecter pour être comptabilisé comme des utilisateurs récurrents dans les intervalles de durée. Vous pouvez sélectionner jusqu’à trois événements récurrents pour comparer la rétention.
* **[!UICONTROL Comptabilisé comme]** : méthode de comptage à appliquer aux utilisateurs conservés. Les options incluent : 
   * **[!UICONTROL Mesure]** : affichez le nombre d’[!UICONTROL utilisateurs] ou le [!UICONTROL pourcentage d’utilisateurs] conservés. Le dénominateur pour le pourcentage d’utilisateurs conservés est celui des utilisateurs inclus pour la cohorte et est le même pour tous les intervalles de durée.
   * **[!UICONTROL Récurrent]** : vous permet de contrôler le décompte des utilisateurs récurrents. Les options incluent : 
      * **[!UICONTROL Activé ou ultérieur]** : souvent appelée rétention « illimitée », cette option comptabilise un utilisateur ou une utilisatrice s’il ou elle revient après la durée spécifiée. Par exemple, le jour 7 ou à tout moment après le jour 7. Cette option est utile pour montrer comment les utilisateurs continuent à interagir et génère ainsi une courbe de rétention plus fluide.
      * **[!UICONTROL Sur exactement]** : souvent appelée rétention « limitée », cette option comptabilise un utilisateur s’il revient exactement à la durée spécifiée. Par exemple, au jour 7 exactement. Cette option est utile pour montrer comment les utilisateurs reviennent dans des délais spécifiques et génère une courbe de rétention avec plus d’ondulation en conséquence. Remarque : l’analyse des cohortes dans Analysis Workspace repose sur un comptage « exactement ».
   * **[!UICONTROL Each]** : période que vous souhaitez que chaque regroupement de durée soit. Les options incluent : 
      * **[!UICONTROL Jour/Semaine/Mois]** : les options disponibles dépendent de la période sélectionnée. Ces options sont identiques au paramètre **[!UICONTROL Intervalle]** lors de la sélection de la période et mettent automatiquement à jour ce paramètre.
      * **[!UICONTROL Crochets personnalisés]** : cette option est disponible uniquement pour le paramètre « Sur chaque ». Vous pouvez ainsi comptabiliser les utilisateurs sur une période plus longue, par exemple, du 7e au 10e jour au lieu du 7e jour uniquement.
   * **[!UICONTROL Paramètres de durée]** : permet de contrôler les intervalles de durée affichés sur le graphique et le tableau. Une durée est la période postérieure à l’événement de début pendant laquelle l’événement de retour s’est produit. Remarque : les utilisateurs qui remplissent les critères pour les intervalles de durée sont basés sur le temps écoulé, et non sur les jours du calendrier. Par exemple, si un utilisateur se qualifie pour un événement à 23h55 le 6 septembre, puis pour un événement récurrent à 00h05 le 7 septembre, il n’apparaîtra pas dans le compartiment de durée d’un jour. Une période complète de 24 heures doit s’écouler avant que l’utilisateur ne soit qualifié pour l’intervalle de durée d’un jour. Les intervalles de durée disponibles dépendent de la période que vous avez définie.
      * **[!UICONTROL Durées automatiques]** définit automatiquement les intervalles de durée en fonction de la longueur de la période et de la proximité par rapport au jour en cours de la période.
      * **[!UICONTROL Durées personnalisées]** vous permet de personnaliser les quatre intervalles de durée affichés sur le graphique et le tableau.
* **[!UICONTROL Segments]** : segments que vous souhaitez mesurer. Chaque segment sélectionné ajoute une ligne au tableau de cohorte. Vous pouvez inclure jusqu’à trois segments.

### Paramètres du graphique

L’analyse [!UICONTROL Rétention] propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : le type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Bar] et [!UICONTROL Line].

### Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de date selon laquelle vous souhaitez afficher les données de rétention. Les options valides sont les suivantes : Quotidien, Hebdomadaire et Mensuel. Une même période peut avoir des intervalles différents, ce qui a un impact sur les options de regroupement de durée.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les périodes personnalisées enregistrées précédemment sont disponibles pour votre commodité. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une période fixe.

Si vous sélectionnez une période proche du jour en cours, les utilisateurs qui s’engagent initialement trop près du jour en cours ne sont pas inclus. Cette analyse donne toujours à tous les utilisateurs la possibilité d’être inclus dans tous les intervalles de durée. Un message situé sous le sélecteur de calendrier fournit des informations sur la période pendant laquelle les utilisateurs et utilisatrices sont engagés, ainsi que sur l’intervalle réservé aux utilisateurs et utilisatrices récurrents :

* **[!UICONTROL Analyse des utilisateurs qui ont lancé l’événement dans [Intervalle de dates]]** : si un utilisateur interagit avec l’événement dans cette période, il est inclus dans l’analyse. Cette période garantit à tous les utilisateurs suffisamment de temps pour se qualifier pour tous les regroupements de durée. Cette période peut être différente de votre sélection si elle est proche du jour présent.
* **[!UICONTROL Les données de [Intervalle de dates] sont réservées pour terminer l’analyse]** : si un utilisateur ou une utilisatrice s’engage pour la première fois au cours de cette période, elles ne sont **pas** incluses dans l’analyse. Pour les périodes récentes, ces utilisateurs n’auraient pas la possibilité de se qualifier pour tous les regroupements de durée. Pour les périodes antérieures, ces utilisateurs étaient actifs en dehors de la période sélectionnée.

<!--
## Example

See below for an example of the analysis.

![Retention](../assets/retention.png)

-->