---
title: Analyse de la rétention
description: Mesurez le nombre de personnes qui continuent à utiliser votre produit.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '1259'
ht-degree: 100%

---

# Analyse de la rétention {#retention}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_retention_button"
>title="Rétention"
>abstract="Mesurez le nombre de personnes qui continuent à utiliser votre produit."

<!-- markdownlint-enable MD034 -->

L’analyse ![Rétention](/help/assets/icons/Retention.svg) **[!UICONTROL Rétention]** mesure la manière dont les utilisateurs et utilisatrices continuent à utiliser votre produit au fil du temps, ce qui peut vous aider à comprendre son adéquation au marché. L’analyse comptabilise les utilisateurs et utilisatrices en fonction de deux événements importants :

* Événement de début : événement utilisé pour qualifier les utilisateurs et utilisatrices en vue de leur inclusion dans votre analyse.
* Événement de retour : un ou plusieurs événements avec lesquels une personne doit interagir pour être comptabilisée comme une personne récurrente dans votre analyse.

Dans cette analyse, l’axe X du graphique représente le temps écoulé depuis l’événement de début initial d’une personne et l’axe Y représente le pourcentage d’utilisateurs et d’utilisatrices qui interagissent avec un ou plusieurs événements de retour. Vous pouvez afficher à la fois la rétention et l’attrition sur des durées, et les durées affichées peuvent être personnalisées à l’aide des paramètres de requête. Sous le graphique, un tableau fournit des données agrégées avec la possibilité d’afficher des cohortes individuelles, c’est-à-dire un groupe de personnes qui ont effectué l’événement de début à la même date.

>[!VIDEO](https://video.tv.adobe.com/v/3430503/?quality=12&learn=on)


## Cas d’utilisation

Les cas d’utilisation de cette analyse sont les suivants :

* **Analyse des cohortes** : regroupez les utilisateurs et utilisatrices en cohortes en fonction des actions qu’ils entreprennent, telles que les inscriptions ou les achats. Vous pouvez comparer la rétention de ces groupes et déterminer comment améliorer l’expérience des clientes et clients de chaque groupe.
* **Adéquation du produit au marché** : mesurez l’utilisation régulière de votre produit et visualisez-la sous la forme de courbes de rétention. Une rétention plus importante signifie une meilleure adéquation du produit au marché, et l’aplatissement de votre courbe indique le temps nécessaire pour atteindre votre adéquation. Affichez cette analyse à un niveau global ou répartissez-la par fonctionnalité de produit individuel pour obtenir des informations plus précises.
* **Analyse des services d’abonnement** : si votre produit utilise un abonnement ou un autre type de modèle de chiffre d’affaires récurrent, vous pouvez voir le pourcentage d’utilisateurs et d’utilisatrices qui tirent le meilleur parti de votre produit. Vous pouvez identifier certaines qualités et certains comportements dont ces utilisateurs et utilisatrices font preuve.
* **Interaction client** : évaluez la manière dont certains types d’utilisateurs et d’utilisatrices interagissent avec votre produit et comparez côte à côte la fréquence à laquelle ils reviennent. Un segment donné avec une rétention plus faible que les autres peut vous donner des informations sur l’amélioration des expériences potentiellement décevantes qu’ils peuvent avoir.

## Interface

Consultez [Interface](../overview.md#interface) pour une vue d’ensemble de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Événement de début]** : critères d’événement qu’une personne doit respecter pour pouvoir être incluse dans votre analyse. Les utilisateurs et utilisatrices qui interagissent avec l’événement de début sont comptabilisés dans la colonne « Utilisateurs et utilisatrices » du tableau. Cet événement sert de dénominateur pour les taux de rétention affichés. Un événement est pris en charge et des filtres de propriété peuvent être appliqués selon les besoins. Par défaut, les événements de début et de retour sont liés, ce qui signifie qu’une personne doit effectuer l’événement sélectionné une seule fois pour être incluse dans la cohorte, puis une nouvelle fois pour être comptabilisée comme une personne récurrente. Sous le menu Plus, vous pouvez annuler le lien des événements de début et de retour si vous souhaitez que l’action de retour soit différente de l’action d’inclusion.
* **[!UICONTROL Événements de retour]** : critères d’événement qu’une personne doit respecter pour être comptabilisée comme une personne récurrente dans les compartiments de durée. Vous pouvez sélectionner jusqu’à trois événements de retour pour comparer la rétention.
* **[!UICONTROL Comptabilisé comme]** : méthode de comptage à appliquer aux utilisateurs et utilisatrices conservés. Les options incluent ce qui suit :
   * **[!UICONTROL Mesure]** : affichez le nombre d’[!UICONTROL utilisateurs et utilisatrices] ou le [!UICONTROL pourcentage d’utilisateurs et d’utilisatrices] conservés. Le dénominateur pour le pourcentage d’utilisateurs et d’utilisatrices conservés est celui des utilisateurs et utilisatrices inclus pour la cohorte et est le même pour tous les compartiments de durée.
   * **[!UICONTROL Récurrent]** : vous permet de contrôler le décompte des utilisateurs et utilisatrices récurrents. Les options incluent ce qui suit :
      * **[!UICONTROL Le ou après le]** : souvent appelée rétention « illimitée », cette option comptabilise une personne si elle revient après la durée spécifiée. Par exemple, le jour 7 ou à tout moment après le jour 7. Cette option est utile pour montrer comment les utilisateurs et utilisatrices continuent à interagir et génère ainsi une courbe de rétention plus fluide.
      * **[!UICONTROL Exactement le]** : souvent appelée rétention « limitée », cette option comptabilise une personne si elle revient exactement à la durée spécifiée. Par exemple, exactement le jour 7. Cette option est utile pour montrer comment les utilisateurs et utilisatrices reviennent dans des délais spécifiques et génère une courbe de rétention avec plus d’ondulation en conséquence. Note : l’analyse des cohortes dans Analysis Workspace repose sur un comptage « exactement le ».
   * **[!UICONTROL Chaque]** : période que vous souhaitez pour chaque regroupement de durée. Les options incluent ce qui suit :
      * **[!UICONTROL Jour/Semaine/Mois]** : les options disponibles dépendent de la période sélectionnée. Ces options sont identiques au paramètre **[!UICONTROL Intervalle]** lors de la sélection de la période et mettent automatiquement à jour ce paramètre.
      * **[!UICONTROL Intervalles personnalisés]** : cette option est disponible uniquement pour le paramètre « Chaque». Vous pouvez ainsi comptabiliser les utilisateurs et utilisatrices sur une période plus longue, par exemple, du 7e au 10e jour au lieu du 7e jour uniquement.
   * **[!UICONTROL Paramètres de durée]** : permet de contrôler les compartiments de durée affichés sur le graphique et le tableau. Une durée est la période postérieure à l’événement de début pendant laquelle l’événement de retour s’est produit. Note : les utilisateurs et utilisatrices qui remplissent les critères pour les compartiments de durée sont basés sur le temps écoulé, et non sur les jours du calendrier. Par exemple, si une personne se qualifie pour un événement à 23 h 55 le 6 septembre, puis pour un événement de retour à 00 h 05 le 7 septembre, elle n’apparaîtra pas dans le compartiment de durée d’une journée. Une période complète de 24 heures doit s’écouler avant que la personne ne soit qualifiée pour l’intervalle de durée d’une journée. Les intervalles de durée disponibles dépendent de la période que vous avez définie.
      * **[!UICONTROL Durées automatiques]** définit automatiquement les compartiments de durée en fonction de la longueur de la période et de la proximité par rapport au jour en cours de la période.
      * **[!UICONTROL Durées personnalisées]** vous permet de personnaliser les quatre compartiments de durée affichés sur le graphique et le tableau.
* **[!UICONTROL Segments]** : segments que vous souhaitez mesurer. Chaque segment sélectionné ajoute une ligne à la table de cohorte. Vous pouvez inclure jusqu’à trois segments.

### Paramètres du graphique

L’analyse [!UICONTROL Rétention] propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Barres] et [!UICONTROL Ligne].

### Période

Période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de date selon laquelle vous souhaitez afficher les données de rétention. Les options valides sont les suivantes : Quotidien, Hebdomadaire et Mensuel. Une même période peut avoir des intervalles différents, ce qui a un impact sur les options de compartiment de durée.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les périodes personnalisées enregistrées précédemment sont disponibles pour votre commodité. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une période fixe.

Si vous sélectionnez une période proche du jour en cours, les utilisateurs et utilisatrices qui s’engagent initialement trop près du jour en cours ne sont pas inclus. Cette analyse donne toujours à tous les utilisateurs et utilisatrices la possibilité d’être inclus dans tous les compartiments de durée. Un message situé sous le sélecteur de calendrier fournit des informations sur la période pendant laquelle les utilisateurs et utilisatrices sont engagés, ainsi que sur l’intervalle réservé aux utilisateurs et utilisatrices récurrents :

* **[!UICONTROL Analyse des utilisateurs et utilisatrices qui ont lancé l’événement dans [Intervalle de dates]]** : si une personne interagit avec l’événement dans cette période, elle est incluse dans l’analyse. Cette période garantit à tous les utilisateurs et utilisatrices suffisamment de temps pour se qualifier pour tous les compartiments de durée. Cette période peut être différente de votre sélection si elle est proche du jour présent.
* **[!UICONTROL Les données d’[Intervalle de dates] sont réservées pour terminer l’analyse]** : si une personne s’engage pour la première fois au cours de cette période, elle n’est **pas** incluse dans l’analyse. Pour les périodes récentes, ces utilisateurs et utilisatrices n’auraient pas la possibilité de se qualifier pour tous les compartiments de durée. Pour les périodes antérieures, ces utilisateurs et utilisatrices étaient actifs en dehors de la période sélectionnée.

<!--
## Example

See below for an example of the analysis.

![Retention](../assets/retention.png)

-->