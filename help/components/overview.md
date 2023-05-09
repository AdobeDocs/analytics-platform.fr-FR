---
title: Quels sont les composants de Customer Journey Analytics ?
description: Découvrez les composants des offres CJA et comment les utiliser dans la création de rapports.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
source-git-commit: d431e781eb18eb3f4904094972c218a9e80980d9
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 62%

---

# Présentation des composants

Les composants sont des fonctionnalités Customer Journey Analytics qui peuvent être utilisées dans les rapports ou qui complètent les fonctionnalités de rapport. Vous pouvez gérer ces composants en procédant comme suit :

1. Connectez-vous à [analytics.adobe.com](https://analytics.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Accédez à [!UICONTROL Composants] > [!UICONTROL Composants] dans le menu d’en-tête.

Vous pouvez gérer les composants suivants :

* [**Annotations**](/help/components/annotations/overview.md) : communiquez les nuances et les insights concernant les données contextuelles à votre organisation.
* [**Filtres :**](filters/filters-overview.md) Exclure des parties de vos données pour se concentrer sur les éléments de dimension communs
* [**Mesures calculées :**](calc-metrics/calc-metr-overview.md) Utiliser les mesures et les formules comme nouveaux composants à utiliser dans les rapports
* [**Périodes**](date-ranges/overview.md) : Personnaliser et affiner les offres Analysis Workspace
* [**Projets :**](/help/analysis-workspace/home.md) Organiser et gérer vos projets dans Analysis Workspace

## Composants d’Analysis Workspace

Les composants d’Analysis Workspace sont constitués de mesures, dimensions, filtres et granularités temporelles que vous pouvez faire glisser et déposer sur un projet. Les composants personnalisés que vous créez sont ajoutés à ces panneaux, par exemple les périodes personnalisées.

Pour accéder au panneau Composants, cliquez sur l’icône **[!UICONTROL Composants]** dans le rail de gauche. Vous pouvez passer d’un panneau à un autre (panneau vierge, [panneau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Quick Insights](/help/analysis-workspace/c-panels/quickinsight.md) ou panneau [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md)), les [visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) et les composants à l’aide des icônes du rail de gauche ou des [touches d’accès rapide](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/components.png)

Voir [Création d’un projet](/help/analysis-workspace/home.md) pour plus d’informations sur l’utilisation du panneau Composants dans un projet.

## Actions des composants

Vous pouvez gérer les composants (individuellement ou en sélectionnant plusieurs à la fois) de plusieurs façons. Cliquez avec le bouton droit de la souris sur un composant ou cliquez sur **[!UICONTROL Actions]** en haut de la liste des composants.

>[!NOTE]
>
>Ces actions ne s’appliquent pas aux composants de temps.

| Action des composants | Description |
| --- | --- |
| Baliser | Organisez ou gérez les composants en leur appliquant des balises. Cela apparaît ensuite dans le gestionnaire de composants correspondant, par exemple [!UICONTROL Analytics] > [!UICONTROL Composants] > [!UICONTROL Filtres] ou [!UICONTROL Analytics] > [!UICONTROL Composants] > [!UICONTROL Projets]. |
| Favori | Ajoutez le composant à votre liste de favoris. Cela apparaît ensuite dans le gestionnaire de composants correspondant, par exemple [!UICONTROL Analytics] > [!UICONTROL Composants] > [!UICONTROL Filtres] ou [!UICONTROL Analytics] > [!UICONTROL Composants] > [!UICONTROL Projets]. |
| Approuver | Approuvez le composant pour le rendre canonique. Cela apparaît ensuite dans le gestionnaire de composants correspondant, par exemple [!UICONTROL Analytics] > [!UICONTROL Composants] > [!UICONTROL Filtres] ou [!UICONTROL Analytics] > [!UICONTROL Composants] > [!UICONTROL Projets]. |
| Partager | S’applique seulement aux filtres. |
| Supprimer | S’applique seulement aux filtres. |

Regardez la vidéo sur la création de mesures, de filtres et de dates :

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Gestion des composants {#actions}

Vous pouvez gérer les composants directement dans le rail de gauche.

1. Cliquez avec le bouton droit de la souris sur un composant.

   OU

   Sélectionnez un composant, puis sélectionnez l’option **Action** Icône (3 points) en haut de la liste des composants.

   >[!TIP]
   >
   >   Vous pouvez sélectionner plusieurs composants en maintenant la touche Maj enfoncée ou en maintenant la touche Commande (sur Mac) ou Ctrl (sur Windows) enfoncée.


   ![](assets/component-actions.png)

   | Action des composants | Description |
   |--- |--- |
   | [!UICONTROL **Balise**] | Organisez ou gérez les composants en leur appliquant des balises. Vous pouvez ensuite effectuer une recherche par balise dans le rail de gauche en cliquant sur le filtre ou en saisissant #. Les balises servent également de filtres dans les gestionnaires de composants. |
   | [!UICONTROL **Favori**] | Ajoutez le composant à votre liste de favoris. Comme avec les balises, vous pouvez effectuer une recherche par Favoris dans le rail de gauche et les utiliser comme filtre dans les gestionnaires de composants. |
   | [!UICONTROL **Approuver**] | Marquez les composants comme Approuvés pour signaler à vos utilisateurs que le composant est approuvé par l’organisation. Comme avec les balises, vous pouvez effectuer une recherche par composants Approuvés dans le rail de gauche et les utiliser comme filtre dans les gestionnaires de composants. |
   | [!UICONTROL **Partager**] | Partagez des composants avec des utilisateurs de votre organisation. Cette option est disponible uniquement pour les composants personnalisés, tels que les filtres ou les mesures calculées. |
   | [!UICONTROL **Supprimer**] | Supprimez les composants dont vous n’avez plus besoin. Cette option est disponible uniquement pour les composants personnalisés, tels que les filtres ou les mesures calculées. |

Les composants personnalisés peuvent également être gérés par l’intermédiaire de leurs gestionnaires de composants respectifs. Par exemple, la variable [Gestion des filtres](/help/components/filters/manage-filters.md).

## Recherche, filtrage et tri de la liste des composants

Vous pouvez rechercher, filtrer et trier la liste des composants dans le rail de gauche d’Analysis Workspace afin de localiser rapidement un composant particulier.

### Recherche dans la liste des composants

1. Sélectionnez la **Composants** icon ![Icône Composants](assets/components-icon.png) dans le rail de gauche.

1. Dans le champ de recherche, commencez à saisir le nom du composant que vous souhaitez utiliser dans votre projet.

   Le type de composant peut être identifié à la fois par couleur et par icône. **Dimensions** ![Icône Dimension](assets/dimension-icon.png) sont orange, **Filtres** ![Icône Filtrer](assets/segment-icon.png) sont bleues, **Périodes** ![Icône Période](assets/date-range-icon.png) sont violets et **Mesures** ![Icône Mesure](assets/default-metric-icon.png) sont vertes. Icône Adobe ![Icône Adobe](assets/default-calc-metric-icon.png) indique soit un modèle de mesure calculée, soit un modèle de filtre, et l’icône du calculateur ![Icône Calcul](assets/calculated-metric-icon-created.png) indique une mesure calculée qui a été créée par un administrateur Analytics de votre entreprise.

1. Sélectionnez le composant lorsqu’il apparaît dans la liste déroulante.

### Filtrage de la liste des composants

1. Sélectionnez la **Composants** icon ![Icône Composants](assets/components-icon.png) dans le rail de gauche.

1. Sélectionnez la **Filtrer** icon ![Icône Filtre du dictionnaire de données](assets/components-filter-icon.png).

   OU

   Saisissez le signe dièse (#) dans le champ de recherche.

1. Sélectionnez l’une des options de filtre suivantes pour filtrer la liste des composants :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Approuvés**] | Afficher uniquement les composants marqués comme approuvés par l’administration. |
   | [!UICONTROL **Favoris**] | Affichez uniquement les composants figurant dans votre liste de favoris. Pour plus d’informations sur l’ajout de composants à votre liste de favoris, voir [Gestion des composants](#manage-components). |
   | [!UICONTROL **Dimensions**] | Afficher uniquement les composants qui sont des dimensions. |
   | [!UICONTROL **Mesures**] | Afficher uniquement les composants qui sont des mesures. |
   | [!UICONTROL **Filtres**] | Afficher uniquement les composants qui sont des filtres. |
   | [!UICONTROL **Périodes**] | Afficher uniquement les composants qui sont des périodes. |
   | [!UICONTROL **Tout afficher**] | Permet d’afficher tous les composants. Cette option est réservée à l’administration. |
   | [!UICONTROL **Non approuvé**] | Permet de n’afficher que les composants qui n’ont pas encore été marqués comme approuvés par l’administration. Cette option est utile pour l’administration pour identifier les composants qui doivent être examinés et approuvés. Cette option est réservée à l’administration. |

1. (Facultatif) Pour affiner davantage la liste, vous pouvez trier la liste de composants, comme décrit dans la section [Tri de la liste des composants](#sort-the-component-list).

### Tri de la liste des composants

1. (Facultatif) Appliquez des filtres à la liste des composants, comme décrit dans la section [Filtrage de la liste des composants](#filter-the-component-list).

1. Sélectionnez la **Composants** icon ![Icône Composants](assets/components-icon.png) dans le rail de gauche.

1. Sélectionnez la **Tri** icon ![Icône Tri des composants](assets/component-sort-icon.png), puis sélectionnez l’une des options de filtre suivantes pour trier la liste des composants :

   {{components-sort-options}}

## Autorisations dʼaccès aux composants

Dans Analysis Workspace, les administrateurs peuvent [traiter](/help/analysis-workspace/curate-share/curate.md) les composants présentés aux utilisateurs dans les comptes rendus des performances.
