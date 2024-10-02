---
title: Gestion des annotations
description: Comment gérer les annotations dans l’espace de travail.
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: 6a279ac39e6b94200ff93ac1a3796d202e6349c7
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 8%

---

# Gestion des annotations

Vous pouvez partager, filtrer, baliser, approuver, copier, supprimer des annotations et marquer les annotations comme favoris depuis une interface de gestion centrale de [!UICONTROL Annotations]. Pour gérer les annotations :

* Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis sélectionnez **[!UICONTROL Annotations]**.


>[!NOTE]
>
>Les annotations que vous créez dans un projet Workspace spécifique n’apparaissent pas dans le gestionnaire [!UICONTROL Annotations], sauf si vous avez rendu l’annotation disponible pour tous vos projets.
>

## Gestionnaire d’annotations

Le gestionnaire d’annotations comprend les éléments d’interface suivants :

![Interface des annotations](assets/annotations-manager.png)

### Liste des annotations

La liste des annotations s’affiche avec toutes les annotations que vous détenez, les annotations qui ont été incluses dans tous vos projets et les annotations qui ont été partagées avec vous. La liste contient les colonnes suivantes :

| Colonne | Description |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Sélectionnez pour favoriser ![Star](/help/assets/icons/Star.svg) ou annuler la faveur de ![StarOutline](/help/assets/icons/StarOutline.svg) d’une annotation. |
| **[!UICONTROL Titre et description]** | Fournis dans le créateur d’annotations. Pour modifier le titre et la description, sélectionnez le lien du titre : ouvre le [créateur d’annotations](/help/components/annotations/create-annotations.md#annotation-builder). Une annotation partagée est indiquée avec ![Share](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Vue de données]** | Les vues de données auxquelles cette annotation s’applique. |
| **[!UICONTROL Propriétaire]** | Propriétaire de l’annotation. En tant qu’utilisateur, vous ne voyez que les annotations que vous possédez ou les annotations qui sont partagées avec vous. |
| **[!UICONTROL Période appliquée]** | La date ou la période à laquelle cette annotation s’applique. |
| **[!UICONTROL Balises]** | Les balises de cette annotation. |
| **[!UICONTROL Partagé avec]** | Les individus ou les groupes avec lesquels vous avez partagé l’annotation. Sélectionnez cette option pour ouvrir la boîte de dialogue **[!UICONTROL Partager le composant]**. |
| **[!UICONTROL Date de modification]** | Affiche la date et l’heure de la dernière modification de l’annotation. |

{style="table-layout:auto"}

Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour spécifier les colonnes à afficher.

### Barre d’actions

Vous pouvez agir sur les annotations à l’aide de la barre d’actions. La barre d’actions contient les actions suivantes :

| Icône | Action | Description |
|:--:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Ajouter]** | Ajoutez une autre annotation à l’aide du [créateur d’annotations](create-annotations.md#annotation-builder). |
| ![Recherche](/help/assets/icons/Search.svg) | [!UICONTROL *Recherche par titre*] | Lorsqu’aucune annotation n’est sélectionnée dans la liste, recherchez les annotations à l’aide de ce champ de recherche. |
| ![Maison de disques](/help/assets/icons/Label.svg) | **[!UICONTROL Balise]** | Balisez les annotations sélectionnées. Dans la boîte de dialogue **[!UICONTROL Composant de balise]**, sélectionnez ou désélectionnez les balises pour les annotations sélectionnées. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les balises des annotations sélectionnées. |
| ![Partager](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Partager]** | Partagez les annotations sélectionnées. Dans la boîte de dialogue **[!UICONTROL Partager le composant]**, vous pouvez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des individus ou des groupes* ou sélectionner **[!UICONTROL Organisation]** ou **[!UICONTROL Groupes]**. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les détails du partage pour les annotations sélectionnées. Pour plus d’informations, voir [Partage des annotations](#share-annotations) . |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimer les annotations sélectionnées. Vous êtes invité à faire une confirmation. |
| ![Modifier](/help/assets/icons/Edit.svg) | **[!UICONTROL Renommer]** | Renommez une seule annotation sélectionnée. Lorsque cette option est sélectionnée, vous pouvez renommer l’annotation intégrée. |
| ![Copier](/help/assets/icons/Copy.svg) | **[!UICONTROL Copier]** | Copiez les annotations sélectionnées. Les nouvelles annotations sont créées avec le même nom et le même suffixe (Copier). |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exporter dans un fichier CSV]** | Exportez les annotations dans un fichier `Annotations List.csv`. |

### Barre de filtres active

La barre de filtre affiche les filtres actifs (le cas échéant). Vous pouvez supprimer rapidement un filtre à l’aide de ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si plusieurs filtres sont spécifiés, vous pouvez les supprimer à l’aide de **[!UICONTROL Tout supprimer]**.

### Panneau Filtrer

Vous pouvez filtrer les annotations à l’aide du panneau de gauche **[!UICONTROL Filtre]** . Le panneau de filtrage affiche le type de filtre et le nombre d’annotations qui respectent le filtre. Sélectionnez ![Filtre](/help/assets/icons/Filter.svg) pour activer/désactiver l’affichage du panneau de filtrage.

Pour filtrer la liste des filtres :

1. Sélectionnez ![Filter](/help/assets/icons/Filter.svg) pour ouvrir le panneau Filtres. Si vous avez besoin d’espace supplémentaire pour la liste Filtres, vous pouvez sélectionner à nouveau ![Filtre](/help/assets/icons/Filter.svg) pour fermer le panneau.
1. Vous pouvez filtrer les annotations à l’aide des [sections de filtrage](#filter-sections) disponibles.

   >[!INFO]
   >
   >*Les éléments* font référence aux éléments d’annotation affichés dans la [liste d’annotations](manage-annotations.md#annotations-list).
   > 

#### Filtrage des sections

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


La [liste d’annotations](manage-annotations.md#annotations-list) est automatiquement mise à jour en fonction de la configuration de votre filtre. Vous pouvez voir les filtres configurés dans la [barre de filtres actifs](manage-annotations.md#active-filter-bar).


## Modification des annotations

Vous pouvez modifier une annotation de deux manières différentes :

* Dans un projet Workspace, utilisez l’icône [Informations sur le composant](/help/components/use-components-in-workspace.md#component-info).

* Dans la liste [[!UICONTROL Annotations]](#annotations-list), sélectionnez le titre de l’annotation.

Vous utilisez le [créateur d’annotations](/help/components/annotations/create-annotations.md#annotation-builder) pour modifier l’annotation.

## Partage des annotations

Les éléments suivants s’appliquent lors du partage d’annotations ou de l’utilisation d’annotations partagées avec vous :

* Les annotations de projet uniquement d’un projet que vous partagez avec d’autres utilisateurs s’affichent pour ces utilisateurs. Les utilisateurs ne peuvent pas modifier ni supprimer ces annotations de projet uniquement.
* Si vous enregistrez une annotation et la partagez directement avec un utilisateur, ce dernier ne peut la modifier et la supprimer que s’il dispose des droits d’administrateur.

* Si un projet est partagé avec vous, les annotations créées dans ce projet s’affichent uniquement dans ce projet. Si une annotation est partagée directement avec vous, elle s’affiche dans tous les projets où elle peut être affichée.

## Annotations et fuseaux horaires

Toutes les annotations sont créées avec un horodatage, mais sans information sur l’heure ou le fuseau horaire. Au moment du rapport, le fuseau horaire de la vue de données configurée pour le panneau est utilisé.
