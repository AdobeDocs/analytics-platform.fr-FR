---
description: Ventilez les dimensions et les éléments de dimension dans Analysis Workspace.
keywords: Analysis Workspace
title: Ventilation des dimensions
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 58%

---

# Ventilation des dimensions dans Workspace

Vous pouvez ventiler vos données de manière illimitée en fonction de vos besoins ; créer des requêtes à l’aide de mesures, dimensions, filtres, chronologies et autres valeurs de ventilation d’analyse pertinentes.

1. Dans une [table à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), dans le menu contextuel d’une ou de plusieurs lignes sélectionnées, sélectionnez **[!UICONTROL Ventilation]** ![ChevronRight](/help/assets/icons/ChevronRight.svg).

   ![Résultat de l’étape présentant l’option Créer une alerte d’après la sélection sélectionnée.](assets/breakdown.png)

1. Dans le sous-menu, sélectionnez **[!UICONTROL Dimensions]**, **[!UICONTROL Mesures]**, **[!UICONTROL Filtres]** ou **[!UICONTROL Plages de données]**, puis sélectionnez un élément.

Vous pouvez ventiler les mesures par éléments de dimension ou filtres d’audience sur plusieurs périodes sélectionnées. Vous pouvez également approfondir l’analyse à un niveau plus détaillé.

>[!NOTE]
>
>Vous ne pouvez pas afficher plus de 200 répartitions dans le tableau. Cette limite augmente dans le cas de l’exportation des répartitions.

## Répartition par position

Par défaut, les ventilations sont fixes en éléments de ligne statiques. Imaginez, par exemple, que vous ventiliez les trois premiers éléments de dimension Page (page d’accueil, résultats de recherche, passage en caisse) par canal marketing. Ensuite, vous quittez le projet et revenez deux semaines plus tard. Lors de la réouverture du projet, les 3 premières pages ont changé. Désormais, la page d’accueil, les résultats de recherche et le passage en caisse figurent sur les 4 à 6 premières pages. Par défaut, les ventilations de canal marketing apparaissent toujours sous Page d’accueil, Résultats de la recherche et Passage en caisse, même si elles se trouvent désormais dans les lignes 4 à 6.

En revanche, la **ventilation par position** ventile toujours les 3 premiers éléments, quels que soient ces éléments. En vous référant à l’exemple, lorsque vous rouvrez votre projet, les ventilations Canal marketing sont liées aux 3 premières pages du tableau. Et pas à la page d’accueil, aux résultats de recherche et au passage en caisse, qui se trouvent désormais dans les lignes 4 à 6. Voir [Paramètres des lignes](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md) pour configurer ce paramètre.



## Application des modèles d’attribution aux répartitions

Il est également possible d’appliquer n’importe quel modèle d’attribution à n’importe quelle répartition dans un tableau. Ce modèle d’attribution peut être identique ou non à la colonne parente. Par exemple, vous pouvez analyser les Commandes linéaires au niveau de la dimension de vos canaux marketing, mais appliquer les Commandes en forme de U aux codes de suivi spécifiques au sein d’un canal. Pour modifier le modèle d’attribution appliqué à une ventilation, passez la souris sur le modèle de ventilation et sélectionnez **[!UICONTROL Modifier]**.

![Comparaison des attributs de commande montrant les paramètres de ventilation](assets/breakdown-attribution.png)

Voici le comportement attendu lors de l’application des modèles d’attribution aux répartitions ou de leur modification :

* Si vous appliquez une attribution lorsqu’il n’en existe aucune autre, celle-ci s’applique à l’ensemble de l’arborescence des colonnes.

* Si vous ajoutez une répartition après l’application d’une attribution, elle utilise la valeur par défaut de la répartition donnée qui a été ajoutée (si cette dimension comporte une valeur par défaut). Sinon, elle utilisera la répartition de la colonne parente. Certaines dimensions disposent d’une attribution par défaut. Par exemple, les dimensions de temps et le référent utilisent la même touche. La dimension Produit utilise la dernière touche. Les autres dimensions ne disposent pas de valeur par défaut et utiliseront l’attribution de la colonne parente.

* Si des attributions sont déjà disponibles dans l’arborescence des colonnes, la modification de l’attribution n’a un impact que sur celle que vous modifiez.

+++ Affichage de vidéos illustrant les ventilations

Dimensions dans Analysis Workspace

>[!VIDEO](https://video.tv.adobe.com/v/23971)

Ventilations des Dimensions

>[!VIDEO](https://video.tv.adobe.com/v/23969)

Ajout de dimensions et de mesures à votre projet dans Analysis Workspace :

>[!VIDEO](https://video.tv.adobe.com/v/30606)

Utilisation des dimensions dans un tableau à structure libre :

>[!VIDEO](https://video.tv.adobe.com/v/40179)

Répartition des dimensions par position :

>[!VIDEO](https://video.tv.adobe.com/v/24033)

{{videoaa}}

+++
