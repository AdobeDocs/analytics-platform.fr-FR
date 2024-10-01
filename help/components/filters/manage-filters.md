---
title: Gestion des filtres
description: Découvrez comment gérer les filtres dans Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: e07197325e992cd85b852899c2f7cef60637f532
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 4%

---

# Gestion des filtres


Vous pouvez [partager](filters-share.md), [filtrer](filters-filter.md), [balise](filters-tag.md), [approuver](filters-approve.md), renommer, [copier](filters-copy.md), supprimer, exporter des filtres et marquer les filtres comme [favori](filters-favorite.md) depuis une interface de gestion [!UICONTROL Filtres] centrale. Pour gérer les filtres :

* Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis **[!UICONTROL Filtres]**.


>[!NOTE]
>
>Les filtres rapides que vous créez dans un projet Workspace spécifique n’apparaissent pas dans le gestionnaire [!UICONTROL Filtres], sauf si vous avez rendu le filtre disponible pour tous vos projets.
>

## Gestionnaire de filtres

Le gestionnaire de filtres comporte les éléments d’interface suivants :

![Interface des filtres](assets/filters-manager.png)

### Liste des filtres

La liste des filtres du affiche tous les filtres que vous possédez, ceux qui ont été définis sur tous vos projets et ceux qui ont été partagés avec vous. La liste contient les colonnes suivantes :

| Colonne | Description |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Sélectionnez pour favoriser ![Star](/help/assets/icons/Star.svg) ou pour annuler ![StarOutline](/help/assets/icons/StarOutline.svg) avec un filtre. Voir [Marquer le filtre comme favori](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Titre et description]** | Pour modifier le filtre, sélectionnez le lien de titre qui ouvre le [Créateur de filtres](filter-builder.md). Un filtre partagé est indiqué avec ![Share](/help/assets/icons/ShareLight.svg). |
| **[!UICONTROL Vue de données]** | Les vues de données auxquelles ce filtre s’applique. |
| **[!UICONTROL Propriétaire]** | Propriétaire du filtre. En tant qu’utilisateur, vous ne voyez que les filtres que vous possédez ou les annotations partagées avec vous. |
| **[!UICONTROL Balises]** | Les balises de ce filtre. |
| **[!UICONTROL Partagé avec]** | Nombre d’individus ou de groupes avec lesquels vous avez partagé le filtre. Sélectionnez cette option pour ouvrir la boîte de dialogue **[!UICONTROL Partager le composant]**. Voir [Partage de filtres](filters-share.md) pour plus d’informations. |
| **[!UICONTROL Date de modification]** | Date et heure de la dernière modification du filtre. |
| **[!UICONTROL Utilisé dans]** | Permet d’indiquer où les filtres sont actuellement utilisés et combien de fois ils sont utilisés dans chaque zone. <p>Par exemple, si le filtre est utilisé dans 40 projets et 2 alertes, la valeur de cette colonne s’affiche sous la forme [!UICONTROL **42 composants**].</p> <p>Sélectionnez la valeur de cette colonne pour voir la répartition de l’emplacement d’utilisation des filtres (par exemple, [!UICONTROL **Projets (40)**], [!UICONTROL **Fiches d’évaluation mobiles (2)**]). De plus, vous pouvez visualiser la liste des éléments pour lesquels les filtres sont utilisés. Par exemple, pour voir la liste des projets dans lesquels ils sont utilisés, sélectionnez le lien [!UICONTROL **Projets (40)**] .</p><p>Chacune des zones suivantes indique le nombre d’instances de filtres utilisés dans cette zone :</p>  <ul><li>[!UICONTROL **Projets**]<p>Contient des filtres [créés dans le Créateur de filtres](/help/components/filters/filter-builder.md#) et disponibles pour tous les projets.</p></li><li>[!UICONTROL **Composants ad hoc**]<p>Contient des filtres [ créés en tant que filtres rapides ](/help/components/filters/quick-filters.md) et disponibles uniquement dans un seul projet.</p></li><li>[!UICONTROL **Projets planifiés**]</li><li>[!UICONTROL **Fiches d’évaluation mobiles**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Mesures calculées**]</li><li>[!UICONTROL **Report Builder**]<p>La sélection de cette option télécharge un fichier CSV avec les colonnes de données suivantes :</p><ul><li>Nom du Report Builder</li><li>Dernier accès</li><li>Dernier identifiant utilisateur IMS accessible</li><li>Dernier nom d’utilisateur</li></ul></li></ul><p>Ces informations vous aident à déterminer si un composant est utile aux utilisateurs de votre entreprise, où il est utilisé et si le composant doit être supprimé ou modifié.</p><p>Tenez compte des points suivants lorsque vous affichez cette colonne :</p><ul><li>Ces informations sont disponibles uniquement pour les administrateurs système.</li><li>La colonne [!UICONTROL **Utilisé dans**] ne s’affiche pas par défaut. Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour configurer l’affichage de cette colonne.</li><li>Ces informations n’incluent pas l’utilisation de l’API ou du Data Warehouse.</li><li>Si cette colonne ne contient aucune donnée pour un composant donné mais que le composant a une date [!UICONTROL **Dernière utilisation**], le composant peut avoir été utilisé dans une analyse sans avoir été enregistré.</li><li>Les informations d’utilisation sont disponibles à partir de septembre 2023.</li></ul><p>Vous pouvez utiliser le [dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md) avec ces informations pour vous aider à suivre et à mieux comprendre comment les composants sont utilisés dans votre organisation.</p> |
| **[!UICONTROL Dernière utilisation]** | La dernière utilisation du filtre. |

{style="table-layout:auto"}

Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour spécifier les colonnes à afficher.

### Barre d’actions

Vous pouvez agir sur les filtres à l’aide de la barre d’actions de la. La barre d’actions contient les actions suivantes :

| Action | Description |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** | Ajoutez un autre filtre à l’aide du [Créateur de filtres](filter-builder.md). |
| ![Rechercher](/help/assets/icons/Search.svg) [!UICONTROL *Rechercher par titre*] | Lorsqu’aucun filtre n’est sélectionné dans la liste, recherchez les filtres utilisant ce champ de recherche. |
| ![Libellé](/help/assets/icons/Label.svg) **[!UICONTROL Balise]** | Balisez les filtres sélectionnés. Dans la boîte de dialogue **[!UICONTROL Filtre de balises]**, sélectionnez ou désélectionnez les balises des filtres sélectionnés. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les balises des filtres sélectionnés. Pour plus d’informations, voir [Filtres de balise](/help/components/filters/filters-tag.md) . |
| ![Partager](/help/assets/icons/ShareLight.svg) **[!UICONTROL Partager]** | Partagez les filtres sélectionnés. Dans la boîte de dialogue **[!UICONTROL Partager le filtre]**, vous pouvez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des individus ou des groupes* ou sélectionner **[!UICONTROL Organisation]** ou **[!UICONTROL Groupes]**. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les détails du partage pour les filtres sélectionnés. Voir [Partage de filtres](filters-share.md) pour plus d’informations. |
| ![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]** | Supprimer les filtres sélectionnés. Vous êtes invité à faire une confirmation. |
| ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Renommer]** | Renommez un seul filtre sélectionné. Lorsque cette option est sélectionnée, vous pouvez renommer le filtre intégré. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Validez les filtres sélectionnés. Voir [Approuver les filtres](filters-approve.md) pour plus d’informations. |
| ![Copier](/help/assets/icons/Copy.svg) **[!UICONTROL Copier]** | Copiez le filtre sélectionné. De nouveaux filtres sont créés avec le même nom et le même suffixe `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exporter au format CSV]** | Exportez les filtres vers un fichier `Filters List.csv`. |

### Barre de filtres active

La barre de filtrage affiche les filtres actifs appliqués du panneau à la liste des filtres (le cas échéant). Vous pouvez supprimer rapidement un filtre à l’aide de ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si plusieurs filtres sont spécifiés, vous pouvez les supprimer à l’aide de **[!UICONTROL Tout supprimer]**.

### Panneau Filtrer

Vous pouvez filtrer la liste des filtres à l’aide du panneau de gauche ![Filtre](/help/assets/icons/Filter.svg) ****. Le panneau Filtre affiche le type de filtre et le nombre de filtres qui respectent le filtre spécifique. Sélectionnez ![Filtre](/help/assets/icons/Filter.svg) pour activer/désactiver l’affichage du panneau de filtrage.

Voir [Filtrer la liste des filtres](filters-filter.md) pour plus d’informations.
