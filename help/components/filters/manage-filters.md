---
title: Gestionnaire de filtres
description: apprenez à gérer les filtres dans Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: e84010b9ea9e6385574e8b1a04f7eccbba3ebc90
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 22%

---

# Gestionnaire de filtres

Le gestionnaire de filtres offre plusieurs manières d’organiser les filtres, par exemple le partage, le balisage, l’approbation, la copie, la suppression et le marquage en tant que favoris.

Le Gestionnaire de filtres vous présente tous les filtres que vous possédez et qui ont été partagés avec vous. Les utilisateurs de niveau administrateur peuvent consulter tous les filtres de l’entreprise. Cet aperçu présente l’interface utilisateur et les fonctionnalités du gestionnaire de filtres.

![](assets/filter-manager-ui.png)

## Accès au gestionnaire de filtres

1. Dans Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Composants]**, puis sélectionnez **[!UICONTROL Filtres]**.

## Actions disponibles dans le gestionnaire de filtres

Dans le gestionnaire de filtres, vous pouvez :

* [Filtrer la liste des filtres](/help/components/filters/filters-filter.md)

* [Marquer des filtres comme favoris](/help/components/filters/filters-favorite.md)

* [Approuver des filtres](/help/components/filters/filters-approve.md)

* [Baliser des filtres](/help/components/filters/filters-tag.md)

* [Partager des filtres](/help/components/filters/filters-share.md)

* Exportez un filtre vers un fichier CSV.

* [Copier des filtres](/help/components/filters/filters-copy.md)

* Supprimer des filtres

## Configuration des colonnes

Vous pouvez paramétrer les informations affichées pour chaque filtre dans le Gestionnaire de filtres en configurant les colonnes affichées.

Pour configurer les colonnes visibles dans le Gestionnaire de filtres :

1. Dans Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Composants]**, puis sélectionnez **[!UICONTROL Filers]**.

1. Dans le gestionnaire de filtres, sélectionnez l’icône **Personnaliser les colonnes** ![Icône Personnaliser les colonnes](assets/customize-columns-icon.png), puis sélectionnez les colonnes à afficher dans le gestionnaire de filtres.

   Les colonnes suivantes sont disponibles :

   | Titre de la colonne | Description |
   |---|---|
   | Titre et description | Ces valeurs sont fournies dans le Créateur de filtres. Pour modifier le titre et la description, sélectionnez le lien du titre pour ouvrir le Créateur de filtres. |
   | Favoris | Affiche des icônes d’étoile en regard de chaque filtre, ce qui vous permet de marquer les filtres comme favoris. Pour plus d’informations, voir [Marquer les filtres comme favoris](/help/components/filters/filters-favorite.md). |
   | Vue de données | Cette colonne indique dans quelle vue de données le filtre a été enregistré en dernier. |
   | Propriétaire | Indique qui possède le filtre. En tant que non administrateur, vous ne pouvez consulter que les filtres que vous possédez ou ceux qui ont été partagés avec vous. |
   | Balises (non cochées dans le sélecteur de colonnes, de ce fait, la colonne n’apparaît pas) | Les balises qui ont été appliquées au filtre, soit par vous, soit par des personnes qui ont partagé le filtre avec vous. |
   | Partagé avec | Répertorie les individus ou les groupes (administrateur uniquement) ou toutes les personnes (administrateur uniquement) avec lesquelles vous avez partagé le filtre. <p>Lorsqu’un filtre est partagé par vous ou avec vous, une icône de partage s’affiche en regard du nom du filtre.</p> |
   | Date de modification | Affiche la date de la dernière modification du filtre. |
   | Utilisation dans | Indique le nombre de composants dans lesquels le filtre est actuellement utilisé. <p>Par exemple, si le filtre est utilisé dans 40 projets et 2 alertes, la valeur de cette colonne s’affiche sous la forme [!UICONTROL **42 composants**].</p> <p>Sélectionnez la valeur de cette colonne pour voir la répartition de l’emplacement d’utilisation du filtre (par exemple, [!UICONTROL **Projets (40)**], [!UICONTROL **Alertes (2)**]).</p><p>Les filtres peuvent être utilisés dans l’un des types de composants suivants :</p> <ul><li>Mesures calculées</li><li>Projets</li><li>Projets planifiés</li></ul><p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié.</p><p>Tenez compte des points suivants lorsque vous affichez cette colonne :</p><ul><li>Ces informations n’incluent pas l’utilisation de l’API, du Report Builder ou du Data Warehouse.</li><li>La colonne [!UICONTROL **Utilisé dans**] ne s’affiche pas par défaut. [Configurez les colonnes](#configure-columns) pour les afficher.</li><li>Si cette colonne ne contient pas de données pour un composant donné mais qu’elle a une date [!UICONTROL **Dernière utilisation**], le composant peut avoir été utilisé dans une analyse sans avoir été enregistré.</li><li>Ces informations sont disponibles uniquement pour les administrateurs système.</li></ul><p>Vous pouvez utiliser le [dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md) avec ces informations pour vous aider à suivre et à mieux comprendre comment les composants sont utilisés dans votre organisation.</p> |
   | Dernière utilisation | Affiche la date de la dernière utilisation du filtre dans l’un des types de composants suivants : <ul><li>Mesures calculées</li><li>Projets</li><li>Projets planifiés</li><li>Filtres</li></ul> <p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs de votre entreprise ou s’il doit être supprimé.</p><p>Tenez compte des points suivants lorsque vous affichez cette colonne :</p><ul><li>Ces informations n’incluent pas l’utilisation de l’API, du Report Builder ou du Data Warehouse.</li><li>Pour certains composants, cette colonne peut ne pas contenir de données si le composant a été utilisé pour la dernière fois avant septembre 2023.</li><li>Ces informations sont disponibles uniquement pour les administrateurs système.</li></ul><p>Vous pouvez utiliser le [dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md) avec ces informations pour vous aider à suivre et à mieux comprendre comment les composants sont utilisés dans votre organisation. |

   {style="table-layout:auto"}
