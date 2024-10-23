---
description: Les configurations des lignes varient selon le composant déposé dans le tableau.
title: Paramètres des lignes
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
source-git-commit: 347ab5b400fb8a5fddc02878f779be7112d693ab
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 15%

---

# Paramètres des lignes

+++ Affichez une démonstration vidéo de cette fonctionnalité.

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

{{videoaa}}

+++

Les configurations des lignes varient selon le composant déposé dans le tableau. Pour accéder aux paramètres des lignes d’un tableau, sélectionnez ![ ](/help/assets/icons/Setting.svg) **[!UICONTROL Paramètres]** en regard d’une dimension, d’un filtre, d’une mesure, d’une période ou d’une ventilation dans chacun de ces objets.

![ Le tableau à structure libre met en surbrillance l’icône Paramètres pour les mesures ](assets/row-settings.png)

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Ventilation par position]** | Par défaut, ce paramètre est désactivé et les répartitions sont fixées aux éléments de la ligne statique. Imaginez, par exemple, que vous ventiliez les trois premiers éléments de dimension Page (page d’accueil, résultats de recherche, passage en caisse) par canal marketing. Ensuite, vous quittez le projet et revenez deux semaines plus tard. Lors de la réouverture du projet, les 3 premières pages ont changé. Désormais, la page d’accueil, les résultats de recherche et le passage en caisse figurent sur les 4 à 6 premières pages. Par défaut, les ventilations de canal marketing apparaissent toujours sous Page d’accueil, Résultats de la recherche et Passage en caisse, même si elles se trouvent désormais dans les lignes 4 à 6. <br>En revanche, la **répartition par position** répartit toujours les 3 premiers éléments, quelle que soit leur nature. En vous référant à l’exemple, lorsque vous rouvrez votre projet, les ventilations Canal marketing sont liées aux 3 premières pages du tableau. Et pas à la page d’accueil, aux résultats de recherche et au passage en caisse, qui se trouvent désormais dans les lignes 4 à 6. |
| **[!UICONTROL Pourcentages]** | **Calculer les pourcentages par colonne** (par défaut) : les pourcentages visibles dans les cellules sont calculés en fonction du total de la colonne. <br>**Calculer les pourcentages par ligne** : les pourcentages dans les cellules sont calculés sur la ligne, par opposition à la colonne inférieure, avec le total général comme dénominateur. Ce calcul est utile pour les pourcentages de tendance. |
| **[!UICONTROL Totaux des colonnes]** | Ces paramètres sont uniquement disponibles pour les lignes [statiques](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Afficher comme somme des lignes actuelles** affiche une somme des lignes du tableau côté client, ce qui signifie que le total ne déduplique *pas* les mesures telles que les visites ou les personnes. <br> **Afficher le total général** affiche une somme côté serveur, ce qui signifie le total des mesures dédupliquées. |

## Modification du nombre de lignes

Pour modifier le nombre de lignes affichées, procédez comme suit :

1. Cliquez sur le numéro en regard de **[!UICONTROL Lignes]** en haut de la première colonne du tableau.

   ![Tableau à structure libre présentant la liste déroulante de pour le nombre de lignes affichées. 400 lignes sont sélectionnées.](assets/change-row-count.gif)

1. Dans la liste déroulante, sélectionnez le nombre de lignes à afficher dans le tableau.


## Menu contextuel

Les options de menu contextuel suivantes sont disponibles lors de la sélection de l’en-tête de dimension.

| Option | Description |
| --- | --- |
| **[!UICONTROL Copier la sélection dans le Presse-papiers]** | Copiez la sélection de la visualisation dans le Presse-papiers. |
| **[!UICONTROL Télécharger des éléments au format CSV (*nom de dimension*)]** | Téléchargez immédiatement les éléments de dimension (jusqu’à 50 000 au maximum) de la visualisation sur votre appareil local. 50 000 éléments de dimension au maximum pour la dimension sélectionnée. |
| **[!UICONTROL Télécharger la sélection au format CSV]** | Téléchargez immédiatement les éléments de dimension de la visualisation sur votre appareil local. |
| **[!UICONTROL Créer un lien hypertexte pour tous les éléments de dimension]** | Créez des hyperliens pour tous les éléments de dimension. Voir [Hyperliens pour les dimensions dans une table à structure libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Modifier l’hyperlien pour tous les éléments de dimension]** | Modifier des hyperliens pour tous les éléments de dimension. Voir [Hyperliens pour les dimensions dans une table à structure libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Supprimer l’hyperlien pour tous les éléments de dimension]** | Supprimez les hyperliens pour tous les éléments de dimension. Voir [Hyperliens pour les dimensions dans une table à structure libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Supprimer]** | Supprime la dimension du tableau. |
| **[!UICONTROL Visualisation]** | Visualisez la dimension à l’aide des visualisations disponibles. |
| **[!UICONTROL Afficher uniquement les lignes sélectionnées]** | Afficher uniquement les éléments sélectionnés dans la visualisation. |
| **[!UICONTROL Créer une annotation d’après la sélection]** | Ouvrez les **[!UICONTROL détails de l’annotation]** pour ajouter une annotation. |


Les options de menu contextuel supplémentaires suivantes sont disponibles lorsque vous sélectionnez un ou plusieurs éléments de dimension (première colonne) ou une ou plusieurs cellules individuelles dans le tableau à structure libre.

| Option | Description |
| --- | --- |
| **[!UICONTROL Créer un lien hypertexte]** | Créez un lien hypertexte pour l’élément. Voir [Hyperliens pour les dimensions dans une table à structure libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Modifier l’hyperlien]** | Modifiez un lien hypertexte pour l’élément. Voir [Hyperliens pour les dimensions dans une table à structure libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Supprimer l’hyperlien]** | Supprimez un lien hypertexte pour l’élément. Voir [Hyperliens pour les dimensions dans une table à structure libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Répartition]** | Ventilez l’élément de dimension. Sélectionnez dans la liste des **[!UICONTROL Dimensions]**, **[!UICONTROL Mesures]**, **[!UICONTROL Filtres]** ou **[!UICONTROL Plages de dates]**. Recherche alternative d’un composant à l’aide de *Recherche*. |
| **[!UICONTROL Supprimer sélectionné]** | Supprimer les lignes sélectionnées (éléments). |
| **[!UICONTROL Sélection de tendances]** | Créez une visualisation de graphique en courbes de tendance pour la sélection. |
| **[!UICONTROL Afficher uniquement les lignes sélectionnées]** | Afficher uniquement les lignes sélectionnées dans la visualisation. |
| **[!UICONTROL Afficher toutes les lignes]** | Afficher toutes les lignes dans la visualisation. |
| **[!UICONTROL Créer un filtre d’après la sélection]** | Ouvrez le **[!UICONTROL Créateur de filtres]** pour créer un filtre à partir de la sélection. |
| **[!UICONTROL Créer une audience d’après la sélection]** | Ouvrez la boîte de dialogue **[!UICONTROL Créer une audience]** pour créer une audience à partir de la sélection. |

Les options de menu contextuel supplémentaires suivantes sont disponibles lors de la sélection de l’en-tête d’une colonne de mesures.

| Option | Description |
|---|---|
| **[!UICONTROL Créer une mesure d’après la sélection]** | Créez une mesure à partir de la mesure sélectionnée. La mesure peut être Moyenne, Média, Max. colonne, Min. colonne, Somme des colonnes. Vous pouvez également sélectionner Ouvrir dans le créateur de mesures calculées pour créer une mesure calculée. |
| **[!UICONTROL Ajout d’une colonne de période]** | Ajoutez une colonne de période. Vous disposez de plusieurs options, où la plage de calendrier du panneau détermine la *plage de dates* : <li>**[!UICONTROL Avant *période* jusqu’à cette période]**</li><li>**[!UICONTROL Ces *plages de dates* jusqu’à cette plage de dates]**.</li><li>**[!UICONTROL Période personnalisée jusqu’à cette période]**. Ouvre le **[!UICONTROL créateur de plages de dates]** pour spécifier la plage de dates.</li>Voir [Comparaison de dates](/help/components/date-ranges/time-comparison.md) pour plus d’informations. |
| **[!UICONTROL Comparaison de périodes]** | Permet d’ajouter des colonnes de périodes de comparaison. Disponible uniquement lorsque la dimension n’est pas basée sur l’heure. Plusieurs options vous sont proposées pour déterminer la *période* : <li>**[!UICONTROL Avant *période* jusqu’à cette période]**</li><li>**[!UICONTROL Période personnalisée jusqu’à cette période]**. Ouvre le **[!UICONTROL créateur de plages de dates]** pour spécifier la plage de dates.</li>Voir [Comparaison de dates](/help/components/date-ranges/time-comparison.md) pour plus d’informations. |
| **[!UICONTROL Modifier les modèles d’attribution]** | Modifiez le modèle d’attribution de la colonne. |
| **[!UICONTROL Comparer le modèle d’attribution]** | Spécifiez un nouveau modèle d’attribution et comparez-le au modèle d’attribution pour la colonne sélectionnée. Une nouvelle colonne est ajoutée avec les nouvelles mesures de modèle d’attribution. Une colonne Pourcentage de changement est également ajoutée pour la comparaison. |
| **[!UICONTROL Réinitialiser la largeur des colonnes]** | Réinitialisez la largeur par défaut des largeurs de colonne. |
| **[!UICONTROL Créer une annotation d’après la sélection]** | Ouvrez les **[!UICONTROL détails de l’annotation]** pour ajouter une annotation. |
| **[!UICONTROL Créer un filtre d’après la sélection]** | Ouvrez le **[!UICONTROL Créateur de filtres]** pour créer un filtre à partir de la sélection. |
| **[!UICONTROL Créer une audience d’après la sélection]** | Ouvrez la boîte de dialogue **[!UICONTROL Créer une audience]** pour créer une audience à partir de la sélection. |
