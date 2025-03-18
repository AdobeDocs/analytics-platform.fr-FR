---
title: Rapports Content Analytics
description: Comment créer des rapports sur Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: df3a877feed82f6cbd181561da68837373bdafb8
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 0%

---

# Rapports Content Analytics - Aperçu

>[!WARNING]
>
>Cet article est un avant-projet non officiel d’une version finale à venir et fait partie de la documentation de Content Analytics. Tout le contenu est sujet à modification et aucune obligation légale quelle qu&#39;elle soit ne peut être dérivée de la version actuelle de cet article.
>

{{release-limited-testing}}

La création de rapports sur les analyses de contenu s’effectue dans Analysis Workspace. Un modèle Workspace [template](#template) spécifique est disponible afin que vous puissiez immédiatement accéder à un projet Workspace prérempli avec des informations pertinentes sur le contenu.

Pour créer entièrement des rapports sur Content Analytics :

1. [Créez un projet](/help/analysis-workspace/build-workspace-project/create-projects.md) ou [ouvrez un projet existant](/help/analysis-workspace/build-workspace-project/open-projects.md) dans Workspace.
1. Veillez à [sélectionner une vue de données](/help/analysis-workspace/c-panels/panels.md#data-view) pour les rapports Content Analytics. La création de rapports Content Analytics n’est disponible que pour les vues de données [configurées](/help/content-analytics/config/configuration.md) pour Content Analytics.
1. Faites glisser une visualisation ![Tableau](/help/assets/icons/Table.svg) [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) sur la zone de travail.
1. Utilisez des [composants Content Analytics spécifiques](components.md) et d’autres [composants génériques](/help/components/overview.md) (tels que les filtres, les périodes, les annotations) pour créer vos informations d’analyse de contenu. Vous pouvez également utiliser le [modèle d’analyse de contenu](#template).

## Miniatures

En fonction des dimensions spécifiques à Content Analytics que vous utilisez dans votre projet, des miniatures s’affichent pour les ressources et les dimensions.

![Miniatures Content Analytics](../assets/aca-thumbnails.png)

## Prévisualisations

Pour les dimensions qui comportent des miniatures (comme le nom de la ressource, le nom de l’expérience, etc.), vous pouvez ouvrir une fenêtre contextuelle d’aperçu.

Pour ouvrir l’aperçu avec les détails suivants :

* Sélectionnez ![ InfoOutline ](/help/assets/icons/InfoOutline.svg). Les détails suivants s’affichent.

  | Aperçu de l’expérience | Aperçu des ressources |
  |---|---|
  | ![Aperçu de l’expérience Content Analytics](../assets/aca-experience-preview.png) | ![Aperçu de la ressource Content Analytics](../assets/aca-asset-preview.png) |
  | **[!UICONTROL Nom de l’expérience]** | **[!UICONTROL Nom de la ressource]** |
  | **[!UICONTROL Impressions (toutes les heures)]** : nombre d’impressions pour l’expérience. | **[!UICONTROL Impressions (toutes les fois)]** : nombre d’impressions de la ressource. |
  | **[!UICONTROL Assets]** : nombre de ressources que contient cette expérience. Sélectionnez ![Répartition](/help/assets/icons/Breakdown.svg) **[!UICONTROL Répartition]** pour examiner les ressources. | **[!UICONTROL Expériences]** : nombre d’expériences dans lesquelles cette ressource est affichée. ![Répartition](/help/assets/icons/Breakdown.svg) **[!UICONTROL Répartition]** pour inspecter les ressources. |
  | **[!UICONTROL Première impression]** : date de la première impression de l’expérience. | **[!UICONTROL Première impression]** : date de la première impression de la ressource. |
  | **[!UICONTROL Dernière impression]** : date de la dernière impression de l’expérience. | **[!UICONTROL Impression la plus récente]** : date de l’impression la plus récente de la ressource. |
  | **[!UICONTROL Attributs d’expérience]** : attributs de l’expérience. | **[!UICONTROL Attributs de ressource]** : les attributs de la ressource. |


## Modèle

Un modèle d’analyse de contenu [template](/help/analysis-workspace/templates/use-templates.md) est disponible pour vous aider à identifier le contenu et les attributs de contenu qui présentent les meilleures performances. Le modèle fait partie du [cas d’utilisation du canal web et de l’engagement](/help/analysis-workspace/templates/use-templates.md#web-engagement) et décrit les performances de votre contenu à un niveau granulaire. Vous pouvez examiner les performances de ressources individuelles ou d’attributs spécifiques.

Selon ce que vous apprendrez, vous pourriez faire un certain nombre de choses. Comme promouvoir des ressources hautement performantes sur votre page d’accueil, personnaliser le contenu pour des segments spécifiques afin d’inclure des attributs hautement performants ou faire pivoter le contenu qui a commencé à devenir obsolète.

Pour utiliser le modèle :

1. Sélectionnez **[!UICONTROL Workspace]** dans le menu principal.
1. Assurez-vous d’avoir sélectionné une vue de données configurée pour Content Analytics.
1. Recherchez ou utilisez des filtres (**[!UICONTROL Web]** pour **[!UICONTROL Canal]** et **[!UICONTROL Engagement]** pour **[!UICONTROL Cas d’utilisation]**s) pour rechercher et sélectionner le modèle **[!UICONTROL Analyse de contenu]**.
1. Sélectionnez **[!UICONTROL Utiliser le modèle]**.
1. Dans la boîte de dialogue **[!UICONTROL Configurer votre modèle]**, sélectionnez une mesure dans la boîte de dialogue **[!UICONTROL Sélectionner une mesure de conversion]**. Par exemple, **[!UICONTROL CTR de ressource]**.
1. Sélectionnez **[!UICONTROL Continuer]**.

Un projet **[!UICONTROL Présentation de Content Analytics]** s’ouvre dans Workspace. Le projet se compose de quatre groupes d&#39;experts qui répondent chacun à des questions précises :

* **Quel contenu est le plus performant ?**
Ce panneau vous aide à comprendre quelles expériences et quelles ressources de ces expériences génèrent de l’engagement et de la conversion. Les expériences sont une page web complète, capturée à un moment spécifique. Une expérience peut contenir du texte et plusieurs ressources d’image individuelles. Une ressource est une image individuelle.

  Le panneau se compose des visualisations suivantes :

   * **Expériences**

      * **Experience CTR** : une visualisation de synthèse des modifications, qui affiche Experience CTR.
      * **Principales expériences de conversion** : visualisation sous forme de graphique à barres horizontales présentant les principales expériences de conversion en fonction de la mesure de conversion sélectionnée.
      * **Expériences les plus performantes** : tableau à structure libre (comprenant des miniatures et des aperçus) pour les expériences les plus performantes.

   * **Assets**

      * **Taux de clics des ressources**
Visualisation [résumé des modifications](/help/analysis-workspace/visualizations/summary-number-change.md) qui affiche le taux de clics de la ressource.
      * **Top conversion des ressources**
Visualisation [barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) qui affiche les principales ressources à convertir en fonction de la mesure de conversion sélectionnée.
      * **Ressources les plus performantes**
Un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (comprenant des [miniatures](#thumbnails) et des [aperçus](#previews)) pour les ressources les plus performantes.
      * **Assets - vues ou conversion.**
Visualisation [en graphique de dispersion](/help/analysis-workspace/visualizations/scatterplot.md) qui présente un graphique de dispersion des vues de ressources en fonction des conversions de ressources.

* **Quels attributs de ressource contribuent aux conversions ?**
Content Analytics utilise l’IA et GenAI pour affecter automatiquement chaque métadonnée de ressource, comme les sujets, les scènes, les couleurs de premier plan, etc. Un attribut est une balise de métadonnées affectée par l’IA décrivant le contenu d’une ressource ou d’une expérience. Par exemple : <code>couleur de premier plan : rouge</code> est un attribut affecté automatiquement. Les visualisations vous aident à identifier les attributs de vos ressources qui contribuent le plus à la conversion.

  Le panneau se compose des visualisations suivantes :

   * **Top conversion des attributs de ressources**
Une [barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) qui affiche les attributs de ressource de conversion supérieurs en fonction de la mesure de conversion sélectionnée.
   * **Meilleure conversion des attributs de ressources par rapport aux 30 jours précédents**
Visualisation [barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) qui affiche les principaux attributs de ressource de conversion, par rapport aux 30 jours précédents, en fonction de la mesure de conversion sélectionnée.
   * **Top conversion des données d’attribut de ressources**
Un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) qui affiche les principaux attributs de conversion en fonction de la mesure de conversion sélectionnée. Sélectionnez une ligne dans le tableau pour mettre à jour la visualisation Tendance des attributs .
   * **Tendance des attributs**
Visualisation [en ligne](/help/analysis-workspace/visualizations/line.md) montrant la tendance de l’attribut sélectionné pour le premier attribut de ressources de conversion.
   * **Couleur de premier plan de la ressource**
Exemple [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) qui compare les performances des éléments d’une seule catégorie d’attributs de ressource : Couleurs de premier plan. Vous pouvez remplacer cet attribut de ressource par d’autres dimensions de catégorie d’attributs de ressource.

* **Quels attributs d’expérience contribuent aux conversions ?**
Alors que les attributs de ressource se concentrent sur les qualités visuelles des images, les attributs d’expérience se concentrent sur le texte de votre page. Les visualisations ci-dessous vous permettent de découvrir quels attributs d’expérience contribuent à la conversion. Ces attributs sont également automatiquement attribués à l’aide des modèles AI et GenAI.

  Le panneau se compose des visualisations suivantes :

   * **Top conversion des attributs d’expérience**
Visualisation [barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) qui affiche les attributs d’expérience de conversion supérieurs en fonction de la mesure de conversion sélectionnée.
   * **Principaux attributs d’expérience de conversion par rapport aux 30 jours précédents**
Visualisation [barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) qui affiche les principaux attributs d’expérience de conversion, par rapport aux 30 jours précédents, en fonction de la mesure de conversion sélectionnée.
   * **Top conversion des données d’attribut d’expérience**
Un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) qui affiche les principales expériences de conversion en fonction de la mesure de conversion sélectionnée. Sélectionnez une ligne dans le tableau pour mettre à jour la visualisation Ligne.
   * **Ligne**
Visualisation [en ligne](/help/analysis-workspace/visualizations/line.md) montrant la tendance de l’attribut d’expérience de conversion le plus élevé sélectionné.
   * **Mots-clés Experience**
Un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) présentant les principaux mots-clés d’expérience en fonction de la mesure de conversion sélectionnée.

* **Où les ressources apparaissent-elles sur mon site ?**
Panneau composé d’un tableau à structure libre qui détaille l’emplacement où les ressources les plus vues apparaissent sur votre site.

  Le panneau se compose d’une visualisation :

   * **Où les ressources les plus consultées apparaissent-elles ?**
Vous pouvez ventiler n’importe quel ID de ressource selon des dimensions qui vous aident à mieux comprendre où cette image s’affiche.

     Dans cet exemple [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (y compris [miniatures](#thumbnails) et [aperçus](#previews)), [!UICONTROL *ID de perception de la ressource*] est utilisé à la place de [!UICONTROL *ID de ressource*]. Parfois, la même image peut être dupliquée sur votre site avec une autre URL d’image. L’attribut [!UICONTROL _Asset Perception_] permet de regrouper ces doublons sous un seul identifiant. Étant donné que les ressources peuvent changer sur une page, chaque ressource est répartie par [!UICONTROL _Experience ID_], afin d’identifier la version de cette page sur laquelle elle est apparue.

     Vous pouvez remplacer [!UICONTROL _Experience ID_] par d’autres dimensions qui vous aident à comprendre l’emplacement d’une ressource sur votre site. Par exemple, [!UICONTROL _Nom de la page_], [!UICONTROL _URL de la page_] ou [!UICONTROL _Section du site_].

     Vous pouvez également remplacer [!UICONTROL _ID de perception_] par [!UICONTROL _ID de ressource_] pour obtenir un enregistrement de l’emplacement de référence des URL d’image spécifiques.


>[!MORELIKETHIS]
>
>[Composants Content Analytics](components.md)
>[Utilisez des modèles](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
