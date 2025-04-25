---
title: Utilisation des segments dans Report Builder dans Customer Journey Analytics
description: Décrit comment utiliser des segments dans Report Builder pour Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
source-git-commit: 6dd8a70293161ff58361953a7e48a98834b7abe0
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 6%

---

# Utilisation des segments

Vous pouvez appliquer des segments lorsque vous créez un bloc de données ou lorsque vous sélectionnez **[!UICONTROL Modifier le bloc de données]** dans le panneau **[!UICONTROL Commandes]**.

## Application de segments à un bloc de données

Pour appliquer un segment à l’ensemble du bloc de données, sélectionnez deux fois un segment ou faites glisser des segments de la liste des composants vers la section des segments du tableau.

## Application de filtres à des mesures individuelles

Pour appliquer des filtres à l’aide de segments à des mesures individuelles :

* Effectuez un glisser-déposer d’un ou plusieurs segments depuis **[!UICONTROL Segments]** vers une mesure du tableau.

* Sinon :

   1. Sélectionnez ![PlusPetit](/help/assets/icons/MoreSmall.svg) pour une mesure spécifique dans le volet **[!UICONTROL Tableau]**, puis sélectionnez **[!UICONTROL Filtrer la mesure]**.

      ![onglet segments affichant les mesures.](./assets/filter-metric.png){zoomable="yes"}

   1. Sélectionnez un ou plusieurs segments dans le menu déroulant **[!UICONTROL Segments]**. Les segments sont ajoutés à la liste **[!UICONTROL Segments appliqués]**.

      ![Segments appliqués](assets/segments-applied.png)
   1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer un segment de la liste **[!UICONTROL Segment appliqué]**. Ou sélectionnez **[!UICONTROL Effacer tout]** pour supprimer tous les segments de la liste **[!UICONTROL Segment appliqué]**.
   1. Sélectionnez **[!UICONTROL Appliquer]**.

Pour afficher les filtres appliqués, survolez une mesure avec la souris ou sélectionnez-la dans le volet Tableau. Les mesures avec des segments appliqués affichent une icône de segment.


## Modification rapide de segments

Vous pouvez utiliser le panneau **[!UICONTROL Modification rapide]** pour ajouter, supprimer ou remplacer des segments pour des blocs de données existants.

Lorsque vous sélectionnez une plage de cellules dans la feuille de calcul, le lien **[!UICONTROL Segments]** du panneau **[!UICONTROL Modification rapide]** affiche une liste récapitulative des segments utilisés par les blocs de données dans cette sélection.

Pour modifier des segments à l’aide du panneau **[!UICONTROL Modification rapide]** :

1. Sélectionnez une plage de cellules à partir dʼun ou de plusieurs blocs de données.

1. Sélectionnez le lien **[!UICONTROL Segments]** pour lancer le panneau **[!UICONTROL Modification rapide]** **[!UICONTROL Segments]**.


### Ajouter ou supprimer des segments

Vous pouvez ajouter ou supprimer des segments à l’aide des options Ajouter/Supprimer .

1. Sélectionnez l’onglet **[!UICONTROL Ajouter/Supprimer]** dans le panneau **[!UICONTROL Modification rapide]** **[!UICONTROL Segments]**.


   1. Sélectionnez un ou plusieurs segments dans le menu déroulant **[!UICONTROL Segments]**. Les segments sont ajoutés à la liste **[!UICONTROL Segments appliqués]**.
   1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer un segment de la liste **[!UICONTROL Segment appliqué]**.
   1. Sélectionnez **[!UICONTROL Appliquer]**.

Report Builder affiche un message pour confirmer les modifications apportées au segment.

### Remplacer les segments

Vous pouvez remplacer un segment existant par un autre segment pour modifier la manière dont les données sont segmentées.

1. Sélectionnez l’onglet **[!UICONTROL Remplacer]** dans le panneau **[!UICONTROL Modification rapide]** **[!UICONTROL Segments]**.

1. Utilisez le champ de recherche **Liste de recherche** pour localiser des segments spécifiques.

1. Sélectionnez un ou plusieurs segments à remplacer.

1. Recherchez un ou plusieurs segments dans le menu déroulant Remplacer par pour ajouter le segment à la liste **[!UICONTROL Remplacer par]**.

1. Sélectionnez **[!UICONTROL Appliquer]**.

Report Builder met à jour la liste des segments pour refléter le remplacement.

## Définir des segments de blocs de données depuis la cellule

Les blocs de données peuvent référencer des segments à partir d’une cellule. Plusieurs blocs de données peuvent référencer la même cellule pour des segments, ce qui vous permet de changer facilement de segment pour plusieurs blocs de données à la fois.

Pour appliquer des segments à partir d’une cellule :

1. [Créez un bloc de données](create-a-data-block.md#create-a-data-block) ou modifiez un bloc de données existant.
1. Sélectionnez l’onglet **[!UICONTROL Segments]** pour définir des segments.
1. Sélectionnez ![DataViewSelector](/help/assets/icons/DataViewSelector.svg).

   ![Sélectionner un segment dans la cellule](assets/select-segment-from-cell.png){zoomable="yes"}

1. Sélectionnez la cellule à partir de laquelle vous souhaitez que les blocs de données référencent un segment.

1. Sélectionnez deux fois pour ajouter un segment à la cellule. Vous pouvez également faire glisser et déposer un ou plusieurs segments dans la section **[!UICONTROL Segments inclus]**.

1. Sélectionnez **[!UICONTROL Appliquer]** pour créer la cellule de référence.

1. Dans l’onglet **Segments**, ajoutez le segment de cellule de référence nouvellement créé à votre bloc de données.

   ![onglet segments affichant le segment Sheet1!J1(All Data) ajouté au tableau.](assets/segment-from-cell-applied.png){zoomable="yes"}

1. Sélectionnez **[!UICONTROL Terminer]**.

Pour appliquer la cellule de référence sous la forme d’un segment à d’autres blocs de données, utilisez la référence de cellule comme l’un des segments de la liste **[!UICONTROL Segments]** de l’onglet **[!UICONTROL Tableau]**.

### Utiliser une cellule de référence pour modifier les segments de bloc de données

1. Sélectionnez la cellule de référence dans votre feuille de calcul.

1. Sélectionnez le lien sous **[!UICONTROL Segments depuis la cellule]** dans le menu **[!UICONTROL Modification rapide]**.

   ![segments du lien de cellule affichant Sheet1!J1 (Toutes les données)](assets/select-segment-from-cell-in-sheet.png){zoomable="yes"}

1. Sélectionnez votre segment dans le menu déroulant.

1. Sélectionnez **[!UICONTROL Appliquer]**.
