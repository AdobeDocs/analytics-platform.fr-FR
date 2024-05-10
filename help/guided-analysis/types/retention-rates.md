---
title: Taux de fidélisation
description: Mesurez le nombre d’utilisateurs qui continuent à utiliser votre produit.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 2%

---

# Taux de fidélisation

La variable **[!UICONTROL Taux de rétention]** La vue affiche le comportement d’utilisation récurrent des utilisateurs dans votre produit au fil du temps, ce qui peut vous aider à comprendre l’adéquation de votre marché de produits. Dans cette vue, l’axe horizontal représente le nombre de jours depuis l’engagement initial d’un utilisateur et l’axe vertical représente le pourcentage d’utilisateurs qui interagissent à nouveau.

Cette analyse comptabilise les utilisateurs en fonction de deux événements importants :

* Événement de début : première interaction d’un utilisateur avec l’événement dans la période
* Événement de retour : la dernière fois qu’un utilisateur s’est engagé avec l’événement au cours de la période analysée.

L’intervalle de durée &quot;Jour 0&quot; représente l’heure initiale à laquelle un utilisateur s’est impliqué dans l’événement, et est toujours exactement égal à 100 %. Ce compartiment est le dénominateur utilisé pour calculer le pourcentage d’utilisateurs conservés.

Les intervalles de durée suivants comptabilisent le nombre d’utilisateurs qui sont revenus sur cette durée ou après cette date. Ce nombre est le numérateur utilisé pour calculer le pourcentage d’utilisateurs conservés.

* Si un utilisateur interagit avec l’événement une seule fois pendant la période souhaitée (l’engagement initial), il apparaît uniquement dans l’intervalle de durée &quot;Jour 0&quot;.
* Si un utilisateur interagit avec l’événement plusieurs jours après s’être qualifié pour la première fois pour être inclus dans l’analyse, il apparaît dans le dernier intervalle de durée de qualification et dans tous les intervalles de durée qui le précèdent. Ce type de calcul est parfois appelé &quot;rétention illimitée&quot;. Vous pouvez modifier ce paramètre de calcul dans le rail de requêtes.

Les utilisateurs admissibles aux intervalles de durée dépendent du temps écoulé, et non du jour calendaire. Par exemple, si un utilisateur est admissible pour un événement à 23 h 55 le 6 septembre, puis est admissible pour un événement de retour à 00 h 05 le 7 septembre, il n’apparaîtra pas dans l’intervalle de durée d’une journée. 24 heures complètes doivent s’écouler avant que l’utilisateur ne soit admissible pour l’intervalle de durée d’un jour.

![Copie d’écran des taux de rétention](../assets/retention-rates.png){style="border:1px solid gray"}

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Analyse des cohortes**: regroupez les utilisateurs en cohortes en fonction des actions qu’ils effectuent, comme les inscriptions ou les achats. Vous pouvez comparer la manière dont ces groupes conservent et déterminer comment améliorer l’expérience utilisateur de chaque groupe.
* **Ajuster le marché des produits**: mesurez l’utilisation régulière de votre produit et visualisez-le comme courbes de rétention. Une plus grande rétention signifie une meilleure adéquation du marché des produits, et l’aplatissement de votre courbe indique le temps nécessaire pour atteindre votre taille. Consultez cette analyse à un niveau global ou ventilation par fonctionnalités de produit individuelles pour obtenir des informations plus approfondies.
* **Analyse du service d&#39;abonnements**: si votre produit utilise un abonnement ou un autre type de modèle de revenu récurrent, vous pouvez voir le pourcentage d’utilisateurs qui tirent le meilleur parti de votre produit. Vous pouvez identifier certaines qualités et comportements que ces utilisateurs exposent.
* **Engagement des utilisateurs**: évaluez la manière dont certains types d’utilisateurs interagissent avec votre produit et comparez côte à côte la fréquence à laquelle ils reviennent. Un segment donné avec une rétention inférieure à celle des autres peut vous donner des informations sur l’amélioration des expériences inférieures potentielles qu’il pourrait avoir.

## Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Événement de démarrage]**: critères d’événement avec lesquels un utilisateur doit interagir pour être inclus dans votre analyse. Les utilisateurs qui interagissent avec l’événement de début sont inclus dans le regroupement initial des utilisateurs qui se monte à 100 %. Un événement est pris en charge, mais vous pouvez inclure des filtres de propriétés. Vous pouvez associer les événements de début et de retour à l’aide du menu à trois points. La liaison des événements de début et de retour signifie que les critères à afficher dans le compartiment de durée initial et les intervalles de durée suivants sont identiques.
* **[!UICONTROL Événements de retour]**: critères d’événement avec lesquels un utilisateur doit interagir pour être inclus dans les intervalles de durée suivants. Vous pouvez sélectionner trois événements de retour au maximum. Chaque événement de retour génère une analyse côte à côte avec les autres événements de retour inclus.
* **[!UICONTROL Compté comme]**: méthode de comptage que vous souhaitez appliquer aux utilisateurs fidélisés. Les options incluent : 
   * **[!UICONTROL Mesure]**: comptabilise le nombre de [!UICONTROL Utilisateurs conservés] ou le [!UICONTROL Pourcentage d&#39;utilisateurs conservés].
   * **[!UICONTROL Renvoi]**: par défaut, cette analyse inclut les utilisateurs dans le compartiment qu’ils ont renvoyé et tous les compartiments précédents. Modifiez ce paramètre en **[!UICONTROL exactement]** pour inclure les utilisateurs dans le compartiment exact auquel ils sont qualifiés.
   * **[!UICONTROL Chaque]**: période que vous souhaitez que chaque intervalle de durée soit. Ce paramètre est identique au paramètre **[!UICONTROL Intervalle]** lors de la sélection de la période.
   * **[!UICONTROL Paramètres de durée]**: permet de contrôler la manière dont l’analyse affiche les utilisateurs en fonction du nombre de jours écoulés. Les intervalles de durée disponibles dépendent de la période que vous avez définie. **[!UICONTROL Durée automatique]** définir automatiquement des intervalles de durée en fonction de la durée de la période et de la proximité par rapport au jour en cours de la période ; **[!UICONTROL Dates personnalisées]** vous permettent de définir manuellement quatre intervalles de durée à des intervalles souhaités.
* **[!UICONTROL Segments]** : segments que vous souhaitez mesurer. Chaque segment sélectionné ajoute une ligne au tableau de cohortes. Vous pouvez inclure jusqu’à trois segments.

## Paramètres du graphique

La variable [!UICONTROL Taux de rétention] La vue propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Type de graphique]**: type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Barre] et [!UICONTROL Ligne]. La visualisation en ligne présente visuellement le jour 0 dans le graphique.

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de rétention. Les options valides sont Quotidienne, Hebdomadaire et Mensuelle. Une même période peut avoir des intervalles différents, ce qui a un impact sur les options du compartiment de durée.
* **[!UICONTROL Date]**: date de début et date de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.

Si vous sélectionnez une période proche du jour actuel, les utilisateurs qui s’engagent trop près du jour en cours ne sont pas inclus. Cette analyse permet toujours à tous les utilisateurs d’être inclus dans tous les intervalles de durée. Un message sous le sélecteur de calendrier fournit des informations sur la période pendant laquelle les utilisateurs s’engagent et l’intervalle réservé uniquement aux utilisateurs récurrents :

* **[!UICONTROL Analyse des utilisateurs qui ont exécuté l’événement de début dans [Intervalle de date]]**: si un utilisateur interagit avec l’événement au cours de cette période, il est inclus dans l’analyse. Cette période garantit à tous les utilisateurs suffisamment de temps pour remplir les critères de tous les intervalles de durée. Cette période peut être différente de votre sélection si elle est proche du jour actuel.
* **[!UICONTROL Données provenant de [Intervalle de date] est réservé à la réalisation de l&#39;analyse]**: si un utilisateur s’engage pour la première fois au cours de cette période, ce sont **not** inclus dans l’analyse. Pour les plages de dates récentes, ces utilisateurs n’auraient pas la possibilité de remplir les conditions requises pour tous les intervalles de durée. Pour les périodes antérieures, ces utilisateurs étaient actifs en dehors de la période sélectionnée.

## Tableau de cohortes

Le tableau sous le graphique fournit une vue agrégée (similaire aux données du graphique) et un tableau de cohortes complet. Le tableau de cohortes complet fournit des détails sur chaque intervalle de dates individuel et le moment où les utilisateurs se sont engagés.
