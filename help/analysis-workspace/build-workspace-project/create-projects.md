---
description: Découvrir comment créer un projet dans Analysis Workspace
title: Créer des projets
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 41%

---

# Créer des projets {#create-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_countrepeatinstances"
>title="Compter les instances répétées"
>abstract="Ce paramètre indique si les instances répétées sont comptabilisées dans les rapports.<br/><br/>Remarque : ce paramètre ne s’applique pas aux visualisations Flux ou Abandons."

<!-- markdownlint-enable MD034 -->


[Projets](/help/analysis-workspace/build-workspace-project/freeform-overview.md) dans Analysis Workspace vous permet de créer et d’afficher des analyses critiques.  Ces analyses peuvent être partagées avec des parties prenantes à l’intérieur ou à l’extérieur de votre organisation.

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Workspace]**.

1. Sélectionnez **[!UICONTROL Projets]** dans le panneau de gauche, puis **[!UICONTROL Créer un projet]**.

1. Sélectionnez **Projet Workspace vierge** pour créer votre projet Workspace à l’aide d’un navigateur.

   Pour plus d’informations sur la création d’un projet de Fiche d’évaluation mobile que vous pouvez partager avec d’autres parties prenantes à l’aide d’une application mobile, voir [Fiche d’évaluation mobile vierge](/help/mobile-app/curator.md) . Voir [Analyse guidée](/help/guided-analysis/overview.md) pour plus d’informations sur les différentes options disponibles pour créer votre projet d’analyse guidée.

1. Sélectionnez [!UICONTROL **Créer**].


Maintenant que vous avez créé un projet Workspace vierge, assurez-vous de connaître l’interface utilisateur [Analysis Workspace](/help/analysis-workspace/home.md). Une fois que vous l’avez fait, vous pouvez créer votre projet. Pour ce faire, procédez comme suit :

![Exemple de projet](assets/example-project.png)

* Ajoutez [panneaux](/help/analysis-workspace/c-panels/panels.md) à votre projet. Par exemple, le **[!DNL Example Panel]**.

* Ajoutez des [visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) à vos panneaux. Par exemple :
   * **[!DNL Line Graph]** [Ligne](/help/analysis-workspace/visualizations/line.md) Visualisation
   * **[!DNL Countries]** [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) tableau de visualisation
* Ajoutez des [composants](/help/components/overview.md) à vos visualisations. Par exemple :
   * **[!DNL Store Country]** [dimension](/help/components/dimensions/overview.md) standard
   * **[!DNL People]** [metric](/help/components/apply-create-metrics.md) 
   * **[!DNL Avg Order Value]** [mesure calculée](/help/components/calc-metrics/calc-metr-overview.md) ➏
   * **[!DNL Mobile App Sessions]** [filter](/help/components/filters/filters-overview.md) ➐
   * **[!DNL Last Month]** [période](/help/components/date-ranges/overview.md) ➑
   * **[!DNL Example]** [annotation](/help/components/annotations/overview.md) ➒


## Informations et paramètres du projet {#project-info-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_repeatinstances"
>title="Compter les instances répétées"
>abstract="Ce paramètre indique si les instances répétées sont comptabilisées dans les rapports.<br/>Remarque : ce paramètre ne s’applique pas aux visualisations Flux ou Abandons."

<!-- markdownlint-enable MD034 -->


Les paramètres du projet fournissent des informations sur le projet actuellement actif.

![Fenêtre Informations et paramètres du projet.](./assets/projectinfo.png)

Les paramètres incluent :

| Paramètre | Description |
|---|---|
| Nom du projet | Nom donné au projet. Double-cliquez dessus pour le modifier. |
| Propriétaire | Nom du titulaire du projet. |
| Dernière modification | Date de la dernière modification du projet. |
| Balises | Répertorie les balises appliquées à un projet afin de faciliter la catégorisation. |
| Description | Une description est utile pour clarifier l’objet d’un projet. Double-cliquez dessus pour la modifier. |
| Compter les instances répétées | Indiquez si les instances répétées sont comptabilisées dans les rapports. Remarque : ce paramètre ne s’applique pas aux visualisations de flux ou d’abandons. |
| Afficher les annotations | Indiquez si les annotations s’affichent pour ce projet ou non. |
| [Palette de couleurs du projet](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Vous pouvez modifier la palette de couleurs catégoriques utilisée dans Workspace en choisissant parmi les palettes prêtes à l’emploi qui ont été optimisées pour le daltonisme ou en spécifiant votre palette personnalisée. Cette fonction affecte de nombreux éléments dans Workspace, y compris la plupart des visualisations. |
| [Densité d’affichage](/help/analysis-workspace/build-workspace-project/view-density.md) | Permet d’afficher plus de données à l’écran en réduisant l’espacement vertical du panneau de gauche, des tableaux à structure libre et des tableaux de cohortes. |



