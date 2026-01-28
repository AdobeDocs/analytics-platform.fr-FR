---
description: Découvrez comment filtrer et trier les tableaux à structure libre dans Analysis Workspace.
title: Filtrer Et Trier
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: 696bd0db44949162307d8ce7d2debed351a76cd6
workflow-type: tm+mt
source-wordcount: '1575'
ht-degree: 46%

---

# Filtrer et trier des tableaux à structure libre

Les tableaux à structure libre dans Analysis Workspace sont la base de l’analyse de données interactive. Ils peuvent donc contenir des milliers de lignes d’informations. Le filtrage et le tri des données peuvent constituer des éléments essentiels à l’amélioration de l’affichage des informations les plus importantes.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/327341?captions=fre_fr)-->

## Filtrer des tableaux

Les filtres dans Analysis Workspace vous aident à afficher les informations les plus importantes.

>[!NOTE]
>
> Seuls les éléments de dimension dynamiques peuvent être filtrés comme décrit dans cette section. Les éléments de dimension statiques ne peuvent pas être filtrés. Pour plus d’informations, consultez [Éléments de dimension dynamiques ou statiques dans les tableaux à structure libre](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

Vous pouvez utiliser plusieurs méthodes pour filtrer les lignes d’un tableau à structure libre.

* Exclure des lignes spécifiques d’un tableau
* Appliquer des filtres à un tableau
* Utiliser les segments d’audience

Veillez à lire comment chaque méthode affecte les [totaux des tableaux à structure libre](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### Exclure des lignes spécifiques d’un tableau

Vous pouvez rapidement exclure des lignes spécifiques du tableau sans avoir à utiliser ![Filtrer](/help/assets/icons/Filter.svg) **[!UICONTROL Filtrer]**.

>[!NOTE]
>
>Lorsque vous excluez des lignes comme décrit dans cette section, une règle [!UICONTROL Toujours exclure les éléments] est automatiquement ajoutée dans la boîte de dialogue de filtre [!UICONTROL Avancé]. Vous pouvez afficher la règle appliquée en sélectionnant l’icône ![Filtrer](/help/assets/icons/Filter.svg) Filtrer, puis [**[!UICONTROL Afficher les paramètres avancés]**](#apply-a-simple-or-advanced-filter-to-a-table).

Pour exclure des lignes spécifiques d’un tableau à structure libre :

1. Pointez sur la ligne à exclure, puis sélectionnez ![Fermer](/help/assets/icons/Close.svg).

   Maintenez la touche ***Maj*** enfoncée pour sélectionner une plage de lignes ou la touche ***Commande*** (sous Mac) ou la touche ***Ctrl*** (sous Windows) enfoncée pour sélectionner plusieurs lignes.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### Appliquer un filtrage simple ou avancé à un tableau

Pour filtrer les données dans les tableaux à structure libre :

1. Pointez sur la colonne contenant les données à filtrer. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) **Filtrer** lorsque l’option s’affiche.

   ![Tableau à structure libre mettant en surbrillance l’icône Filtrer.](assets/table-filter-icon.png)

   Les options suivantes sont disponibles dans la boîte de dialogue **[!UICONTROL Rechercher]** :

   ![Filtre simple](assets/filter-simple.png){width="500"}

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Inclure « Aucune valeur »**] | Sélectionnez cette option pour afficher une ligne **[!UICONTROL Aucune valeur]** dans le tableau pour les données qui n’ont aucune valeur pour la dimension sélectionnée. Désélectionnez cette option pour masquer les lignes **[!UICONTROL Aucune valeur]**.<!-- Add at multi dim GA: When tables include multiple dimension columns, you can deselect this option to show data only when it applies to each dimension column in the table.--> |
   | [!UICONTROL **Mot ou expression de recherche**] | Spécifiez un mot ou une expression à utiliser comme filtre. Seules les lignes contenant le mot ou l’expression exacte spécifié(e) sont affichées. |


1. (Facultatif) Pour filtrer selon différents ou plusieurs critères, sélectionnez [!UICONTROL **Afficher les paramètres avancés**].

   Les options avancées de filtre disponibles sont les suivantes :

   ![Filtre simple](assets/filter-advanced.png){width=500}

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Inclure « Aucune valeur »**] | Sélectionnez cette option pour afficher une ligne **[!UICONTROL Aucune valeur]** dans le tableau pour les données qui n’ont aucune valeur pour la dimension sélectionnée. Désélectionnez cette option pour masquer la ligne **[!UICONTROL Aucune valeur]**. |
   | [!UICONTROL **Correspond à**] | Choisissez [!UICONTROL **Si tous les critères sont satisfaits**] pour afficher uniquement les données qui répondent à tous les critères que vous spécifiez. Cette option produit généralement des données plus précises.<br/><br/>Choisissez [!UICONTROL **Si au moins l’un des critères est satisfait**] pour afficher les données qui répondent à l’un des critères de filtre que vous spécifiez. Cette option aboutit généralement à des données moins précises. |
   | [!UICONTROL **Critères**] | Sélectionnez l’une des options de filtre suivantes :<br/><ul><li>[!UICONTROL **Contient l’expression**] (par défaut) : seules les données contenant l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. Les mots doivent être dans l’ordre spécifié dans le champ [!UICONTROL **Chercher un mot ou une expression**].</li><li>[!UICONTROL **Contient n’importe quel terme**] : seules les données contenant un ou plusieurs mots de l’expression que vous spécifiez sont incluses dans les résultats filtrés. </li><li>[!UICONTROL **Contient tous les termes**] : seules les données contenant tous les mots de l’expression que vous spécifiez sont incluses dans les résultats filtrés. Les mots n’ont pas nécessairement à être dans l’ordre spécifié dans le champ [!UICONTROL **Chercher un mot ou une expression**].</li><li>[!UICONTROL **Ne contient aucun terme**] : seules les données qui ne contiennent aucun des mots de l’expression que vous spécifiez sont incluses dans les résultats filtrés. </li><li>[!UICONTROL **Ne contient pas l’expression**] : seules les données qui ne contiennent pas l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. Les mots doivent être dans l’ordre spécifié dans le champ [!UICONTROL **Chercher un mot ou une expression**].</li><li>[!UICONTROL **Est égal à**] : seules les données qui correspondent exactement à l’expression que vous spécifiez sont incluses dans les résultats filtrés. </li><li>[!UICONTROL **N’est pas égal à**] : seules les données qui ne correspondent pas exactement à l’expression spécifiée sont incluses dans les résultats filtrés. </li><li>[!UICONTROL **Commence par**] : seules les données commençant par le mot ou l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. </li><li>[!UICONTROL **Se termine par**] : seules les données qui se terminent par le mot ou l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. </li></ul>Sélectionnez ![Ajouter](/help/assets/icons/Add.svg) [!UICONTROL **Ajouter une ligne**] pour ajouter plusieurs critères de filtre. L’option que vous sélectionnez pour [!UICONTROL **Correspondance**] détermine **[!UICONTROL Si tous les critères sont satisfaits]** ou **[!UICONTROL Si au moins l’un des critères est satisfait]**. |
   | [!UICONTROL **Toujours exclure les éléments**] | Indiquez le nom des éléments que vous souhaitez exclure des données filtrées. |

1. Sélectionnez **[!UICONTROL Appliquer]** pour filtrer les données. Sélectionnez **[!UICONTROL Effacer]** pour effacer toutes les saisies. Sélectionnez **[!UICONTROL Annuler]** pour annuler et fermer la boîte de dialogue  <br/>Une icône colorée ![Filtre](/help/assets/icons/FilterColored.svg) **Filtre** indique et affiche les détails lorsqu’un filtre est appliqué au tableau.

### Incluez des critères de filtre dans les données de tendance dans les graphiques sparkline et en ligne {#include-filter-criteria}

Tous les critères de filtre de recherche appliqués à la dimension du tableau à structure libre sont toujours inclus dans les graphiques sparkline.

Outre les graphiques sparkline, vous pouvez configurer des critères de filtre à inclure dans les visualisations lignes connectées. (Par défaut, les critères de filtre ne sont pas inclus dans les visualisations en ligne. Les visualisations en ligne affichent les données de la ligne sélectionnée dans le tableau connecté. Si aucune ligne n&#39;est sélectionnée, seules les données de la première dimension du tableau connecté sont affichées.)

Pour plus d’informations sur les graphiques sparkline et les visualisations en ligne, voir [Affichage des données de tendances pour un tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).

#### Configuration des visualisations en ligne pour inclure des critères de filtre

1. Sélectionnez le graphique sparkline dans l’en-tête de colonne de mesures.

   Lorsque la cellule du graphique sparkline est sélectionnée, elle s’affiche en gris foncé. Cela indique que les critères de filtre sont inclus dans la visualisation Ligne connectée. Le critère de filtre est appliqué sous la forme d’un segment sur la colonne. <!--show how to see it? Show what the segment looks like when it's applied? -->

   ![graphique sparkline sélectionné](assets/table-sparkline-selected.png)

#### Comprendre quand les totaux des colonnes peuvent être inexacts

Les totaux des colonnes peuvent ne pas être exacts dans les scénarios suivants :

* Lorsque des composants statiques sont utilisés dans la colonne de gauche et que [les totaux des colonnes sont calculés comme la somme des lignes](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)

  Si des éléments de ligne contiennent des données qui se chevauchent dans ce scénario, les totaux des colonnes seront inexacts.

  Par exemple, si vous ajoutez des segments statiques à la colonne de gauche, puis que vous ajoutez des utilisateurs en tant que mesure dans la colonne de droite, certains de ces utilisateurs peuvent faire partie de plusieurs segments statiques. Dans ce cas, Workspace ne déduplique pas les utilisateurs pour chaque segment statique. Cela peut entraîner un nombre total d’utilisateurs plus élevé, car certains utilisateurs peuvent être comptabilisés plus d’une fois.

* Lors de l’utilisation de dimensions à plusieurs valeurs

>[!NOTE]
>
>Le graphique en graphiques sparkline et en courbes reflète toujours les totaux exacts dans ces scénarios.

### Utiliser les segments d’audience

Voir [Présentation de la segmentation](/help/components/segments/seg-overview.md) pour plus d’informations.

## Trier des tableaux

Dans Analysis Workspace, vous pouvez trier les données d’un tableau à structure libre selon n’importe quelle colonne, qu’il s’agisse de dimensions ou de mesures. Vous pouvez même trier par plusieurs colonnes en même temps.

Par défaut, les dimensions sont triées par ordre croissant et les mesures sont triées par ordre décroissant.

### Trier les tableaux par colonne

Lorsque vous triez les données d’une seule colonne comme décrit dans cette section, tout [tri avancé](#sort-tables-by-multiple-columns-advanced-sorting) appliqué au tableau est supprimé.

Pour trier les données des tableaux selon une seule colonne :

1. Placez le pointeur de la souris sur l’en-tête de la colonne à trier, puis sélectionnez l’icône **Trier** ![Trier](/help/assets/icons/SortOrderDown.svg) lorsqu’elle s’affiche.

   ![Menu déroulant Tri](assets/sort-dropdown-menu.png)

1. Sélectionnez **[!UICONTROL Croissant]** ou **[!UICONTROL Décroissant]**.

   L’icône de tri reste visible lorsque le tri est appliqué à la colonne. Une flèche indique le mode de tri des données (![Tri](/help/assets/icons/SortOrderUp.svg) pour l’ordre croissant ou ![Tri](/help/assets/icons/SortOrderDown.svg) pour l’ordre décroissant).

### Trier des tableaux sur plusieurs colonnes (tri avancé)

{{release-limited-testing-section}}

#### Appliquer le tri à plusieurs colonnes

Pour trier les données des tableaux en fonction de plusieurs colonnes :

1. Placez le pointeur de la souris sur l’en-tête d’une colonne à trier, puis sélectionnez l’icône **Trier** ![Trier](/help/assets/icons/SortOrderDown.svg) lorsqu’elle s’affiche.

   ![Menu déroulant Tri](assets/sort-dropdown-menu.png)

1. Sélectionnez **[!UICONTROL Tri avancé]**.

   ![&#x200B; Boîte de dialogue Tri avancé &#x200B;](assets/sort-advanced-dialog.png)

1. Dans la boîte de dialogue Tri avancé , effectuez l’une des opérations suivantes :

   * Ajoutez les colonnes qui ne sont pas encore triées en sélectionnant le bouton **[!UICONTROL Ajouter une colonne de tri]**.

   * Supprimez les colonnes que vous ne souhaitez plus trier en sélectionnant l’icône **Supprimer** ![Supprimer](/help/assets/icons/Close.svg).

   * Faire glisser les colonnes plus haut ou plus bas dans la liste pour ajuster la priorité de tri.

     Pour plus d’informations, voir [Priorité de tri](#sort-priority).

   * Modifiez la valeur de tri en sélectionnant **[!UICONTROL Croissant]** ou **[!UICONTROL Décroissant]** dans le menu déroulant.

   * Sélectionnez une autre colonne en sélectionnant le menu déroulant Nom de la colonne .

1. Sélectionnez **[!UICONTROL Appliquer]**.

L’icône de tri reste visible lorsque le tri est appliqué à une colonne. Une flèche indique le mode de tri des données (![Tri](/help/assets/icons/SortOrderUp.svg) pour l’ordre croissant ou ![Tri](/help/assets/icons/SortOrderDown.svg) pour l’ordre décroissant).

![exemple multi-tri](assets/dimensions-multiple-sort.png)

#### Priorité de tri

Lorsque vous triez des données pour plusieurs colonnes, les données sont triées en fonction de la priorité que vous attribuez à chaque colonne. La numérotation de priorité s’affiche en regard de l’icône de tri ![SortOrderDown](/help/assets/icons/SortOrderDown.svg)<sup>➊</sup>.

La colonne ayant la priorité principale détermine l&#39;ordre principal ; la colonne ayant la priorité secondaire détermine l&#39;ordre dans lequel les lignes ont la même valeur dans la colonne principale ; la colonne ayant la priorité tertiaire détermine l&#39;ordre dans lequel les lignes ont la même valeur dans les colonnes principale et secondaire ; et ainsi de suite.

Prenons l’exemple d’un tableau avec les colonnes suivantes :

* Jour du mois (dimension)

* Heure de la journée (dimension)

* Événements (mesure)

Vous pouvez attribuer une priorité de tri à chaque colonne, comme suit :

| Nom de la colonne (composant) | Type de composant | Priorité de tri |
|---------|----------|---------|
| Jour du mois | Dimension | 1 |
| Heure de la journée | Dimension | 2 |
| Événements | Mesure | 3 |

En attribuant une priorité de tri à chaque colonne, vous pouvez contrôler exactement l’affichage des données dans le tableau. Dans cet exemple, les informations sont d’abord triées par Jour du mois, puis par Heure de la journée et enfin par Événements.

![exemple multi-tri](assets/dimensions-multiple-sort.png)
