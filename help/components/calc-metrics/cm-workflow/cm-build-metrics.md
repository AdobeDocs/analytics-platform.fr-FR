---
description: Le créateur de mesures calculées fournit un canevas où faire glisser et déposer des dimensions, des mesures, des filtres et des fonctions permettant de créer des mesures personnalisées en fonction de la logique de hiérarchie des conteneurs, des règles et des opérateurs. Grâce à cet outil de développement intégré, vous pouvez créer et enregistrer des mesures calculées simples ou des mesures calculées avancées complexes.
title: Création de mesures calculées
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: 37209097327ffb142068b5df184c07c7c8021442
workflow-type: tm+mt
source-wordcount: '1526'
ht-degree: 10%

---

# Création de mesures calculées {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_productcompatibility"
>title="Compatibilité des produits"
>abstract="Indique l’endroit où cette mesure calculée peut être utilisée dans Customer Journey Analytics, par exemple dans Analysis Workspace, Report Builder, etc. Certaines mesures calculées ne peuvent pas être utilisées avec l’expérimentation."
>additional-url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="Utiliser les mesures calculées dans l’expérimentation"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_externalid"
>title="ID externe"
>abstract="La modification de l’ID externe peut avoir une incidence sur la manière dont la mesure calculée apparaît dans des sources externes, telles que les outils de Business Intelligence."

<!-- markdownlint-enable MD034 -->


La boîte de dialogue **[!UICONTROL Créateur de mesures calculées]** permet de créer ou de modifier des mesures calculées existantes. La boîte de dialogue s’intitule **[!UICONTROL Nouvelle mesure calculée]** ou **[!UICONTROL Modifier la mesure calculée]** pour les mesures que vous créez ou gérez à partir du [[!UICONTROL  gestionnaire de mesures calculées]](/help/components/calc-metrics/cm-workflow/cm-manager.md).

>[!BEGINTABS]

>[!TAB Créateur de mesures calculées]

![Fenêtre de détails des mesures calculées présentant les champs et options décrits dans la section suivante.](assets/calculated-metric-builder.png)

>[!TAB Créer ou modifier une mesure calculée]

![Fenêtre de détails des mesures calculées présentant les champs et options décrits dans la section suivante.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. Spécifiez les détails suivants (![Obligatoire](/help/assets/icons/Required.svg) requis) :

   | Élément | Description |
   | --- | --- |
   | **[!UICONTROL Vue de données]** | Vous pouvez sélectionner la vue de données pour la mesure calculée.  La mesure calculée que vous définissez est disponible dans les projets Workspace en fonction de la vue de données sélectionnée. |
   | **[!UICONTROL Mesure Projet uniquement]** | Une boîte d’informations pour expliquer que la mesure n’est visible que dans le projet où elle est créée et que la mesure ne sera pas ajoutée à votre liste de composants. Activez **[!UICONTROL Rendez cette mesure disponible pour tous vos projets et ajoutez-la à votre liste de composants]** pour modifier ce paramètre. Cette zone d’informations n’est visible que lorsque vous créez une mesure dans Workspace à l’aide de la fonction **[!UICONTROL Créer une mesure d’après la sélection]** et que vous avez sélectionné une fonction (telle que **[!UICONTROL Moyenne]** ou **[!UICONTROL Médiane]**). Ensuite, utilisez les [informations sur les composants](/help/components/use-components-in-workspace.md#component-info) pour modifier cette mesure créée. |
   | **[!UICONTROL Titre]** ![ ](/help/assets/icons/Required.svg) | Nommez la mesure calculée, par exemple `Conversion Rate`. |
   | **[!UICONTROL ID externe]** ![ ](/help/assets/icons/Required.svg) | Nom de la mesure calculée lors de l’utilisation d’un outil de BI externe et de l’extension de BI. La valeur est automatiquement définie comme `undefined_xxx`, sauf si vous remplacez la valeur. |
   | **[!UICONTROL Description]** | Fournissez une description du filtre, par exemple, `Calculated metric to define the conversion rate.` Il n’est pas nécessaire de décrire la formule de la mesure calculée, car la formule est déjà automatiquement disponible dans [!UICONTROL Résumé]. |
   | **[!UICONTROL Format]** | Sélectionnez un format pour la mesure calculée : vous pouvez choisir entre **[!UICONTROL Décimale]**, **[!UICONTROL Durée]**, **[!UICONTROL Pourcentage]** et **[!UICONTROL Devise]**. |
   | **[!UICONTROL Nombre de décimales]** | Indiquez le nombre de décimales pour le format sélectionné. activée uniquement lorsque le format sélectionné est Décimal, Devise et Pourcentage. |
   | **[!UICONTROL Afficher la tendance à la hausse sous forme de]** | Indiquez si une tendance à la hausse de la mesure calculée s’affiche comme ▲ **[!UICONTROL Bon (Vert)]** ou ▼ **[!UICONTROL Mauvais (Rouge)]**. |
   | **[!UICONTROL Devise]** | Spécifiez la devise de la mesure calculée. Uniquement activée lorsque le format sélectionné est Devise. |
   | **[!UICONTROL Balises]** | Organisez la mesure calculée en créant ou en appliquant une ou plusieurs balises. Commencez à saisir pour rechercher les balises existantes que vous pouvez sélectionner. Ou appuyez sur **[!UICONTROL ENTER]** pour ajouter une nouvelle balise. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer une balise. |
   | **[!UICONTROL Aperçu]** | L’aperçu couvre les 90 derniers jours et permet d’évaluer si vous avez correctement défini votre mesure. |
   | **[!UICONTROL Résumé]** | Affiche un résumé de la définition de la mesure calculée. <br/>Par Exemple : ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Total Commandes]** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]**. |
   | **[!UICONTROL Définition]** ![Obligatoire](/help/assets/icons/Required.svg) | Définissez votre filtre à l’aide du [Créateur de définitions](#definition-builder). |

1. Pour vérifier si la définition de la mesure calculée est correcte, utilisez l’ **[!UICONTROL Aperçu]** constamment mis à jour des résultats de la mesure calculée. L’ **[!UICONTROL aperçu]** couvre les 90 derniers jours et évalue continuellement la définition de votre mesure calculée.

   La **** indique si la mesure calculée peut être utilisée dans l’expérimentation. Les valeurs possibles sont les suivantes :
   * **[!UICONTROL Partout en Customer Journey Analytics]** : la mesure calculée peut être utilisée dans tous les Customer Journey Analytics.
   * **[!UICONTROL Partout en Customer Journey Analytics (hors expérimentation)]** : la mesure calculée peut être utilisée dans tous les Customer Journey Analytics, à l’exception du panneau Expérience.

1. Sélectionnez :
   * **[!UICONTROL Enregistrer]** pour enregistrer la mesure calculée.
   * **[!UICONTROL Enregistrer sous]** pour enregistrer une copie de la mesure calculée.
   * **[!UICONTROL Annuler]** pour annuler toute modification apportée à la mesure calculée ou annuler la création d’une nouvelle mesure calculée.


## Créateur de définitions

Le créateur de définitions vous permet de faire glisser et de déposer des dimensions, des mesures, des filtres et des fonctions afin de créer des mesures personnalisées en fonction d’opérateurs, de règles et d’une logique de hiérarchie de conteneurs. Dans cette construction, vous pouvez utiliser des mesures standard, des mesures définies par Adobe, des mesures calculées, des filtres, des dimensions et des fonctions. Tous ces composants sont disponibles à partir du panneau des composants dans le créateur de mesures calculées. De plus, vous pouvez utiliser des opérateurs et des conteneurs dans la définition.

![Créer une mesure calculée](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

Seules les mesures sont définies en tant que composants uniques dans la zone **[!UICONTROL Définition]**. Tous les autres composants sont définis sous la forme d’un conteneur, de mesures d’encapsulation ou d’autres conteneurs. Voir [Conteneurs](#containers) pour plus d’informations.

### Mesures

Pour ajouter une mesure :

* Faites glisser et déposez un composant ![Événements](/help/assets/icons/Event.svg) **** du panneau Composants sur **[!UICONTROL Faites glisser et déposez des mesures, des dimensions, des éléments de dimension, des filtres et/ou des fonctions ici]**. Vous pouvez utiliser la ![recherche](/help/assets/icons/Search.svg) dans la barre de composants pour rechercher des composants spécifiques.

Lorsque vous utilisez une mesure calculée dans le cadre de votre définition, la mesure calculée est développée.

Pour modifier une mesure :

1. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) dans un composant de mesure dans la zone **[!UICONTROL Définition]**.
1. Dans la boîte de dialogue contextuelle, vous pouvez définir le type de mesure et un modèle d’attribution. Voir [Type de mesure et Attribution](m-metric-type-alloc.md).

Pour supprimer une mesure :

* Sélectionnez ![Fermer](/help/assets/icons/Close.svg) dans la mesure.

### Opérateurs

Les opérateurs permettent de définir l&#39;opérateur entre les composants ou les conteneurs. Les opérateurs apparaissent automatiquement entre les

* deux mesures ou plus dans un conteneur,
* deux ou plusieurs conteneurs dans un conteneur,
* une ou plusieurs mesures et un ou plusieurs conteneurs dans un conteneur.

Vous pouvez sélectionner :

| Symbole | Opérateur |
|:---:|---|
| ![Diviser](/help/assets/icons/Divide.svg) | Diviser (par défaut) |
| ![Fermer](/help/assets/icons/Close.svg) | Multiplication |
| ![Supprimer](/help/assets/icons/Remove.svg) | Soustraction |
| ![Ajouter](/help/assets/icons/Add.svg) | Ajouter |

### Nombre statique

Vous pouvez ajouter un nombre statique à votre définition de mesure calculée. Pour ajouter un nombre statique :

* Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** depuis un conteneur.
* Sélectionnez **[!UICONTROL Numéro statique]**. Un conteneur de nombres statiques s’affiche.
* Sélectionnez [!UICONTROL *Cliquez pour ajouter une valeur*] et saisissez une valeur.


### Conteneurs

Vous ajoutez des dimensions, des filtres et des fonctions en tant que conteneurs à une définition de mesure calculée. Vous pouvez également ajouter un conteneur générique. Les conteneurs fonctionnent comme une expression mathématique et déterminent la séquence des opérations. Tout ce qui se trouve dans un conteneur est traité avant le composant ou conteneur suivant.


#### Conteneur de filtres

Vous utilisez le concept de conteneur de filtres pour créer une [mesure filtrée](metrics-with-segments.md). Vous pouvez construire un conteneur de filtres à l’aide d’un filtre ou en utilisant un filtre que vous créez à partir d’une dimension.

* Pour ajouter un conteneur de filtres à partir d’une dimension :

   1. Faites glisser et déposez un composant ![Dimensions](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimensions]** du panneau Composants sur **[!UICONTROL Faites glisser et déposez des mesures, des dimensions, des éléments de dimension, des filtres et/ou des fonctions ici]**. Vous pouvez utiliser la ![recherche](/help/assets/icons/Search.svg) dans la barre de composants pour rechercher des composants spécifiques.
   1. Dans la fenêtre contextuelle **[!UICONTROL Créer un filtre à partir de la Dimension]**, définissez la condition du filtre. Sélectionnez dans la liste des opérateurs une valeur ou saisissez une valeur. Par exemple, **[!UICONTROL Month]** **[!UICONTROL est égal à]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`.
   1. Sélectionnez **[!UICONTROL Done]**. Un conteneur de filtres est ajouté à la **[!UICONTROL définition]**.


* Pour ajouter un conteneur de filtres à partir d’un filtre, vous pouvez utiliser :

   * Faites glisser et déposez un composant ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtres]** du panneau Composants sur **[!UICONTROL Faites glisser et déposez des mesures, des dimensions, des éléments de dimension, des filtres et/ou des fonctions ici]**. Vous pouvez utiliser la ![recherche](/help/assets/icons/Search.svg) dans la barre de composants pour rechercher des filtres spécifiques.
Un conteneur de filtre est automatiquement ajouté à la **[!UICONTROL définition]** à l’aide du nom du filtre.

   * Faites glisser et déposez un composant ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtres]** du panneau Composants sur un conteneur générique. Le conteneur est modifié en conteneur de filtre.

   * Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** depuis un conteneur :

      1. Sélectionnez **[!UICONTROL Filter]**. Un conteneur de filtres est ajouté à la **[!UICONTROL définition]**.
      1. Dans le nouveau conteneur de filtres, sélectionnez un filtre dans le menu déroulant [!UICONTROL *Sélectionner...*] .

  >[!TIP]
  >
  >Vous pouvez ajouter plusieurs filtres à un conteneur.

  Les filtres du conteneur sont nommés d’après le composant de filtre. Par exemple, ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL sessions web]**. Sélectionnez ![InfoOutline](/help/assets/icons/InfoOutline.svg) pour afficher une fenêtre contextuelle contenant des détails sur le filtre. Dans la fenêtre contextuelle, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) pour modifier la définition de filtre.

Pour supprimer un filtre d’un conteneur :

* Sélectionnez ![Fermer](/help/assets/icons/Close.svg) en regard du nom du filtre.

Pour plus d’informations et d’exemples, voir [Mesures filtrées](metrics-with-segments.md) .

#### Conteneur de fonctions

Pour ajouter un conteneur de fonctions, vous pouvez utiliser :

* Effectuez un glisser-déposer :

   1. Faites glisser et déposez un composant ![Fonction](/help/assets/icons/Effect.svg) **** du panneau Composants sur **[!UICONTROL Faites glisser et déposez des mesures, des dimensions, des éléments de dimension, des filtres et/ou des fonctions ici]**. Vous pouvez utiliser la ![recherche](/help/assets/icons/Search.svg) dans la barre de composants pour rechercher des fonctions spécifiques.
   1. Un conteneur de fonctions est automatiquement ajouté à la **[!UICONTROL Définition]** à l’aide du nom de la fonction .

* Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** depuis un conteneur :

   1. Sélectionnez **[!UICONTROL Fonction]**.
   1. Dans le conteneur, sélectionnez une fonction dans le menu déroulant [!UICONTROL *Sélectionner...*] .

Le conteneur de fonctions est nommé d’après le composant de fonction . Par exemple, ![Fonction](/help/assets/icons/Effect.svg) **[!UICONTROL RACINE CARRÉ (mesure)]**. Sélectionnez ![InfoOutline](/help/assets/icons/InfoOutline.svg) pour afficher une fenêtre contextuelle contenant des détails sur la fonction. Sélectionnez **[!UICONTROL En savoir plus]** pour plus d’informations sur la fonction.

Voir [Utilisation des fonctions](cm-using-functions.md) pour plus d’informations sur l’utilisation des fonctions et sur les fonctions disponibles pour créer une mesure calculée.


#### Conteneur générique

Pour ajouter un conteneur générique :

* Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** depuis un conteneur
* Sélectionnez **[!UICONTROL Conteneur]**. Un nouveau conteneur générique vide est ajouté à la **[!UICONTROL Définition]**. Vous pouvez utiliser un conteneur générique pour imbriquer ou créer une hiérarchie dans la définition de votre mesure calculée.


#### Suppression d’un conteneur

Pour supprimer un conteneur, sélectionnez ![Fermer](/help/assets/icons/Close.svg) au niveau du conteneur.

>[!MORELIKETHIS]
>
>[Utilisation des fonctions](cm-using-functions.md)
>[Filtres](/help/components/filters/filters-overview.md)
>

