---
title: Analyse de la rétention
description: Mesurez le nombre d’utilisateurs et d’utilisatrices qui continuent à utiliser votre produit.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: aff01f4fc3520d461ca800382cc24d8d948d9cbc
workflow-type: tm+mt
source-wordcount: '1249'
ht-degree: 2%

---

# Analyse de la rétention

L’analyse ![Rétention](/help/assets/icons/Retention.svg) **[!UICONTROL Rétention]** mesure la manière dont les utilisateurs continuent à utiliser votre produit au fil du temps, ce qui peut vous aider à comprendre l’adéquation de votre marché de produits. L’analyse comptabilise les utilisateurs en fonction de deux événements importants :

* Événement de début : événement utilisé pour qualifier les utilisateurs d’inclusion dans votre analyse.
* Événement de retour : un ou plusieurs événements avec lesquels un utilisateur doit interagir pour être comptabilisé comme utilisateur récurrent dans votre analyse.

Dans cette analyse, l’axe x du graphique représente le temps écoulé depuis l’événement de début initial d’un utilisateur et l’axe y représente le pourcentage des utilisateurs qui interagissent avec un ou plusieurs événements de retour. Vous pouvez afficher la rétention et la perte de clientèle sur plusieurs durées. Les durées affichées peuvent être personnalisées par le biais des paramètres de requête. Sous le graphique, un tableau fournit des données agrégées avec l’option permettant d’afficher les cohortes individuelles, qui sont un groupe de personnes qui ont effectué l’événement de début à la même date.

>[!VIDEO](https://video.tv.adobe.com/v/3430503/?learn=on)


## Cas d’utilisation

Voici quelques cas pratiques de cette analyse :

* **Analyse des cohortes** : Regroupez les utilisateurs en cohortes en fonction des actions qu’ils effectuent, telles que les inscriptions ou les achats. Vous pouvez comparer la manière dont ces groupes conservent et déterminer comment améliorer l’expérience utilisateur de chaque groupe.
* **Ajustement du marché du produit** : mesurez l’utilisation régulière de votre produit et visualisez-le comme courbes de rétention. Une plus grande rétention signifie une meilleure adéquation du marché des produits, et l’aplatissement de votre courbe indique le temps nécessaire pour atteindre votre taille. Consultez cette analyse à un niveau global ou ventilation par fonctionnalités de produit individuelles pour obtenir des informations plus approfondies.
* **Analyse du service d’abonnements** : si votre produit utilise un abonnement ou un autre type de modèle de revenu récurrent, vous pouvez voir le pourcentage d’utilisateurs qui tirent le meilleur parti de votre produit. Vous pouvez identifier certaines qualités et comportements que ces utilisateurs exposent.
* **Engagement de l’utilisateur** : évaluez la manière dont certains types d’utilisateurs interagissent avec votre produit et comparez côte à côte la fréquence à laquelle ils reviennent. Un segment donné avec une rétention inférieure à celle des autres peut vous donner des informations sur l’amélioration des expériences inférieures potentielles qu’il pourrait avoir.

## Interface

Voir [Interface](../overview.md#interface) pour un aperçu de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Démarrer l’événement]** : critères d’événement avec lesquels un utilisateur doit interagir pour être inclus dans votre analyse. Les utilisateurs qui interagissent avec l’événement de début sont comptabilisés dans la colonne &quot;Utilisateurs&quot; du tableau. Cet événement sert de dénominateur pour les taux de rétention affichés. Un événement est pris en charge et des filtres de propriétés peuvent être appliqués selon les besoins. Par défaut, les événements de début et de retour sont liés, ce qui signifie qu’un utilisateur doit effectuer l’événement sélectionné une fois pour être inclus dans la cohorte, puis à nouveau pour être compté comme un utilisateur récurrent. Sous le menu Plus, vous pouvez dissocier les événements de début et de retour si vous souhaitez que l’action de retour soit différente de l’action d’inclusion.
* **[!UICONTROL Événements de retour]** : critères d’événement avec lesquels un utilisateur doit interagir pour compter comme utilisateurs récurrents dans les intervalles de durée. Vous pouvez sélectionner jusqu’à trois événements de retour pour comparer la rétention.
* **[!UICONTROL Compté comme]** : méthode de comptage que vous souhaitez appliquer aux utilisateurs conservés. Les options incluent : 
   * **[!UICONTROL Mesure]** : afficher le nombre de [!UICONTROL Utilisateurs] ou le [!UICONTROL pourcentage d&#39;utilisateurs] conservés. Le dénominateur du pourcentage d’utilisateurs conservés correspond aux utilisateurs inclus pour la cohorte et est le même dans tous les intervalles de durée.
   * **[!UICONTROL Renvoi]** : vous permet de contrôler la manière dont les utilisateurs réguliers sont comptabilisés. Les options incluent : 
      * **[!UICONTROL Sur ou après]** : souvent appelée rétention &quot;illimitée&quot;, cette option comptabilise un utilisateur s’il revient sur le site ou après la durée spécifiée. Par exemple, le jour 7 ou à tout autre moment après le jour 7. Cette option s’avère utile pour montrer comment les utilisateurs continuent à interagir et génère par conséquent une courbe de rétention plus fluide.
      * **[!UICONTROL Sur exactement]** : souvent appelée rétention &quot;limitée&quot;, cette option comptabilise un utilisateur s’il revient exactement sur la durée spécifiée. Par exemple, le jour 7 exactement. Cette option est utile pour montrer comment les utilisateurs reviennent dans des périodes spécifiques et génère une courbe de rétention avec plus d’ondulation en conséquence. Remarque : L’analyse des cohortes dans Analysis Workspace utilise le comptage &quot;exactement&quot; comme base de son analyse.
   * **[!UICONTROL Chaque]** : période que vous souhaitez que chaque intervalle de durée soit. Les options incluent : 
      * **[!UICONTROL Jour/Semaine/Mois]** : les options disponibles dépendent de la période sélectionnée. Ces options sont identiques au paramètre **[!UICONTROL Intervalle]** lors de la sélection de la période et mettent automatiquement à jour ce paramètre.
      * **[!UICONTROL Crochets personnalisés]** : cette option est disponible uniquement pour le paramètre &quot;À chaque&quot;. Il vous permet de compter les utilisateurs sur une période plus longue, par exemple, Jour 7-10, au lieu de Jour 7 uniquement.
   * **[!UICONTROL Paramètres de durée]** : permet de contrôler les intervalles de durée affichés sur le graphique et le tableau. Une durée correspond à la période qui suit l’événement de début au cours de laquelle l’événement de retour s’est produit. Remarque : les utilisateurs admissibles aux intervalles de durée sont basés sur le temps écoulé, et non sur les jours calendaires. Par exemple, si un utilisateur est admissible pour un événement à 23 h 55 le 6 septembre, puis est admissible pour un événement de retour à 00 h 05 le 7 septembre, il n’apparaîtra pas dans l’intervalle de durée d’une journée. 24 heures complètes doivent s’écouler avant que l’utilisateur ne soit admissible pour l’intervalle de durée d’un jour. Les intervalles de durée disponibles dépendent de la période que vous avez définie.
      * **[!UICONTROL Durée automatique]** définit automatiquement les intervalles de durée en fonction de la durée de la période et de la proximité du jour en cours à l’intérieur de la période.
      * **[!UICONTROL Les durées personnalisées]** vous permettent de personnaliser les quatre intervalles de durée affichés sur le graphique et le tableau.
* **[!UICONTROL Segments]** : segments que vous souhaitez mesurer. Chaque segment sélectionné ajoute une ligne au tableau de cohortes. Vous pouvez inclure jusqu’à trois segments.

### Paramètres du graphique

L’analyse [!UICONTROL Rétention] offre les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Bar] et [!UICONTROL Line].

### Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de date selon laquelle vous souhaitez afficher les données de rétention. Les options valides sont Quotidienne, Hebdomadaire et Mensuelle. Une même période peut avoir des intervalles différents, ce qui a un impact sur les options du compartiment de durée.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.

Si vous sélectionnez une période proche du jour actuel, les utilisateurs qui s’engagent trop près du jour en cours ne sont pas inclus. Cette analyse permet toujours à tous les utilisateurs d’être inclus dans tous les intervalles de durée. Un message sous le sélecteur de calendrier fournit des informations sur la période pendant laquelle les utilisateurs s’engagent et l’intervalle réservé uniquement aux utilisateurs récurrents :

* **[!UICONTROL Analyse des utilisateurs qui ont exécuté l’événement de début dans [Intervalle de date]]** : si un utilisateur interagit avec l’événement au cours de cette période, ils sont inclus dans l’analyse. Cette période garantit à tous les utilisateurs suffisamment de temps pour remplir les critères de tous les intervalles de durée. Cette période peut être différente de votre sélection si elle est proche du jour actuel.
* **[!UICONTROL Les données de [l’intervalle de date] sont réservées pour terminer l’analyse]** : si un utilisateur se lance pour la première fois au cours de cette période, elles ne sont **pas** incluses dans l’analyse. Pour les plages de dates récentes, ces utilisateurs n’auraient pas la possibilité de remplir les conditions requises pour tous les intervalles de durée. Pour les périodes antérieures, ces utilisateurs étaient actifs en dehors de la période sélectionnée.

<!--
## Example

See below for an example of the analysis.

![Retention](../assets/retention.png)

-->