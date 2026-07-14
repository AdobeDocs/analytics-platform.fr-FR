---
description: Découvrez comment le créateur de segments fournit une zone de travail pour faire glisser et déposer des mesures, des dimensions, des segments et des événements vers les visiteurs du segment en fonction de la logique de hiérarchie de conteneur, des règles et des opérateurs. Découvrez comment créer et enregistrer des segments simples ou complexes qui identifient les attributs et actions des visiteurs et visiteuses entre les visites et accès aux pages.
title: Créer des segments
feature: Filters, Segments
role: User
hold: true
exl-id: 160021f1-6942-4682-9114-d375307d9912
TQID: https://experienceleague.adobe.com/MFqcgWkCqZbtbI58nF8boBZU3YzfcuAAsJxXbjBcT5E
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: b342654b753f679f86750e43efbed1eb149e1b17
workflow-type: tm+mt
source-wordcount: 1851
ht-degree: 79%

---

# Créer des segments {#build-segments}

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="Créer une audience"
>abstract="Les audiences peuvent être créées à partir d’un segment et partagées avec Adobe Experience Platform pour activation."

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="Prévisualisation des données"
>abstract="Compare les données de ce segment aux données de la vue de données. Le pourcentage de prévisualisation est basé sur le nombre total dans la vue de données des **90 derniers jours**.<br><br/>Si la prévisualisation ne se charge pas, il se peut que votre connexion soit encore en train de remplir les données."

La boîte de dialogue du **[!UICONTROL Créateur de segments]** permet de créer ou de modifier des segments existants. La boîte de dialogue s’intitule **[!UICONTROL Nouveau segment]** ou **[!UICONTROL Modifier le segment]** pour les segments que vous créez ou gérez à partir du [[!UICONTROL gestionnaire de segments]](/help/components/segments/seg-manage.md).

>[!BEGINTABS]

>[!TAB Créateur de segments]

![Fenêtre de détails des segments présentant les champs et options décrits dans la section suivante.](assets/filter-builder.png)

>[!TAB Créer ou modifier un segment]

![Fenêtre de détails des segments présentant les champs et options décrits dans la section suivante.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Spécifiez les détails suivants (![Requis](/help/assets/icons/Required.svg) est obligatoire) :

   | Élément | Description |
   | --- | --- |
   | **[!UICONTROL Vue de données]** | Vous pouvez sélectionner la vue de données du segment.  Le segment que vous définissez est disponible sous la forme d’un segment dans l’onglet [Paramètres](/help/data-views/create-dataview.md#settings-filters) d’une vue de données. |
   | **[!UICONTROL Segment de projet uniquement]** | Zone d’informations expliquant que le segment est uniquement visible dans le projet dans lequel il est créé et que le segment ne sera pas ajouté à votre liste de composants. Activez **[!UICONTROL Rendre ce segment disponible pour tous vos projets et l’ajouter à votre liste de composants]** pour modifier ce paramètre. Cette zone d’informations n’est visible que lorsque vous créez un [segment rapide](seg-quick.md) et transformez le segment rapide en segment standard à l’aide de l’option **[!UICONTROL Ouvrir le créateur]** dans l’interface [!UICONTROL Segment rapide]. |
   | **[!UICONTROL Titre]** ![Requis](/help/assets/icons/Required.svg) | Nommez le segment, par exemple `Last month mobile customers`. |
   | **[!UICONTROL Description]** | Fournissez une description du segment, par exemple `Segment to define the mobile customers for the last month`. |
   | **[!UICONTROL Balises]** | Organisez le segment en créant ou en appliquant une ou plusieurs balises. Commencez à saisir du texte pour rechercher les balises existantes que vous pouvez sélectionner. Ou appuyez sur **[!UICONTROL ENTRÉE]** pour ajouter une nouvelle balise. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer une étiquette. |
   | **[!UICONTROL Définition]** ![Obligatoire](/help/assets/icons/Required.svg) | Définissez votre segment à l’aide du [créateur de définitions](#definition-builder). |

   {style="table-layout:auto"}

1. Pour vérifier si votre définition du segment est correcte, utilisez la prévisualisation constamment mise à jour des résultats du segment en haut à droite.
1. Pour créer une audience à partir du segment et la partager avec Experience Platform, sélectionnez **[!UICONTROL Créer une audience à partir d’un segment]**. Consultez [Création et publication d’audiences](/help/components/audiences/publish.md) pour plus d’informations.
1. Sélectionnez :
   * **[!UICONTROL Enregistrer]** pour enregistrer le segment.
   * **[!UICONTROL Enregistrer sous]** pour enregistrer une copie du segment.
   * **[!UICONTROL Supprimer]** pour supprimer le segment.
   * **[!UICONTROL Annuler]** pour annuler toute modification apportée à un segment ou annuler la création d’un segment.


## Créateur de définitions

Le créateur de définitions permet de créer votre définition de segment. Dans cette construction, vous utilisez des composants, des conteneurs, des opérateurs et une logique.

Vous pouvez configurer le type et l’étendue de votre définition :

1. Pour spécifier le type de votre définition, indiquez si vous souhaitez que la définition soit inclusive ou exclusive. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Options]** et dans la liste déroulante, **[!UICONTROL Inclure]** ou **[!UICONTROL Exclure]**.
1. Pour spécifier la portée de votre définition, choisissez dans le menu déroulant **[!UICONTROL Inclure]** ou **[!UICONTROL Exclure]** si vous souhaitez que la portée de la définition soit **[!UICONTROL Événement]**, **[!UICONTROL Session]**, **[!UICONTROL Personne]**, **[!UICONTROL Compte global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} ou **[!UICONTROL Groupe d’achat]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

Vous pourrez toujours modifier ces paramètres ultérieurement.

### Composants

Une partie essentielle de la création de votre définition de segment consiste à utiliser des dimensions, des mesures, des segments existants et des périodes. Tous ces composants sont disponibles à partir du panneau des composants dans le créateur de segments.

![Commencer à créer une définition](assets/start-building-filter.gif){width=100%}

Pour ajouter un composant, procédez comme suit :

1. Faites glisser et déposez un composant du panneau Composants sur **[!UICONTROL Faire glisser et déposer ici les mesures, les segments et/ou les dimensions]**.
   * Vous pouvez utiliser la fonction ![Rechercher](/help/assets/icons/Search.svg) dans la barre des composants pour rechercher des composants spécifiques.
   * Vous pouvez utiliser ![Filtre](/help/assets/icons/Filter.svg) dans la barre de composants pour filtrer les composants ![Coche](/help/assets/icons/Checkmark.svg) **[!UICONTROL Approuvé]**, ![Étoile](/help/assets/icons/Star.svg) **[!UICONTROL Favoris]**, ![DataDimension](/help/assets/icons2/DataDimension.svg)Dimensions **[!UICONTROL ,]** Event![Metrics](/help/assets/icons/Event.svg), **[!UICONTROL Segments]**, ![Calendar](/help/assets/icons/Segmentation.svg)**[!UICONTROL DateRange]** et ![Layer](/help/assets/icons/Calendar.svg)container **&#x200B;**&#x200B;![&#x200B; &#x200B;](/help/assets/icons/Layer.svg) **[!UICONTROL **]**(tels que Produits et Assets de contenu). Vous pouvez également filtrer selon les balises ![Libellé](/help/assets/icons/Label.svg).
1. Spécifiez les détails du composant. Par exemple, sélectionnez une valeur dans **[!UICONTROL Sélectionner la valeur]**. Ou Saisissez une valeur. Le contenu et la manière dont vous pouvez spécifier une ou plusieurs valeurs dépendent du composant et de l’opérateur.
1. Modifiez éventuellement l’opérateur par défaut. Par exemple, de **[!UICONTROL égal]** à **[!UICONTROL égal à n’importe lequel]**. Consultez [Opérateurs](seg-operators.md) pour une présentation détaillée des opérateurs disponibles.

Pour ajouter un composant, procédez comme suit :

* Sélectionnez un nouvel opérateur pour le composant dans le menu déroulant des opérateurs.
* Sélectionnez ou spécifiez une autre valeur pour l’opérateur, le cas échéant.
* Si le type de composant est une dimension, vous pouvez définir le modèle d’attribution. Consultez [Modèle d’attribution](#attribution) pour en savoir plus.

Pour ajouter un composant, procédez comme suit :

* Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) dans un composant.

### Conteneurs

Vous pouvez regrouper plusieurs composants dans un ou plusieurs conteneurs et définir une logique au sein des conteneurs et entre ceux-ci. Les conteneurs vous permettent de créer des définitions complexes pour votre segment.

![Ajouter un conteneur](assets/add-container.gif){Width=100%}

* Pour ajouter un conteneur, sélectionnez **[!UICONTROL Ajouter un conteneur]** dans ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Options]**.
* Pour ajouter un composant existant au conteneur, faites-le glisser dans le conteneur.
* Pour ajouter un autre composant au conteneur, faites glisser un composant du panneau des composants et déposez-le dans le conteneur. Utilisez la ligne d’insertion bleue comme guide.
* Pour ajouter un autre composant à l’extérieur du conteneur, faites glisser un composant depuis le panneau des composants à l’extérieur du conteneur, mais à l’intérieur du conteneur de définition principal. Utilisez la ligne d’insertion bleue comme guide.
* Pour modifier la logique entre les composants d’un conteneur, entre les conteneurs ou entre un conteneur et un composant, sélectionnez les opérateurs **[!UICONTROL Et]**, **[!UICONTROL Ou]** et **[!UICONTROL Alors]** appropriés. Lorsque vous sélectionnez Ensuite, vous transformez le segment en segment séquentiel. Consultez [Créer un segment séquentiel](seg-sequential-build.md) pour plus d’informations.
* Pour changer de niveau de conteneur, sélectionnez ![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL Compte global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![Compte](/help/assets/icons/Account.svg) **[!UICONTROL Compte]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![Opportunity](/help/assets/icons/Opportunity.svg)Opportunity **[!UICONTROL [!BADGE B2B edition]**, &#x200B;]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}BuyingGroup![Buying Group](/help/assets/icons/BuyingGroup.svg) [!BADGE B2B edition **[!UICONTROL ,]** Page]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}Event![, &#x200B;](/help/assets/icons/WebPage.svg)Visit **&#x200B;**&#x200B;Session![, &#x200B;](/help/assets/icons/Visit.svg)User **&#x200B;**&#x200B;Person![&#x200B; ou &#x200B;](/help/assets/icons/User.svg)Layer **&#x200B;**&#x200B;Object![&#x200B; &#x200B;](/help/assets/icons/Layer.svg) **&#x200B;**. Lorsque vous sélectionnez ![Calque](/help/assets/icons/Layer.svg) **[!UICONTROL Objet]**, sélectionnez le [conteneur personnalisé](/help/data-views/create-dataview.md#containers-1) à utiliser. Par exemple, Products ou Content Assets.

Vous pouvez utiliser ![Paramètre](/help/assets/icons/Setting.svg) dans un conteneur pour les actions suivantes :

| Action du conteneur | Description |
|---|---|
| **[!UICONTROL Ajouter un conteneur]** | Ajoutez un conteneur imbriqué au conteneur. |
| **[!UICONTROL Exclure]** | Excluez le résultat du conteneur dans la définition du segment. Une fine barre rouge à gauche identifie un conteneur d’exclusion. |
| **[!UICONTROL Inclure]** | Incluez le résultat du conteneur dans la définition du segment. L’inclusion est le paramètre par défaut. Une fine barre grise à gauche identifie un conteneur d’inclusion. |
| **[!UICONTROL Nommer le conteneur]** | Renommez le conteneur à partir de sa description par défaut. Saisissez un nom dans le champ de texte. Si vous ne fournissez aucune entrée, la description par défaut est utilisée. |
| **[!UICONTROL Supprimer le conteneur]** | Supprimez le conteneur de la définition. |

Lorsque vous faites glisser une dimension ou une mesure que vous avez définie en tant que [conteneur](/help/data-views/create-dataview.md#containers-1) dans le Créateur de segments ou le panneau de segments rapides, le système sélectionne automatiquement le conteneur approprié et n’utilise pas le conteneur **[!UICONTROL Événement]** par défaut. Ce comportement limite le segment au conteneur individuel plutôt qu’à l’événement entier.

Lorsque vous faites glisser des composants au niveau du [conteneur](/help/data-views/create-dataview.md#containers-1) et de l’événement dans une seule règle de segment, le système utilise le conteneur **[!UICONTROL Event]**, qui est le conteneur partagé le plus élevé (le moins granulaire). Si tous les composants qui font partie d’une règle de segment se trouvent au même niveau de conteneur, ce conteneur est utilisé.

## Périodes

Vous pouvez créer des segments qui contiennent des périodes variables. Vous pouvez ainsi répondre aux questions sur les campagnes ou les événements en cours. Vous pouvez par exemple créer un segment qui comprend *toutes les personnes qui ont effectué un achat en ligne au cours des 60 derniers jours*.

![Segment avec une période variable](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Périodes flottantes dans les segments](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/segmentation/rolling-date-ranges-in-segments){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Empiler des segments {#stack}

Vous pouvez créer un segment à l’aide de segments. Lorsque vous utilisez des segments dans un segment, vous pouvez l’optimiser et en réduire la complexité.

Imaginez que vous souhaitiez effectuer une segmentation sur la combinaison du type d’appareil (2) et des états américains (50). Vous pouvez créer 100 segments, un pour chaque combinaison unique de type d’appareil (téléphone mobile ou tablette) et d’État des États-Unis. Pour obtenir les utilisateurs et utilisatrices de tablettes de la Californie, vous devez utiliser l’un des 100 segments suivants :

![Segment simple pour Californie et tablette](assets/filter-ca-tablet-single.png)

Vous pouvez également définir 52 segments : 50 segments pour les États américains, un pour le téléphone mobile et un pour la tablette. Empilez ensuite les segments pour obtenir les mêmes résultats. Pour obtenir les utilisateurs de tablettes en Californie, vous devez empiler deux segments :

![Segment empilé pour Californie et tablette](assets/filter-ca-tablet-stacked.png)


## Attribution {#attribution}

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="Répétitif"
>abstract="Inclut des instances et des valeurs persistantes pour la dimension."


>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="Instance"
>abstract="Inclut des instances pour la dimension."


>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="Instance non répétitive"
>abstract="Inclut des instances uniques (non répétées) pour la dimension."




Lorsque vous utilisez une dimension dans le créateur de segments, vous disposez des options permettant de spécifier le modèle d’attribution de cette dimension. Le modèle d’attribution que vous sélectionnez détermine si les données sont admissibles pour la condition que vous avez spécifiée pour le composant de dimension.

Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) dans le composant de dimension, puis sélectionnez l’un des modèles d’attribution dans la fenêtre contextuelle :

| Modèles | Description |
|---|---|
| **[!UICONTROL Modèle répétitif (par défaut)]** | Incluez l’instance et les valeurs persistantes pour la dimension afin de déterminer la qualification. |
| **[!UICONTROL Instance]** | Incluez uniquement des valeurs d’instance pour la dimension afin de déterminer la qualification. |
| **[!UICONTROL Instance non répétitive]** | Incluez des valeurs d’instance uniques (non répétitives) pour la dimension afin de déterminer la qualification. |


![Modèle d’attribution sur la dimension lors de la création d’un segment](assets/filter-dimension-attribution.png)

### Exemple

Dans le cadre d’une définition de segment, vous avez spécifié la condition suivante : Nom de page est égal à Femmes. Similaire à l’exemple ci-dessus. Vous répétez cette définition de segment à l’aide des deux autres modèles d’attribution. Vous disposez donc de trois segments ayant chacun leur propre modèle d’attribution :

* Page Femmes - Attribution - Répétition (par défaut)
* Page Femmes - Attribution - Instance
* Page Femmes - Attribution - Instance non répétitive


Le tableau ci-dessous explique, pour chaque modèle d’attribution, les événements entrants qualifiés ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) pour cette condition.


| Page Femmes - Attribution - <br/>*Modèle d’attribution* | Événement 1 : <br/>Nom de page égal<br/>Femmes | Événement 2 : <br/>Nom de page égal<br/> Hommes | Événement 3 : <br/>Nom de page égal<br/>Femmes | Événement 4 : <br/>Nom de page égal<br/>Femmes<br/>(persistant) | Événement 5 : <br/>Nom depage égal<br/>Passage en caisse | Événement 6 : <br/>Nom de page égal<br/>Femmes | Événement 7 : <br/>Nom de page égal<br/>Accueil |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Répétition (par défaut) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) |
| Instance | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) |
| Instance non répétitive | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) |

Un exemple de rapport sur les événements utilisant les trois segments ressemble à ceci :

![Segmenter les résultats du modèle d’attribution](assets/filter-dimension-attribution-results.png)
