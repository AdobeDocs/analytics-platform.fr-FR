---
description: Documentation décrivant comment filtrer et trier les tables dans Analysis Workspace.
title: Filtrage et tri des tableaux
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
source-git-commit: 43c8af6f9010354258a702fb702a330873d9cb8e
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 7%

---

# Filtrage et tri des tableaux

Les tableaux à structure libre dans Analysis Workspace sont la base de l’analyse de données interactive. Ils peuvent donc contenir des milliers de lignes d’informations. Le filtrage et le tri des données peuvent constituer des éléments essentiels pour améliorer l’affichage des informations les plus importantes.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Filtrage des tableaux {#section_36E92E31442B4EBCB052073590C1F025}

Les filtres dans Analysis Workspace vous aident à afficher les informations les plus importantes.

Pour filtrer les données dans les tableaux à structure libre :

1. Dans un tableau à structure libre, passez la souris sur la colonne contenant les données à filtrer. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Sélectionnez la **Filtrer** s’affiche.

   ![Icône Filtrer dans un tableau](assets/table-filter-icon.png)

1. Dans le [!UICONTROL **Mot ou expression de recherche**] , indiquez un mot ou une expression que vous souhaitez filtrer. Seules les lignes contenant le mot ou l’expression exacte spécifiée s’affichent.

1. (Facultatif) Pour filtrer selon différents critères ou selon plusieurs critères, sélectionnez [!UICONTROL **Afficher les paramètres avancés**].

   Les options suivantes sont disponibles

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Inclure non spécifié (aucun)**] | Sélectionnez cette option pour afficher dans le tableau les données qui ne tombent dans aucune des dimensions du tableau. <!--what is this?--> |
   | [!UICONTROL **Correspond à**] | <p>Choisir [!UICONTROL **Si tous les critères sont satisfaits**] pour afficher uniquement les données qui répondent à tous les critères que vous spécifiez. Cette option produit généralement des données plus affinées.</p> <p>Choisir [!UICONTROL **Si l’un des critères est satisfait**] pour afficher les données qui répondent à l’un des critères de filtre que vous spécifiez. Cette option génère généralement des données moins affinées.</p> |
   | [!UICONTROL **Critères**] | <p>Sélectionnez l’une des options de filtre suivantes :</p><p>(Sélectionner) [!UICONTROL **Ajouter une ligne**] pour ajouter plusieurs critères de filtre. L’option que vous sélectionnez dans le [!UICONTROL **Correspondance**] détermine si tout ou partie des critères que vous ajoutez doit être satisfait.)</p><ul><li><p>[!UICONTROL **Contient l’expression**]: Seules les données contenant exactement l’expression que vous spécifiez sont incluses dans les résultats filtrés. Les mots doivent être dans l’ordre spécifié dans la variable [!UICONTROL **Champ de mot ou d’expression de recherche**].<p>Il s’agit du paramètre par défaut lors d’une recherche simple.</p></p></li><li><p>[!UICONTROL **Contient n’importe quel terme**]: Seules les données contenant un ou plusieurs mots de l’expression que vous spécifiez sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **Contient tous les termes**]: Seules les données contenant tous les mots de l’expression que vous spécifiez sont incluses dans les résultats filtrés. Les mots ne doivent pas nécessairement être dans l’ordre spécifié dans la variable [!UICONTROL **Champ de mot ou d’expression de recherche**].</p></li><li><p>[!UICONTROL **Ne contient aucun terme**]: Seules les données qui ne contiennent aucun des mots de l’expression que vous spécifiez sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **Ne contient pas l’expression**]: Seules les données qui ne contiennent pas l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. Les mots doivent être dans l’ordre spécifié dans la variable [!UICONTROL **Champ de mot ou d’expression de recherche**].</p></li><li><p>[!UICONTROL **Est égal à**]: Seules les données qui correspondent exactement à l’expression que vous spécifiez sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **N’est pas égal à**]: Seules les données qui ne correspondent pas exactement à l’expression spécifiée sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **Commence par**]: Seules les données commençant par le mot ou l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **Se termine par**]: Seules les données qui se terminent par le mot ou l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. </p></li></ul> |
   | [!UICONTROL **Toujours exclure les éléments**] | Indiquez le nom des éléments que vous souhaitez exclure des données filtrées. |

1. Sélectionner [!UICONTROL **Appliquer**] pour filtrer les données.

   Le **Filtrer** icon ![Icône Filtre bleu filtré tableau](assets/table-filter-blue-icon.png) devient bleu lorsqu’un filtre est appliqué au tableau.

## Tri des tableaux

Vous pouvez trier les données d’un tableau à structure libre selon n’importe quelle colonne d’Analysis Workspace qui est une Dimension ou une mesure.

Icône Flèche vers le bas ![Icône Flèche vers le bas dans la colonne du tableau trié](assets/table-sort-arrow-icon.png) est visible dans l’en-tête de la colonne par laquelle les données sont actuellement triées.

1. Dans un tableau à structure libre d’Analysis Workspace, cliquez sur la flèche en regard du nom de la Dimension ou de la mesure.

   Tenez compte des points suivants lors du tri :

   * La flèche de déplacement vers le bas trie par ordre descendant et la flèche vers le haut (par défaut) par ordre ascendant.
   * Vous pouvez trier les Dimensions par ordre alphabétique ou numérique. Par exemple, vous pouvez avoir des étapes numérotées dans un workflow et vouloir trier par numéro d’étape. Vous pouvez trier une dimension liée à la date en fonction de la date. Vous pouvez également trier les sources de données par ordre alphabétique, comme dans l’image suivante.

   ![](assets/sort-dimensions.png)


