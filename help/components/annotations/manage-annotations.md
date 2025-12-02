---
title: Gestion des annotations
description: Découvrez comment gérer les annotations dans Workspace.
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 91%

---

# Gestion des annotations

Vous pouvez partager, filtrer, étiqueter, approuver, copier, supprimer des annotations et marquer des annotations comme favorites depuis une interface de gestion centralisée des [!UICONTROL Annotations]. Pour gérer les annotations :

* Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis sélectionnez **[!UICONTROL Annotations]**.


>[!NOTE]
>
>Les annotations que vous créez dans un projet Workspace spécifique n’apparaissent pas dans le gestionnaire d’[!UICONTROL annotations], sauf si vous avez rendu l’annotation disponible pour tous vos projets.
>

## Gestionnaire d’annotations

Le gestionnaire d’annotations comprend les éléments d’interface suivants :

![Interface d’annotations](assets/annotations-manager.png)

### Liste des annotations

La ➊ Liste des annotations affiche toutes les annotations que vous possédez, celles qui ont été incluses dans tous vos projets et celles qui ont été partagées avec vous. La liste comporte les colonnes suivantes :

| Colonne | Description |
| --- | --- |
| ![Contour en forme d’étoile](/help/assets/icons/StarOutline.svg) | Cliquez pour ajouter aux favoris ![Étoile](/help/assets/icons/Star.svg) ou retirer des favoris ![Contour en forme d’étoile](/help/assets/icons/StarOutline.svg) une annotation. |
| **[!UICONTROL Titre et description]** | Fournis dans le créateur d’annotations. Pour modifier le titre et la description, sélectionnez le lien du titre : cela ouvre le [créateur d’annotations](/help/components/annotations/create-annotations.md#annotation-builder). Une annotation partagée est indiquée par ![Partagé](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Vue de données]** | Les vues de données auxquelles cette annotation s’applique. |
| **[!UICONTROL Propriétaire]** | La personne propriétaire de l’annotation. En tant qu’utilisateur ou utilisatrice, vous ne pouvez consulter que les annotations que vous possédez ou celles qui ont été partagées avec vous. |
| **[!UICONTROL Période appliquée]** | La date ou la période à laquelle cette annotation s’applique. |
| **[!UICONTROL Étiquettes]** | Les étiquettes de cette annotation. |
| **[!UICONTROL Partagé avec]** | Les individus ou les groupes avec lesquels vous avez partagé l’annotation. Sélectionnez cette option pour ouvrir la boîte de dialogue **[!UICONTROL Partager le composant]**. |
| **[!UICONTROL Date de modification]** | Affiche la date et l’heure de la dernière modification de l’annotation. |

{style="table-layout:auto"}

Utilisez ![Paramètres de colonne](/help/assets/icons/ColumnSetting.svg) pour spécifier les colonnes à afficher.

### Barre d’actions

Vous pouvez agir sur les annotations à l’aide de la barre d’actions ➋. La barre d’actions contient les actions suivantes :

| Icône | Action | Description |
|:--:|---|---|
| ![Cercle d’ajout](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Ajouter]** | Ajoutez une autre annotation à l’aide du [créateur d’annotations](create-annotations.md#annotation-builder). |
| ![Recherche](/help/assets/icons/Search.svg) | [!UICONTROL *Rechercher par titre*] | Lorsqu’aucune annotation n’est sélectionnée dans la liste, recherchez des annotations à l’aide de ce champ de recherche. |
| ![Libellé](/help/assets/icons/Label.svg) | **[!UICONTROL Étiquette]** | Étiquetez les annotations sélectionnées. Dans la boîte de dialogue **[!UICONTROL Étiqueter le composant]**, sélectionnez ou désélectionnez les étiquettes pour les annotations sélectionnées. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les étiquettes pour les annotations sélectionnées. |
| ![Partager](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Partager]** | Partagez les annotations sélectionnées. Dans la boîte de dialogue **[!UICONTROL Partager le composant]**, vous pouvez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des individus ou des groupes* ou sélectionner **[!UICONTROL Organisation]** ou **[!UICONTROL Groupes]**. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les détails de partage pour les annotations sélectionnées. Pour plus de détails, consultez la section [Partager des annotations](#share-annotations). |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimez les annotations sélectionnées. Il vous est demandé de confirmer. |
| ![Modifier](/help/assets/icons/Edit.svg) | **[!UICONTROL Renommer]** | Renommez une seule annotation sélectionnée. Lorsque cette option est sélectionnée, vous pouvez directement renommer l’annotation. |
| ![Copier](/help/assets/icons/Copy.svg) | **[!UICONTROL Copier]** | Copiez les annotations sélectionnées. Les nouvelles annotations sont créées avec le même nom et le même suffixe (Copie). |
| ![Fichier CSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exporter dans un fichier CSV]** | Exportez les annotations dans un fichier `Annotations List.csv`. |

### Barre de filtres actifs

La barre de filtres affiche ➌ les filtres actifs (le cas échéant). Vous pouvez supprimer rapidement un filtre à l’aide de ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si plusieurs filtres sont spécifiés, vous pouvez tous les supprimer à l’aide de **[!UICONTROL Tout supprimer]**.

### Panneau Filtrer

Vous pouvez filtrer les annotations à l’aide du **[!UICONTROL du panneau de gauche]** Filtrer➍. Le panneau Filtrer affiche le type de filtre et le nombre d’annotations qui correspondent au filtre. Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) pour afficher ou masquer le panneau Filtrer.

Pour filtrer la liste des filtres :

1. Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) pour ouvrir le panneau Filtres. Si vous avez besoin d’espace supplémentaire pour la liste des filtres, vous pouvez sélectionner à nouveau ![Filtrer](/help/assets/icons/Filter.svg) pour fermer le panneau.
1. Vous pouvez filtrer les annotations à l’aide des [sections de filtrage](#filter-sections) disponibles.

   >[!INFO]
   >
   >*Les éléments* font référence aux éléments d’annotation affichés dans la [Liste des annotations](manage-annotations.md#annotations-list).
   > 

#### Sections de filtrage

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


La [Liste des annotations](manage-annotations.md#annotations-list) est automatiquement mise à jour en fonction de la configuration de vos filtres. Vous pouvez voir les filtres configurés dans la [Barre des filtres actifs](manage-annotations.md#active-filter-bar).


## Modification des annotations

Vous pouvez modifier une annotation de deux manières différentes :

* Dans un projet Workspace, utilisez l’icône [Informations sur le composant](/help/components/use-components-in-workspace.md#component-info).

* Dans la liste des [[!UICONTROL annotations]](#annotations-list), cliquez sur le titre de l’annotation.

Utilisez le [Créateur d’annotations](/help/components/annotations/create-annotations.md#annotation-builder) pour modifier l’annotation.

## Partage des annotations

Les éléments suivants s’appliquent lorsque vous partagez ou utilisez des annotations partagées avec vous :

* Les annotations limitées uniquement au projet que vous partagez avec d’autres utilisateurs et utilisatrices s’affichent pour ces utilisateurs et utilisatrices. Les utilisateurs et utilisatrices ne peuvent pas modifier ou supprimer ces annotations limitées uniquement au projet.
* Si vous enregistrez une annotation et la partagez directement avec un utilisateur ou une utilisatrice, ceux-ci ne peuvent la modifier ou la supprimer que s’ils disposent de droits d’administration.

* Si un projet est partagé avec vous, les annotations créées dans ce projet s’affichent uniquement dans ce projet. Si une annotation est partagée directement avec vous, elle apparaîtra dans tous les projets où elle peut être affichée.

## Annotations et fuseaux horaires

Toutes les annotations sont créées avec un horodatage qui n’inclut pas l’heure ou le fuseau horaire. Au moment du rapport, le fuseau horaire de la vue de données configurée pour le panneau est utilisé.
