---
description: Créez des périodes personnalisées dans Analysis Workspace et enregistrez-les sous la forme de composants de type Heure.
keywords: Analysis Workspace
title: Création de périodes personnalisées
topic: Reports and analytics
uuid: c8873d41-454d-4f22-ad1f-38cacec5a3bc
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 100%

---


# Création de périodes personnalisées

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

Créez des périodes personnalisées dans Analysis Workspace et enregistrez-les sous la forme de composants de type Heure.

**[!UICONTROL Composants]** > **[!UICONTROL Nouvelle période]**

Une période s’applique au niveau du panneau. Pour ajouter une période au projet, cliquez sur **Panneaux** > *`<select panel>`*, puis spécifiez une nouvelle période.

## Période pour « deux mois auparavant » 

La période personnalisée suivante présente une période pour « deux mois auparavant », avec une visualisation Synthèse des changements présentant le changement directionnel.

![](assets/date-range-two-months-ago.png)

La plage de dates personnalisée s’affiche au haut du panneau du composant [!UICONTROL Plage de dates] dans votre projet :

![](assets/date-range-panel-two-months-ago.png)

Vous pouvez la faire glisser dans une colonne le long d’une plage de dates variable mensuelle personnalisée, en utilisant pour comparaison le paramètre prédéfini Mois dernier. Ajoutez une visualisation Synthèse des changements et sélectionnez les totaux de chaque colonne pour afficher le changement directionnel :

![](assets/date-range-two-months-table.png)

## Utiliser une période variable de sept jours

Une plage de dates s’applique au niveau du panneau. Pour ajouter une plage de dates au projet, cliquez sur **Actions** > **Ajouter le panneau**, puis spécifiez une nouvelle plage de dates.

Dans le créateur de plages de dates, créez une plage de dates personnalisée qui s’affichera dans le panneau Composants avec les autres plages de dates.

Par exemple, vous pouvez créer une plage de dates qui spécifie un créneau variable de 7 jours qui s’est terminé il y a une semaine :

![](assets/create_date_range.png)

Sélectionnez l’option *`rolling daily`*.

* Le paramètre Début correspondrait à *`current day minus 14 days`*.

* Le paramètre Fin correspondrait à *`current day minus 7 days`*.

Cette période peut être un composant que vous faites glisser sur un tableau à structure libre.
