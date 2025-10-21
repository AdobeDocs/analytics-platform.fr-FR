---
description: Découvrez comment générer des présentations au format pptx à partir de rapports Workspace.
keywords: Analysis Workspace
title: Génération de présentations à partir de rapports Workspace
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: f6e64e850b8c416817b76697d869c10adb9b544b
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 4%

---

# Storytelling de données : génération de présentations de diapositives à partir de rapports Workspace {#generate-powerpoint}

Les utilisateurs disposant [des autorisations nécessaires](#permission-requirements-to-generate-slides) peuvent générer automatiquement des présentations .pptx à partir de projets Analysis Workspace. Lors de la génération de ces présentations de diapositives, Customer Journey Analytics crée automatiquement une histoire à partir de vos données en identifiant les informations clés et en les convertissant en diapositives prêtes pour les parties prenantes.

Cette histoire de données générée automatiquement réduit le temps, les efforts et l’expertise requis pour rechercher des résultats dans un projet Workspace. Les analystes peuvent se concentrer davantage sur l’exploration des données, tout en permettant à Customer Journey Analytics de créer et de formater le récit exécutif et de communiquer l’impact commercial aux parties prenantes.

## Comprendre les histoires de données dans les présentations de diapositives

Analysis Workspace utilise l’IA générative pour créer un récit basé sur vos données Workspace, dans un format de présentation des diapositives.

Les sections suivantes décrivent la valeur supplémentaire apportée par les histoires de données, les éléments nécessaires d’un projet qui contribuent à façonner le récit et les éléments clés inclus dans chaque sortie de présentation.

### Valeur supplémentaire fournie par les histoires de données

Les histoires de données apportent de la valeur et des informations à un projet Workspace en rendant les données accessibles aux utilisateurs et utilisatrices qui ont moins d’expérience en analyse de données.

Les histoires de données complètent une analyse pour un projet Workspace donné en :

* Ajout d’un contexte

* Mise en évidence d’informations importantes

* Fournir des conseils sur la validité des données dans un contexte donné

* Évaluer si certaines variables sont sous-évaluées ou surévaluées.

* Signaler des tendances cachées, des anomalies et d’autres facteurs contributifs

* Identification des principaux moteurs

* Suggérer des étapes à suivre

### Éléments de projet qui façonnent les histoires de données

Analysis Workspace crée des histoires de données en tenant compte des éléments de projet suivants :

* Relations interdimensionnelles et intermétriques

* Les éléments individuels qui forment la base de l’analyse : dimensions, mesures, filtres, structure des tableaux à structure libre, visualisations et panneaux

* Les noms donnés aux panneaux, tableaux et visualisations

* Ordre des mesures dans un tableau à structure libre (pour déterminer la priorité)

* Synthèse des chiffres et synthèse des textes (pour déterminer les mesures qui doivent être mises en évidence dans le récit des données)

### Éléments de présentation d’une histoire de données

Les histoires de données se composent d’un résumé exécutif, de diapositives détaillées et de séparateurs de section.

**Résumé analytique :** donne la priorité aux informations les plus précieuses et rédige une histoire globale d’une durée comprise entre 1 et 5 phrases.

**Diapositives détaillées :** génère des informations relatives aux tableaux, panneaux ou visualisations d’un projet Workspace. Les informations se composent de tendances, de saisons, d’anomalies et de corrélations.

**Diviseurs de section :** divise les informations avec des séparateurs de section nommés et placés de manière appropriée.

## Générer une présentation .pptx basée sur un projet Workspace

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-powerpoint-include-visualizations"
>title="Panneaux et visualisations inclus"
>abstract="Choisissez les panneaux et les visualisations que vous souhaitez inclure dans la présentation. Vous pouvez inclure jusqu’à 50 visualisations."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-presentation-emphasized-components"
>title="Composants mis en évidence"
>abstract="Sélectionnez jusqu’à 5 mesures et 5 dimensions dans vos visualisations, sur lesquelles vous souhaitez mettre l’accent dans la présentation. Les mesures que vous choisissez s’affichent en italique, les dimensions en gras et les éléments de dimension en contraste de couleur."

<!-- markdownlint-enable MD034 -->

1. Accédez au projet Workspace qui contient les données que vous souhaitez utiliser comme base de votre présentation de diapositives.

1. Sélectionnez **[!UICONTROL Générer des diapositives]** dans le coin supérieur droit de la page.

   La boîte de dialogue Générer des diapositives s’affiche.

   ![Boîte de dialogue Générer des diapositives](assets/generate-slides.png)

1. Indiquez les informations suivantes :

   | Option | Description |
   |---------|----------|
   | **[!UICONTROL Titre de la couverture]** | Indiquez un titre pour la présentation. Ce titre s&#39;affiche sur la diapositive de titre de la présentation. |
   | **[!UICONTROL Inclure le nom du présentateur]** | Spécifiez le nom du présentateur. Ce nom apparaît sur la diapositive de titre de la présentation, sous le titre de couverture. |
   | **[!UICONTROL Panneaux et visualisations à inclure]** | Choisissez les panneaux et la visualisation à inclure dans la présentation. Vous pouvez inclure jusqu’à 50 visualisations.<p>La plupart des panneaux et des visualisations sont pris en charge. Pour plus d’informations sur les panneaux et les visualisations non pris en charge, voir [Éléments et fonctionnalités de projet non pris en charge](#unsupported-project-elements-and-features).</p> |
   | **[!UICONTROL Descriptions des panneaux et des visualisations]** | |
   | **[!UICONTROL Annotations]** | |
   | **[!UICONTROL Mettre en gras les composants]** | Sélectionnez jusqu’à 5 mesures et 5 dimensions dans vos visualisations, sur lesquelles vous souhaitez mettre l’accent dans la présentation.<p>Lorsque aucun accent n’est mis, les composants s’affichent dans les présentations comme suit :<ul><li>**Mesures et dimensions :** italique</li><li>**Éléments Dimension :** guillemets</li></ul></p><p>Lorsque l’accent est mis, les composants s’affichent dans les présentations comme suit :</p><ul><li>**Mesures et dimensions :** italiques et gras</li><li>**Éléments Dimension :** gras lorsque la dimension correspondante est mise en évidence<p>Une couleur est également appliquée à l’élément de dimension lorsque celui-ci est mis en surbrillance dans le graphique.</p></li></ul> |

1. (Conditionnel) Sélectionnez **[!UICONTROL Thème par défaut]** si vous souhaitez générer rapidement des diapositives en moins d’étapes et si aucun thème d’entreprise n’est requis pour votre présentation de diapositives.

   Il vous suffit de choisir le thème de couleur de votre présentation en sélectionnant la couleur souhaitée.

   ![Générer des diapositives avec le thème par défaut](assets/generate-slides-default-theme.png)

1. (Conditionnel) Sélectionnez **[!UICONTROL Charger le modèle]** si la présentation des diapositives doit correspondre à un thème d’entreprise. Cette option nécessite de charger un modèle personnalisé et d’appliquer vos styles personnalisés.

   ![Générer des diapositives avec un modèle personnalisé](assets/generate-slides-upload-template.png)

   Pour charger un modèle personnalisé, effectuez l’une des opérations suivantes :

   * (Recommandé) Téléchargez un modèle vierge et modifiez-le.

      1. Téléchargez ce modèle vierge. <!--add link-->

      1. Appliquez vos styles personnalisés au modèle vierge.

      1. Chargez à nouveau le modèle sans modifier le nom de la disposition principale.

   * Chargez directement un modèle personnalisé.

      1. À partir de votre système de fichiers, faites glisser votre modèle personnalisé vers la zone de dépôt.

         Ou

         Sélectionnez **[!UICONTROL Parcourir]**, puis recherchez et sélectionnez votre modèle personnalisé dans le système de fichiers.

         Assurez-vous que le fichier chargé contient des dispositions principales avec les noms suivants : « Title_Slide », « Section_Divider », « Title_Text », « Title_Chart », « Title_Two_Content_Mixed », « Title_Three_Content_Mixed »

         Les fichiers .pptx et .potx d’une taille maximale de 25 Mo sont pris en charge.

1. Sélectionnez **[!UICONTROL Exporter PPT]**.

1. (Recommandé) Passez en revue et modifiez la présentation .ppt et apportez les modifications nécessaires, comme décrit dans la section suivante, [Modifier les diapositives d&#39;une présentation générée précédemment](#edit-slides-from-a-previously-generated-presentation).

## Modifier les diapositives d&#39;une présentation générée précédemment


## Télécharger une présentation .pptx générée



## Exigences d’autorisation pour générer des diapositives

>[!AVAILABILITY]
>
>Si votre entreprise ne dispose pas de l’accès nécessaire pour générer des présentations de diapositives à partir d’un projet Workspace, contactez votre représentant de compte Adobe pour en savoir plus sur les licences.
>
>Cette fonctionnalité est activée par défaut pour tous les utilisateurs des organisations qui disposent des licences requises.

Les administrateurs de profil de produit dont les organisations disposent d’une licence pour générer des diapositives peuvent désactiver l’accès si nécessaire.

Dans [!UICONTROL Adobe Admin Console], l&#39;autorisation [!UICONTROL Outils de création de rapports] **[!UICONTROL storytelling de données]** détermine l&#39;accès à cette fonctionnalité. Un [administrateur de profil de produit](https://helpx.adobe.com/fr/enterprise/using/manage-product-profiles.html) doit suivre les étapes suivantes dans [!UICONTROL Admin Console] s’il souhaite désactiver l’accès :
1. Accédez à **[!UICONTROL Admin Console]** > **[!UICONTROL Produits et services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Profils de produit]**.
1. Sélectionnez le titre du profil de produit pour lequel vous souhaitez fournir l’accès à [!UICONTROL Data storytelling].
1. Dans le profil de produit spécifique, sélectionnez **[!UICONTROL Autorisations]**.
1. Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) pour modifier les **[!UICONTROL Outils de création des rapports]**.
1. Sélectionnez ![AddCircle](/help/assets/icons/RemoveCircle.svg) pour supprimer **Data storytelling** des **[!UICONTROL Éléments d’autorisation inclus]**.

   <!--add screenshot of permission in the admin console-->

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les autorisations.

Pour plus d’informations, voir [Accès au niveau de l’utilisateur](/help/technotes/access-control.md#user-level-access) dans [Contrôle d’accès](/help/technotes/access-control.md#access-control).

## Éléments et fonctionnalités de projet non pris en charge {#unsupported}

Les éléments et fonctionnalités Analysis Workspace suivants utilisés dans un projet ne sont pas pris en charge lors de la génération de diapositives :

* Panneau d’attribution

  Ce panneau s’affiche en grisé lorsque les options de configuration s’affichent.

  Tous les autres panneaux peuvent être inclus dans les diapositives générées à partir d’un projet Workspace.

* Quelques visualisations

  La plupart des visualisations peuvent être incluses dans les diapositives générées à partir d’un projet Workspace. Toutefois, les visualisations suivantes ne peuvent pas être incluses et s’affichent en grisé lorsque les options de configuration sont affichées :

   * Table de cohorte

   * Zone de travail de parcours

   * Puces

   * Combo

   * Nuage de points

   * Plan en arborescence

* Répartitions

* Analyses guidées


