---
description: Créez des périodes personnalisées dans Analysis Workspace et enregistrez-les sous la forme de composants de type Heure.
keywords: Analysis Workspace
title: Création de périodes personnalisées
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 85%

---

# Création de périodes personnalisées

Créez des périodes personnalisées dans Analysis Workspace et enregistrez-les sous la forme de composants de type Heure.

**[!UICONTROL Composants]** > **[!UICONTROL Nouvelle période]**

Une période s’applique au niveau du panneau. Pour ajouter une période au projet, cliquez sur **Panneaux** > *`<select panel>`*, puis spécifiez une nouvelle période.

## Période pour « deux mois auparavant » 

La période personnalisée suivante présente une période pour « deux mois auparavant », avec une visualisation Synthèse des changements présentant le changement directionnel.

![Créateur de plages de dates affichant Utiliser des dates variables pour il y a deux mois](assets/date-range-two-months-ago.png)

La plage de dates personnalisée s’affiche au haut du panneau du composant [!UICONTROL Plage de dates] dans votre projet :

![Panneau du composant Période avec une flèche pointant vers le haut il y a deux mois.](assets/date-range-panel-two-months-ago.png)

Vous pouvez la faire glisser dans une colonne le long d’une plage de dates variable mensuelle personnalisée, en utilisant pour comparaison le paramètre prédéfini Mois dernier. Ajoutez une visualisation Synthèse des changements et sélectionnez les totaux de chaque colonne pour afficher le changement directionnel :

![Synthèse des changements affiché et augmentation de 14,45 %.](assets/date-range-two-months-table.png)

## Utiliser une période variable de sept jours

Une plage de dates s’applique au niveau du panneau. Pour ajouter une plage de dates au projet, cliquez sur **Actions** > **Ajouter le panneau**, puis spécifiez une nouvelle plage de dates.

Dans le créateur de périodes, créez une période personnalisée qui s’affichera dans le panneau Composants avec les autres périodes.

Par exemple, vous pouvez créer une plage de dates qui spécifie un créneau variable de 7 jours qui s’est terminé il y a une semaine :

![Créateur de plages de dates présentant une plage de dates qui spécifie une fenêtre de suivi de 7 jours.](assets/create_date_range.png)

Utilisez *`rolling daily`*.

* Le paramètre Début correspondrait à *`current day minus 14 days`*.

* Le paramètre Fin correspondrait à *`current day minus 7 days`*.

Cette période peut être un composant que vous faites glisser sur un tableau à structure libre.
