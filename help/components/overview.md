---
title: Quels sont les composants de Customer Journey Analytics ?
description: Découvrez les composants des offres du Customer Journey Analytics et comment les utiliser dans les rapports.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
source-git-commit: 202a726dc68853f55a24e566c656c92785e3b3f0
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 80%

---

# Présentation des composants

Les composants sont des fonctionnalités Customer Journey Analytics qui peuvent être utilisées dans les rapports ou qui complètent les fonctionnalités de rapport. Vous pouvez gérer ces composants en procédant comme suit :

1. Connectez-vous à [analytics.adobe.com](https://analytics.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Accédez à [!UICONTROL Composants] > [!UICONTROL Composants] dans le menu d’en-tête.

Vous pouvez gérer les composants suivants :

* [**Annotations**](/help/components/annotations/overview.md) : communiquez les nuances et les informations concernant les données contextuelles à votre organisation.
* [**Audiences**](/help/components/audiences/audiences-overview.md): Créer et publier des audiences découvertes dans Customer Journey Analytics vers [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr) (RTCDP) dans Adobe Experience Platform pour le ciblage et la personnalisation des clients.
* [**Filtres**](filters/filters-overview.md): Créez, gérez, partagez et appliquez des filtres d’audience puissants et ciblés à vos rapports. Les filtres permettent d’identifier des sous-ensembles de personnes en fonction de caractéristiques ou d’interactions.
* [**Mesures calculées :**](calc-metrics/calc-metr-overview.md) Utiliser les mesures et les formules comme nouveaux composants à utiliser dans les rapports
* [**Dictionnaire de données**](/help/components/data-dictionary/data-dictionary-overview.md): Permet aux utilisateurs et aux administrateurs de suivre et de mieux comprendre les composants dans leur environnement Analytics.
* [**Périodes**](date-ranges/create.md) : Personnaliser et affiner les offres Analysis Workspace.
* [**Dimensions**](/help/components/dimensions/view-dimensions.md): Les Dimensions sont des variables qui contiennent généralement des valeurs de chaîne. Les dimensions courantes sont Page et Domaine référent.
* [**Mesures**](/help/components/apply-create-metrics.md): Permet de quantifier les points de données dans Analysis Workspace.
* [**Projets :**](/help/analysis-workspace/home.md) Organiser et gérer vos projets dans Analysis Workspace.

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

## Gérer les composants {#actions}

Vous pouvez gérer les composants directement dans le rail de gauche.

1. Cliquez avec le bouton droit sur un composant.

   OU

   Sélectionnez un composant, puis cliquez sur l’icône (de 3 points) **Action** en haut de la liste des composants.

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

## Rechercher, filtrer et trier la liste des composants

Vous pouvez rechercher, filtrer et trier la liste des composants dans le rail de gauche d’Analysis Workspace afin de localiser rapidement un composant particulier.

### Rechercher dans la liste des composants

1. Sélectionnez l’icone **Composants** ![l’icône Composants](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) dans le rail de gauche.

2. Dans le champ de recherche, commencez à saisir le nom du composant que vous souhaitez utiliser dans votre projet.

   Le type de composant peut être identifié à la fois par couleur et par icône. **Dimensions** ![Icône Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sont orange, **Filtres** ![Icône Filtrer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sont bleues, **Périodes** ![Icône Période](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sont violets et **Mesures** ![Icône Mesure](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sont vertes. Icône Adobe ![Icône Adobe](assets/default-calc-metric-icon.png) indique soit un modèle de mesure calculée, soit un modèle de filtre, et l’icône du calculateur ![Icône Calcul](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indique une mesure calculée qui a été créée par un administrateur Analytics de votre entreprise.

3. Sélectionnez le composant lorsqu’il apparaît dans la liste déroulante.

### Filtrer la liste des composants

1. Sélectionnez l’icône **Composants** ![icône Composants](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) dans le rail de gauche.

2. Sélectionnez l’icône **Filtre** ![icône Filtre du dictionnaire de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)).

   OU

   Saisissez le signe dièse (#) dans le champ de recherche.

3. Sélectionnez l’une des options de filtre suivantes pour filtrer la liste des composants :

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

4. (Facultatif) Pour affiner davantage la liste, vous pouvez trier la liste de composants, comme décrit dans la section [Trier la liste des composants](#sort-the-component-list).

### Trier la liste des composants

{{release-limited-testing-section}}

1. (Facultatif) Appliquez des filtres à la liste des composants, comme décrit dans la section [Filtrer la liste des composants](#filter-the-component-list).

2. Sélectionnez l’icône **Composants** ![icône Composants](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) dans le rail de gauche.

3. Sélectionnez l’icône **Trier** ![icône Trier les composants](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), puis sélectionnez l’une des options de filtre suivantes pour trier la liste des composants :

   {{components-sort-options}}

## Autorisations dʼaccès aux composants

Dans Analysis Workspace, les administrateurs peuvent [traiter](/help/analysis-workspace/curate-share/curate.md) les composants présentés aux utilisateurs dans les comptes rendus des performances.
