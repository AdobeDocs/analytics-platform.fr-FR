---
description: Les configurations des lignes varient selon le composant déposé dans le tableau.
title: Paramètres des lignes
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 89%

---


# Paramètres des lignes

>[!NOTE]
>
>Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

Les configurations des lignes varient selon le composant déposé dans le tableau.

Vous pouvez aussi gérer les lignes sélectionnées à l’aide des [options contextuelles (clic avec le bouton droit) dans un tableau](/help/analysis-workspace/visualizations/freeform-table.md).

Pour accéder aux paramètres de ligne d’un tableau, cliquez sur l’icône Paramètres en regard d’une dimension, d’un segment, d’une mesure, d’une période ou d’une ventilation :

![](assets/row-settings.png)

| Paramètre de ligne | Description |
|--- |--- |
| Comparaison de dates | Harmonisez les dates de chaque colonne afin qu’elles commencent à la même ligne.   Si vous harmonisez les dates, par exemple dans le cadre d’une comparaison d’un mois à l’autre entre octobre et septembre 2016, la colonne de gauche commence au 1er octobre et la colonne de droite au 1er septembre.<br>Option désactivée par défaut. |
| Pourcentages | Calcul des pourcentages par ligne  Oblige le tableau à structure libre à calculer les pourcentages des cellules par ligne, et non pas par colonne. Cette fonctionnalité est particulièrement utile pour les pourcentages de tendance.<br>Fonction activée par défaut lors de l’utilisation de l’icône Visualiser. |
| Totaux des colonnes | Ce paramètre est accessible uniquement pour les [static rows](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) (when you have selected a finite set of items), not with dynamic rows (i.e., when you drop in a dimension that shows all items).<ul><li>**[!UICONTROL Afficher la somme des lignes actuelles en tant que total]** : affiche la somme des lignes du tableau côté client, ce qui signifie que le total ne dédupliquera **pas** de mesures telles que les visites ou les visiteurs.</li><li>**[!UICONTROL Afficher le total général]** : indique une somme côté serveur, ce qui signifie que le total dédupliquera les mesures telles que les visites ou les visiteurs.</li></ul> |
| Ventilations | **[!UICONTROL Ventilation par position]** :  Ventilez les données en fonction d’une position fixe dans un tableau à structure libre. Vous pouvez par exemple spécifier que les sept premières lignes du tableau sont toujours ventilées.<br>(Auparavant, la liste des valeurs de la ventilation était « verrouillée ». Par conséquent, si par exemple vous aviez une ventilation de date par page, vous obteniez une liste des 50 premières pages pour la période sélectionnée. Si vous enregistriez ce rapport puis l’exécutiez à nouveau un mois plus tard, il est probable que les 50 premières pages auraient changé. Toutefois, Analysis Workspace utilisait les résultats de la ventilation d’origine et renvoyait les mêmes pages, avec pour période le mois en cours.)<br>Pour ventiler des données en fonction d’une position fixe : 1. Ventilez quelques lignes du tableau. 2. Cliquez sur l’icône de paramètres (engrenage) en regard de la ligne de tableau à définir sur une position fixe. 3. Activez la case à cocher en regard de l’option Ventilation par position. 4. Changez l’ordre de tri ou la plage de dates. Vous remarquerez que les ventilations sont maintenant liées à la position des lignes, et non aux lignes codées en dur.<br>Option désactivée par défaut. |