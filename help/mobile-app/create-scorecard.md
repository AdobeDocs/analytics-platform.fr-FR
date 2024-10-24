---
description: Comment créer et partager des fiches d’évaluation des tableaux de bord Analytics
title: Création et partage de fiches d’évaluation
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
solution: Customer Journey Analytics
source-git-commit: 31381cd397a821cc3ff1b3c15ae968a7260a6e9e
workflow-type: tm+mt
source-wordcount: '2672'
ht-degree: 68%

---

# Créer une carte de performance mobile {#create-a-mobile-scorecard}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_mobilescorecard_annotations"
>title="Annotations"
>abstract="Vous pouvez créer des annotations dans le gestionnaire de composants d’un projet d’espace de travail."

<!-- markdownlint-enable MD034 -->


Les informations suivantes indiquent aux curateurs de données de Customer Journey Analytics comment configurer et présenter des tableaux de bord pour les utilisateurs en charge de l’exécution. Pour commencer, vous pouvez afficher la vidéo du créateur de Fiche d’évaluation des tableaux de bord Analytics :

>[!VIDEO](https://video.tv.adobe.com/v/343458)

>[!NOTE]
>
>Les captures d’écran de la fiche d’évaluation Analytics pour cette page ont été effectuées à partir de l’interface utilisateur d’Adobe Analytics, et non de Customer Journey Analytics. Les interfaces utilisateur sont presque identiques.

Une fiche d’évaluation Analytics affiche les visualisations de données clés pour les utilisateurs en charge de l’exécution dans une mise en page en mosaïque, comme illustré ci-dessous :

![Exemple de Fiche d’évaluation Analytics montrant la démonstration de la Fiche d’évaluation mobile](assets/intro_scorecard.png)

En tant que curateur de cette Fiche d’évaluation, vous pouvez utiliser le créateur de Fiche d’évaluation pour configurer les mosaïques qui apparaissent sur la Fiche d’évaluation de votre consommateur en charge de l’exécution. Vous pouvez également configurer la manière dont lʼaffichage des détails ou les répartitions sʼajustent lorsque lʼutilisateur appuie sur les mosaïques. L’interface du créateur de Fiche d’évaluation est illustrée ci-dessous :

![Créateur de Fiche d’évaluation présentant la nouvelle fenêtre de Fiche d’évaluation mobile. ](assets/scorecard_builder.png)

Pour créer la fiche d’évaluation, vous devez effectuer les opérations suivantes :

1. Accédez au modèle de [!UICONTROL Fiche d’évaluation mobile vierge].
2. Configurer la carte de performance avec des données, puis enregistrez-la.

## Accéder au modèle de [!UICONTROL Fiche d’évaluation mobile vierge] {#template}

Vous pouvez accéder au modèle de [!UICONTROL Carte de performance mobile vierge] en créant un projet ou à partir du menu Outils.

### Créer un nouveau projet {#create}

1. Ouvrez Customer Journey Analytics et cliquez sur l’onglet **[!UICONTROL Workspace]** .
1. Cliquez sur **[!UICONTROL Créer un projet]**, puis sélectionnez le modèle de projet **[!UICONTROL Carte de performance mobile vierge]**.
1. Cliquez sur **[!UICONTROL Créer]**.

![Fenêtre Tous les modèles avec la Fiche d’évaluation Mbile vierge sélectionnée.](assets/new_template.png)

### Menu Outils

1. Dans le menu **[!UICONTROL Outils]**, sélectionnez **[!UICONTROL Tableaux de bord Analytics (application mobile)]**.
1. Sur lʼécran suivant, cliquez sur **[!UICONTROL Créer une carte de performance]**.

## Configurez la carte de performance avec des données, puis enregistrez-la. {#configure}

Pour mettre en oeuvre le modèle de Fiche d’évaluation :

1. Sous **[!UICONTROL Propriétés]** (dans le rail droit), précisez la **[!UICONTROL vue de données du projet]** depuis laquelle vous souhaitez utiliser les données.

   ![Nouvelle fenêtre de Fiche d’évaluation mobile présentant la sélection de vue de données](assets/properties_save.png)

1. Pour ajouter une nouvelle mosaïque à votre fiche d’évaluation, faites glisser une mesure depuis le panneau de gauche et déposez-la dans la zone **[!UICONTROL Faire glisser les mesures ici]** . Vous pouvez également insérer une mesure entre deux mosaïques en utilisant un workflow similaire.

   ![Nouvelle fenêtre de la Fiche d’évaluation mobile avec une flèche pointant vers une mesure (Nouvel indicateur de performance clé) déposée dans la Fiche d’évaluation. ](assets/build_list.png)


1. Depuis chaque mosaïque, vous pouvez accéder à une vue détaillée qui affiche des informations supplémentaires sur la mesure comme les éléments principaux pour une liste de dimensions associées.

## Ajout de dimensions ou de mesures {#dimsmetrics}

Pour ajouter une dimension associée à une mesure, faites glisser une dimension depuis le panneau de gauche, puis déposez-la dans une mosaïque.

Par exemple, vous pouvez ajouter des dimensions appropriées (comme **[!DNL Marketing Channel]** dans cet exemple) à la mesure **[!UICONTROL Visiteurs uniques]** en effectuant une opération de glisser-déposer sur la mosaïque. Les répartitions de dimensions sʼaffichent sous la section [!UICONTROL Répartition] des **[!UICONTROL Propriétés]** propres à la mosaïque. Plusieurs dimensions peuvent être ajoutées à chaque mosaïque.

![Nouvelle fenêtre de Fiche d’évaluation mobile avec une flèche pointant vers le volet de la liste des dimensions vers la Fiche d’évaluation.](assets/layer_dimensions.png)

## Appliquer des filtres {#filters}

Pour appliquer des filtres à des mosaïques individuelles, faites glisser un filtre (les segments sont des filtres en Customer Journey Analytics) à partir du panneau de gauche et déposez-le directement au-dessus de la mosaïque.

Si vous souhaitez appliquer le filtre à toutes les mosaïques de la Fiche d’évaluation, déposez la mosaïque en haut de la Fiche d’évaluation. Vous pouvez également appliquer des filtres en les sélectionnant dans le menu de filtre situé sous les périodes. Vous [ configurez et appliquez des filtres pour vos fiches d’évaluation ](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=fr) de la même manière que vous le feriez dans Customer Journey Analytics Workspace.

![Sélecteur de liste déroulante de filtre mettant en surbrillance les filtres de création](assets/segment_ui.png)

## Ajout de périodes {#dates}

Ajoutez et supprimez des combinaisons de périodes pouvant être sélectionnées dans votre carte de performance en cliquant sur le menu déroulant des périodes.

![Nouvelle fiche d’évaluation mobile surlignée hier par rapport au même jour la semaine dernière](assets/new_score_card.png)

Chaque nouvelle carte de performance démarre avec 6 combinaisons de périodes centrées sur les données du jour et de la veille. Vous pouvez supprimer les périodes inutiles en cliquant sur le x. Vous pouvez également modifier chaque combinaison de périodes en cliquant sur le crayon.

![Nouvelle fiche d’évaluation mobile mettant en surbrillance l’icône en forme de crayon](assets/new_score_card2.png)

Pour créer ou modifier une date principale, utilisez la liste déroulante pour sélectionner une période disponible ou faites glisser un composant de date depuis le rail de droite et déposez-le dans la zone de dépôt.

![Nouvelle fiche d’évaluation mobile présentant les plages de dates avec la date Principal/hier sélectionnée](assets/new_score_card3.png)

Pour créer une date de comparaison, vous pouvez choisir parmi des paramètres prédéfinis utiles aux comparaisons d’heures fréquentes dans le menu déroulant. Vous pouvez également glisser-déposer un composant de date à partir du rail de droite.

![Nouvelle fiche d’évaluation mobile présentant les plages de dates avec la date de comparaison définie sur le même jour la semaine dernière sélectionnée](assets/new_score_card4.png)

Si la période souhaitée n’a pas encore été créée, vous pouvez en créer une nouvelle en cliquant sur l’icône Calendrier.

![Icône Calendrier](assets/new_score_card5.png)

Vous accédez ainsi au créateur de périodes, où vous pouvez créer un composant de période avant de l’enregistrer.

### Afficher ou masquer les périodes de comparaison {#show-comparison-dates}

Pour inclure des périodes de comparaison, activez le paramètre **Inclure des dates de comparaison**.

![Nouvelle fiche d’évaluation mobile présentant les dates d’hier et d’précédent et inclusion de comparaison](assets/include-comparison-dates.png)

Le paramètre est *activé* par défaut. Réglez-le sur *désactivé* si vous ne souhaitez pas afficher de dates de comparaison.

![ Nouvelle fiche d’évaluation mobile surlignée hier et dates de comparaison des inclusions](assets/no-comparison-dates.png)

## Appliquer des visualisations {#viz}

Les tableaux de bord Analytics offrent quatre visualisations qui vous donnent des informations détaillées sur les mesures et les éléments de dimension. Appliquez une visualisation différente en modifiant le [!UICONTROL type de graphique] des [!UICONTROL propriétés] d’une mosaïque. Sélectionnez simplement la mosaïque de droite, puis modifiez le type de graphique.

![Propriétés de la mosaïque](assets/properties.png)

Ou cliquez sur l’icône [!UICONTROL Visualisations] dans le rail de gauche, puis glissez-déposez la visualisation de droite sur la mosaïque :

![Visualisations](assets/vizs.png)

### [!UICONTROL Numéro du résumé]

Utilisez la visualisation Synthèse des chiffres pour mettre en évidence un grand nombre d’éléments importants dans un projet.

![Nouvelle fiche d’évaluation mobile avec visualisation de synthèse des chiffres mettant en évidence les visites 13.3K](assets/summary-number.png)

### [!UICONTROL Anneau]

Semblable à un graphique en secteurs, cette visualisation présente les données comme des portions d’un tout. Utilisez un graphique en anneau pour comparer les pourcentages dʼun total. Par exemple, vous souhaitez savoir quelle plateforme publicitaire a contribué au nombre total de personnes uniques :

![Nouvelle fiche d’évaluation mobile présentant une visualisation Anneau](assets/donut-viz.png)

### [!UICONTROL Ligne]

Dans la visualisation en ligne, les mesures sont représentées sous la forme d’une ligne afin d’indiquer l’évolution des valeurs dans le temps. Un graphique en lignes affiche les dimensions au fil du temps, mais fonctionne avec n’importe quelle visualisation. Dans cet exemple, vous visualisez la dimension de catégorie de produits.

![ Nouvelle fiche d’évaluation mobile présentant une visualisation Ligne ](assets/line.png)

### [!UICONTROL Barre horizontale]

Dans cette visualisation, des barres horizontales représentent plusieurs valeurs pour une ou plusieurs mesures. Par exemple, pour voir facilement quels sont vos principaux produits, utilisez [!UICONTROL Barre horizontale] comme visualisation préférée.

![Nouvelle fiche d’évaluation mobile présentant une barre horizontale](assets/horizontal.png)

## Nommer les Fiches d’évaluation {#name}

Pour nommer la fiche d’évaluation, cliquez sur l’espace de noms dans le coin supérieur gauche de l’écran, puis saisissez le nouveau nom.

![Naming_Scorecards](assets/new_name.png)

### Supprimer l’élément de dimension [!UICONTROL Non spécifié] {#remove-dims}

Si vous souhaitez supprimer [!UICONTROL Non spécifié] des éléments de dimension de vos données, procédez comme suit :

1. Sélectionnez la mosaïque appropriée.
1. Dans le rail de droite, sous **[!UICONTROL Analyses]**, sélectionnez la flèche vers la droite en regard de l’élément de dimension pour lequel vous voulez supprimer les éléments **[!UICONTROL Non spécifiés]**.

   ![ Propriétés avec flèche pointant vers la flèche droite en regard du nom de la dimension.](assets/unspecified.png)

1. Cliquez sur l’icône en regard de **[!UICONTROL Non spécifié]** pour supprimer les données non spécifiées de vos comptes rendus de performances. (Vous pouvez également supprimer tout autre élément de dimension.)

## Afficher et configurer des propriétés dʼune vignette {#tiles}

Lorsque vous cliquez sur une mosaïque du créateur de Fiche d’évaluation, le rail de droite affiche les propriétés et les caractéristiques associées à cette mosaïque et à sa diapositive de détail. Dans ce rail, vous pouvez fournir un nouveau **titre** pour la vignette ainsi que la configurer en appliquant des filtres. Les segments sont des filtres dans Customer Journey Analytics.

![Volet Propriétés](assets/properties-tile-new.png)

## Afficher les diapositives détaillées {#view-detail-slides}

Si vous cliquez sur les vignettes, une fenêtre pop-up dynamique monte comment l’utilisateur en charge de l’exécution voit la diapositive détaillée dans l’application. Vous pouvez ajouter des dimensions pour ventiler vos données selon vos besoins. Si aucune dimension n’a été appliquée, la dimension de répartition sera **heure** ou **jours**, en fonction de la période par défaut.

Les répartitions affinent votre analyse en répartissant les mesures par éléments de dimension, tels que :

* Mesure Visiteurs uniques ventilée par Plateforme publicitaire (AMO ID)
* Mesure Visites ventilée par Catégorie de produit (vente au détail)
* Mesure Chiffre dʼaffaires total ventilée par Nom de produit

![Breakdown_view](assets/break_view.png)

Chaque dimension ajoutée à la mosaïque apparaît dans une liste déroulante dans la vue détaillée de l’application. L’utilisateur en charge de l’exécution peut alors choisir parmi les options répertoriées dans la liste déroulante.

## Personnaliser des diapositives détaillées {#customize-detail-slide}

Les diapositives détaillées personnalisées vous permettent d’être encore plus ciblé sur les informations que vous partagez avec votre audience.

>[!VIDEO](https://video.tv.adobe.com/v/3410002)

Vous pouvez modifier la disposition de chaque diapositive détaillée et ajouter du texte afin de mieux expliquer ce que l’utilisateur final peut voir dans les données. Vous pouvez également modifier le type de graphique à l’aide du menu déroulant.

![Diapositive détaillée personnalisée](assets/custom-detail-slide.png)

### Modifier la disposition de la diapositive

Modifiez la disposition de la diapositive pour vous concentrer sur les informations les plus importantes. Par exemple, vous pouvez modifier la disposition pour n’afficher qu’un graphique ou un tableau. Pour modifier la disposition de la diapositive, sélectionnez l’un des formats prédéfinis.

![Disposition des diapositives](assets/layout.png)

Vous pouvez également modifier la disposition des diapositives en glissant-déposant les composants de visualisation du rail de gauche sur la zone de travail. Chaque diapositive détaillée ne peut contenir que deux visualisations à la fois.

![Modification la disposition des diapositives](assets/slide-layout-change.png)

### Ajouter un texte descriptif à une diapositive

Vous pouvez ajouter du texte pour fournir des informations significatives sur le contenu des graphiques ou des nuances sur les données.

Pour ajouter du texte à une diapositive détaillée, sélectionnez une disposition qui affiche le symbole `T` ou glissez-déposez le composant Visualisation de texte depuis le rail de gauche. L’éditeur de texte s’ouvre automatiquement lors de l’ajout d’une nouvelle visualisation de texte ou du choix d’une disposition de diapositives avec texte. L’éditeur de texte fournit toutes les options standard pour le formatage de votre texte. Vous pouvez appliquer des styles de texte tels que des paragraphes, des en-têtes et des sous-titres, ainsi qu’appliquer des polices en gras et en italique. Vous pouvez justifier du texte, ajouter des listes à puces ou numérotées et ajouter des liens. Une fois la modification terminée, cliquez sur le bouton Réduire dans le coin supérieur droit de l’éditeur de texte pour le fermer. Pour modifier le texte que vous avez déjà ajouté, cliquez sur l’icône en forme de crayon pour ouvrir à nouveau l’éditeur de texte.

![Modifier la disposition des diapositives](assets/add-descriptive-text.png)

## Supprimer des composants {#remove}

De même, pour supprimer un composant appliqué à la totalité de la fiche d’évaluation, cliquez n’importe où sur la fiche d’évaluation en dehors des mosaïques, puis supprimez-le en cliquant sur le **x** qui s’affiche lorsque vous passez la souris sur le composant, comme illustré ci-dessous pour les **Premières visites** :

![Remove_components](assets/new_remove.png)

## Créer des histoires de données {#create-data-story}

Une histoire de données consiste en un ensemble de points de données complémentaires, de contexte commercial et de mesures associées construit autour d’un thème central ou d’une mesure commune.

Par exemple, si vous vous concentrez sur le trafic web, la mesure la plus importante peut être les visites, mais vous pouvez également vous intéresser aux nouvelles personnes, aux personnes uniques, et vous souhaitez peut-être voir les données ventilées par page web ou par type de périphérique d’où provient le trafic. Les histoires de données contées dans les projets des cartes de performance mobiles vous permettent de faire ressortir vos mesures les plus importantes, tout en racontant la logique derrière les mesures grâce à plusieurs diapositives détaillées.

Regardez la vidéo pour en savoir plus sur la création d’histoires de données dans les projets des cartes de performance mobiles d’Analysis Workspace.

>[!VIDEO](https://video.tv.adobe.com/v/3416392/?quality=12&learn=on)

**Pour créer un article de données** {#data-story-create}

Créez votre histoire de données en ajoutant plusieurs diapositives détaillées à une mosaïque.

1. Commencez par un projet de carte de performance mobile.
1. Sélectionnez une mosaïque à partir de laquelle vous souhaitez créer une histoire.
   ![Création d’une histoire de données](assets/data-story1.png)
   ![Création d’icônes d’histoire de données](assets/create-data-story.png){width=".50%"}
1. Ajoutez des diapositives pour élaborer votre histoire de données. Votre première diapositive est générée par défaut.
Pour ajouter de nouvelles diapositives, pointez ou cliquez sur une diapositive, puis sélectionnez l’une des options disponibles :
   * Appuyez sur le signe « + » pour créer une diapositive.
   * Appuyez sur l’icône de duplication pour dupliquer la diapositive existante.
1. Si vous créez une diapositive vierge, faites glisser et déposez des composants depuis le rail de gauche ou choisissez une disposition pour remplir automatiquement la diapositive avec les données de la mosaïque.
   ![Création d’une histoire de données.](assets/data-story2.png)
Pour supprimer une diapositive, appuyez sur l’icône de corbeille.

### Personnaliser une histoire de données {#customize-data-story}

Les histoires de données vous permettent de personnaliser chaque élément, afin de partager uniquement les informations que vous souhaitez partager, et d’exclure tout ce dont vous n’avez pas besoin. Personnalisez les mosaïques et les diapositives : ajoutez des filtres, affichez des répartitions et modifiez la disposition ainsi que les visualisations.

**Pour personnaliser les mosaïques**

1. Appuyez sur une mosaïque. La mosaïque sélectionnée est entourée en bleu et le panneau de droite affiche ses propriétés.
1. Modifiez le titre, le type de graphique et d’autres options de mosaïque.
1. Faites glisser un composant sur la mosaïque.
   ![Création d’une histoire de données.](assets/data-story3.png)
Lorsque vous faites glisser et déposez un composant, tel qu’une visualisation, sur une mosaïque, le composant est appliqué à toutes les diapositives de l’histoire de données.
1. Pour appliquer une modification uniquement au titre, maintenez la touche Maj enfoncée pour appliquer la modification.
   ![Création d’une histoire de données](assets/data-story4.png)

>[!NOTE]
>Les diapositives héritent des composants de la mosaïque, mais les mosaïques n’héritent pas des composants des diapositives.

**Pour personnaliser des diapositives individuelles**

Vous pouvez modifier la visualisation de diapositives individuelles d’une histoire de données. Vous pouvez, par exemple, remplacer une barre horizontale par un graphique en anneau dans une diapositive. Vous pouvez également modifier la disposition. Consultez la section [Personnaliser les diapositives détaillées](#customize-detail-slide).

### Prévisualiser une histoire de données {#preview-data-story}

Une fois votre histoire de données créée, appuyez sur le bouton **Prévisualiser** pour afficher votre histoire de données et interagir avec elle comme si vous étiez un utilisateur ou une utilisatrice de l’application. Pour plus d’informations sur la prévisualisation des histoires de données, consultez la section [Prévisualiser une carte de performance](#preview)

### Naviguer entre les mosaïques et les diapositives {#navigate-tiles-slides}

La barre de navigation affiche des icônes reflétant le contenu de chaque diapositive. La barre de navigation permet d’accéder facilement à une diapositive spécifique si vous disposez de nombreuses diapositives.

Pour accéder à une autre mosaïque ou diapositive, appuyez sur la barre de navigation.
![Création d’une histoire de données](assets/data-story5.png)
![Création d’une histoire de données](assets/data-story-nav.png){width="45%"}

Pour naviguer d’avant en arrière, utilisez les flèches de votre clavier ou sélectionnez un composant et maintenez-le à gauche ou à droite de l’écran pour le faire défiler.

## Aperçu des fiches d’évaluation {#preview}

Vous pouvez prévisualiser l’aspect et le fonctionnement de la fiche d’évaluation une fois qu’elle sera publiée dans l’application de tableaux de bord Adobe Analytics.

1. Cliquez sur **[!UICONTROL Prévisualisation]** dans le coin supérieur droit de l’écran.

   ![Preview_scorecards](assets/preview.png)

1. Pour afficher la carte de performance telle qu’elle apparaîtra sur différents appareils, sélectionnez un appareil dans le menu déroulant [!UICONTROL Prévisualisation de l’appareil].

   ![Device_preview](assets/device-preview.png)

1. Pour interagir avec la prévisualisation, vous pouvez :

   * Cliquer avec le bouton gauche pour simuler l’appui sur l’écran du téléphone.

   * Utiliser la fonction de défilement de votre ordinateur pour simuler le défilement de l’écran du téléphone avec votre doigt.

   * Cliquer et maintenir la touche appuyée pour simuler la pression et le maintien de votre doigt sur l’écran du téléphone. Cela s’avère utile pour interagir avec les visualisations dans la vue détaillée.

## Partage des fiches d’évaluation {#share}

Pour partager la fiche d’évaluation avec un utilisateur en charge de l’exécution :

1. Cliquez sur le menu **[!UICONTROL Partager]**, puis sélectionnez **[!UICONTROL Partager la fiche d’évaluation]**.

1. Dans le formulaire **[!UICONTROL Partager la Fiche d’évaluation mobile]**, renseignez les champs en :

   * indiquant le nom de la carte de performance
   * fournissant une description de la carte de performance
   * ajoutant des balises pertinentes
   * précisant les destinataires de la carte de performance

1. Cliquez sur **[!UICONTROL Partager]**.

![Share_Scorecards](assets/new_share.png)

Après avoir partagé une carte de performance, vos destinataires peuvent y accéder depuis leurs tableaux de bord Analytics. Si vous apportez des modifications ultérieures à la Fiche d’évaluation dans le créateur de Fiche d’évaluation, elles seront automatiquement mises à jour dans la Fiche d’évaluation partagée. Les utilisateurs en charge de l’exécution verront alors les modifications après avoir actualisé la fiche d’évaluation sur leur application.

Si vous mettez à jour la carte de performance en ajoutant de nouveaux composants, vous voudrez peut-être à nouveau la partager (et cocher lʼoption **[!UICONTROL Partager les composants incorporés]**) afin de vous assurer que vos utilisateurs en charge de lʼexécution ont accès à ces modifications.

### Partage de fiches d’évaluation à l’aide d’un lien partageable

L’utilisation d’un lien partageable facilite le partage d’une fiche d’évaluation dans une application de messagerie électronique, de document ou de message texte. Le lien partageable permet aux destinataires d’ouvrir la fiche d’évaluation sur leur bureau ou dans l’application mobile des tableaux de bord. La possibilité de partager des liens profonds facilite encore le partage de projets et améliore l’engagement avec vos parties prenantes.

Pour partager une fiche d’évaluation à l’aide d’un lien partageable

1. Cliquez sur le menu **[!UICONTROL Partager]**, puis sélectionnez **[!UICONTROL Partager la fiche d’évaluation]**.

   ![Share_Scorecards](assets/share-scorecard.png)

1. Copiez le lien et collez-le dans un email, un document ou une application de messagerie instantanée.

   Lorsqu’un destinataire utilise une appli de bureau ou un navigateur pour ouvrir le lien, le projet de Fiche d’évaluation mobile s’ouvre dans Workspace.

   Lorsqu’un destinataire ouvre le lien sur un appareil mobile, la fiche d’évaluation s’ouvre directement dans l’application de tableaux de bord Adobe Analytics.

   Si un destinataire n’a pas téléchargé l’application mobile, il est redirigé vers la liste des applications dans App Store ou Google Play Store où il peut la télécharger.

