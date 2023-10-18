---
title: Taux de fidélisation
description: Mesurez le nombre d’utilisateurs qui continuent à utiliser votre produit.
feature: Guided Analysis
keywords: analytics du produit
source-git-commit: 74525c4ce9ad1fd3f3abf35a9d9cb2c521d23874
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 1%

---

# Taux de fidélisation

La variable **[!UICONTROL Taux de rétention]** affiche le pourcentage d’utilisateurs qui reviennent après leur engagement initial au cours de la période souhaitée. L’axe horizontal représente le nombre de jours depuis le premier engagement d’un utilisateur. L’axe vertical représente le pourcentage d’utilisateurs qui reprennent le contact.

Cette analyse comptabilise les utilisateurs en fonction de deux événements importants :

* Première interaction d’un utilisateur avec l’événement au cours de la période
* La dernière fois qu’un utilisateur s’est engagé dans l’événement au cours de la période analysée

L’intervalle de durée &quot;jour 0&quot; représente la première fois qu’un utilisateur interagit avec l’événement, et est toujours exactement égal à 100 %. Le temps qui s’écoule entre l’engagement initial et l’engagement de retour détermine l’emplacement sous lequel l’utilisateur apparaît.

* Si un utilisateur interagit avec l’événement une seule fois pendant la période souhaitée (l’engagement initial), il apparaît uniquement dans l’intervalle de durée &quot;jour 0&quot;.
* Si un utilisateur interagit avec l’événement plusieurs jours après s’être qualifié pour la première fois pour être inclus dans l’analyse, il apparaît dans le dernier intervalle de durée de qualification et dans tous les intervalles de durée qui le précèdent.
* Si un utilisateur interagit plusieurs fois avec l’événement au cours de la période configurée, seuls les premiers et derniers événements sont inclus dans l’analyse.

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Analyse des cohortes**: regroupez les utilisateurs en cohortes en fonction de n’importe quel événement, comme les inscriptions ou les achats. Vous pouvez comparer l’attractivité de ces groupes et déterminer comment améliorer l’expérience utilisateur de ce groupe.
* **Analyse du service d&#39;abonnements**: si votre produit utilise un abonnement ou un autre type de modèle de revenu récurrent, vous pouvez voir le pourcentage d’utilisateurs qui tirent le meilleur parti de votre produit. Ceux qui n’utilisent pas votre produit ou service sont plus susceptibles de se produire, ce qui vous permet d’identifier ces utilisateurs et de vous concentrer sur ces utilisateurs.
* **Engagement des utilisateurs**: évaluez la manière dont certains types d’utilisateurs interagissent avec votre produit et comparez côte à côte la fréquence à laquelle ils reviennent. Un segment donné avec une courbe de rétention plus rapide que les autres peut vous fournir des informations sur l’amélioration des expériences inférieures potentielles qu’il pourrait avoir.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Événement de démarrage et de retour]**: critères d’événement avec lesquels un utilisateur doit interagir pour être inclus dans votre analyse. Un événement est pris en charge, mais vous pouvez inclure des filtres de propriétés.
* **[!UICONTROL Personnes]**: segments que vous souhaitez mesurer. Chaque segment sélectionné ajoute une ligne au tableau de cohortes. Vous pouvez inclure jusqu’à trois segments.

## Paramètres du graphique

La variable [!UICONTROL Taux de rétention] La vue propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Mesure]**: méthode de mesure des utilisateurs conservés. Les options incluent [!UICONTROL Utilisateurs conservés] et [!UICONTROL Pourcentage d&#39;utilisateurs conservés].
* **[!UICONTROL Type de graphique]**: type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Barre] et [!UICONTROL Ligne].

## Paramètres de durée

Permet de contrôler l’affichage des utilisateurs par le nombre de jours écoulés dans l’analyse.

* **[!UICONTROL Durée automatique]**: définit automatiquement des durées en fonction de la durée de la période et de la proximité par rapport au jour en cours de la période.
* **[!UICONTROL Dates personnalisées]**: définissez manuellement les jours écoulés souhaités. Vous pouvez définir quatre durées.

Vous ne pouvez pas définir une durée supérieure au temps nécessaire pour qu’un utilisateur interagisse avec un événement et soit admissible pour le dernier intervalle de durée avant d’atteindre le jour actuel. Par exemple, si la date actuelle est le 30 septembre et que la période que vous avez configurée est le 1er au 30 septembre, la durée maximale pour cette période est de 14 jours.

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: granularité de date que vous souhaitez voir pour les données de rétention. Les options valides sont Quotidienne, Hebdomadaire, Mensuelle et Trimestrielle. Une même période peut avoir des intervalles différents, ce qui affecte automatiquement la définition de jours de durée.
* **[!UICONTROL Date]**: date de début et date de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.

Si vous sélectionnez une période proche du jour actuel, les utilisateurs qui s’engagent trop près du jour en cours ne sont pas inclus. Cette analyse permet toujours à tous les utilisateurs d’être inclus dans tous les intervalles de durée. Un message sous le sélecteur de calendrier fournit des informations sur la période pendant laquelle les utilisateurs s’engagent et l’intervalle réservé uniquement aux utilisateurs récurrents :

* **Analyser la première [Intervalle de date] de la cohorte de [Période]**: si un utilisateur interagit avec l’événement au cours de cette période, il est inclus dans l’analyse. Cette période garantit à tous les utilisateurs suffisamment de temps pour remplir les critères de tous les intervalles de durée. Cette période peut être différente de votre sélection si elle est proche du jour actuel.
* **La finale [Intervalle de date] est réservé à la réalisation de l&#39;analyse**: si un utilisateur interagit avec l’événement pour la première fois dans cet intervalle, ce sont les **not** inclus dans l’analyse. Les utilisateurs qui interagissent initialement avec l’événement au cours de cet intervalle n’auraient pas la possibilité de remplir tous les critères pour les intervalles de durée, ou se trouvent en dehors de la période souhaitée.

## Tableau de cohortes

Le tableau sous le graphique fournit une vue agrégée (similaire aux données du graphique) et un tableau de cohortes complet. Le tableau de cohortes complet fournit des détails sur chaque intervalle de dates individuel et le moment où les utilisateurs se sont engagés.
