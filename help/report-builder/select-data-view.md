---
title: Comment sélectionner une vue de données dans Report Builder
description: Décrit comment sélectionner des vues de données dans Adobe Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: bf765144-34f8-465b-b06d-53e4ca91014a
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 1%

---

# Sélectionner une vue de données

Vous pouvez sélectionner une vue de données dans le menu déroulant ou sélectionner une vue de données dans une cellule et mettre automatiquement à jour votre bloc de données avec une nouvelle vue de données.

## Sélectionner la vue de données depuis une cellule

La sélection d’une vue de données dans une cellule facilite l’actualisation des blocs de données à l’aide de différentes vues de données. Au lieu de créer des rapports entièrement nouveaux avec des blocs de données distincts, vous pouvez actualiser les blocs de données avec une vue de données sélectionnée à partir d’une cellule.

La sélection d’une vue de données à partir d’une cellule s’avère utile lorsque vous disposez des éléments suivants :

* Plusieurs vues de données similaires ou identiques dans leur structure.
* Formats de blocs de données complexes comprenant des composants et des mises en page personnalisés.

Pour sélectionner une vue de données dans une cellule, commencez par créer un bloc de données et affectez plusieurs vues de données à une cellule à l’extérieur de votre bloc de données. Utilisez ensuite le panneau **[!UICONTROL Vue de données à partir de la cellule]** pour actualiser vos blocs de données à partir de différentes vues de données.

1. Créez un bloc de données. Pour plus d’informations sur la création d’un bloc de données, voir [Créer un bloc de données](/help/report-builder/create-a-data-block.md).

1. Sélectionnez ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) dans **[!UICONTROL Vues des données]**.

1. Sélectionnez une cellule à l’aide de ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) en dehors du bloc de données.

1. Ajoutez une ou plusieurs vues de données à partir de la **[!UICONTROL Sélectionner les vues de données à ajouter à la vue de données à partir de la cellule]** en effectuant un glisser-déposer. Vous pouvez également sélectionner deux fois une vue de données pour l’ajouter à la liste **[!UICONTROL Vues de données incluses]**.

   * Vous pouvez utiliser ![Rechercher](/help/assets/icons/Search.svg) **[!UICONTROL _Sélectionner les vues de données_]** pour rechercher des vues de données.
   * Utilisez ![MoreSmall](/help/assets/icons/MoreSmall.svg) pour ouvrir un menu contextuel afin de déplacer les vues de données vers le haut ou vers le bas dans la liste **[!UICONTROL Vues de données incluses]**.
   * Utilisez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer une vue de données de la liste **[!UICONTROL Vues de données incluses]**.

   ![Sélectionner la vue de données depuis une cellule](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. Sélectionnez **[!UICONTROL Appliquer]** pour appliquer les vues de données sélectionnées à la cellule sélectionnée.


## Modifier la vue de données d’une cellule

1. Sélectionnez l’emplacement de la cellule de la vue de données dans votre feuille.
1. Dans le hub Report Builder, cliquez sur le lien **[!UICONTROL Vues de données à partir de la cellule]** dans **[!UICONTROL Modification rapide]**.
1. Sélectionnez une vue de données dans le menu déroulant **[!UICONTROL Vue de données]**.

   ![Modifier la vue de données d’une cellule](assets/change-data-view-from-cell.png){zoomable="yes"}
1. Facultatif, sélectionnez **[!UICONTROL Actualiser le(s) bloc(s) de données lors de la modification]**.

1. Sélectionnez **[!UICONTROL Appliquer]**. Report Builder actualise le bloc de données en fonction de la vue de données sélectionnée.
