---
description: Documentation décrivant comment filtrer et trier les tableaux dans Analysis Workspace.
title: Filtrer et trier des tableaux
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
source-git-commit: 54032271e8f12673cc6d4f2b209b4fa89f5c4406
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 79%

---

# Filtrer et trier des tableaux

Les tableaux à structure libre dans Analysis Workspace sont la base de l’analyse de données interactive. Ils peuvent donc contenir des milliers de lignes d’informations. Le filtrage et le tri des données peuvent constituer des éléments essentiels à l’amélioration de l’affichage des informations les plus importantes.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Filtrer des tableaux {#section_36E92E31442B4EBCB052073590C1F025}

Les filtres dans Analysis Workspace vous aident à afficher les informations les plus importantes.

>[!NOTE]
>
> Seuls les éléments de dimension dynamiques peuvent être filtrés comme décrit dans cette section. Les éléments de dimension statiques ne peuvent pas être filtrés. Pour plus d’informations, voir [Éléments de dimension dynamiques ou statiques dans les tableaux à structure libre](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

### Exclusion rapide de lignes spécifiques d’un tableau

Vous pouvez exclure rapidement des lignes spécifiques du tableau sans avoir à ouvrir la boîte de dialogue Filtrer .

>[!NOTE]
>
>Lorsque vous excluez des lignes comme décrit dans cette section, une [!UICONTROL **N’est pas égal à**] s’applique automatiquement dans la variable [**[!UICONTROL Filtrage avancé]**](#apply-a-simple-or-advanced-filter) boîte de dialogue.

Pour exclure rapidement des lignes spécifiques d’un tableau à structure libre :

1. Pointez sur la ligne à exclure, puis sélectionnez l’icône x.

   Maintenez la touche Maj enfoncée pour sélectionner une rangée ou maintenez la touche Commande (sur Mac) ou la touche Ctrl (sous Windows) enfoncée pour sélectionner plusieurs rangées.

### Application d’un filtre simple ou avancé à un tableau

Pour filtrer les données dans les tableaux à structure libre :

1. Pointez sur la colonne contenant les données à filtrer. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Sélectionnez l’icône **Filtre** lorsqu’elle s’affiche.

   ![Icône Filtre dans un tableau.](assets/table-filter-icon.png)

   Les options disponibles sont les suivantes :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Mot ou expression de recherche**] | Indiquez un mot ou une expression à filtrer. Seules les lignes contenant le mot ou l’expression exacte spécifié(e) sont affichées. |
   | [!UICONTROL **Inclure non spécifié (aucun)**] | Sélectionnez cette option pour afficher dans le tableau les données qui n’appartiennent à aucune des dimensions du tableau. <!--what is this?--> |

1. (Facultatif) Pour filtrer selon différents critères ou selon plusieurs critères, sélectionnez [!UICONTROL **Filtrage avancé**].

   Les options suivantes sont disponibles :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Inclure non spécifié (aucun)**] | Sélectionnez cette option pour afficher dans le tableau les données qui n’appartiennent à aucune des dimensions du tableau. <!--what is this?--> |
   | [!UICONTROL **Correspond à**] | <p>Choisissez [!UICONTROL **Si tous les critères sont satisfaits**] pour afficher uniquement les données qui répondent à tous les critères que vous spécifiez. Cette option produit généralement des données plus précises.</p> <p>Choisissez [!UICONTROL **Si au moins l’un des critères est satisfait**] pour afficher les données qui répondent à l’un des critères de filtre que vous spécifiez. Cette option aboutit généralement à des données moins précises.</p> |
   | [!UICONTROL **Critères**] | <p>Sélectionnez l’une des options de filtre suivantes :</p><p>(Sélectionnez [!UICONTROL **Ajouter une ligne**] pour ajouter plusieurs critères de filtre. L’option que vous sélectionnez dans la section [!UICONTROL **Correspondance**] détermine si la totalité ou une partie des critères que vous ajoutez doit être satisfaite.)</p><ul><li><p>[!UICONTROL **Contient l’expression**] : seules les données contenant l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. Les mots doivent être dans l’ordre spécifié dans le champ [!UICONTROL **Chercher un mot ou une expression**].<p>Il s’agit du paramètre par défaut lors d’une recherche simple.</p></p></li><li><p>[!UICONTROL **Contient n’importe quel terme**] : seules les données contenant un ou plusieurs mots de l’expression que vous spécifiez sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **Contient tous les termes**] : seules les données contenant tous les mots de l’expression que vous spécifiez sont incluses dans les résultats filtrés. Les mots n’ont pas nécessairement à être dans l’ordre spécifié dans le champ [!UICONTROL **Chercher un mot ou une expression**].</p></li><li><p>[!UICONTROL **Ne contient aucun terme**] : seules les données qui ne contiennent aucun des mots de l’expression que vous spécifiez sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **Ne contient pas l’expression**] : seules les données qui ne contiennent pas l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. Les mots doivent être dans l’ordre spécifié dans le champ [!UICONTROL **Chercher un mot ou une expression**].</p></li><li><p>[!UICONTROL **Est égal à**] : seules les données qui correspondent exactement à l’expression que vous spécifiez sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **N’est pas égal à**] : seules les données qui ne correspondent pas exactement à l’expression spécifiée sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **Commence par**] : seules les données commençant par le mot ou l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **Se termine par**] : seules les données qui se terminent par le mot ou l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. </p></li></ul> |
   | [!UICONTROL **Toujours exclure les éléments**] | Indiquez le nom des éléments que vous souhaitez exclure des données filtrées. |

1. Sélectionnez [!UICONTROL **Appliquer**] pour filtrer les données.

   L’icône **Filtre** ![Icône de filtre bleue du tableau filtré](assets/table-filter-blue-icon.png) devient bleue lorsqu’un filtre est appliqué au tableau.

## Trier les tableaux

Vous pouvez trier les données d’un tableau à structure libre selon n’importe quelle colonne d’Analysis Workspace qui est une dimension ou une mesure.

Une icône de flèche vers le bas ![Icône de flèche vers le bas dans la colonne du tableau trié](assets/table-sort-arrow-icon.png) est visible dans l’en-tête de la colonne par laquelle les données sont actuellement triées.

1. Dans un tableau à structure libre d’Analysis Workspace, cliquez sur la flèche en regard du nom de la dimension ou de la mesure.

   Tenez compte des points suivants lors du tri :

   * La flèche de déplacement vers le bas trie par ordre décroissant et la flèche vers le haut (par défaut) par ordre croissant.
   * Vous pouvez trier les dimensions par ordre alphabétique ou numérique. Par exemple, vous pouvez avoir des étapes numérotées dans un workflow et vouloir trier par numéro d’étape. Vous pouvez trier une dimension liée à la date en fonction de la date. Ou vous pouvez trier les sources de données par ordre alphabétique, comme dans l’image ci-après.

   ![](assets/sort-dimensions.png)


