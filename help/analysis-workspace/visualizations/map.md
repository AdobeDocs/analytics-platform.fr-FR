---
description: Utilisez la visualisation des cartes pour tracer des données sur une visualisation de carte géographique.
title: Carte
feature: Visualizations
role: User, Admin
hide: true
hidefromtoc: true
exl-id: 6656b34a-ae1e-4f9f-9c6d-13c54e49625c
source-git-commit: 4163228b2ffb08a04e386e6ca31151c7143aed5c
workflow-type: tm+mt
source-wordcount: '2270'
ht-degree: 10%

---

# Carte {#map}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="Carte"
>abstract="Cette visualisation représente les mesures en les superposant sur une carte. Cela s’avère utile pour identifier les données dans différentes régions géographiques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_bubbles"
>title="Bulles"
>abstract="Représente les événements à l’aide de bulles."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_heatmap"
>title="Carte thermique"
>abstract="Tracer des événements à l’aide d’une carte thermique."

<!-- markdownlint-enable MD034 -->


{{release-limited-testing}}

>[!BEGINSHADEBOX]

_Cet article présente la visualisation des cartes dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Voir [Map](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/visualizations/map-visualization) pour la version_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de cet article._

>[!ENDSHADEBOX]

La visualisation ![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL Map]** d’Analysis Workspace vous permet de créer une carte visuelle de n’importe quelle mesure (y compris les mesures calculées). Il est utile pour identifier et comparer des données de mesure dans différentes régions géographiques.

## Conditions préalables

### Ajouter des libellés de contexte dans les vues de données

Dans les paramètres des vues de données Customer Journey Analytics, les administrateurs peuvent ajouter des [libellés de contexte](/help/data-views/component-settings/overview.md) à une dimension ou à une mesure, et les services Customer Journey Analytics tels que la visualisation [!UICONTROL carte] peuvent utiliser ces libellés à leurs fins.

#### Libellés de contexte requis pour la visualisation des cartes

Les libellés de contexte sont requis pour que la visualisation des cartes fonctionne. Sans les libellés de contexte suivants, la visualisation de carte ne fonctionne pas, car il n’y a aucune donnée de latitude et de longitude à utiliser.

* [!UICONTROL Géographique : Latitude]
* [!UICONTROL Géo : Longitude]

Pour ajouter ces libellés de contexte :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Vues des données]**.

1. Sur la page Vues des données , sélectionnez la vue de données contenant les données à analyser dans la visualisation des cartes.

1. Sélectionnez l’onglet **[!UICONTROL Composants]**, puis sélectionnez la dimension contenant les données de longitude.

1. Dans la section **[!UICONTROL Paramètres des composants]** du rail de droite, dans le champ **[!UICONTROL Libellés de contexte]**, commencez à saisir du `Longitude`, puis sélectionnez-le dans le menu déroulant.

   ![Libellés contextuels de latitude et longitude](assets/map-context-labels-lat-long.png)

1. Répétez cette procédure pour ajouter le libellé de contexte **[!UICONTROL Latitude]** à la dimension contenant les données de latitude.

1. Sélectionnez **[!UICONTROL Enregistrer et continuer]** > **[!UICONTROL Enregistrer et terminer]**.

#### Libellés de contexte requis pour les modèles géographiques

Adobe fournit plusieurs [modèles préconfigurés](/help/analysis-workspace/templates/use-templates.md#web-audience) qui utilisent la visualisation des cartes. Pour utiliser chaque modèle, vous devez ajouter le libellé de contexte correspondant à une dimension dans votre vue de données.

Vous trouverez ci-dessous les modèles et le libellé de contexte requis. Sans ces libellés, les modèles ne fonctionnent pas, car il n’existe aucune donnée géographique à utiliser.

| Nom du modèle | Libellé de contexte obligatoire |
|---------|----------|
| Pays géographiques | [!UICONTROL Géo : Pays géographique] |
| Régions géographiques | [!UICONTROL Géo : Région géographique] |
| Villes géographiques | [!UICONTROL Géo : Ville géographique] |
| États américains géographiques | [!UICONTROL Géo : État géographique] |
| DMA États-Unis géographiques | [!UICONTROL Géo : Dma Géographique] |

Pour ajouter ces libellés de contexte :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Vues des données]**.

1. Sur la page Vues de données , sélectionnez la vue de données contenant les données à analyser avec les modèles préconfigurés qui utilisent la visualisation de carte. Dans cette vue de données, vous allez sélectionner cinq dimensions : une avec les données du pays, une avec les données de la région, une avec les données de la ville, une avec les données de l’État et une avec les données de la DMA. Vous étiquetez ensuite ces dimensions avec le libellé de contexte correspondant.

1. Sélectionnez l’onglet **[!UICONTROL Composants]** puis sélectionnez la dimension contenant les données du pays.

1. Dans la section **[!UICONTROL Paramètres des composants]** du rail de droite, dans le champ **[!UICONTROL Libellés de contexte]**, commencez à saisir du `Geo Country`, puis sélectionnez-le dans le menu déroulant.

   ![Libellés contextuels des modèles](assets/map-context-labels-templates.png)

1. Répétez cette procédure pour ajouter le libellé de contexte **[!UICONTROL Géo : Région géographique]**, **[!UICONTROL Géo : Ville géographique]**, **[!UICONTROL Géo : État géographique]** et **[!UICONTROL Géo : Dma]** à chaque dimension contenant les données correspondantes.

1. Sélectionnez **[!UICONTROL Enregistrer et continuer]** > **[!UICONTROL Enregistrer et terminer]**.

### Les pilotes graphiques doivent prendre en charge le rendu WebGL

La visualisation des cartes utilise WebGL pour l’affichage des graphiques. Si vos pilotes graphiques ne prennent pas en charge le rendu WebGL, vous devrez peut-être mettre à jour vos pilotes.

## Visualisation des cartes dans Customer Journey Analytics par rapport à Adobe Analytics

La visualisation des cartes dans Customer Journey Analytics diffère de la visualisation des cartes dans Adobe Analytics des manières suivantes :

| Fonctionnalité | Customer Journey Analytics | Adobe Analytics |
|---------|----------|---------|
| Source de données | Utilisez n’importe quel segment disponible dans votre vue de données comme source de données. | Propose les options suivantes : <ul><li>Lat/long pour mobiles</li><li>Dimension géographique <br/> représente les données de segmentation géographique relatives à l’emplacement du visiteur en fonction de son adresse IP. </li></ul> |
| Précision | Pour les jeux de données avec une précision élevée, vous pouvez configurer les dimensions dans votre vue de données pour afficher jusqu’à 5 décimales. Cela permet à la visualisation de la carte d’être précise à moins d’un mètre. <p>Pour plus d’informations, voir [Configurer des emplacements précis pour les dimensions](#configure-precise-locations-for-dimensions).</p> | Les données sont exactes au niveau [!UICONTROL Pays], [!UICONTROL Région] et [!UICONTROL Ville]. (Elle n’atteint pas le niveau de la DMA ou du code postal.) |
| Création d’un segment à partir d’une sélection | Créez un segment en fonction d’une zone spécifique que vous sélectionnez dans la visualisation de carte. <p>Pour plus d’informations, voir [Création d’un segment à partir de la visualisation des cartes](#create-a-segment-from-the-map-visualization).</p> | Créez un segment basé sur les données rapportées dans la visualisation des cartes en général. |
| Création d’une audience à partir d’une sélection | Créez une audience basée sur une zone spécifique que vous sélectionnez dans la visualisation de carte. <p>Pour plus d’informations, voir [Création d’une audience à partir de la visualisation de carte](#create-an-audience-from-the-map-visualization). | Impossible de créer une audience à partir de la visualisation de carte. |
| Création d’une tendance à partir d’une sélection | Créez une visualisation sous forme de graphique en courbes de tendance en fonction d’une zone spécifique que vous sélectionnez dans la visualisation des cartes. <p>Pour plus d’informations, voir [Création d’un graphique en courbes de tendance à partir de la visualisation des cartes](#create-a-trended-line-chart-from-the-map-visualization). <!-- is this correct? --> | Impossible de créer une tendance à partir de la visualisation des cartes. |
| Ajouter une répartition depuis une sélection | Ventilez un élément de dimension, une mesure, un segment ou une période spécifique dans une zone spécifique que vous sélectionnez dans la visualisation de carte. <p>Pour plus d’informations, voir [Ajouter une répartition à partir de la visualisation des cartes](#add-a-breakdown-from-the-map-visualization). | Impossible d’ajouter une répartition à partir de la visualisation des cartes. |

## Commencer à créer une visualisation de carte {#begin-building-map}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_panel"
>title="Configurer la visualisation des cartes"
>abstract="Sélectionnez la mesure ou la mesure calculée utilisée comme base pour votre visualisation des cartes. Vous pouvez également ajouter un segment si vous souhaitez vous concentrer sur un sous-ensemble spécifique des données.<p>Vous pouvez mettre à jour ces informations à tout moment après le rendu de la visualisation.</p>"

<!-- markdownlint-enable MD034 -->

1. Sélectionnez l’icône [!UICONTROL **Visualisations**] dans le rail de gauche, puis faites glisser la visualisation **[!UICONTROL Map]** ![Map](/help/assets/icons/Globe.svg) dans un panneau contenant un tableau à structure libre.

   Ou

   Ajoutez une visualisation de carte de l’une des manières décrites dans la section [Ajouter des visualisations à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) de la [Vue d’ensemble des visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

   ![Configuration de la carte](assets/map-configuration.png){width="50%"}

1. Spécifiez les informations de base suivantes pour configurer la visualisation des cartes :

   * **[!UICONTROL Ajouter une mesure]** : dans la liste déroulante des mesures, sélectionnez une mesure ou une mesure calculée. (Vous pouvez également faire glisser une mesure à partir du rail de gauche.)

     >[!IMPORTANT]
     >
     >Si vous choisissez une mesure à laquelle une [attribution](/help/data-views/component-settings/attribution.md#attribution-models) est appliquée, la même attribution est appliquée aux paires de latitude et de longitude dans la fenêtre d’affichage actuelle de la visualisation de carte.
     >

     <!-- Only choose metrics that use Last Touch as the [attribution model](/help/data-views/component-settings/attribution.md#attribution-models) (this is the default attribution model for all metrics). Choosing a metric that has an attribution model other than Last Touch results in inaccurate map data, because attribution is applied to the latitude and longitude pairs. -->

   * **[!UICONTROL Ajouter un segment]** : (facultatif) dans la liste déroulante de segments, sélectionnez un segment. Vous pouvez également faire glisser un segment depuis la liste des segments.

   Vous pouvez mettre à jour ces informations une fois la visualisation créée en sélectionnant l’icône de modification ![Modifier](/help/assets/icons/Edit.svg) dans l’en-tête de la visualisation.

1. Sélectionnez la **[!UICONTROL Version]**.

   Une visualisation de carte du monde avec des bulles est générée.

   ![](assets/map-visualization.png)

1. Continuez avec [Visualisation d’une carte](#view-a-map-visualization) et [Configuration des paramètres de visualisation](#configure-visualization-settings).

## Visualisation Carte

1. Si ce n’est pas déjà fait, créez une visualisation de carte, comme décrit dans la section [Commencer à créer une visualisation de carte](#begin-building-a-map-visualization).

1. Dans la visualisation des cartes d’Analysis Workspace, effectuez l’une des opérations suivantes :

   * **Zoom avant** : Vous pouvez effectuer un zoom avant sur la carte pour agrandir certaines zones de l’une des manières suivantes :

      * Double-cliquez sur la carte avec la souris.

      * Utilisez la roulette de défilement de la souris ou une action similaire sur le trackpad.

      * Sélectionnez l’icône plus ![icône de zoom avant](assets/map-zoomin-icon.png) dans la visualisation de la carte.

     La carte effectue un zoom en conséquence. La dimension requise (pays > État > ville) est automatiquement mise à jour en fonction du niveau de zoom.

   * **Zoom arrière** : vous pouvez effectuer un zoom arrière sur la carte pour afficher des zones plus grandes de l’une des manières suivantes :

      * Maintenez la touche Maj enfoncée et double-cliquez sur la carte avec la souris.

      * Utilisez la roulette de défilement de la souris ou une action similaire sur le trackpad.

      * Sélectionnez l’icône moins ![icône de zoom arrière](assets/map-zoomout-icon.png) dans la visualisation de la carte.

     La carte effectue un zoom en conséquence. La dimension requise (pays > État > ville) est automatiquement mise à jour en fonction du niveau de zoom.

   * **Rotation** : vous pouvez faire pivoter la carte en 2D ou 3D en maintenant la touche [!UICONTROL Ctrl] enfoncée et en faisant glisser la carte avec la souris.

     Pour réinitialiser la carte à son alignement nord d’origine, sélectionnez l’icône compass ![icône compass](assets/map-compass-icon.png).

   * **Outil de sélection** : vous pouvez sélectionner une zone de la carte pour [créer un segment](#create-a-segment-from-the-map-visualization), [créer une tendance](#create-a-trended-line-chart-from-the-map-visualization) ou [ajouter une répartition](#add-a-breakdown-from-the-map-visualization).

     Cliquez sur l’outil de sélection ![icône de mappage de la sélection](assets/map-selection-icon.png), puis faites glisser la souris pour sélectionner la zone souhaitée.

   * **Comparer** : vous pouvez comparer plusieurs visualisations de carte dans le même projet en les plaçant côte à côte.

   * **Afficher des comparaisons période par période (par exemple, année par année)** :

      * Afficher les nombres négatifs.

        Par exemple, si vous tracez une mesure d’une année à l’autre, la carte peut afficher -33 % sur New York.
      * Avec les mesures de type *pourcentage*, le regroupement effectue la moyenne des pourcentages.
      * Une palette de couleurs verte et rouge indique positif et négatif.

   * **Paramètres de visualisation supplémentaires** : sélectionnez l’icône Paramètres ![Paramètre](/help/assets/icons/Setting.svg) dans l’en-tête de visualisation pour afficher les paramètres supplémentaires pour la visualisation de la carte. Pour plus d’informations, voir [Configurer les paramètres de visualisation](#configure-visualization-settings).

1. **Enregistrer** le projet pour enregistrer tous les paramètres des cartes (coordonnées, zoom, rotation).
1. (Facultatif) Le tableau à structure libre situé sous la visualisation peut être renseigné en faisant glisser les dimensions et mesures d’emplacement depuis le rail de gauche.

## Configurer les paramètres de visualisation

Pour configurer les paramètres de la visualisation des cartes :

1. Dans Analysis Workspace, ouvrez une visualisation de carte existante ou [commencez à en créer une nouvelle](#begin-building-a-map-visualization).

1. Pointez sur la visualisation des cartes, puis sélectionnez l’icône Paramètres ![Paramètre](/help/assets/icons/Setting.svg) dans l’en-tête de visualisation.

   Les options disponibles sont les suivantes :

   | Section | Paramètre | Description |
   | --- |--- |--- |
   | **[!UICONTROL Type de carte]** | | |
   | | **[!UICONTROL Bulles]** | Représente les événements à l’aide de bulles. Un graphique en bulles est un graphique à plusieurs variables à mi-chemin entre un graphique de dispersion et un graphique à zones proportionnelles. Il s’agit de l’affichage par défaut. |
   | | **[!UICONTROL Carte thermique]** | Représente les événements à l’aide d’une carte thermique. Une carte thermique est une représentation graphique des données où les valeurs individuelles contenues dans une matrice sont représentées sous la forme de couleurs. |
   | **[!UICONTROL Styles]** | | |
   | | **[!UICONTROL Thème de couleur]** | Affiche le jeu de couleurs pour la carte thermique et les bulles. Vous avez le choix entre Corail, Rouges, Verts ou Bleus. La valeur par défaut est Corail. |
   | | **[!UICONTROL Style de carte]** | Vous avez le choix entre De base, Rues, Lumineux, Clair, Foncé et Satellite. |
   | | **[!UICONTROL Rayon du cluster]** | Regroupe les points de données qui se trouvent dans le nombre spécifié de pixels. La valeur par défaut est de 50. |
   | | **[!UICONTROL Valeur maximale personnalisée]** | Permet de modifier le seuil de la valeur maximale pour la carte. L’ajustement de cette valeur ajuste l’échelle des valeurs des bulles ou de la carte thermique (couleur et taille) par rapport à la valeur maximale personnalisée que vous avez définie. |
   | | **[!UICONTROL Afficher les annotations]** | Affiche les annotations effectuées pour cette visualisation. |
   | | **[!UICONTROL Masquer le titre]** | Masque le titre de la visualisation. |

## Configurer des emplacements précis pour les dimensions

Si vous disposez de jeux de données personnalisés avec une précision élevée, vous pouvez configurer la visualisation des cartes afin d’obtenir une précision de localisation d’un seul mètre.

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Vues des données]**.

1. Sélectionnez la vue de données qui contient les dimensions que vous souhaitez configurer pour utiliser des emplacements plus précis.

1. Dans la vue de données, sélectionnez l’onglet **[!UICONTROL Composants]**.

1. Sélectionnez la dimension à configurer.

1. Configurez le niveau de précision de la dimension :

   1. La dimension à configurer étant toujours sélectionnée, développez la section **[!UICONTROL Format]** dans le rail de droite.

      ![élément de dimension sélectionné avec la section format développée](assets/map-dimension-format.png)

   1. Dans le champ **[!UICONTROL Nombre de décimales]**, modifiez le nombre de décimales pour refléter le niveau de précision souhaité :

      * **0:** Précise au niveau de la grande région ou du pays dans la visualisation de la carte. Affiche 0 décimale dans les rapports Espace de travail.

      * **1:** Précise au niveau de la région ou de la grande ville dans la visualisation de la carte.  Affiche 1 décimale dans les rapports Espace de travail.

      * **2:** Précis au niveau de la ville ou du code postal dans la visualisation de la carte. Affiche 2 décimales dans les rapports Espace de travail.

        Il s’agit de la sélection par défaut.

      * **3:** Précise au niveau de la très petite ville ou du quartier dans la visualisation de la carte. Affiche 3 décimales dans les rapports Espace de travail.

      * **4:** Précise à une parcelle de terrain ou un niveau de bâtiment spécifique dans la visualisation de la carte. Affiche 4 décimales dans les rapports Espace de travail.

      * **5:** Précise à un seul mètre dans la visualisation de la carte. Affiche 5 décimales dans les rapports Espace de travail.

1. Sélectionnez **[!UICONTROL Enregistrer et continuer]** > **[!UICONTROL Enregistrer et terminer]**.

## Création d’un segment à partir de la visualisation des cartes {#map-create-segment}

Vous pouvez créer un segment en fonction d’une zone spécifique que vous sélectionnez dans la visualisation de carte. Lorsque vous créez un segment en fonction d’une zone sélectionnée, toutes les données comprises dans la latitude et la longitude de votre sélection sont incluses dans le segment.

Pour créer un segment à partir de la visualisation des cartes :

1. (Facultatif) Effectuez un zoom avant sur la zone spécifique de la carte qui contient les données que vous souhaitez utiliser pour le segment.

1. Cliquez sur l’outil de sélection ![icône de mappage de la sélection](assets/map-selection-icon.png), puis faites glisser la souris pour sélectionner la zone souhaitée.

1. Sélectionnez **[!UICONTROL Créer un segment à partir de la sélection]** dans le menu déroulant qui s’affiche.

1. Utilisez le créateur de segments pour définir le nouveau segment. Pour plus d’informations, voir [Créateur de segments](/help/components/segments/seg-builder.md).

## Création d’une audience à partir de la visualisation de carte

Vous pouvez créer une audience basée sur une zone spécifique que vous sélectionnez dans la visualisation de la carte.

Pour créer une audience à partir de la visualisation de carte :

1. (Facultatif) Effectuez un zoom avant sur la zone spécifique de la carte qui contient les données que vous souhaitez utiliser pour l’audience.

1. Cliquez sur l’outil de sélection ![icône de mappage de la sélection](assets/map-selection-icon.png), puis faites glisser la souris pour sélectionner la zone souhaitée.

1. Sélectionnez **[!UICONTROL Créer une audience à partir de la sélection]** dans le menu déroulant qui s’affiche.

1. Utilisez le créateur d’audiences pour définir la nouvelle audience. Pour plus d’informations, voir [Créateur d’audiences](/help/components/audiences/publish.md#audience-builder) dans [Création et publication d’audiences](/help/components/audiences/publish.md)

## Créer un graphique en courbes de tendance à partir de la visualisation des cartes

Vous pouvez créer une visualisation sous forme de graphique en courbes de tendance pour les données d’une zone spécifique que vous sélectionnez dans la visualisation des cartes.

Pour créer un graphique en courbes de tendance à partir de la visualisation des cartes :

1. (Facultatif) Effectuez un zoom avant sur la zone spécifique de la carte qui contient les données que vous souhaitez utiliser pour le graphique en courbes de tendance.

1. Cliquez sur l’outil de sélection ![icône de mappage de la sélection](assets/map-selection-icon.png), puis faites glisser la souris pour sélectionner la zone souhaitée.

1. Sélectionnez **[!UICONTROL Tendance]** dans le menu déroulant qui s’affiche.

   Une visualisation linéaire est créée qui comprend une ligne de tendance. Pour plus d’informations sur cette visualisation, voir [Ligne](/help/analysis-workspace/visualizations/line.md).

<!--

Can you do this?

## Add a breakdown from the map visualization

You can break down a specific dimension item, metric, segment, or date range for the data within a designated area that you select in the map visualization.

To add a breakdown from the map visualization:

1. (Optional) Zoom in on the specific area of the map that contains the data where you want to add the breakdown.

1. Click the selection tool ![map selection icon](assets/map-selection-icon.png), then drag your mouse to select the desired area.

1. Select **[!UICONTROL Add breakdown]**. 

-->

<!--

Can you do this?

## Export the map visualization as a PDF

To export the map visualization in PDF format:

1. how...

-->

