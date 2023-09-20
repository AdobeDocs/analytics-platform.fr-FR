---
title: Gestionnaire de filtres
description: apprenez à gérer les filtres dans Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
source-git-commit: 8d6dc1d220fc3719b13842e812aaf6ddc55ae47c
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 24%

---

# Gestionnaire de filtres

Le gestionnaire de filtres offre plusieurs manières d’organiser les filtres, par exemple le partage, le balisage, l’approbation, la copie, la suppression et le marquage en tant que favoris.

Le Gestionnaire de filtres vous présente tous les filtres que vous possédez et qui ont été partagés avec vous. Les utilisateurs de niveau administrateur peuvent consulter tous les filtres de l’entreprise. Cet aperçu présente l’interface utilisateur et les fonctionnalités du gestionnaire de filtres.

![](assets/filter-manager-ui.png)

## Accès au gestionnaire de filtres

1. Dans Customer Journey Analytics, sélectionnez la variable **[!UICONTROL Composants]** , puis sélectionnez **[!UICONTROL Filtres]**.

## Actions disponibles dans le gestionnaire de filtres

Dans le gestionnaire de filtres, vous pouvez :

* [Filtrer la liste des filtres](/help/components/filters/filters-filter.md)

* [Marquage de filtres comme favoris](/help/components/filters/filters-favorite.md)

* [Approbation de filtres](/help/components/filters/filters-approve.md)

* [Balisage de filtres](/help/components/filters/filters-tag.md)

* [Partage de filtres](/help/components/filters/filters-share.md)

* Exportez un filtre vers un fichier CSV.

* [Copie de filtres](/help/components/filters/filters-copy.md)

* Supprimer des filtres

## Configuration des colonnes

Vous pouvez paramétrer les informations affichées pour chaque filtre dans le Gestionnaire de filtres en configurant les colonnes affichées.

Pour configurer les colonnes visibles dans le Gestionnaire de filtres :

1. Dans Customer Journey Analytics, sélectionnez la variable **[!UICONTROL Composants]** , puis sélectionnez **[!UICONTROL Filtres]**.

1. Dans le Gestionnaire de filtres, sélectionnez l’option **Personnalisation des colonnes** icon ![Icône Personnaliser les colonnes](assets/customize-columns-icon.png), puis sélectionnez les colonnes à afficher dans le Gestionnaire de filtres.

   Les colonnes suivantes sont disponibles :

   | Titre de la colonne | Description |
   |---|---|
   | Titre et description | Ces valeurs sont fournies dans le Créateur de filtres. Pour modifier le titre et la description, sélectionnez le lien du titre pour ouvrir le Créateur de filtres. |
   | Favoris | Affiche des icônes d’étoile en regard de chaque filtre, ce qui vous permet de marquer les filtres comme favoris. Pour plus d’informations, voir [Marquage des filtres comme favoris](/help/components/filters/filters-favorite.md). |
   | Vue de données | Cette colonne indique dans quelle vue de données le filtre a été enregistré en dernier. |
   | Propriétaire | Indique qui possède le filtre. En tant que non administrateur, vous ne pouvez consulter que les filtres que vous possédez ou ceux qui ont été partagés avec vous. |
   | Balises (non cochées dans le sélecteur de colonnes, de ce fait, la colonne n’apparaît pas) | Les balises qui ont été appliquées au filtre, soit par vous, soit par des personnes qui ont partagé le filtre avec vous. |
   | Partagé avec | Répertorie les individus ou les groupes (administrateur uniquement) ou toutes les personnes (administrateur uniquement) avec lesquelles vous avez partagé le filtre. <p>Lorsqu’un filtre est partagé par vous ou avec vous, une icône de partage s’affiche en regard du nom du filtre.</p> |
   | Date de modification | Affiche la date de la dernière modification du filtre. |
   | Utilisé dans | **Remarque :** Cette fonctionnalité est disponible dans la phase de tests limités de la version et peut ne pas être encore disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de mise à jour du Customer Journey Analytics, voir [Versions des fonctionnalités de Customer Journey Analytics](/help/release-notes/releases.md).<p>Indique dans quels types de composants le filtre est actuellement utilisé :</p> <ul><li>Mesures calculées</li><li>Projets</li><li>Projets planifiés</li><li>Filtres</li></ul> Par exemple, si le filtre est utilisé dans 40 projets et 2 mesures calculées, cette colonne affiche [!UICONTROL **Mesures calculées (2), Projets (40)**]. <p>Ces informations peuvent vous aider à déterminer si un filtre est utile aux utilisateurs de votre entreprise ou s’il doit être supprimé.</p><p>Ces informations n’incluent pas l’utilisation de l’API ou du Report Builder.</p><p>Vous pouvez utiliser la variable [Dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md) ainsi que ces informations pour vous aider à effectuer le suivi et à mieux comprendre comment les composants sont utilisés dans votre entreprise. |
   | Dernière utilisation | **Remarque :** Cette fonctionnalité est disponible dans la phase de tests limités de la version et peut ne pas être encore disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de mise à jour du Customer Journey Analytics, voir [Versions des fonctionnalités de Customer Journey Analytics](/help/release-notes/releases.md).<p>Affiche la date de la dernière utilisation du filtre dans l’un des types de composants suivants :</p> <ul><li>Mesures calculées</li><li>Projets</li><li>Projets planifiés</li><li>Filtres</li></ul> <p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs de votre entreprise ou s’il doit être supprimé.</p><p>Ces informations n’incluent pas l’utilisation de l’API ou du Report Builder.</p><p>Vous pouvez utiliser la variable [Dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md) ainsi que ces informations pour vous aider à effectuer le suivi et à mieux comprendre comment les composants sont utilisés dans votre entreprise. |

   {style="table-layout:auto"}
