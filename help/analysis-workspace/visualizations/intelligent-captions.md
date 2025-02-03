---
description: Utilisez des légendes intelligentes pour générer des informations en langage naturel afin de faire apparaître les tendances dans les visualisations.
title: Légendes intelligentes
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 4d566411778774d21be04c4f3d6cf2ffabed6db2
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 19%

---

# Légendes intelligentes {#intelligent-captions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_area"
>title="Légendes intelligentes : zone"
>abstract="Générez des informations en langage naturel pour faciliter la compréhension et l’interprétation des données pour cette visualisation."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_bar"
>title="Légendes intelligentes : barre"
>abstract="Générez des informations en langage naturel pour faciliter la compréhension et l’interprétation des données pour cette visualisation."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_donut"
>title="Légendes intelligentes : anneau"
>abstract="Générez des informations en langage naturel pour faciliter la compréhension et l’interprétation des données pour cette visualisation."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_horizontalbar"
>title="Légendes intelligentes : barre horizontale"
>abstract="Générez des informations en langage naturel pour faciliter la compréhension et l’interprétation des données pour cette visualisation."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_line"
>title="Légendes intelligentes : ligne"
>abstract="Générez des informations en langage naturel pour faciliter la compréhension et l’interprétation des données pour cette visualisation."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_fallout"
>title="Légendes intelligentes : abandons"
>abstract="Générez des informations en langage naturel pour faciliter la compréhension et l’interprétation des données pour cette visualisation."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_flow"
>title="Légendes intelligentes : flux"
>abstract="Générez des informations en langage naturel pour faciliter la compréhension et l’interprétation des données pour cette visualisation."

<!-- markdownlint-enable MD034 -->

La fonctionnalité de légendes intelligentes utilise l’IA générative avancée pour fournir des informations essentielles sur les visualisations Workspace les plus utilisées en langage naturel.

Les sous-titres intelligents sont conçus pour :

* Les analystes, qui ont besoin de récits à partager avec d&#39;autres utilisateurs. Les analystes ont besoin de ces informations pour pouvoir fournir un contexte à leurs utilisateurs.
* Les utilisateurs professionnels, qui souhaitent découvrir rapidement des points à retenir de haut niveau.

>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Légendes intelligentes](https://video.tv.adobe.com/v/3420131/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Lancer les légendes intelligentes {#launch}

Pour lancer des légendes intelligentes générées automatiquement pour une visualisation, sélectionnez ![ Légendes intelligentes ](/help/assets/icons/AI.svg) en haut à droite de la visualisation. Cette sélection génère des informations en langage naturel.

![Lancez la fenêtre Analyse qui affiche les légendes intelligentes pour la tendance des consultations de produits. ](assets/intelligent-captions.gif)


Gardez les éléments suivants à l’esprit :

* Vous avez besoin d’au moins 3 points de données pour générer des sous-titres avec succès. Dans le cas contraire, vous pourriez obtenir une erreur telle que **[!UICONTROL Pas assez de données à analyser]**.

* Les légendes sont générées chaque fois que les données sélectionnées sous-jacentes sont modifiées dans le tableau qui alimente la visualisation.

* S’il existe plusieurs mesures dans un tableau à structure libre associé, les légendes ne sont générées que pour la première mesure ou la mesure actuellement sélectionnée par l’utilisateur ou l’utilisatrice. Cependant, des légendes peuvent être générées pour plusieurs mesures dans les visualisations en ligne et en zone.

* Si vous enregistrez le projet à un moment donné et que vous le rechargez ultérieurement, les sous-titres sont automatiquement mis à jour avec les nouvelles données. Il en va de même pour les projets planifiés et les fichiers de PDF exportés à partir d’un projet.


## Visualisations {#visualizations}

Les légendes intelligentes sont prises en charge sur les visualisations suivantes :

* [Ligne](line.md) (y compris multiligne)
* [Barre](bar.md)
* [Barre horizontale](horizontal-bar.md)
* [Surface](area.md) (y compris les lignes de surface multiples)
* [Anneau](donut.md)
* [Abandon](fallout/fallout-flow.md)
* [Flux](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## Actions

Vous pouvez effectuer les actions suivantes sur les légendes intelligentes :

### Copier dans le presse-papiers {#copy}

Vous pouvez copier les légendes dans un presse-papiers et les coller dans un fichier PowerPoint ou dans d’autres outils. Vous pouvez copier des sous-titres individuels dans la vue un par un ou copier toutes les sous-titres à la fois dans la vue de sous-titres développée.

* Pour copier les légendes, sélectionnez ![Copier les légendes dans le presse-papiers](/help/assets/icons/Copy.svg) en haut à droite de la boîte de dialogue des légendes.

### Afficher toutes les légendes intelligentes ou des légendes individuelles  {#show-all-or-individual}

Vous pouvez afficher toutes les légendes intelligentes à la fois dans une vue développée ou afficher des légendes intelligentes individuelles dans une vue détaillée.

* Pour afficher toutes les légendes intelligentes, sélectionnez ![ Afficher toutes les légendes intelligentes ](/help/assets/icons/Maximize.svg).
* Pour afficher individuellement les légendes intelligentes, sélectionnez ![Afficher les légendes intelligentes individuelles](/help/assets/icons/Minimize.svg).

### Modifier l’affichage {#edit}

Vous pouvez modifier l’affichage des légendes, par exemple en masquant ou en affichant une catégorie particulière d’informations.

1. Sélectionnez ![Modifier la visibilité des légendes intelligentes](/help/assets/icons/EditInLight.svg) dans la boîte de dialogue Légendes intelligentes .

1. Basculez entre ![Activer/désactiver la visibilité](/help/assets/icons/Visibility.svg) pour afficher une information spécifique (comme **[!UICONTROL Min]**) ou ![Activer/désactiver la visibilité](/help/assets/icons/VisibilityOff.svg) pour masquer une information spécifique (comme **[!UICONTROL Pic]**).

   ![Modifier les légendes intelligentes](assets/edit-intelligent-captions.png)

1. Sélectionnez **[!UICONTROL Appliquer]**.


### Fournir des commentaires

Vous pouvez commenter les légendes intelligentes générées (les commentaires ne peuvent être fournis que dans la vue de légende développée).

1. Sélectionnez ![Autres actions](/help/assets/icons/More.svg) dans la boîte de dialogue Légendes intelligentes .

1. Sélectionnez ![Bonne réponse](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL Bonne réponse]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL Mauvaise réponse]** ou ![Indicateur](/help/assets/icons/Flag.svg) **[!UICONTROL Report]**.

1. Dans la boîte de dialogue **[!UICONTROL Merci pour vos commentaires]**, saisissez vos commentaires et sélectionnez **[!UICONTROL Envoyer]** pour envoyer les commentaires.

### Exporter {#export}

Vous pouvez exporter des légendes intelligentes dans le cadre d’un PDF, à condition que le projet soit enregistré avec les légendes intelligentes générées.

### Basculer vers désactivé {#toggle}

Si vous préférez ne pas afficher de légendes intelligentes, vous pouvez désactiver la fonction.

1. Accédez à [Préférences de visualisation](/help/analysis-workspace/user-preferences.md#visualizations-preferences).
1. Décochez **[!UICONTROL Afficher les légendes intelligentes]**.

   ![Options de visualisation en ligne présentant l’option permettant de désélectionner Afficher les légendes intelligentes.](assets/toggle-captions.png)

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer la préférence.


## Légendes intelligentes dans les cartes de performance mobiles

Les légendes intelligentes sont également disponibles dans le Customer Journey Analytics [cartes de performance mobiles](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions).

## Accès aux fonctionnalités

Les paramètres suivants régissent l’accès aux légendes intelligentes :

* **Accès à la solution** : la fonctionnalité de légendes intelligentes est disponible dans Customer Journey Analytics, mais pas dans Adobe Analytics.

* **Accès contractuel** : si vous ne pouvez pas utiliser de légendes intelligentes, contactez l’administrateur ou l’administratrice de votre entreprise ou le représentant ou la représentante de compte d’Adobe (Admin). Avant de pouvoir utiliser des légendes intelligentes dans votre organisation, vous devez accepter certains termes juridiques liés à Generative AI.

* **Autorisations** : dans [!UICONTROL Adobe Admin Console], l’autorisation [!UICONTROL Outils de création de rapports] **[!UICONTROL Légendes intelligentes]** détermine l’accès. Un [administrateur de profil de produit](https://helpx.adobe.com/fr/enterprise/using/manage-product-profiles.html) doit suivre les étapes suivantes dans l’Admin Console  :
   1. Accédez à **[!UICONTROL Admin Console]** > **[!UICONTROL Produits et services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Profils de produit]**.
   1. Sélectionnez le titre du profil de produit pour lequel vous souhaitez fournir un accès aux sous-titres intelligents.
   1. Dans le profil de produit spécifique, sélectionnez **[!UICONTROL Autorisations]**.
   1. Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) pour modifier **[!UICONTROL Outils de reporting]**.
   1. Sélectionnez ![AjouterCercle](/help/assets/icons/AddCircle.svg) pour ajouter **Légendes intelligentes** aux **[!UICONTROL Éléments d’autorisation inclus]**.

      ![Ajouter une autorisation](./assets/intelligent-captions-permissions.png)

   1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les autorisations.

Voir [Contrôle d’accès](/help/technotes/access-control.md#access-control) pour plus d’informations.
