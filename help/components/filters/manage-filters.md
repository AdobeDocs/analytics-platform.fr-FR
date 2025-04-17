---
title: Gérer les filtres
description: Découvrir comment gérer les filtres dans Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: ht
source-wordcount: '884'
ht-degree: 100%

---

# Gérer les filtres


Vous pouvez [partager](filters-share.md), [filtrer](filters-filter.md), [baliser](filters-tag.md), [approuver](filters-approve.md), renommer, [copier](filters-copy.md), supprimer, exporter des filtres et marquer les filtres comme [favoris](filters-favorite.md) depuis une interface de gestion centrale [!UICONTROL Filtres]. Pour gérer les filtre, procédez comme suit :

* Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis sélectionnez **[!UICONTROL Filtres]**.


>[!NOTE]
>
>Les filtres rapides que vous créez dans un projet Workspace spécifique n’apparaissent pas dans le gestionnaire de [!UICONTROL filtres], sauf si vous avez rendu le filtre disponible pour tous vos projets.
>

## Gestionnaire de filtres

Le gestionnaire de filtres comprend les éléments d’interface suivants :

![Interface des filtres](assets/filters-manager.png)

### Liste des filtres

La liste des filtres ➊ affiche tous les filtres que vous possédez, les filtres qui ont été inclus dans tous vos projets et les filtres qui ont été partagés avec vous. La liste comporte les colonnes suivantes :

| Colonne | Description |
| --- | --- | 
| ![Contour en forme d’étoile](/help/assets/icons/StarOutline.svg) | Sélectionnez ![Étoile](/help/assets/icons/Star.svg) pour ajouter un filtre aux favoris ou ![StarOutline](/help/assets/icons/StarOutline.svg) pour retirer un filtre des favoris. Consultez [Marquer le filtre comme favori](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Titre et description]** | Pour modifier le filtre, sélectionnez le lien du titre : cela ouvre le [créateur de filtres](filter-builder.md). Un filtre partagé est indiquée par ![Partagé](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Vue de données]** | Vues de données auxquelles ce filtre s’applique. |
| **[!UICONTROL Propriétaire]** | Personne propriétaire du filtre. En tant qu’utilisateur ou utilisatrice, vous ne pouvez consulter que les filtres que vous possédez ou ceux qui ont été partagés avec vous. |
| **[!UICONTROL Étiquettes]** | Balises pour ce filtre. |
| **[!UICONTROL Partagé avec]** | Répertorie le nombre de personnes ou de groupes avec lesquels vous avez partagé le filtre. Sélectionnez cette option pour ouvrir la boîte de dialogue **[!UICONTROL Partager le composant]**. Consultez [Partager des filtres](filters-share.md) pour plus dʼinformations. |
| **[!UICONTROL Date de modification]** | Date et heure de dernière modification du filtre. |
| **[!UICONTROL Utilisation dans]** | Indiquez où les filtres sont actuellement utilisés et combien de fois ils le sont dans chaque zone. <p>Par exemple, si le filtre est utilisé dans 40 projets et 2 alertes, la valeur de cette colonne s’affiche sous la forme [!UICONTROL **42 composants**].</p> <p>Sélectionnez la valeur dans cette colonne pour afficher la répartition des emplacements où les filtres sont utilisés (par exemple, [!UICONTROL **Projets (40)**] [!UICONTROL **Cartes de performance mobiles (2)**]). De plus, vous pouvez afficher la liste des éléments pour lesquels les filtres sont utilisés. Par exemple, pour afficher la liste des projets dans lesquels ils sont utilisés, sélectionnez le lien [!UICONTROL **Projets (40)**].</p><p>Chacune des zones suivantes indique le nombre d’instances de filtres utilisées dans cette zone :</p>  <ul><li>[!UICONTROL **Projets**]<p>Contient les filtres qui ont été [créés dans le créateur de filtres](/help/components/filters/filter-builder.md#) et qui sont disponibles pour tous les projets.</p></li><li>[!UICONTROL **Composants ad hoc**]<p>Contient des filtres qui ont été [créés en tant que filtres rapides](/help/components/filters/quick-filters.md) et qui sont disponibles uniquement dans un seul projet.</p></li><li>[!UICONTROL **Projets planifiés**]</li><li>[!UICONTROL **Cartes de performances mobiles**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Mesures calculées**]</li><li>[!UICONTROL **Report Builder**]<p>La sélection de cette option télécharge un fichier CSV avec les colonnes de données suivantes :</p><ul><li>Nom dans Report Builder</li><li>Dernier accès</li><li>Dernier ID d’utilisateur ou utilisatrice IMS consulté</li><li>Nom de l’utilisateur ou de l’utilisatrice consulté en dernier</li></ul></li></ul><p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs et utilisatrices de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié.</p><p>Tenez compte des points suivants lorsque vous affichez cette colonne :</p><ul><li>Ces informations sont réservées aux administrateurs et administratrices système.</li><li>La colonne [!UICONTROL **Utilisation dans**] ne s’affiche pas par défaut. Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour configurer l’affichage de cette colonne.</li><li>Ces informations n’incluent pas l’utilisation de l’API ou de Data Warehouse.</li><li>Si cette colonne ne contient aucune donnée pour un composant donné, mais que le composant possède une date [!UICONTROL **Dernière utilisation**], il se peut que le composant ait été utilisé dans une analyse sans avoir été enregistré.</li><li>Les informations d’utilisation sont disponibles à partir de septembre 2023.</li></ul><p>Vous pouvez utiliser le [dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md) avec ces informations pour vous aider à effectuer le suivi et à mieux comprendre comment les composants sont utilisés dans votre organisation.</p> |
| **[!UICONTROL Dernière utilisation]** | Date de la dernière utilisation du filtre. |

{style="table-layout:auto"}

Utilisez ![Paramètres de colonne](/help/assets/icons/ColumnSetting.svg) pour spécifier les colonnes à afficher.

### Barre d’actions

Vous pouvez agir sur les filtres à l’aide de la barre d’actions ➋. La barre d’actions contient les actions suivantes :

| Action | Description |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** | Ajoutez un autre filtre à l’aide du [créateur de filtres](filter-builder.md). |
| ![Recherche](/help/assets/icons/Search.svg) [!UICONTROL *Recherche par titre*] | Lorsqu’aucun filtre n’est sélectionné dans la liste, recherchez des filtres à l’aide de ce champ de recherche. |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Étiquette]** | Balisez les filtres sélectionnés. Dans la boîte de dialogue **[!UICONTROL Baliser le filtre]**, sélectionnez ou désélectionnez les balises pour les filtres sélectionnés. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les balises pour les filtres sélectionnés. Consultez [Baliser les filtres](/help/components/filters/filters-tag.md) pour plus dʼinformations. |
| ![Partager](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Partager]** | Partagez les filtres sélectionnés. Dans la boîte de dialogue **[!UICONTROL Partager le filtre]**, vous pouvez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des personnes ou des groupes* ou sélectionner **[!UICONTROL Organisation]** ou **[!UICONTROL Groupes]**. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les détails de partage pour les filtres sélectionnés. Consultez [Partager des filtres](filters-share.md) pour plus dʼinformations. |
| ![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]** | Supprimez les filtres sélectionnés. Il vous est demandé de confirmer. |
| ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Renommer]** | Renommez un seul filtre sélectionné. Lorsque cette option est sélectionnée, vous pouvez directement renommer le filtre. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approuver]** | Approuvez les filtres sélectionnés. Consultez [Approuver des filtres](filters-approve.md) pour plus dʼinformations. |
| ![Copier](/help/assets/icons/Copy.svg) **[!UICONTROL Copier]** | Copiez les filtres sélectionnés. Les nouveaux filtres sont créés avec le même nom et le même suffixe `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exporter au format CSV]** | Exportez les filtres dans un fichier `Filters List.csv`. |

### Barre de filtres actifs

La barre de filtrage ➌ affiche les filtres actifs appliqués à partir du panneau de filtrage à la liste des filtres (le cas échéant). Vous pouvez supprimer rapidement un filtre à l’aide de ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si plusieurs filtres sont spécifiés, vous pouvez tous les supprimer à l’aide de **[!UICONTROL Tout supprimer]**.

### Panneau Filtrer

Vous pouvez filtrer la liste des filtres à l’aide du du panneau de gauche ![Filtrer](/help/assets/icons/Filter.svg) **[!UICONTROL Filtrer]** ➍. Le panneau de filtrage affiche le type de filtre et le nombre de filtres qui correspondent au filtre spécifique. Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) pour afficher ou masquer le panneau Filtrer.

Consultez [Filtrer la liste des filtres](filters-filter.md) pour plus d’informations.
