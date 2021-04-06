---
description: Créez un projet et ajoutez des composants (dimensions, mesures, filtres, plages de dates) au panneau à structure libre.
keywords: Analysis Workspace
title: Création d’un projet Workspace
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 86%

---


# Création d’un projet Workspace

Créez un projet et ajoutez des composants (dimensions, mesures, filtres, plages de dates) au panneau à structure libre.

Cet article présente les éléments d’Analysis Workspace et explique comment créer un projet.

## Création d’un projet

1. Spécifiez les autorisations de création et de traitement des projets de l’utilisateur.

   Avant de créer ou de traiter un projet Analysis Workspace, les administrateurs doivent vous ajouter à un groupe avec l’autorisation **[!UICONTROL Créer/Traiter les projets dans Analysis Workspace]** activée ou au groupe d’utilisateurs **[!UICONTROL Accès à tous les rapports]**. (**[!UICONTROL Administration]** > **[!UICONTROL Gestion utilisateur]** > [Groupes](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=fr-FR)).

1. Dans [!DNL Experience Cloud], cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**.

   ![](assets/analysis_workspace_menu.png)

   Vous pouvez également entrer une barre oblique (/) afin d’ouvrir la barre de recherche des rapports, puis entrer *`workspace`*.

   ![](assets/analysis-app-search.png)

1. Cliquez sur **[!UICONTROL Créer un projet]**.

   Vous pouvez créer un projet d’après :

* un projet vierge (par défaut). Pour obtenir des instructions, voir ci-dessous.
* d’un modèle personnalisé. Les utilisateurs dotés de droits d’administration peuvent créer ces modèles.

   ![](assets/start_modal.png)

1. Pour créer un projet à partir d’un projet vierge, cliquez sur **[!UICONTROL Projet vierge]**.

   * Cliquez ensuite sur **[!UICONTROL Créer]**, ou
   * cliquez simplement sur **[!UICONTROL Entrée]**.

   Un projet vierge s’affiche, avec un panneau à structure libre et une visualisation de tableau de données.

   ![](assets/fa_project_new.png)

<table id="table_3989E45D9D4241CBB2E58B29DA257B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/analysis-workspace-components.md"  > Composants</a> </td> 
   <td colname="col2"> <p>Dimensions, mesures, filtres et plages de dates que vous pouvez faire glisser dans les projets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > Visualisations</a> </td> 
   <td colname="col2"> <p>Éléments que vous pouvez faire glisser sur le panneau ou les zones du projet dans l’interface. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md"  > Panneau à structure libre</a> </td> 
   <td colname="col2"> <p>Trame ou espace de travail avec lequel vous interagissez dans Analysis Workspace. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Enregistrez le projet. Nommez-le, décrivez-le (facultatif, mais utile), balisez-le (facultatif), puis cliquez sur **[!UICONTROL Enregistrer le projet]**.

   ![](assets/save_project.png)

1. Désormais, vous pouvez cliquer avec le bouton droit de la souris sur une visualisation ou un panneau pour le copier, puis le coller (« insérer ») à un autre emplacement du projet ou dans un autre projet.

   Utilisez cette fonction pour créer des blocs de construction (visualisations ou panneaux prédéfinis) qui pourront être copiés dans d’autres projets afin de démarrer plus rapidement, avec des données spécifiques à votre entreprise.

   >[!NOTE]
   >
   >Une fois que le projet a été copié/enregistré sous, les liens internes appartiennent alors au projet dans lequel ils apparaissent et non plus au projet d’origine à partir duquel ils ont été copiés.

## Ajouter des composants et des visualisations {#task_CDAC9B3007BE4A3790AFAD3746D669B1}

1. Créez votre projet en faisant glisser *`components`* et *`visualizations`* vers le projet.

   **Composants**

   La barre d’outils Composant affiche les dimensions, mesures, filtres et plages de dates pouvant faire l’objet de recherches que vous utilisez le plus souvent.

<table id="table_4626163E26DE46CB86391868BBA3AD32"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Composant </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensions (orange) </td> 
   <td colname="col2"> <p>Appliquez-les au niveau du projet. </p> <p><img  src="assets/dimensions.png" id="image_353BAF1A7AC04C7DB5F5CDFDE7614402" align="left" placement="break" width="300px" /> </p> <p>Les dimensions Prop#, eVar# et event# sont ajoutées aux noms des dimensions et vous pouvez en rechercher les numéros. Exemple : « Campagne interne » apparaît dans le rail de gauche comme « Campagne interne (evar2) ». </p> <p> Notez que les numéros des dimensions prop, eVar et event n’apparaissent pas dans le tableau (afin de conserver des titres courts). </p> <p>Il existe un ordre de classement par défaut pour certaines dimensions prêtes à l’emploi lorsqu’elles sont déposées dans un tableau à structure libre ou lorsqu’elles s’affichent dans le rail de gauche. Par exemple, lorsque la dimension « Heure du jour » est déposée dans un tableau ou affichée dans le rail de gauche, elle est triée par heure, de 00h à 23h. Vous avez toujours la possibilité de les classer en fonction de n’importe quelle colonne de mesures. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mesures (vert) </td> 
   <td colname="col2"> <p>Appliquez-les au niveau du projet. </p> <p><img  src="assets/metrics.png" id="image_7C874C72992E414CBEE6B90CEF7B9F3C" /> </p> <p> <span class="term"> Occurrences</span> est la mesure par défaut pour le tableau de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtres (bleu) </td> 
   <td colname="col2"> <p>Vous pouvez les faire glisser uniquement au niveau du panneau, mais vous pouvez créer des filtres intégrés dans le tableau de données. </p> <p><img  src="assets/segments.png" id="image_5674B18BC3AB47A2B1FEE584E0FBF47C" /> </p> <p>Voir les Filtres <a href="/help/analysis-workspace/components/t-freeform-project-segment.md"  > </a> pour plus d'informations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plages de dates et granularités (violet) </td> 
   <td colname="col2"> <p>Vous pouvez les faire glisser uniquement au niveau du panneau. Vous pouvez créer un projet à partir du calendrier, lorsque vous configurez une plage de dates. </p> <p><img  src="assets/date-ranges.png" id="image_A1750DA921234AD0BB02166865EB8FCC" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

**[Visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)**

Le panneau [!UICONTROL Visualisations] fournit des graphiques, des diagrammes, des anneaux, des tableaux de données,  des tableaux de [cohortes](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), des diagrammes de Venn, etc. Vous pouvez faire glisser-déposer plusieurs visualisations sur votre projet.

![Résultat de l’étape](assets/visualizations.png)

![](assets/fa_full_panel.png)

1. Étape

## Utilisez le menu contextuel pour personnaliser vos données {#concept_8117C300F21843B99F4E1B9AB7B11B6F}

Grâce au menu contextuel, vous pouvez exécuter les actions suivantes, selon la cellule du tableau dans laquelle vous cliquez avec le bouton droit.

![Résultat de l’étape](assets/fa_data_table_actions.png)

<table id="table_0F84CC5B604D4D41BD0C9668DF525929"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Action </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Ajout d’une colonne de période</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Comparaison de périodes</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copier dans le Presse-papiers </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Supprimer la sélection </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-alerts/intellligent-alerts.md"  > Création d’une alerte d’après la sélection</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/dimensions/t-breakdown-fa.md"  > Ventilation</a> 
    <ul id="ul_18C83B8514AD4C1C86C071AA8402CB5C"> 
     <li id="li_6CA84ED293EA4940A7495DA9D9121264">Dimensions </li> 
     <li id="li_EA16EE017B2E4A6998918706938A21BF">Mesures </li> 
     <li id="li_0405D339CD01405DB508A7D8D1A976B4">Filtres </li> 
     <li id="li_819CE81C552F49BB9C1B83ED3B42C5F7">Heure </li> 
    </ul> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > Visualisation</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/curate-share/download-send.md"  > Téléchargement au format CSV</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/home.md"  > Sélection de tendances</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/t-freeform-project-segment.md"  > Création d’un filtre d’après une sélection</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Afficher uniquement les lignes sélectionnées </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Afficher toutes les lignes </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

Voir [Interactions clavier-souris dans Analysis Workspace](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) pour obtenir des informations sur la copie et la sélection de lignes.
