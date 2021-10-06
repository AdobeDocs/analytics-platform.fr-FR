---
description: Comment créer une fiche d’évaluation des tableaux de bord Adobe Analytics
title: Création d’une Fiche d’évaluation
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
source-git-commit: a9e1242a5038c57d8fd687df1ceff84a365cf141
workflow-type: tm+mt
source-wordcount: '1342'
ht-degree: 54%

---

# Création d’une Fiche d’évaluation

Les informations suivantes indiquent aux curateurs des données Adobe Analytics comment configurer et présenter des tableaux de bord pour les utilisateurs en charge de l’exécution. Pour commencer, vous pouvez visionner la vidéo Créateur de Fiche d’évaluation des tableaux de bord Adobe Analytics :

>[!VIDEO](https://video.tv.adobe.com/v/34544)

Une fiche d’évaluation Adobe Analytics affiche les visualisations de données clés pour les utilisateurs en charge de l’exécution sous la forme d’une mosaïque, comme illustré ci-dessous :

![Exemple de Fiche d’évaluation](assets/intro_scorecard.png)

En tant que curateur de cette Fiche d’évaluation, vous pouvez utiliser le Créateur de Fiche d’évaluation pour configurer les mosaïques qui apparaissent sur la Fiche d’évaluation de votre consommateur en charge de l’exécution. Vous pouvez également configurer la manière dont les vues détaillées, ou les ventilations, peuvent être ajustées une fois que les mosaïques sont activées. L’interface du Créateur de Fiche d’évaluation est illustrée ci-dessous :

![Créateur de Fiche d’évaluation](assets/scorecard_builder.png)

Pour créer la Fiche d’évaluation, procédez comme suit :

1. Accédez au modèle de [!UICONTROL Fiche d’évaluation mobile vierge].
2. Configurez la fiche d’évaluation avec des données et enregistrez-la.

## Accéder au modèle de [!UICONTROL Fiche d’évaluation mobile vierge]

Vous pouvez accéder au modèle [!UICONTROL Fiche d’évaluation mobile vierge] en créant un projet ou à partir du menu Outils.

### Créer un nouveau projet

1. Ouvrez Adobe Analytics, puis cliquez sur l’onglet **[!UICONTROL Workspace]**.
1. Cliquez sur **[!UICONTROL Créer un projet]** et sélectionnez le modèle de projet **[!UICONTROL Fiche d’évaluation mobile vierge]**.
1. Cliquez sur **[!UICONTROL Créer]**.

![Modèle de Fiche d’évaluation](assets/new_template.png)

### Menu Outils

1. Dans le menu **[!UICONTROL Outils]**, sélectionnez **[!UICONTROL Tableaux de bord Analytics (application mobile)]**.
1. Sur l’écran suivant, cliquez sur **[!UICONTROL Créer une fiche d’évaluation]**.

## Configuration de la Fiche d’évaluation avec des données et enregistrement

Pour implémenter le modèle de Fiche d’évaluation :

1. Dans **[!UICONTROL Propriétés]** (dans le rail droit), précisez la **[!UICONTROL suite de rapports du projet]** depuis laquelle vous souhaitez utiliser les données.

   ![Sélection de la suite de rapports](assets/properties_save.png)

1. Pour ajouter une nouvelle mosaïque à votre fiche d’évaluation, faites glisser une mesure depuis le panneau de gauche et déposez-la dans la zone **[!UICONTROL Glisser-déposer les mesures ici]**. Vous pouvez également insérer une mesure entre deux mosaïques en utilisant un workflow similaire.

   ![Ajouter des mosaïques](assets/build_list.png)


1. Depuis chaque mosaïque, vous pouvez accéder à une vue détaillée qui affiche des informations supplémentaires sur la mesure comme les éléments principaux pour une liste de dimensions associées.

## Ajout de dimensions ou de mesures

Pour ajouter une dimension associée à une mesure, faites glisser une dimension depuis le panneau de gauche, puis déposez-la dans une mosaïque.

Par exemple, vous pouvez ajouter des dimensions appropriées (comme **[!DNL Marketing Channel]** dans cet exemple) à la mesure **[!UICONTROL Visiteurs uniques]** en la faisant glisser sur la mosaïque. Les ventilations de Dimensions s’affichent sous la section [!UICONTROL Exploration ] (ventilation) des **[!UICONTROL Propriétés]** spécifiques à la mosaïque. Plusieurs dimensions peuvent être ajoutées à chaque mosaïque.

![Ajouter des dimensions](assets/layer_dimensions.png)

## Appliquer les segments

Pour appliquer des segments à des mosaïques individuelles, faites glisser un segment du panneau de gauche et déposez-le directement en haut de la mosaïque.

Si vous souhaitez appliquer le segment à toutes les mosaïques de la Fiche d’évaluation, déposez la mosaïque en haut de la Fiche d’évaluation. Vous pouvez également appliquer des segments en les sélectionnant dans le menu de filtre situé sous les périodes. Vous [configurez et appliquez des filtres pour vos Fiches d’évaluation](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=fr) de la même manière que dans Adobe Analytics Workspace.

![Création de segments pour le filtre](assets/segment_ui.png)

## Ajout de plages de dates

Ajoutez et supprimez des combinaisons de périodes pouvant être sélectionnées dans votre carte de performance en cliquant sur le menu déroulant des périodes.

![Nouvelle carte de performance](assets/new_score_card.png)

Chaque nouvelle carte de performance démarre avec 6 combinaisons de périodes centrées sur les données du jour et de la veille. Vous pouvez supprimer les périodes inutiles en cliquant sur le x. Vous pouvez également modifier chaque combinaison de périodes en cliquant sur le crayon.

![Nouvelle carte de performance 2](assets/new_score_card2.png)

Pour créer ou modifier une date principale, utilisez la liste déroulante pour sélectionner une période disponible ou faites glisser un composant de date depuis le rail de droite et déposez-le dans la zone de dépôt.

![Nouvelle carte de performance 3](assets/new_score_card3.png)

Pour créer une date de comparaison, vous pouvez choisir parmi des paramètres prédéfinis utiles aux comparaisons d’heures fréquentes dans le menu déroulant. Vous pouvez également glisser-déposer un composant de date à partir du rail de droite.

![Nouvelle carte de performance 4](assets/new_score_card4.png)

Si la période souhaitée n’a pas encore été créée, vous pouvez en créer une en cliquant sur l’icône de calendrier.

![Nouvelle carte de performance 5](assets/new_score_card5.png)

Vous accédez ainsi au créateur de périodes, où vous pouvez créer un composant de période avant de l’enregistrer.

## Application de visualisations

Les tableaux de bord Analytics offrent quatre visualisations qui vous donnent un aperçu complet des éléments de dimension et des mesures. Changez de visualisation en modifiant le [!UICONTROL type de graphique] des [!UICONTROL Propriétés] d’une mosaïque. Sélectionnez simplement la mosaïque de droite, puis modifiez le type de graphique.

![Propriétés de la mosaïque](assets/properties.png)

Ou cliquez sur l’icône [!UICONTROL Visualisations] dans le rail de gauche et faites glisser la visualisation de droite sur la mosaïque :

![Visualisations](assets/vizs.png)

### [!UICONTROL Numéro de résumé]

Utilisez la visualisation Synthèse des chiffres pour mettre en évidence un grand nombre d’éléments importants dans un projet.

![Numéro de résumé](assets/sparkline.png)

### [!UICONTROL Anneau]

Semblable à un graphique circulaire, cette visualisation présente les données comme des portions ou des segments d’un tout. Utilisez un graphique en anneau pour comparer des pourcentages d’un total. Supposons, par exemple, que vous souhaitiez identifier la plateforme publicitaire qui a contribué au nombre total de visiteurs uniques :

![Visualisation en anneau](assets/donut-viz.png)

### [!UICONTROL Ligne]

Dans la visualisation en ligne, les mesures sont représentées sous la forme d’une ligne afin d’indiquer l’évolution des valeurs dans le temps. Un graphique en courbes affiche les dimensions au fil du temps, mais fonctionne avec n’importe quelle visualisation. Dans cet exemple, vous visualisez la dimension de catégorie de produits.

![Visualisation en ligne](assets/line.png)

### [!UICONTROL Barre horizontale]

Dans cette visualisation, des barres horizontales représentent plusieurs valeurs pour une ou plusieurs mesures. Par exemple, pour voir facilement quels sont vos principaux produits, utilisez [!UICONTROL Barre horizontale] pour la visualisation de votre choix.

![barre horizontale](assets/horizontal.png)

### Supprimer l’élément de dimension [!UICONTROL Non spécifié]

Si vous souhaitez supprimer des éléments de dimension [!UICONTROL Non spécifiés] de vos données, procédez comme suit :

1. Sélectionnez la mosaïque appropriée.
1. Dans le rail de droite, sous **[!UICONTROL Exploration]**, sélectionnez la flèche vers la droite en regard de l’élément de dimension dont vous souhaitez supprimer les éléments **[!UICONTROL Non spécifié]**.

   ![non spécifié](assets/unspecified.png)

1. Cliquez sur l’icône en regard de **[!UICONTROL Non spécifié]** pour supprimer les données non spécifiées de vos rapports. (Vous pouvez également supprimer tout autre élément de dimension.)

## Affichage et configuration des propriétés de mosaïque

Lorsque vous cliquez sur une mosaïque dans le créateur de Fiche d’évaluation, le rail de droite affiche les propriétés et les caractéristiques associées à cette mosaïque. Depuis ce rail, vous pouvez renseigner un nouveau **[!UICONTROL Titre]** pour la mosaïque ou configurer la mosaïque en précisant des composants au lieu de les faire glisser et de les déposer depuis le rail de gauche.

![Volet Propriétés](assets/properties_tile.png)

## Afficher les analyses (ventilations)

Lorsque vous cliquez sur des mosaïques, une fenêtre contextuelle dynamique s’affiche pour l’utilisateur en charge de l’exécution dans l’application avec la vue Exploration (ventilation). Si aucune dimension n’a été appliquée à la mosaïque, la dimension de ventilation sera **heure** ou **jours**, en fonction de la période par défaut.

Les ventilations affinent votre analyse en ventilant littéralement les mesures et les dimensions selon d’autres mesures et dimensions, comme dans cet exemple de vente au détail :

* Mesure Visiteurs uniques ventilée par plateforme d’annonces publicitaires (AMO ID)
* Visites ventilées par catégorie de produit (vente au détail)
* Recettes totales ventilées par nom de produit

![Breakdown_view](assets/break_view.png)

Chaque dimension ajoutée à la mosaïque apparaît dans une liste déroulante dans la vue détaillée de l’application. L’utilisateur en charge de l’exécution peut alors choisir parmi les options répertoriées dans la liste déroulante.

## Suppression de composants

De même, si vous souhaitez supprimer un composant appliqué à la totalité de la carte de performance, cliquez n’importe où sur celle-ci en dehors des mosaïques, puis supprimez le composant en cliquant sur le **x** qui apparaît lorsque vous placez le pointeur de la souris au-dessus de lui, comme indiqué ci-dessous pour le segment **Premières visites** :

![Remove_components](assets/new_remove.png)

## Nommer une fiche d’évaluation

Pour nommer la Fiche d’évaluation, cliquez sur l’espace de noms en haut à gauche de l’écran, puis saisissez le nouveau nom.

![Naming_Scorecards](assets/new_name.png)

## Partage d’une fiche d’évaluation

Pour partager la Fiche d’évaluation avec un utilisateur en charge de l’exécution :

1. Cliquez sur le menu **[!UICONTROL Partager]**, puis sélectionnez **[!UICONTROL Partager la fiche d’évaluation]**.

1. Dans le formulaire **[!UICONTROL Partager la fiche d’évaluation mobile]**, complétez les champs en :

   * indiquant le nom de la fiche d’évaluation ;
   * Fournir une description de la fiche d’évaluation
   * ajoutant des balises pertinentes ;
   * Spécification des destinataires pour la fiche d’évaluation

1. Cliquez sur **[!UICONTROL Partager]**.

![Share_Scorecards](assets/new_share.png)

Une fois que vous avez partagé une fiche d’évaluation, vos destinataires peuvent y accéder dans leurs tableaux de bord Analytics. Si vous apportez des modifications ultérieures à la Fiche d’évaluation dans le Créateur de Fiche d’évaluation, elles seront automatiquement mises à jour dans la Fiche d’évaluation partagée. Les utilisateurs en charge de l’exécution pourront accéder aux changements en actualisant la Fiche d’évaluation sur leur application.

Si vous mettez à jour la Fiche d’évaluation en ajoutant de nouveaux composants, vous pouvez vouloir partager à nouveau la Fiche d’évaluation (et cocher l’option **[!UICONTROL Partager les composants incorporés]** ) afin de vous assurer que vos utilisateurs en charge de l’exécution ont accès à ces modifications.
