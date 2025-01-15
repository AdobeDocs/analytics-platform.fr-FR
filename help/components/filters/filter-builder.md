---
description: Le créateur de filtres fournit une zone de travail dans laquelle faire glisser et déposer des Dimensions de mesure, des filtres et des événements afin de filtrer les personnes en fonction de la logique de hiérarchie des conteneurs, des règles et des opérateurs. Cet outil de développement intégré vous permet de créer et d’enregistrer des filtres simples ou complexes qui identifient les attributs de personne et les actions sur les visites et les événements.
title: Création de filtres
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: 8eb146fccbdbe47df8ca28f7b8dcbce2bf6888fd
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 10%

---

# Création de filtres {#build-filters}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="Création d’une audience"
>abstract="Les audiences peuvent être créées à partir d’un filtre et partagées avec Adobe Experience Platform pour activation."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="Prévisualisation des données"
>abstract="Compare les données de ce filtre aux données de la vue de données. Le pourcentage de prévisualisation est basé sur le nombre total dans la vue de données des **90 derniers jours**.<br><br/>Si la prévisualisation ne se charge pas, il se peut que votre connexion soit encore en train de remplir les données."

<!-- markdownlint-enable MD034 -->



La boîte de dialogue **[!UICONTROL Créateur de filtres]** permet de créer des filtres ou de modifier des filtres existants. La boîte de dialogue s’intitule **[!UICONTROL Nouveau filtre]** ou **[!UICONTROL Modifier le filtre]** pour les filtres que vous créez ou gérez à partir du gestionnaire [[!UICONTROL Filtres]](/help/components/filters/manage-filters.md).

>[!BEGINTABS]

>[!TAB  Créateur de filtres ]

![Fenêtre Détails du filtre affichant les champs et options décrits dans la section suivante.](assets/filter-builder.png)

>[!TAB Créer ou modifier un filtre]

![Fenêtre Détails du filtre affichant les champs et options décrits dans la section suivante.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Spécifiez les détails suivants (![Requis](/help/assets/icons/Required.svg) est obligatoire) :

   | Élément | Description |
   | --- | --- |
   | **[!UICONTROL Vue de données]** | Vous pouvez sélectionner la vue de données pour le filtre.  Le filtre que vous définissez est disponible sous forme de filtre dans l’onglet [Paramètres](/help/data-views/create-dataview.md#settings-filters) d’une vue de données. |
   | **[!UICONTROL Filtre Projet uniquement]** | Une zone d’informations expliquant que le filtre est uniquement visible dans le projet dans lequel il est créé et que le filtre ne sera pas ajouté à votre liste de composants. Activez **[!UICONTROL Rendre ce filtre disponible pour tous vos projets et l’ajouter à votre liste de composants]** pour modifier ce paramètre. Cette zone d’informations n’est visible que lorsque vous créez un [filtre rapide](quick-filters.md) et transformez les informations du filtre rapide en filtre standard à l’aide de **[!UICONTROL Ouvrir le créateur]** dans l’interface [!UICONTROL Filtre rapide]. |
   | **[!UICONTROL Titre]** ![Requis](/help/assets/icons/Required.svg) | Nommez le filtre, par exemple `Last month mobile customers`. |
   | **[!UICONTROL Description]** | Fournissez une description du filtre, par exemple, `Filter to define the mobile customers for the last month`. |
   | **[!UICONTROL Étiquettes]** | Organisez le filtre en créant ou en appliquant une ou plusieurs balises. Commencez à saisir du texte pour rechercher les étiquettes existantes que vous pouvez sélectionner. Ou appuyez sur **[!UICONTROL ENTRÉE]** pour ajouter une nouvelle balise. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer une étiquette. |
   | **[!UICONTROL Définition]** ![Obligatoire](/help/assets/icons/Required.svg) | Définissez votre filtre à l’aide du [créateur de définitions](#definition-builder). |

   {style="table-layout:auto"}

1. Pour vérifier si votre définition de filtre est correcte, utilisez l’aperçu constamment mis à jour des résultats du filtre en haut à droite.
1. Pour créer une audience à partir du filtre et la partager avec un Experience Platform, sélectionnez **[!UICONTROL Créer une audience à partir du filtre]**. Voir [Création et publication d’audiences](/help/components/audiences/publish.md) pour plus d’informations.
1. Sélectionner :
   * **[!UICONTROL Enregistrer]** pour enregistrer le filtre.
   * **[!UICONTROL Enregistrer sous]** pour enregistrer une copie du filtre.
   * **[!UICONTROL Supprimer]** pour supprimer le filtre.
   * **[!UICONTROL Annuler]** pour annuler les modifications apportées au filtre ou annuler la création d’un nouveau filtre.


## Créateur de définitions

Le créateur de définitions permet de créer votre définition de filtre. Dans cette construction, vous utilisez des composants, des conteneurs, des opérateurs et une logique.

Vous pouvez configurer le type et l’étendue de votre définition :

1. Pour spécifier le type de votre définition, indiquez si vous souhaitez que la version puisse inclure ou exclure la définition. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Options]** et dans la liste déroulante **[!UICONTROL Inclure]** ou **[!UICONTROL Exclure]**.
1. Pour spécifier la portée de votre définition, choisissez dans le menu déroulant **[!UICONTROL Inclure]** ou **[!UICONTROL Exclure]** si vous souhaitez que la portée de la définition soit **[!UICONTROL Événement]**, **[!UICONTROL Session]** ou **[!UICONTROL Personne]**.

Vous pourrez toujours modifier ces paramètres ultérieurement.

### Composants

Une partie essentielle de la création de votre définition de filtre consiste à utiliser des dimensions, des mesures, des filtres existants et des périodes. Tous ces composants sont disponibles à partir du panneau des composants dans le créateur de filtres.

![Commencer à créer une définition](assets/start-building-filter.gif){width=100%}

Pour ajouter un composant :

1. Faites glisser et déposez un composant du panneau des composants sur **[!UICONTROL Faites glisser et déposez ici les mesures, les filtres et/ou les Dimensions]**. Vous pouvez utiliser la fonction ![Rechercher](/help/assets/icons/Search.svg) dans la barre des composants pour rechercher des composants spécifiques.
1. Spécifiez les détails du composant. Par exemple, sélectionnez une valeur dans **[!UICONTROL Sélectionner la valeur]**. Ou saisissez une valeur. Le contenu et la manière dont vous pouvez spécifier une ou plusieurs valeurs dépendent du composant et de l’opérateur.
1. Modifiez éventuellement l’opérateur par défaut. Par exemple, de **[!UICONTROL égal]** à **[!UICONTROL égal à n’importe lequel]**. Voir [Opérateurs](operators.md) pour une présentation détaillée des opérateurs disponibles.

Pour modifier un composant :

* Sélectionnez un nouvel opérateur pour le composant dans le menu déroulant opérateur .
* Sélectionnez ou spécifiez une autre valeur pour l’opérateur, le cas échéant.
* Si le type de composant est une dimension, vous pouvez définir le modèle d’attribution. Voir [Modèle d’attribution](#attribution-models) pour plus d’informations.

Pour supprimer un composant :

* Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) dans un composant.

### Conteneurs

Vous pouvez regrouper plusieurs composants dans un ou plusieurs conteneurs et définir une logique au sein des conteneurs et entre ceux-ci. Les conteneurs vous permettent de créer des définitions complexes pour votre filtre.

![Ajouter un conteneur](assets/add-container.gif){Width=100%}

* Pour ajouter un conteneur, sélectionnez **[!UICONTROL Ajouter un conteneur]** dans ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Options]**.
* Pour ajouter un composant existant au conteneur, faites-le glisser dans le conteneur.
* Pour ajouter un autre composant au conteneur, faites glisser un composant du panneau des composants et déposez-le dans le conteneur. Utilisez la ligne d&#39;insertion bleue comme guide.
* Pour ajouter un autre composant à l’extérieur du conteneur, faites glisser un composant depuis le panneau des composants à l’extérieur du conteneur, mais à l’intérieur du conteneur de définition principal. Utilisez la ligne d&#39;insertion bleue comme guide.
* Pour modifier la logique entre les composants d’un conteneur, entre les conteneurs ou entre un conteneur et un composant, sélectionnez les **[!UICONTROL Et]**, **[!UICONTROL Ou]**, **[!UICONTROL Alors]** appropriés. Lorsque vous sélectionnez Ensuite, vous transformez le filtre en filtre séquentiel. Voir [Créer un filtre séquentiel](seg-sequential-build.md) pour plus d’informations.
* Pour changer le niveau de conteneur, sélectionnez ![WebPage](/help/assets/icons/WebPage.svg) **[!UICONTROL Event]**, ![Visit](/help/assets/icons/Visit.svg) **[!UICONTROL Session]** ou ![User](/help/assets/icons/User.svg) **[!UICONTROL Person]**.

Vous pouvez utiliser ![Paramètre](/help/assets/icons/Setting.svg) dans un conteneur pour les actions suivantes :

| Action du conteneur | Description |
|---|---|
| **[!UICONTROL Ajouter un conteneur]** | Ajoutez un conteneur imbriqué au conteneur . |
| **[!UICONTROL Exclure]** | Excluez le résultat du conteneur dans la définition du filtre. Une fine barre de gauche rouge identifie un conteneur d’exclusion. |
| **[!UICONTROL Inclure]** | Incluez le résultat du conteneur dans la définition du filtre. Inclure est la valeur par défaut. Une fine barre de gauche grise identifie un conteneur d’inclusion. |
| **[!UICONTROL Nom du conteneur]** | Renommez le conteneur à partir de sa description par défaut. Saisissez un nom dans le champ de texte. Si vous ne fournissez aucune entrée, la description par défaut est utilisée. |
| **[!UICONTROL Supprimer le conteneur]** | Supprimez le conteneur de la définition . |


## Périodes

Vous pouvez créer des filtres qui contiennent des périodes flottantes. Vous pouvez ainsi répondre aux questions sur les campagnes ou les événements en cours. Par exemple, vous pouvez créer un filtre qui inclut *toute personne ayant effectué un achat en ligne au cours des 60 derniers jours*.

![Filtrer à l’aide d’une période variable](assets/filter-rolling-date-range.gif)

+++ Regardez cette vidéo sur l’utilisation de périodes flottantes dans les filtres

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

{{videoaa}}

+++

## Empilage de filtres {#stack}

Vous pouvez créer un filtre à l’aide de filtres. Lorsque vous utilisez des filtres dans un filtre, vous pouvez l’optimiser et en réduire la complexité.

Imaginez que vous souhaitiez filtrer selon la combinaison du type d’appareil (2) et des états américains (50). Vous pouvez créer 100 filtres, chacun pour la combinaison unique de type d’appareil (téléphone mobile ou tablette) et d’état des États-Unis. Pour attirer les utilisateurs californiens de tablettes, vous devez utiliser l’un des 100 filtres suivants :

![Filtre simple pour CA et tablette](assets/filter-ca-tablet-single.png)

Vous pouvez également définir 52 filtres : 50 filtres pour les États américains, un pour le téléphone mobile et un pour la tablette. Empilez ensuite les filtres pour obtenir les mêmes résultats. Pour attirer les utilisateurs californiens de tablettes, vous devez empiler deux filtres :

![Filtre empilé pour CA et tablette](assets/filter-ca-tablet-stacked.png)


## Attribution {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="Répétitif"
>abstract="Inclut des instances et des valeurs persistantes pour la dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="Instance"
>abstract="Inclut des instances et des valeurs persistantes pour la dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="Instance non répétitive"
>abstract="Inclut des instances uniques (non répétées) pour la dimension."

<!-- markdownlint-enable MD034 -->



Lorsque vous utilisez une dimension dans le créateur de filtres, vous disposez des options permettant de spécifier le modèle d’attribution de cette dimension. Le modèle d’attribution que vous sélectionnez détermine si les données sont admissibles pour la condition que vous avez spécifiée pour le composant de dimension.

Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) dans le composant de dimension, puis sélectionnez l’un des modèles d’attribution dans la fenêtre contextuelle :

| Modèles | Description |
|---|---|
| **[!UICONTROL Modèle répété (par défaut)]** | Incluez l’instance et les valeurs persistantes pour la dimension afin de déterminer la qualification. |
| **[!UICONTROL Instance]** | Incluez uniquement des valeurs d’instance pour la dimension afin de déterminer la qualification. |
| **[!UICONTROL Instance non répétitive]** | Incluez des valeurs d’instance uniques (non répétées) pour la dimension afin de déterminer la qualification. |


![Modèle d’attribution sur la dimension lors de la création d’un filtre](assets/filter-dimension-attribution.png)

### Exemple

Dans le cadre d’une définition de filtre, vous avez spécifié la condition suivante : Le nom de page est égal à Femmes. Similaire à l’exemple ci-dessus. Vous répétez cette définition de filtre à l’aide des deux autres modèles d’attribution. Vous disposez donc de trois filtres ayant chacun leur propre modèle d’attribution :

* Page Femmes - Attribution - Répétition (par défaut)
* Page Femmes - Attribution - Instance
* Page Femmes - Attribution - Instance non répétitive


Le tableau ci-dessous explique, pour chaque modèle d’attribution, les événements entrants qualifiés ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) pour cette condition.


| Page Femmes - Attribution - <br/>*modèle d’attribution* | Event 1:<br/>Nom de page égal <br/> femmes | Event 2:<br/>Nom de page égal <br/> Hommes | Event 3:<br/>Nom de page égal <br/> femmes | Événement 4:<br/>Nom de page égal <br/> femmes<br/>(persistant) | Événement 5:<br/>Nom de la page est égal <br/> Passage en caisse | Event 6:<br/>Nom de page égal <br/> femmes | Event 7:<br/>Page Name equals<br/>Home |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Répétition (par défaut) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) |
| Instance | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) |
| Instance non répétitive | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) |

Un exemple de rapport sur les événements utilisant les trois filtres ressemble à ceci :

![Filtrage des résultats du modèle d’attribution](assets/filter-dimension-attribution-results.png)
