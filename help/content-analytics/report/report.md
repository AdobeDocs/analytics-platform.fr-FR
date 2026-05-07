---
title: Création de rapports Content Analytics
description: Découvrez comment créer des rapports sur Content Analytics à l’aide de visualisations telles que les tableaux à structure libre, les barres et les nuages de points.
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: f29a55379d83fc9bdd89c82f0b27c4321a139908
workflow-type: tm+mt
source-wordcount: '1410'
ht-degree: 47%

---


# Vue d’ensemble de la création de rapports sur Content Analytics

Vous créez des rapports, effectuez des analyses et obtenez des informations sur les [!DNL Content Analytics] dans [Analysis Workspace](/help/analysis-workspace/home.md). Un [modèle](#template) Workspace spécifique est disponible afin que vous puissiez immédiatement accéder à un projet Workspace prérempli avec des informations pertinentes sur le contenu.

Pour créer entièrement votre propre rapport Content Analytics, procédez comme suit :

1. Créez un [projet](/help/analysis-workspace/build-workspace-project/create-projects.md) ou ouvrez un [projet existant](/help/analysis-workspace/build-workspace-project/open-projects.md) dans Workspace.
1. Veillez à [sélectionner une vue de données](/help/analysis-workspace/c-panels/panels.md#data-view) pour la création de rapports sur Content Analytics. La création de rapports sur Content Analytics n’est disponible que pour les vues de données [configurées](/help/content-analytics/config/configuration.md) pour Content Analytics.
1. Faites glisser une visualisation ![Tableau](/help/assets/icons/Table.svg) [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) sur la zone de travail.
1. Utilisez des [composants d’analyse du contenu spécifiques](components.md) et d’autres [composants](/help/components/overview.md) génériques (tels que des segments, des périodes, des annotations) pour créer vos informations d’analyse du contenu.
1. Utilisez d’autres [visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) pour améliorer votre projet.


## Miniatures

En fonction des dimensions spécifiques à Content Analytics que vous utilisez dans votre projet, des miniatures s’affichent dans les visualisations suivantes :

### Tableau à structure libre

![Miniatures Content Analytics](../assets/aca-thumbnails.png)

Par défaut, les miniatures s’affichent dans un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). Pour configurer l’affichage de miniatures pour une dimension Content Analytics :

* Pointez sur la ligne d’en-tête d’une dimension Content Analytics. Par exemple, **[!UICONTROL ID de la ressource]** ou **[!UICONTROL ID d’expérience]**.
* Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg).
* Dans la fenêtre contextuelle **[!UICONTROL Paramètres de la ligne]**, sous **[!UICONTROL Paramètres]**, cochez ou décochez la case **[!UICONTROL Afficher les miniatures]**.


### Barres (empilées) et Barres horizontales (empilées)

{{release-limited-testing-section}}

![Miniatures Content Analytics pour le graphique à barres](/help/content-analytics/assets/aca-bar-thumbnail.png)


Des miniatures s’affichent dans le cadre de la légende sur l’axe vertical ou horizontal. Des miniatures s’affichent également lorsque vous pointez sur une barre dans une [barre (empilée)](/help/analysis-workspace/visualizations/bar.md) et une [barre horizontale (empilée)](/help/analysis-workspace/visualizations/horizontal-bar.md).


### Nuage de points

{{release-limited-testing-section}}

![Miniatures Content Analytics pour la dispersion](/help/content-analytics/assets/aca-scatter-thumbnail.png)

Des miniatures s’affichent lorsque vous pointez sur un point de données dans une [nuage de points](/help/analysis-workspace/visualizations/scatterplot.md).

## Prévisualisations

>[!AVAILABILITY]
>
>Les visualisations à barres et en nuage de points décrites dans cette section font l’objet de tests limités et peuvent ne pas être disponibles dans votre environnement. Cette note est supprimée lorsque la fonctionnalité est disponible. Pour plus d’informations sur le processus de mise à jour de Customer Journey Analytics, consultez [Mise à jour des fonctionnalités de Customer Journey Analytics](/help/release-notes/releases.md).
>

Vous pouvez ouvrir une fenêtre contextuelle d’aperçu. Pour ce faire, procédez comme suit :

* Sélectionnez ![&#x200B; InfoOutline &#x200B;](/help/assets/icons/InfoOutline.svg) dans un [tableau à structure libre](#freeform-table).
* Sélectionnez une barre spécifique dans une visualisation [barre](#bar-and-horizontal-bar) ou [barre horizontale](#bar-and-horizontal-bar) ou un point de données dans une visualisation [nuage de points](#scatter).


Les détails suivants s’affichent.

| Prévisualisation de l’expérience | Prévisualisation de la ressource |
|---|---|
| ![Prévisualisation de l’expérience Content Analytics](../assets/aca-experience-preview.png) | ![Prévisualisation de la ressource Content Analytics](../assets/aca-asset-preview.png) |
| Nom de la dimension (par exemple, **[!UICONTROL ID d’expérience])** | Nom de la dimension de ressource (par exemple, **[!UICONTROL ID de ressource])** |
| **[!UICONTROL Impressions (toutes périodes)]** : nombre d’impressions pour l’expérience. | **[!UICONTROL Impressions (toutes périodes)]** : nombre d’impressions pour la ressource. |
| **[!UICONTROL Ressources]** : nombre de ressources que contient cette expérience. <br/>Sélectionnez ![Répartition](/help/assets/icons/Breakdown.svg) **[!UICONTROL Répartition]** pour examiner les ressources. | **[!UICONTROL Expériences]** : nombre d’expériences dans lesquelles cette ressource apparaît. <br/>Sélectionnez ![Répartition](/help/assets/icons/Breakdown.svg) **[!UICONTROL Répartition]** pour examiner les ressources. |
| **[!UICONTROL Première impression]** : date de la première impression de l’expérience. | **[!UICONTROL Première impression]** : date de la première impression de la ressource. |
| **[!UICONTROL Impression la plus récente]** : date de l’impression la plus récente de l’expérience. | **[!UICONTROL Impression la plus récente]** : date de l’impression la plus récente de la ressource. |
| **[!UICONTROL Attributs d’expérience]** : les [attributs](/help/content-analytics/report/components.md#experience-attributes) de l’expérience. | **[!UICONTROL Attributs de ressources]** : les [attributs](/help/content-analytics/report/components.md#asset-attributes) de la ressource. |


## Modèle

Un modèle [template](/help/analysis-workspace/templates/use-templates.md) Content Analytics est disponible pour vous aider à identifier le contenu et les attributs de contenu qui présentent les meilleures performances. Le modèle fait partie du [cas d’utilisation du canal web et de l’engagement](/help/analysis-workspace/templates/use-templates.md#web-engagement) et décrit les performances de votre contenu à un niveau granulaire. Vous pouvez examiner les performances de ressources individuelles ou d’attributs spécifiques.

En fonction de ce que vous apprendrez, vous pourrez effectuer un certain nombre d’opérations, comme promouvoir des ressources hautement performantes sur votre page d’accueil, personnaliser le contenu de segments spécifiques afin d’inclure des attributs hautement performants ou retirer du contenu qui commence à devenir obsolète.

Pour utiliser le modèle :

1. Sélectionnez **[!UICONTROL Workspace]** dans le menu principal.
1. Vérifiez que vous avez sélectionné une vue de données déjà configurée pour Content Analytics.
1. Recherchez ou utilisez des segments (**[!UICONTROL Web]** pour **[!UICONTROL Canal]** et **[!UICONTROL Engagement]** pour **[!UICONTROL Cas d’utilisation]**) pour trouver et sélectionner le modèle **[!UICONTROL Analyse de contenu]**.
1. Sélectionnez **[!UICONTROL Utiliser le modèle]**.
1. Dans la boîte de dialogue **[!UICONTROL Configurer votre modèle]**, sélectionnez une mesure dans la boîte de dialogue **[!UICONTROL Sélectionner une mesure de conversion]**. Par exemple, **[!UICONTROL CTR des ressource]**.
1. Sélectionnez **[!UICONTROL Continuer]**.

Un projet **[!UICONTROL Vue d’ensemble de Content Analytics]** s’ouvre dans [Analysis Workspace](/help/analysis-workspace/home.md). Le projet se compose de quatre [panneaux](/help/analysis-workspace/c-panels/panels.md), où chaque panneau fournit [tableaux à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) et [visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) pour répondre à une question spécifique. Vous pouvez utiliser la répartition **[!UICONTROL Canal de contenu]** pour [répartir](/help/analysis-workspace/c-panels/panels.md#break-down-a-panel) le panneau du canal de contenu qui vous intéresse : **[!UICONTROL web]** ou **[!UICONTROL mobile]**.

Les quatre panneaux sont les suivants :

* **Quel est le contenu le plus performant ?**
Ce panneau identifie les expériences et les ressources qui génèrent l’engagement et la conversion. Les expériences sont des pages web complètes capturées à un moment spécifique ou une combinaison de texte, de ressources et d’appels à l’action définis dans une application mobile.

   * **Expériences**

     >[!NOTE]
     >
     >Ces visualisations ne s’affichent dans votre modèle que lorsque vous avez configuré le système pour [inclure des expériences](/help/content-analytics/config/guided.md#experience-capture-and-definition) dans votre configuration Content Analytics.
     > 

      * **Experience CTR** : visualisation [synthèse des modifications](/help/analysis-workspace/visualizations/summary-number-change.md) qui affiche Experience CTR.
      * **Principales expériences de conversion** : visualisation en [barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) représentant les principales expériences de conversion en fonction de la mesure de conversion sélectionnée.
      * **Expériences les plus performantes** : un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (y compris [miniatures](#thumbnails) et [aperçus](#previews)) pour les expériences les plus performantes.

   * **Ressources**

      * **Taux de clics des ressources**
Visualisation [résumé des modifications](/help/analysis-workspace/visualizations/summary-number-change.md) qui affiche le taux de clics de la ressource.
      * **Principales conversions de ressources**
Visualisation [barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) qui affiche les principales ressources à convertir en fonction de la mesure de conversion sélectionnée.
      * **Ressources les plus performantes**
Un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (comprenant des [miniatures](#thumbnails) et des [aperçus](#previews)) pour les ressources les plus performantes.
Assets - vues par rapport à la conversion.
Visualisation [en graphique de dispersion](/help/analysis-workspace/visualizations/scatterplot.md) qui présente un graphique de dispersion des vues de ressources en fonction des conversions de ressources.

* **Quels sont les attributs de ressources qui contribuent aux conversions ?**
Content Analytics utilise l’IA et GenAI pour affecter automatiquement des métadonnées et des attributs, tels que les objets, les scènes et les couleurs de premier plan, à chaque ressource.

   * **Principaux attributs de ressource de conversion**
Une [barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) qui affiche les attributs de ressource de conversion supérieurs en fonction de la mesure de conversion sélectionnée.
   * **Meilleure conversion des attributs de ressource par rapport aux 30 jours précédents**
Visualisation [barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) qui affiche les principaux attributs de ressource de conversion, par rapport aux 30 jours précédents, en fonction de la mesure de conversion sélectionnée.
   * **Principale conversion des données d’attribut des ressources**
Un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) qui affiche les principaux attributs de conversion en fonction de la mesure de conversion sélectionnée. Sélectionnez une ligne dans le tableau pour mettre à jour la visualisation Tendance des attributs.
   * **Tendance des attributs**
Visualisation [en ligne](/help/analysis-workspace/visualizations/line.md) montrant la tendance de l’attribut de la ressource de conversion la plus élevée sélectionnée.
   * **Couleur de premier plan des ressources**
Exemple [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) qui compare les performances des éléments d’une seule catégorie d’attributs de ressource : Couleurs de premier plan. Vous pouvez remplacer cet attribut de ressource par d’autres dimensions de catégorie d’attributs de ressource.

* **Quels sont les attributs d’expérience qui contribuent aux conversions ?**

  >[!NOTE]
  >
  >Ce panneau s’affiche uniquement lorsque vous avez [inclus des expériences](/help/content-analytics/config/guided.md#experience-capture-and-definition) dans votre configuration Content Analytics.
  > 

  Alors que les attributs de ressource se concentrent sur les qualités visuelles des images, les attributs d’expérience se concentrent sur le texte de votre page. Les visualisations ci-dessous vous permettent de découvrir quels attributs d’expérience contribuent à la conversion. Ces attributs sont également automatiquement affectés à l’aide des modèles d’IA et GenAI.

  Le panneau se compose des visualisations suivantes :

   * **Principaux attributs d’expérience de conversion**
Visualisation [barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) qui affiche les attributs d’expérience de conversion supérieurs en fonction de la mesure de conversion sélectionnée.
Principaux attributs d’expérience de conversion par rapport aux 30 jours précédents
Visualisation [barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) qui affiche les principaux attributs d’expérience de conversion, par rapport aux 30 jours précédents, en fonction de la mesure de conversion sélectionnée.
   * **Top conversion des données d’attribut d’expérience**
Un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) qui affiche les principales expériences de conversion en fonction de la mesure de conversion sélectionnée. Sélectionnez une ligne dans le tableau pour mettre à jour la visualisation en lignes.
   * **Ligne**
Visualisation [en ligne](/help/analysis-workspace/visualizations/line.md) montrant la tendance de l’attribut d’expérience de conversion le plus élevé sélectionné.
   * **Mots-clés d’expérience**
Un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) présentant les principaux mots-clés d’expérience en fonction de la mesure de conversion sélectionnée.

* **Où les ressources apparaissent-elles sur mon site ?**
Ce tableau à structure libre détaille l’emplacement des ressources les plus consultées. Utilisez cette analyse pour identifier les pages hautement performantes et optimiser l’emplacement des ressources.

   * **Où les ressources les plus consultées apparaissent-elles ?**
Vous pouvez ventiler n’importe quelle ressource par dimension afin de mieux comprendre où cette image s’affiche.

     Dans l’exemple de [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (comprenant des [miniatures](#thumbnails) et des [prévisualisations](#previews)), **[!UICONTROL ID de perception de ressource]** est utilisé à la place de [!UICONTROL ID de ressource]. Parfois, la même image peut être dupliquée sur votre site avec une autre URL d’image. L’attribut [!UICONTROL ID de perception de ressource] permet de regrouper ces doublons sous un seul ID.

     Étant donné que les ressources peuvent changer sur une page, le système répartit chaque ressource par **[!UICONTROL Experience Id]** afin d’identifier la version de la page où la ressource s’est affichée. Vous pouvez remplacer l’[!UICONTROL ID d’expérience] par d’autres dimensions qui vous permettant de déterminer l’emplacement d’une ressource sur votre site. Par exemple, [!UICONTROL Nom de la page], [!UICONTROL URL de la page] ou [!UICONTROL Section du site].

     Vous pouvez également remplacer l’[!UICONTROL ID de perception de ressource] par l’[!UICONTROL ID de ressource] pour obtenir un enregistrement de l’emplacement où des URL d’images spécifiques sont référencées.


>[!MORELIKETHIS]
>
>[Composants Content Analytics](components.md)
>[Utiliser des modèles](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
