---
description: Le générateur de filtres fournit un canevas pour glisser-déposer des dimensions, des filtres et des événements de mesure afin de filtrer des personnes en fonction de la logique hiérarchique de conteneur, des règles et des opérateurs. Cet outil de développement intégré vous permet de créer et d’enregistrer des filtres simples ou complexes qui identifient les attributs et les actions des personnes dans les visites et les événements.
title: Création de filtres
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '1570'
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



La **[!UICONTROL boîte de dialogue Générateur]** de filtres sert à créer ou à modifier des filtres existants. La boîte de dialogue est intitulée **[!UICONTROL Nouveau filtre]** ou **[!UICONTROL Modifier le filtre]** pour les filtres que vous créez ou gérez à partir du [[!UICONTROL Gestionnaire de filtres]](/help/components/filters/manage-filters.md).

>[!BEGINTABS]

>[!TAB Créateur de filtres]

![Fenêtre Détails du filtre affichant les champs et options décrits dans la section suivante.](assets/filter-builder.png)

>[!TAB Créer ou modifier un filtre]

![Fenêtre Détails du filtre affichant les champs et options décrits dans la section suivante.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Spécifiez les détails suivants (![Requis](/help/assets/icons/Required.svg) est obligatoire) :

   | Élément | Description |
   | --- | --- |
   | **[!UICONTROL Vue de données]** | Vous pouvez sélectionner la vue de données pour le filtre.  Le filtre que vous définissez est disponible sous forme de filtre dans l’onglet [Paramètres](/help/data-views/create-dataview.md#settings-filters) d’une vue de données. |
   | **[!UICONTROL Filtre Projet uniquement]** | Une zone d’informations expliquant que le filtre est uniquement visible dans le projet dans lequel il est créé et que le filtre ne sera pas ajouté à votre liste de composants. Activez **[!UICONTROL Rendre ce filtre disponible pour tous vos projets et l’ajouter à votre liste de composants]** pour modifier ce paramètre. Cette boîte d’information n’est visible que lorsque vous créez un [filtre](quick-filters.md) rapide et que vous transformez les informations de filtre rapide en filtre régulier à l’aide **[!UICONTROL de Open builder]** dans l’interface [!UICONTROL Filtre] rapide. |
   | **[!UICONTROL Titre]** ![Requis](/help/assets/icons/Required.svg) | Nommez le filtre, par exemple `Last month mobile customers`. |
   | **[!UICONTROL Description]** | Fournissez une description du filtre, par exemple, `Filter to define the mobile customers for the last month`. |
   | **[!UICONTROL Balises]** | Organisez le filtre en créant ou en appliquant une ou plusieurs balises. Commencez à saisir du texte pour rechercher les étiquettes existantes que vous pouvez sélectionner. Ou appuyez sur **[!UICONTROL ENTRÉE]** pour ajouter une nouvelle balise. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer une étiquette. |
   | **[!UICONTROL Définition]** ![requise](/help/assets/icons/Required.svg) | Définissez votre filtre à l’aide du Générateur de [définitions](#definition-builder). |

   {style="table-layout:auto"}

1. Pour vérifier si votre définition de filtre est correcte, utilisez l’aperçu constamment mis à jour des résultats du filtre en haut à droite.
1. Pour créer une audience à partir du filtre et la partager avec Experience Platform, sélectionnez **[!UICONTROL Créer une audience à partir d&#39;un filtre]**. Voir [Création et publication d’audiences](/help/components/audiences/publish.md) pour plus d’informations.
1. Sélectionner :
   * **[!UICONTROL Enregistrer]** pour enregistrer le filtre.
   * **[!UICONTROL Enregistrer sous]** pour enregistrer une copie du filtre.
   * **[!UICONTROL Supprimer]** pour supprimer le filtre.
   * **[!UICONTROL Annulez]** pour annuler toutes les modifications apportées au filtre ou annuler la création d’un nouveau filtre.


## Créateur de définitions

Utilisez le Générateur de définitions pour construire votre définition de filtre. Dans cette construction, vous utilisez des composants, des conteneurs, des opérateurs et une logique.

Vous pouvez configurer le type et l’étendue de votre définition :

1. Pour spécifier le type de votre définition, indiquez si vous souhaitez que la version puisse inclure ou exclure la définition. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Options]** et dans la liste déroulante **[!UICONTROL Inclure]** ou **[!UICONTROL Exclure]**.
1. Pour spécifier la portée de votre définition, choisissez dans le menu déroulant **[!UICONTROL Inclure]** ou **[!UICONTROL Exclure]** si vous souhaitez que la portée de la définition soit **[!UICONTROL Événement]**, **[!UICONTROL Session]**, **[!UICONTROL Personne]**, **[!UICONTROL Compte global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics Édition B2B"}, **[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} ou **[!UICONTROL Groupe d’achat]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}

Vous pourrez toujours modifier ces paramètres ultérieurement.

### Composants

Une partie essentielle de la construction de votre définition de filtre consiste à utiliser des dimensions, des métriques, des filtres existants et des plages de dates. Tous ces composants sont disponibles à partir du panneau Composant du Générateur de filtres.

![Commencer à créer une définition](assets/start-building-filter.gif){width=100%}

Pour ajouter un composant :

1. Faites glisser et déposez un composant du panneau Composants sur **[!UICONTROL Faites glisser et déposez ici les mesures, les filtres et/ou les dimensions]**. Vous pouvez utiliser la fonction ![Rechercher](/help/assets/icons/Search.svg) dans la barre des composants pour rechercher des composants spécifiques.
1. Spécifiez les détails du composant. Par exemple, sélectionnez une valeur dans **[!UICONTROL Sélectionner la valeur]**. Ou saisissez une valeur. Le contenu et la manière dont vous pouvez spécifier une ou plusieurs valeurs dépendent du composant et de l’opérateur.
1. Modifiez éventuellement l’opérateur par défaut. Par exemple, de **[!UICONTROL égal]** à **[!UICONTROL égal à n’importe lequel]**. Voir [Opérateurs](operators.md) pour une présentation détaillée des opérateurs disponibles.

Pour modifier un composant :

* Sélectionnez un nouvel opérateur pour le composant dans le menu déroulant opérateur .
* Sélectionnez ou spécifiez une autre valeur pour l’opérateur, le cas échéant.
* Si le type de composant est une dimension, vous pouvez définir le modèle d’attribution. Voir [Modèle](#attribution-models) d’attribution pour plus d’informations.

Pour supprimer un composant :

* Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) dans un composant.

### Conteneurs

Vous pouvez regrouper plusieurs composants dans un ou plusieurs conteneurs et définir une logique au sein des conteneurs et entre eux. Les conteneurs vous permettent de créer des définitions complexes pour votre filtre.

![Ajouter un conteneur](assets/add-container.gif){Width=100%}

* Pour ajouter un conteneur, sélectionnez **[!UICONTROL Ajouter un conteneur]** dans ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Options]**.
* Pour ajouter un composant existant au conteneur, faites-le glisser dans le conteneur.
* Pour ajouter un autre composant au conteneur, faites glisser et déposez un composant du panneau de composants dans le conteneur. Utilisez la ligne d’insertion bleue comme guide.
* Pour ajouter un autre composant à l’extérieur du conteneur, faites glisser et déposez un composant à partir du panneau de composants à l’extérieur du conteneur, mais à l’intérieur du conteneur de définition principal. Utilisez la ligne d&#39;insertion bleue comme guide.
* Pour modifier la logique entre les composants d’un conteneur, entre les conteneurs ou entre un conteneur et un composant, sélectionnez les **[!UICONTROL Et]**, **[!UICONTROL Ou]**, **[!UICONTROL Alors]** appropriés. Lorsque vous sélectionnez Ensuite, vous transformez le filtre en filtre séquentiel. Voir [Créer un filtre séquentiel](seg-sequential-build.md) pour plus d’informations.
* Pour changer de niveau de conteneur, sélectionnez ![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL Compte global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Compte](/help/assets/icons/Account.svg) **[!UICONTROL Compte]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Opportunity](/help/assets/icons/Opportunity.svg)Opportunity **[!UICONTROL [!BADGE B2B edition]**, ]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}BuyingGroup![Buying Group](/help/assets/icons/BuyingGroup.svg) [!BADGE B2B edition **[!UICONTROL ,]** Page]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}Event![, ](/help/assets/icons/WebPage.svg)Visit **** ou ![User](/help/assets/icons/Visit.svg)**[!UICONTROL Person]** ![ ](/help/assets/icons/User.svg) ****.

Vous pouvez utiliser ![Paramètre](/help/assets/icons/Setting.svg) dans un conteneur pour les actions suivantes :

| Action du conteneur | Description |
|---|---|
| **[!UICONTROL Ajouter un conteneur]** | Ajoutez un conteneur imbriqué au conteneur . |
| **[!UICONTROL Exclure]** | Excluez le résultat du conteneur dans la définition du filtre. Une fine barre de gauche rouge identifie un conteneur d’exclusion. |
| **[!UICONTROL Inclure]** | Incluez le résultat du conteneur dans la définition du filtre. Inclure est la valeur par défaut. Une fine barre de gauche grise identifie un conteneur d’inclusion. |
| **[!UICONTROL Conteneur de noms]** | Renommez le conteneur à partir de sa description par défaut. Tapez un nom dans le champ de texte. Si vous ne fournissez aucune entrée, la description par défaut est utilisée. |
| **[!UICONTROL Supprimer le conteneur]** | Supprimez le conteneur de la définition . |


## Périodes

Vous pouvez créer des filtres qui contiennent des périodes flottantes. Vous pouvez ainsi répondre aux questions sur les campagnes ou les événements en cours. Par exemple, vous pouvez créer un filtre qui inclut *toute personne ayant effectué un achat en ligne au cours des 60 derniers jours*.

![Filtrer à l’aide d’une période variable](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Périodes flottantes dans les segments](https://video.tv.adobe.com/v/25403/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Empilage de filtres {#stack}

Vous pouvez créer un filtre à l’aide de filtres. Lorsque vous utilisez des filtres dans un filtre, vous pouvez l’optimiser et en réduire la complexité.

Imaginez que vous souhaitiez filtrer selon la combinaison du type d’appareil (2) et des états américains (50). Vous pouvez soit construire 100 filtres, chacun pour la combinaison unique du type d’appareil (téléphone mobile versus tablette) et de l’état américain. Pour obtenir les utilisateurs de tablettes californiennes, vous devez utiliser l’un des 100 filtres :

![Filtre simple pour autorité de certification et tablette](assets/filter-ca-tablet-single.png)

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
>title="Instance non répétée"
>abstract="Inclut des instances uniques (non répétées) pour la dimension."

<!-- markdownlint-enable MD034 -->



Lorsque vous utilisez une dimension dans le créateur de filtres, vous disposez des options permettant de spécifier le modèle d’attribution de cette dimension. Le modèle d’attribution que vous sélectionnez détermine si les données sont admissibles pour la condition que vous avez spécifiée pour le composant de dimension.

Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) dans le composant de dimension, puis sélectionnez l’un des modèles d’attribution dans la fenêtre contextuelle :

| Modèles | Description |
|---|---|
| **[!UICONTROL Modèle répété (par défaut)]** | Incluez l’instance et les valeurs persistantes pour la dimension afin de déterminer la qualification. |
| **[!UICONTROL Instance]** | Incluez uniquement des valeurs d’instance pour la dimension afin de déterminer la qualification. |
| **[!UICONTROL Instance non répétitive]** | Insérez des valeurs d’instance uniques (non répétitives) pour la dimension afin de déterminer la qualification. |


![Modèle d’attribution sur la dimension lors de la création d’un filtre](assets/filter-dimension-attribution.png)

### Exemple

Dans le cadre d’une définition de filtre, vous avez spécifié la condition suivante : Nom de page est égal à Femmes. Semblable à l’exemple ci-dessus. Vous répétez cette définition de filtre en utilisant les deux autres modèles d’attribution. Vous disposez donc de trois filtres, chacun avec son propre modèle d’attribution :

* Page Femmes - Attribution - Répétition (par défaut)
* Page Femmes - Attribution - Instance
* Page Femmes - Attribution - Instances non répétitives


Le tableau ci-dessous explique, pour chaque modèle d’attribution, quels événements entrants sont qualifiés ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) pour cette condition.


| Page Femmes - Attribution - <br/>*modèle d’attribution* | Événement 1 :<br/> nom de page est égal à<br/>femmes | Event 2:<br/>Nom de page égal <br/> Hommes | Event 3:<br/>Nom de page égal <br/> femmes | Événement 4:<br/>Nom de page égal <br/> femmes<br/>(persistant) | Événement 5:<br/>Nom de la page est égal <br/> Passage en caisse | Event 6:<br/>Nom de page égal <br/> femmes | Event 7:<br/>Page Name equals<br/>Home |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Répétitif (par défaut) | ![Cercle de coche](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![Cercle de coche](/help/assets/icons/CheckmarkCircle.svg) | ![Cercle de coche](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) |
| Instance | ![Cercle de coche](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) |
| Instance non répétée | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![Supprimer](/help/assets/icons/Remove.svg) | ![Cercle de coche](/help/assets/icons/CheckmarkCircle.svg) | ![Supprimer](/help/assets/icons/Remove.svg) |

Un exemple de rapport sur les événements utilisant les trois filtres ressemble à ceci :

![Filtrage des résultats du modèle d’attribution](assets/filter-dimension-attribution-results.png)
