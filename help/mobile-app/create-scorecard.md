---
description: Méthode de création dʼune carte de performance pour les tableaux de bord Adobe Analytics
title: Création dʼune carte de performance
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
solution: Customer Journey Analytics
source-git-commit: e2a79bc9d39d1c7758c1ff61c5de5af31c92d34c
workflow-type: tm+mt
source-wordcount: '1769'
ht-degree: 71%

---

# Créer une carte de performance mobile

Les informations suivantes indiquent aux curateurs des données Adobe Analytics comment configurer et présenter des tableaux de bord pour les utilisateurs en charge de l’exécution. Regardez dʼabord la vidéo sur le Créateur de cartes de performance pour les tableaux de bord Adobe Analytics :

>[!VIDEO](https://video.tv.adobe.com/v/343458)

>[!NOTE]
>Les captures d’écran de la carte de performance pour cette page ont été effectuées à partir de l’interface utilisateur d’Adobe Analytics, et non de CJA. Les interfaces utilisateur sont presque identiques.

Une carte de performance Adobe Analytics affiche les visualisations de données principales pour les utilisateurs en charge de lʼexécution sous la forme dʼune disposition en mosaïques, comme indiqué ci-dessous :

![Exemple de Fiche d’évaluation](assets/intro_scorecard.png)

En tant que curateur de cette carte de performance, vous pouvez utiliser le Créateur de cartes de performance pour configurer les mosaïques qui apparaissent sur la carte de performance de votre consommateur en charge de lʼexécution. Vous pouvez également configurer la manière dont lʼaffichage des détails ou les ventilations sʼajustent lorsque lʼutilisateur appuie sur les mosaïques. L’interface du Créateur de Fiche d’évaluation est illustrée ci-dessous :

![Créateur de Fiche d’évaluation](assets/scorecard_builder.png)

Pour créer la Carte de performance, procédez comme suit :

1. Accédez au modèle de [!UICONTROL Fiche d’évaluation mobile vierge].
2. Configurer la carte de performance avec des données, puis enregistrez-la.

## Accéder au modèle de [!UICONTROL Fiche d’évaluation mobile vierge] {#template}

Vous pouvez accéder au modèle de [!UICONTROL Carte de performance mobile vierge] en créant un projet ou à partir du menu Outils.

### Créer un nouveau projet {#create}

1. Ouvrez Adobe Analytics, puis cliquez sur l’onglet **[!UICONTROL Espace de travail]**.
1. Cliquez sur **[!UICONTROL Créer un projet]**, puis sélectionnez le modèle de projet **[!UICONTROL Carte de performance mobile vierge]**.
1. Cliquez sur **[!UICONTROL Créer]**.

![Modèle de Fiche d’évaluation](assets/new_template.png)

### Menu Outils

1. Dans le menu **[!UICONTROL Outils]**, sélectionnez **[!UICONTROL Tableaux de bord Analytics (application mobile)]**.
1. Sur lʼécran suivant, cliquez sur **[!UICONTROL Créer une carte de performance]**.

## Configurez la carte de performance avec des données, puis enregistrez-la. {#configure}

Pour implémenter le modèle de Fiche d’évaluation :

1. Dans **[!UICONTROL Propriétés]** (dans le rail droit), précisez la **[!UICONTROL suite de rapports du projet]** depuis laquelle vous souhaitez utiliser les données. Les suites de rapports sont des vues de données dans CJA.

   ![Sélection de la suite de rapports](assets/properties_save.png)

1. Pour ajouter une nouvelle mosaïque à votre fiche d’évaluation, faites glisser une mesure depuis le panneau de gauche et déposez-la dans la zone **[!UICONTROL Glisser-déposer les mesures ici]**. Vous pouvez également insérer une mesure entre deux mosaïques en utilisant un workflow similaire.

   ![Ajouter des mosaïques](assets/build_list.png)


1. Depuis chaque mosaïque, vous pouvez accéder à une vue détaillée qui affiche des informations supplémentaires sur la mesure comme les éléments principaux pour une liste de dimensions associées.

## Ajout de dimensions ou de mesures {#dimsmetrics}

Pour ajouter une dimension associée à une mesure, faites glisser une dimension depuis le panneau de gauche, puis déposez-la dans une mosaïque.

Par exemple, vous pouvez ajouter des dimensions appropriées (comme **[!DNL Marketing Channel]** dans cet exemple) à la mesure **[!UICONTROL Visiteurs uniques]** en effectuant une opération de glisser-déposer sur la mosaïque. Les ventilations de dimensions sʼaffichent sous la section [!UICONTROL Ventilation] des **[!UICONTROL Propriétés]** propres à la mosaïque. Plusieurs dimensions peuvent être ajoutées à chaque mosaïque.

![Ajouter des dimensions](assets/layer_dimensions.png)

## Filtres appliqués {#filters}

Pour appliquer des filtres à des mosaïques individuelles, faites glisser un filtre (les segments sont des filtres dans CJA) à partir du panneau de gauche et déposez-le directement au-dessus de la mosaïque.

Si vous souhaitez appliquer le filtre à toutes les mosaïques de la carte de performance, déposez la mosaïque en haut de cette dernière. Vous pouvez également appliquer des filtres en les sélectionnant dans le menu de filtre situé sous les périodes. Vous [configurez et appliquez des filtres pour vos Fiches d’évaluation](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=fr) de la même manière que dans Adobe Analytics Workspace.

![Création de filtres](assets/segment_ui.png)

## Ajout de périodes {#dates}

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

## Application de visualisations {#viz}

Les tableaux de bord Analytics offrent quatre visualisations qui vous donnent un aperçu complet des éléments de dimension et des mesures. Appliquez une visualisation différente en modifiant le [!UICONTROL type de graphique] des [!UICONTROL propriétés] d’une mosaïque. Sélectionnez simplement la mosaïque de droite, puis modifiez le type de graphique.

![Propriétés de la mosaïque](assets/properties.png)

Ou cliquez sur l’icône [!UICONTROL Visualisations] dans le rail de gauche, puis glissez-déposez la visualisation de droite sur la mosaïque :

![Visualisations](assets/vizs.png)

### [!UICONTROL Numéro du résumé]

Utilisez la visualisation Synthèse des chiffres pour mettre en évidence un grand nombre d’éléments importants dans un projet.

![Numéro de résumé](assets/summary-number.png)

### [!UICONTROL Anneau]

Tout comme un graphique circulaire, cette visualisation présente les données comme des parties d’un tout. Utilisez un graphique en anneau pour comparer les pourcentages dʼun total. Supposons, par exemple, que vous souhaitiez identifier la plateforme publicitaire responsable du nombre total de visiteurs uniques :

![Visualisation en anneau](assets/donut-viz.png)

### [!UICONTROL Ligne]

Dans la visualisation en ligne, les mesures sont représentées sous la forme d’une ligne afin d’indiquer l’évolution des valeurs dans le temps. Un graphique en lignes affiche les dimensions au fil du temps, mais fonctionne avec n’importe quelle visualisation. Dans cet exemple, vous visualisez la dimension de catégorie de produits.

![Visualisation en ligne](assets/line.png)

### [!UICONTROL Barre horizontale]

Dans cette visualisation, des barres horizontales représentent plusieurs valeurs pour une ou plusieurs mesures. Par exemple, pour voir facilement quels sont vos principaux produits, utilisez [!UICONTROL Barre horizontale] comme visualisation préférée.

![barre horizontale](assets/horizontal.png)

### Supprimer l’élément de dimension [!UICONTROL Non spécifié]

Si vous souhaitez supprimer [!UICONTROL Non spécifié] des éléments de dimension de vos données, procédez comme suit :

1. Sélectionnez la mosaïque appropriée.
1. Dans le rail de droite, sous **[!UICONTROL Analyses]**, sélectionnez la flèche vers la droite en regard de l’élément de dimension pour lequel vous voulez supprimer les éléments **[!UICONTROL Non spécifiés]**.

   ![non spécifié](assets/unspecified.png)

1. Cliquez sur l’icône en regard de **[!UICONTROL Non spécifié]** pour supprimer les données non spécifiées de vos comptes rendus de performances. (Vous pouvez également supprimer tout autre élément de dimension.)

## Affichage et configuration des propriétés dʼune mosaïque {#tiles}

Lorsque vous cliquez sur une mosaïque du Créateur de Fiche d’évaluation, le rail de droite affiche les propriétés et les caractéristiques associées à cette mosaïque et à sa diapositive de détail. Dans ce rail, vous pouvez fournir une nouvelle **Titre** pour la mosaïque et configurez la mosaïque en appliquant des filtres. Les segments sont des filtres dans CJA.

![Volet Propriétés](assets/properties-tile-new.png)

## Afficher les diapositives détaillées {#view-detail-slides}

Lorsque vous cliquez sur des mosaïques, une fenêtre contextuelle dynamique affiche la diapositive de détail à l’intention de l’utilisateur en charge de l’exécution dans l’application. Vous pouvez ajouter des dimensions pour ventiler vos données selon vos besoins. Si aucune dimension n’a été appliquée, la dimension de ventilation sera **hour** ou **days**, selon la période par défaut.

Les ventilations affinent votre analyse en ventilant les mesures par éléments de dimension, tels que :

* Mesure Visiteurs uniques ventilée par Plateforme publicitaire (AMO ID)
* Mesure Visites ventilée par Catégorie de produit (vente au détail)
* Mesure Chiffre dʼaffaires total ventilée par Nom de produit

![Breakdown_view](assets/break_view.png)

Chaque dimension ajoutée à la mosaïque apparaît dans une liste déroulante dans la vue détaillée de l’application. L’utilisateur en charge de l’exécution peut alors choisir parmi les options répertoriées dans la liste déroulante.

## Personnalisation des diapositives détaillées {#customize-detail-slide}

Les diapositives détaillées personnalisées vous permettent d’être encore plus ciblé sur les informations que vous partagez avec votre audience. Vous pouvez modifier la mise en page de chaque diapositive de détail et ajouter du texte afin de mieux expliquer ce que l’utilisateur peut voir dans les données. Vous pouvez également modifier le type de graphique à l’aide du menu déroulant.

![Diapositive de détails personnalisée](assets/custom-detail-slide.png)

### Modifier la disposition de la diapositive

Modifiez la disposition de la diapositive pour vous concentrer sur les informations les plus importantes. Par exemple, vous pouvez modifier la mise en page pour n’afficher qu’un graphique ou un tableau. Pour modifier la disposition de la diapositive, sélectionnez l’un des formats prédéfinis.

![Disposition des diapositives](assets/layout.png)

Vous pouvez également modifier la disposition des diapositives en faisant glisser et en déposant les composants de visualisation du rail de gauche sur la zone de travail. Chaque diapositive de détail ne peut contenir que deux visualisations à la fois.

![Modification de la mise en page des diapositives](assets/slide-layout-change.png)

### Ajout d’un texte descriptif à une diapositive

Vous pouvez ajouter du texte pour fournir des informations significatives sur ce qui est contenu dans les graphiques ou des nuances sur les données.

Pour ajouter du texte à une diapositive de détail, sélectionnez une mise en page qui affiche le `T` ou faites glisser et déposez le composant Visualisation de texte depuis le rail de gauche. L’éditeur de texte s’ouvre automatiquement lors de l’ajout d’une nouvelle visualisation de texte ou du choix d’une mise en page avec diapositives. L’éditeur de texte fournit toutes les options standard pour le formatage de votre texte. Vous pouvez appliquer des styles de texte tels que des paragraphes, des en-têtes et des sous-titres, et appliquer une police en gras et en italique. Vous pouvez justifier du texte, ajouter des listes à puces et numérotées et ajouter des liens. Une fois la modification terminée, cliquez sur le bouton Réduire dans le coin supérieur droit de l’éditeur de texte pour le fermer. Pour modifier le texte que vous avez déjà ajouté, cliquez sur l’icône représentant un crayon pour ouvrir à nouveau l’éditeur de texte.

![Modification de la mise en page des diapositives](assets/add-descriptive-text.png)

## Suppression de composants {#remove}

De même, pour supprimer un composant appliqué à la totalité de la Fiche d’évaluation, cliquez n’importe où sur la Fiche d’évaluation en dehors des mosaïques, puis supprimez-le en cliquant sur l’icône **x** qui s’affiche lorsque vous placez le pointeur de la souris sur le composant, comme illustré ci-dessous pour la fonction **Premières visites**:

![Remove_components](assets/new_remove.png)

## Prévisualiser la carte de performance {#preview}

Vous pouvez prévisualiser l’aspect et le fonctionnement de la carte de performance une fois qu’elle sera publiée dans l’application de tableaux de bord Analytics.

1. Cliquez sur **[!UICONTROL Prévisualisation]** dans le coin supérieur droit de l’écran.

   ![Preview_scorecards](assets/preview.png)

1. Pour afficher la carte de performance telle qu’elle apparaîtra sur différents appareils, sélectionnez un appareil dans le menu déroulant [!UICONTROL Prévisualisation de l’appareil].

   ![Device_preview](assets/device-preview.png)

1. Pour interagir avec la prévisualisation, vous pouvez :

   * Cliquer avec le bouton gauche pour simuler l’appui sur l’écran du téléphone.

   * Utiliser la fonction de défilement de votre ordinateur pour simuler le défilement de l’écran du téléphone avec votre doigt.

   * Cliquer et maintenir la touche appuyée pour simuler la pression et le maintien de votre doigt sur l’écran du téléphone. Cela s’avère utile pour interagir avec les visualisations dans la vue détaillée.

## Nommer une carte de performance {#name}

Pour nommer la Fiche d’évaluation, cliquez sur l’espace de noms en haut à gauche de l’écran, puis saisissez le nouveau nom.

![Naming_Scorecards](assets/new_name.png)

## Partage dʼune carte de performance {#share}

Pour partager la Fiche d’évaluation avec un utilisateur en charge de l’exécution :

1. Cliquez sur le menu **[!UICONTROL Partager]**, puis sélectionnez **[!UICONTROL Partager la fiche d’évaluation]**.

1. Dans le formulaire **[!UICONTROL Partager la fiche d’évaluation mobile]**, complétez les champs en :

   * indiquant le nom de la carte de performance
   * fournissant une description de la carte de performance
   * ajoutant des balises pertinentes ;
   * précisant les destinataires de la carte de performance

1. Cliquez sur **[!UICONTROL Partager]**.

![Share_Scorecards](assets/new_share.png)

Après avoir partagé une carte de performance, vos destinataires peuvent y accéder depuis leurs tableaux de bord Analytics. Si, par la suite, vous apportez des modifications à la carte de performance dans le Créateur de cartes de performance, celles-ci seront mises à jour automatiquement dans la carte de performance que vous avez partagée. Les utilisateurs en charge de l’exécution pourront accéder aux changements en actualisant la Fiche d’évaluation sur leur application.

Si vous mettez à jour la carte de performance en ajoutant de nouveaux composants, vous voudrez peut-être à nouveau la partager (et cocher lʼoption **[!UICONTROL Partager les composants incorporés]**) afin de vous assurer que vos utilisateurs en charge de lʼexécution ont accès à ces modifications.
