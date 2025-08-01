---
description: Découvrez comment utiliser le gestionnaire de segments pour gérer les segments tels que partager, filtrer, baliser, approuver, copier, supprimer des segments et les marquer comme favoris.
title: Gestion des segments
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 31%

---

# Gérer les segments


Vous pouvez [partager](seg-share.md), [segment](seg-filter.md), [balise](seg-tag.md), [approuver](seg-approve.md), renommer, [copier](seg-copy.md), supprimer, exporter des segments et marquer les segments comme [favori](seg-favorite.md) depuis une interface de gestion [!UICONTROL Segment] centrale. Pour gérer les segments :

* Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis sélectionnez **[!UICONTROL Segments]**.


>[!NOTE]
>
>Les segments rapides que vous créez dans un projet Workspace spécifique n’apparaissent pas dans le gestionnaire [!UICONTROL Segment], sauf si vous avez mis le segment à disposition de tous vos projets.
>

## Gestionnaire de segments

Le gestionnaire de segments comporte les éléments d’interface suivants :

![ Interface des segments ](assets/filters-manager.png)

### Liste des segments

La liste des segments affiche ➊ tous les segments que vous possédez, les segments qui ont été étendus à tous vos projets et les segments qui ont été partagés avec vous. La liste comporte les colonnes suivantes :

| Colonne | Description |
| --- | --- | 
| ![Contour en forme d’étoile](/help/assets/icons/StarOutline.svg) | Sélectionnez pour favoriser ![Étoile](/help/assets/icons/Star.svg) ou annuler la préférence ![ÉtoileContour](/help/assets/icons/StarOutline.svg) un segment. Voir [Marquer le segment comme favori](/help/components/segments/seg-favorite.md) |
| **[!UICONTROL Titre et description]** | Pour modifier le segment, sélectionnez le lien de titre, qui ouvre le [créateur de segments](seg-builder.md). Un segment partagé est indiqué par la mention ![Partager](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Vue de données]** | Vues de données auxquelles ce segment s’applique. |
| **[!UICONTROL Propriétaire]** | Propriétaire du segment. En tant qu’utilisateur, vous ne voyez que les segments que vous possédez ou les annotations qui sont partagées avec vous. |
| **[!UICONTROL Balises]** | Balises pour ce segment. |
| **[!UICONTROL Partagé avec]** | Nombre d’individus ou de groupes avec lesquels vous avez partagé le segment. Sélectionnez cette option pour ouvrir la boîte de dialogue **[!UICONTROL Partager le composant]**. Voir [Partager des segments](seg-share.md) pour plus d’informations. |
| **[!UICONTROL Date de modification]** | Date et heure de la dernière modification du segment. |
| **[!UICONTROL Utilisation dans]** | Indique où les segments sont actuellement utilisés et le nombre de fois où ils sont utilisés dans chaque zone. <p>Par exemple, si le segment est utilisé dans 40 projets et 2 alertes, la valeur de cette colonne s’affiche sous la forme de composants [!UICONTROL **42**].</p> <p>Sélectionnez la valeur dans cette colonne pour afficher la répartition des emplacements où les segments sont utilisés (par exemple, [!UICONTROL **Projets (40)**] [!UICONTROL **Cartes de performance mobiles (2)**]). De plus, vous pouvez afficher la liste des éléments dans lesquels les segments sont utilisés. Par exemple, pour afficher la liste des projets dans lesquels ils sont utilisés, sélectionnez le lien [!UICONTROL **Projets (40)**].</p><p>Chacune des zones suivantes indique le nombre d’instances de segments utilisées dans cette zone :</p>  <ul><li>[!UICONTROL **Projets**]<p>Contient des segments qui ont été [créés dans le créateur de segments](/help/components/segments/seg-builder.md#) et qui sont disponibles pour tous les projets.</p></li><li>[!UICONTROL **Composants ad hoc**]<p>Contient des segments qui ont été [créés en tant que segments rapides](/help/components/segments/seg-quick.md) et qui ne sont disponibles que dans un seul projet.</p></li><li>[!UICONTROL **Projets planifiés**]</li><li>[!UICONTROL **Cartes de performances mobiles**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Mesures calculées**]</li><li>[!UICONTROL **Report Builder**]<p>La sélection de cette option télécharge un fichier CSV avec les colonnes de données suivantes :</p><ul><li>Nom dans Report Builder</li><li>Dernier accès</li><li>Dernier ID d’utilisateur ou utilisatrice IMS consulté</li><li>Nom de l’utilisateur ou de l’utilisatrice consulté en dernier</li></ul></li></ul><p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs et utilisatrices de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié.</p><p>Tenez compte des points suivants lorsque vous affichez cette colonne :</p><ul><li>Ces informations sont réservées aux administrateurs et administratrices système.</li><li>La colonne [!UICONTROL **Utilisation dans**] ne s’affiche pas par défaut. Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour configurer l’affichage de cette colonne.</li><li>Ces informations n’incluent pas l’utilisation de l’API ou de Data Warehouse.</li><li>Si cette colonne ne contient aucune donnée pour un composant donné, mais que le composant possède une date [!UICONTROL **Dernière utilisation**], il se peut que le composant ait été utilisé dans une analyse sans avoir été enregistré.</li><li>Les informations d’utilisation sont disponibles à partir de septembre 2023.</li></ul><p>Vous pouvez utiliser le [dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md) avec ces informations pour vous aider à effectuer le suivi et à mieux comprendre comment les composants sont utilisés dans votre organisation.</p> |
| **[!UICONTROL Dernière utilisation]** | Date de la dernière utilisation du segment. |

Utilisez ![Paramètres de colonne](/help/assets/icons/ColumnSetting.svg) pour spécifier les colonnes à afficher.

### Barre d’actions

Vous pouvez agir sur les segments à l’aide de la barre d’actions ➋. La barre d’actions contient les actions suivantes :

| Action | Description |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** | Ajoutez un autre segment à l’aide du [créateur de segments](seg-builder.md). |
| ![Recherche](/help/assets/icons/Search.svg) [!UICONTROL *Recherche par titre*] | Lorsqu’aucun segment n’est sélectionné dans la liste, recherchez des segments à l’aide de ce champ de recherche. |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Étiquette]** | Balisez les segments sélectionnés. Dans la boîte de dialogue **[!UICONTROL Baliser le segment]**, sélectionnez ou désélectionnez les balises des segments sélectionnés. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les balises des segments sélectionnés. Voir [Balisage de segments](/help/components/segments/seg-tag.md) pour plus d’informations. |
| ![Partager](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Partager]** | Partagez les segments sélectionnés. Dans la boîte de dialogue **[!UICONTROL Partager le segment]**, vous pouvez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des individus ou des groupes* ou sélectionner **[!UICONTROL Organisation]** ou **[!UICONTROL Groupes]**. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les détails de partage pour les segments sélectionnés. Voir [Partager des segments](seg-share.md) pour plus d’informations. |
| ![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]** | Supprimez les segments sélectionnés. Vous êtes invité à confirmer l’opération. <br/>Lorsque vous supprimez un segment, gardez à l’esprit que : <ul><li>Les rapports planifiés et les projets auxquels ce segment est appliqué continuent à fonctionner normalement.</li><li> Les rapports planifiés ne sont pas mis à jour lorsque vous modifiez un segment portant le même nom.</li> </ul> |
| ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Renommer]** | Renommez un seul segment sélectionné. Lorsque cette option est sélectionnée, vous pouvez renommer le segment en ligne. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approuver]** | Valider les segments sélectionnés. Voir [Approuver les segments](seg-approve.md) pour plus d’informations. |
| ![Copier](/help/assets/icons/Copy.svg) **[!UICONTROL Copier]** | Copiez le segment sélectionné. Les nouveaux segments sont créés avec les mêmes nom et suffixe `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exporter au format CSV]** | Exportez les segments vers un fichier `Segments List.csv`. |

### Barre de filtres actifs

La barre de filtrage affiche ➌ les segments actifs appliqués à partir du panneau de filtrage à la liste des segments (le cas échéant). Vous pouvez supprimer rapidement un filtre à l’aide de ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si plusieurs filtres sont spécifiés, vous pouvez supprimer tous les filtres à l’aide de l’option **[!UICONTROL Tout supprimer]**.

### Panneau Filtrer

Vous pouvez filtrer la liste des segments à l’aide du ![ du panneau de gauche ](/help/assets/icons/Filter.svg)Filtrer **&#x200B;**&#x200B;Filtrer➍. Le panneau de filtrage affiche le type de filtre et le nombre de segments qui respectent le filtre spécifique. Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) pour activer/désactiver l’affichage du panneau Filtre.

Voir [Filtrer la liste des segments](seg-filter.md) pour plus d’informations.
