---
description: Le Créateur de filtres propose un canevas permettant de faire glisser et de déposer des Dimensions de mesures, des filtres et des événements afin de filtrer les personnes en fonction d’opérateurs, de règles et d’une logique de hiérarchie de conteneurs. Cet outil de développement intégré vous permet de créer et d’enregistrer des filtres simples ou complexes qui identifient les attributs et actions des personnes entre les visites et les événements.
title: Création de filtres
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '1450'
ht-degree: 4%

---

# Création de filtres {#build-filters}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_createaudience"
>title="Créer une audience"
>abstract="Les audiences peuvent être créées à partir d’un filtre, puis partagées avec Adobe Experience Platform pour l’activation."

<!-- markdownlint-enable MD034 -->


La boîte de dialogue **[!UICONTROL Créateur de filtres]** est utilisée pour créer ou modifier des filtres existants. La boîte de dialogue est intitulée **[!UICONTROL Nouveau filtre]** ou **[!UICONTROL Modifier le filtre]** pour les filtres que vous créez ou gérez à partir du [[!UICONTROL gestionnaire de filtres]](/help/components/filters/manage-filters.md).

>[!BEGINTABS]

>[!TAB Créateur de filtres]

![Fenêtre de détails du filtre affichant les champs et options décrits dans la section suivante.](assets/filter-builder.png)

>[!TAB Créer ou modifier un filtre]

![Fenêtre de détails du filtre affichant les champs et options décrits dans la section suivante.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Spécifiez les détails suivants (![Obligatoire](/help/assets/icons/Required.svg) requis) :

   | Élément | Description |
   | --- | --- |
   | **[!UICONTROL Vue de données]** | Vous pouvez sélectionner la vue de données pour le filtre.  Le filtre que vous définissez est disponible sous la forme d’un filtre dans l’onglet [Paramètres](/help/data-views/create-dataview.md#settings-filters) d’une vue de données. |
   | **[!UICONTROL Filtre Projet uniquement]** | Une boîte d’informations pour expliquer que le filtre n’est visible que dans le projet où il est créé et que le filtre ne sera pas ajouté à votre liste de composants. Activez **[!UICONTROL Rendez ce filtre disponible pour tous vos projets et ajoutez-le à votre liste de composants]** pour modifier ce paramètre. Cette zone d’informations n’est visible que lorsque vous créez un [filtre rapide](quick-filters.md) et que vous transformez les informations de filtre rapide en filtre normal à l’aide de l’outil **[!UICONTROL Ouvrir le créateur]** de l’interface [!UICONTROL Filtre rapide]. |
   | **[!UICONTROL Titre]** ![ ](/help/assets/icons/Required.svg) | Nommez le filtre, par exemple `Last month mobile customers`. |
   | **[!UICONTROL Description]** | Fournissez une description du filtre, par exemple, `Filter to define the mobile customers for the last month`. |
   | **[!UICONTROL Balises]** | Organisez le filtre en créant ou en appliquant une ou plusieurs balises. Commencez à saisir pour rechercher les balises existantes que vous pouvez sélectionner. Ou appuyez sur **[!UICONTROL ENTER]** pour ajouter une nouvelle balise. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer une balise. |
   | **[!UICONTROL Définition]** ![Obligatoire](/help/assets/icons/Required.svg) | Définissez votre filtre à l’aide du [Créateur de définitions](#definition-builder). |

   {style="table-layout:auto"}

1. Pour vérifier si votre définition de filtre est correcte, utilisez l’aperçu constamment mis à jour des résultats du filtre en haut à droite.
1. Pour créer une audience à partir du filtre et la partager avec l’Experience Platform, sélectionnez **[!UICONTROL Créer une audience à partir du filtre]**. Voir [Création et publication d’audiences](/help/components/audiences/publish.md) pour plus d’informations.
1. Sélectionnez :
   * **[!UICONTROL Enregistrez]** pour enregistrer le filtre.
   * **[!UICONTROL Enregistrer sous]** pour enregistrer une copie du filtre.
   * **[!UICONTROL Supprimer]** pour supprimer le filtre.
   * **[!UICONTROL Annuler]** pour annuler toute modification apportée au filtre ou annuler la création d’un nouveau filtre.


## Créateur de définitions

Vous utilisez le créateur de définitions pour construire votre définition de filtre. Dans cette construction, vous utilisez des composants, des conteneurs, des opérateurs et une logique.

Vous pouvez configurer le type et la portée de votre définition :

1. Pour spécifier le type de votre définition, indiquez si vous souhaitez que la version comporte une définition d’inclusion ou d’exclusion. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Options]** et dans le bouton de basculement **[!UICONTROL Inclure]** ou **[!UICONTROL Exclure]**.
1. Pour spécifier la portée de votre définition, sélectionnez dans la liste déroulante **[!UICONTROL Include]** ou **[!UICONTROL Exclude]** si vous souhaitez que la portée de la définition soit **[!UICONTROL Event]**, **[!UICONTROL Session]** ou **[!UICONTROL Person]**.

Vous pouvez toujours modifier ces paramètres ultérieurement.

### Composants

Une partie essentielle de la construction de votre définition de filtre consiste à utiliser des dimensions, des mesures, des filtres existants et des périodes. Tous ces composants sont disponibles à partir du panneau du composant dans le Créateur de filtres.

![Commencer à créer une définition](assets/start-building-filter.gif){width=100%}

Pour ajouter un composant :

1. Faites glisser et déposez un composant du panneau Composants sur **[!UICONTROL Faire glisser et déposer des mesures, des filtres et/ou des Dimensions ici]**. Vous pouvez utiliser la ![recherche](/help/assets/icons/Search.svg) dans la barre de composants pour rechercher des composants spécifiques.
1. Spécifiez les détails du composant. Par exemple, sélectionnez une valeur dans **[!UICONTROL Select value]**. Ou saisissez une valeur. Le contenu et la manière dont vous pouvez spécifier une ou plusieurs valeurs dépendent du composant et de l’opérateur.
1. Vous pouvez éventuellement modifier l’opérateur par défaut. Par exemple, de **[!UICONTROL equals]** à **[!UICONTROL equals any of]**. Voir [Opérateurs](operators.md) pour un aperçu détaillé des opérateurs disponibles.

Pour modifier un composant :

* Sélectionnez un nouvel opérateur pour le composant dans le menu déroulant de l’opérateur.
* Sélectionnez ou spécifiez une autre valeur pour l’opérateur, le cas échéant.
* Si le type de composant est une dimension, vous pouvez définir le modèle d’attribution. Voir [Modèle d’attribution](#attribution-models) pour plus d’informations.

Pour supprimer un composant :

* Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) dans un composant.

### Conteneurs

Vous pouvez regrouper plusieurs composants dans un ou plusieurs conteneurs et définir une logique au sein et entre les conteneurs. Les conteneurs permettent de créer des définitions complexes pour votre filtre.

![Ajouter un conteneur](assets/add-container.gif){Width=100%}

* Pour ajouter un conteneur, sélectionnez **[!UICONTROL Ajouter un conteneur]** dans ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Options]**.
* Pour ajouter un composant existant au conteneur, faites-le glisser et déposez-le dans le conteneur.
* Pour ajouter un autre composant au conteneur, faites glisser-déposer un composant du panneau Composant dans le conteneur. Utilisez la ligne d’insertion bleue comme guide.
* Pour ajouter un autre composant en dehors du conteneur, faites glisser et déposez un composant à partir du panneau Composant en dehors du conteneur, mais dans le conteneur de définition principal. Utilisez la ligne d’insertion bleue comme guide.
* Pour modifier la logique entre les composants d’un conteneur, entre des conteneurs ou entre un conteneur et un composant, sélectionnez les **[!UICONTROL Et]**, **[!UICONTROL Ou]**, **[!UICONTROL Then]** appropriés. Lorsque vous sélectionnez Alors, vous transformez le filtre en filtre séquentiel. Voir [Création d’un filtre séquentiel](seg-sequential-build.md) pour plus d’informations.
* Pour changer le niveau du conteneur, sélectionnez ![WebPage](/help/assets/icons/WebPage.svg) **[!UICONTROL Evénement]**, ![Visite](/help/assets/icons/Visit.svg) **[!UICONTROL Session]** ou ![Utilisateur](/help/assets/icons/User.svg) **[!UICONTROL Personne]**.

Vous pouvez utiliser ![Paramètre](/help/assets/icons/Setting.svg) dans un conteneur pour les actions suivantes :

| Action de conteneur | Description |
|---|---|
| **[!UICONTROL Ajouter un conteneur]** | Ajoutez un conteneur imbriqué au conteneur. |
| **[!UICONTROL Exclure]** | Excluez le résultat du conteneur dans la définition de filtre. Une fine barre de gauche rouge identifie un conteneur d’exclusion. |
| **[!UICONTROL Inclure]** | Incluez le résultat du conteneur dans la définition de filtre. Inclure est la valeur par défaut. Une fine barre de gauche grise identifie un conteneur d’inclusion. |
| **[!UICONTROL Nom container]** | Renommez le conteneur de sa description par défaut. Saisissez un nom dans le champ de texte. Si vous ne fournissez aucune entrée, la description par défaut est utilisée. |
| **[!UICONTROL Supprimer le conteneur]** | Supprimez le conteneur de la définition. |


## Périodes

Vous pouvez créer des filtres qui contiennent des plages de dates variables. Vous pouvez ainsi répondre à des questions sur les campagnes ou les événements en cours. Par exemple, vous pouvez créer un filtre qui inclut *toutes les personnes qui ont effectué un achat en ligne au cours des 60 derniers jours*.

![Filtre utilisant une période variable](assets/filter-rolling-date-range.gif)

+++ Cette vidéo sur l’utilisation de périodes flottantes dans les filtres

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

{{videoaa}}

+++

## Empilage de filtres {#stack}

Vous pouvez créer un filtre à l’aide de filtres. Lorsque vous utilisez des filtres dans un filtre, vous pouvez optimiser votre filtre et réduire la complexité.

Imaginez que vous souhaitez filtrer selon la combinaison du type d’appareil (2) et des états américains (50). Vous pouvez créer 100 filtres, chacun pour la combinaison unique de type d&#39;appareil (téléphone mobile contre tablette) et d&#39;état américain. Pour obtenir les utilisateurs de tablettes californiennes, vous devez utiliser l’un des 100 filtres suivants :

![Filtre simple pour CA et tablette](assets/filter-ca-tablet-single.png)

Vous pouvez également définir 52 filtres : 50 filtres pour les États-Unis, un pour les téléphones mobiles et un pour les tablettes. Puis empiler les filtres pour obtenir les mêmes résultats. Pour obtenir les utilisateurs de tablettes californiennes, vous devez empiler deux filtres :

![Filtre empilé pour CA et tablette](assets/filter-ca-tablet-stacked.png)


## Attribution {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_attribution_repeating"
>title="Répétitif"
>abstract="Inclut des instances et des valeurs persistantes pour la dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_attribution_instance"
>title="Instance"
>abstract="Inclut des instances et des valeurs persistantes pour la dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_attribution_nonrepeatinginstance"
>title="Instance non répétitive"
>abstract="Inclut des instances uniques (non répétées) pour la dimension."

<!-- markdownlint-enable MD034 -->



Lorsque vous utilisez une dimension dans le Créateur de filtres, vous avez la possibilité de spécifier le modèle d’attribution pour cette dimension. Le modèle d’attribution que vous sélectionnez détermine si les données sont admissibles pour la condition que vous avez spécifiée pour le composant de dimension.

Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) dans le composant de dimension et sélectionnez l’un des modèles d’attribution dans la fenêtre contextuelle :

| Modèles | Description |
|---|---|
| **[!UICONTROL Modèle de répétition (par défaut)]** | Incluez l’instance et les valeurs persistantes pour la dimension afin de déterminer la qualification. |
| **[!UICONTROL Instance]** | Inclure uniquement les valeurs d’instance pour la dimension afin de déterminer la qualification. |
| **[!UICONTROL Instance non répétée]** | Incluez des valeurs d’instance uniques (non répétées) pour la dimension afin de déterminer la qualification. |


![Modèle d’attribution sur la dimension lors de la création d’un filtre](assets/filter-dimension-attribution.png)

### Exemple

Dans le cadre d’une définition de filtre, vous avez spécifié la condition suivante : Nom de page = Femmes. Semblable à l’exemple ci-dessus. Vous répétez cette définition de filtre à l’aide des deux autres modèles d’attribution. Vous disposez donc de trois filtres chacun avec leur propre modèle d’attribution :

* Page Femmes - Attribution - Répétition (par défaut)
* Page Femmes - Attribution - Instance
* Page Femmes - Attribution - Instance non répétée


Le tableau ci-dessous explique, pour chaque modèle d’attribution, quels événements entrants sont qualifiés ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) pour cette condition.


| Page Femmes - Attribution - <br/>*modèle d’attribution* | Événement 1 :<br/>Nom de page =<br/>Femmes | Événement 2 : <br/>Nom de page =<br/>Hommes | Événement 3 : <br/>Nom de page =<br/>Femmes | Événement 4 : <br/>Nom de page = <br/>Femmes<br/>(persistante) | Événement 5 : <br/>Nom de page =<br/>Passage en caisse | Événement 6 :<br/>Nom de page =<br/>Femmes | Événement 7 : <br/>Nom de page =<br/>Accueil |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Répétitif (par défaut) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) |
| Instance | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) |
| Instance non répétitive | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) |

Voici un exemple de rapport sur les événements utilisant les trois filtres :

![Filtrer les résultats du modèle d’attribution](assets/filter-dimension-attribution-results.png)
