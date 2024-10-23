---
title: Création d’annotations
description: Comment créer des annotations dans l’espace de travail.
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 24%

---

# Création d’annotations

Par défaut, seuls les administrateurs peuvent créer des annotations. Les utilisateurs ont les droits d’afficher les annotations, comme la manière dont les utilisateurs affichent d’autres composants (filtres, mesures calculées, etc.).

Cependant, les administrateurs peuvent accorder l’autorisation **[!UICONTROL Création d’annotations]** pour **[!UICONTROL Outils de création de rapports]** dans **[!UICONTROL Modifier les autorisations pour l’accès CJA Workspace]** aux utilisateurs via l’Admin Console. Pour plus d’informations, voir [Contrôle d’accès au niveau de l’utilisateur](/help/technotes/access-control.md#user-level-access) .

Vous pouvez créer une annotation de la manière suivante :

![Créer une annotation](assets/create-annotation.png)

* ?? Dans l’interface principale, sélectionnez **[!UICONTROL Composants]** et sélectionnez **[!UICONTROL Annotations]**. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL ****] dans le gestionnaire [[!UICONTROL Annotations]](/help/components/annotations/manage-annotations.md).
* ?? Dans un projet Workspace, dans le menu contextuel d’une visualisation, sélectionnez **[!UICONTROL Créer une annotation d’après la sélection]**.
* ?? Dans un projet Workspace, dans le menu contextuel d’un graphique linéaire, sélectionnez **[!UICONTROL Annoter la sélection]**.
* ??Dans un projet Workspace, sélectionnez **[!UICONTROL Composants]** dans le menu, puis **[!UICONTROL Créer une annotation]**.
* ?? Dans un projet Workspace, utilisez le raccourci **[!UICONTROL ctrl+maj+o]** (Windows) ou **[!UICONTROL maj+commande+o]** (macOS)

Pour définir l’annotation, utilisez le [[!UICONTROL créateur d’annotations]](#annotation-builder) :

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## Créateur d’annotations {#annotation-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_details"
>title="Détails de l’annotation"
>abstract="Les annotations vous permettent de communiquer efficacement à votre organisation les nuances et informations concernant les données contextuelles. Elles vous permettent de lier les événements du calendrier à des dimensions/mesures spécifiques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_scope"
>title="Champ d’application"
>abstract="La portée vous permet de personnaliser les données qui seront annotées. Les mesures calculées et les segments n’hériteront pas automatiquement des annotations appliquées aux composants utilisés dans leurs définitions. Vous pouvez ajouter de nouvelles mesures calculées à la section de portée d’une annotation existante. Les nouveaux segments nécessitent une nouvelle annotation."

<!-- markdownlint-enable MD034 -->


La boîte de dialogue **[!UICONTROL Créateur d’annotations]** permet de créer ou de modifier des annotations existantes. La boîte de dialogue s’intitule **[!UICONTROL Nouvelle annotation]** ou **[!UICONTROL Modifier l’annotation]** pour les annotations que vous créez ou gérez à partir du gestionnaire [[!UICONTROL Annotations]](/help/components/annotations/manage-annotations.md).


>[!BEGINTABS]

>[!TAB Créateur d’annotations]

![Fenêtre de détails des annotations présentant les champs et options décrits dans la section suivante.](assets/annotation-builder.png)

>[!TAB Créer/modifier une annotation]

![Fenêtre de détails des annotations présentant les champs et options décrits dans la section suivante.](assets/create-edit-annotation.png)

>[!ENDTABS]

1. Spécifiez les détails suivants (![Obligatoire](/help/assets/icons/Required.svg) requis) :

   | Élément | Description |
   | --- | --- |
   | **[!UICONTROL Vue de données]** | Vous pouvez sélectionner la vue de données de l’annotation. L’annotation que vous définissez est disponible sous forme d’annotation dans les projets Workspace en fonction de la vue de données sélectionnée. Cette sélection est annulée lorsque vous avez activé [!UICONTROL Appliquer à toutes les vues de données]. |
   | **[!UICONTROL Annotation réservée au projet]** | Une boîte d’informations expliquant que l’annotation que vous créez n’est visible que dans le projet Workspace sur lequel vous travaillez. Activez **[!UICONTROL Rendre cette annotation disponible pour tous vos projets]**, afin de rendre l’annotation visible pour tous vos projets. Cette zone d’informations n’est visible que lorsque vous créez une annotation à partir d’un projet Workspace. |
   | **[!UICONTROL Titre]** ![ ](/help/assets/icons/Required.svg) | Nommez l’annotation, par exemple `Needs further investigation`. |
   | **[!UICONTROL Description]** | Fournissez une description de l’annotation, par exemple, `We never expected such a fluctuation in numbers.`. |
   | **[!UICONTROL Balises]** | Organisez l’annotation en créant ou en appliquant une ou plusieurs balises. Commencez à saisir pour rechercher les balises existantes que vous pouvez sélectionner. Ou appuyez sur **[!UICONTROL Entrée]** pour ajouter une nouvelle balise. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer une balise. |
   | **[!UICONTROL Date appliquée]** ![Obligatoire](/help/assets/icons/Required.svg) | Sélectionnez la date ou la période qui doit être présente pour que l’annotation soit visible. Lorsque vous créez une annotation à l’aide du raccourci, celle-ci correspond par défaut à une période correspondant au seul jour. Lorsque vous créez une annotation à l’aide d’une sélection dans une visualisation, l’annotation utilise par défaut la période en fonction de la période du panneau auquel appartient la visualisation. |
   | **[!UICONTROL Couleur]** | Appliquez une couleur à l’annotation. L’annotation apparaît dans le projet avec la couleur sélectionnée. Vous pouvez utiliser la couleur pour classer les annotations comme les jours fériés, les événements externes, les problèmes de suivi, etc. |
   | **[!UICONTROL Portée]** | Faites glisser et déposez les mesures à partir du panneau du composant qui déclenche l’annotation. Par exemple Personnes, Sessions et Événements. Faites ensuite glisser et déposez les dimensions ou filtres du panneau du composant qui agissent comme des filtres pour déterminer s’il faut afficher ou non l’annotation. Si vous ne spécifiez pas de portée, l’annotation s’applique à toutes vos données. <br/>Vous avez deux options :<ul><li>**[!UICONTROL Toutes ces mesures sont présentes]** : faites glisser jusqu’à 10 mesures qui déclenchent l’annotation à afficher.<br/>Par exemple, la mesure Recettes a cessé de collecter des données pour une période spécifique. Faites glisser la mesure Recettes dans cette zone.</li><li>**[!UICONTROL Avec tous ces filtres]** : faites glisser jusqu’à 10 dimensions ou filtres qui filtrent si l’annotation s’affiche.</li></ul><p><p>**Remarque :** Toute annotation appliquée à un composant qui est ensuite utilisée dans le cadre d’une mesure calculée ou d’une définition de filtre n’hérite PAS automatiquement de l’annotation. La mesure calculée souhaitée doit également être ajoutée à la section de la portée pour afficher l’annotation. Toutefois, une nouvelle annotation doit être créée pour tout filtre que vous souhaitez annoter avec les mêmes informations. Par exemple, vous appliquez une annotation à [!UICONTROL Commandes] un jour spécifique. Vous pouvez ensuite utiliser [!UICONTROL Commandes] dans une mesure calculée pour la même période. La nouvelle mesure calculée n’affiche pas automatiquement l’annotation pour les commandes. Ajoutez également la mesure calculée à la section de portée pour que l’annotation s’affiche. |
   | **[!UICONTROL Appliquer à toutes les vues de données]** | Par défaut, l’annotation s’applique à la vue de données d’origine. En cochant cette case, vous pouvez faire en sorte que l’annotation s’applique à toutes les vues de données de l’entreprise. |

   {style="table-layout:auto"}

1. Sélectionner
   * **[!UICONTROL Enregistrer]** pour enregistrer l’annotation.
   * **[!UICONTROL Enregistrer sous]** pour enregistrer une copie de l’annotation.
   * **[!UICONTROL Supprimer]** pour supprimer une annotation.
   * **[!UICONTROL Annuler]** pour annuler toute modification apportée à une annotation ou annuler la création d’une nouvelle annotation.
