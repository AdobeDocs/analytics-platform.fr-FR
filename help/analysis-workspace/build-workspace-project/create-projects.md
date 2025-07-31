---
description: Découvrez comment créer un projet dans Analysis Workspace.
title: Créer des projets
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 518bebc18611136873fce5c23dd7041afafe1220
workflow-type: ht
source-wordcount: '454'
ht-degree: 100%

---

# Créer des projets {#create-projects}


Les [projets](/help/analysis-workspace/build-workspace-project/freeform-overview.md) dans Analysis Workspace vous permettent de créer et de visualiser des analyses critiques.  Ces analyses peuvent être partagées avec des parties prenantes au sein de votre organisation ou en dehors.

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Workspace]**.

1. Sélectionnez **[!UICONTROL Projets]** dans le panneau de gauche, puis **[!UICONTROL Créer un projet]**.

1. Sélectionnez **Projet Workspace vierge** pour créer votre projet Workspace à l’aide d’un navigateur.

   Pour plus d’informations sur la création d’un projet de carte de performance mobile que vous pouvez partager avec d’autres parties prenantes à l’aide d’une application mobile, consultez [Carte de performance mobile vierge](/help/mobile-app/curator.md). Consultez également [Analyse guidée](/help/guided-analysis/overview.md) pour plus d’informations sur les différentes options disponibles pour créer votre projet d’analyse guidée.

1. Sélectionnez [!UICONTROL **Créer**].


Maintenant que vous avez créé un projet Workspace vierge, assurez-vous de connaître l’interface utilisateur d’[Analysis Workspace](/help/analysis-workspace/home.md). Une fois l’interface connue, vous pouvez créer votre projet. Pour ce faire, procédez comme suit :

![Exemple de projet](assets/example-project.png)

* Ajoutez des [panneaux](/help/analysis-workspace/c-panels/panels.md) à votre projet. Par exemple, **[!DNL Example Panel]** ➊.

* Ajoutez des [visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) à vos panneaux. Par exemple :
   * **[!DNL Line Graph]** [Visualisation](/help/analysis-workspace/visualizations/line.md) sous forme de lignes➋
   * **[!DNL Countries]** [Visualisation sous forme de ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)tableau à structure libre➌
* Ajoutez des [composants](/help/components/overview.md) à vos visualisations. Par exemple :
   * **[!DNL Store Country]** [dimension](/help/components/dimensions/overview.md) ➍
   * **[!DNL People]** [mesure](/help/components/apply-create-metrics.md) ➎
   * **[!DNL Avg Order Value]** [mesure calculée](/help/components/calc-metrics/calc-metr-overview.md) ➏
   * **[!DNL Mobile App Sessions]** [segment](/help/components/segments/seg-overview.md) ➐
   * **[!DNL Last Month]** [période](/help/components/date-ranges/overview.md) ➑
   * **[!DNL Example]** [annotation](/help/components/annotations/overview.md) ➒


## Informations et paramètres du projet {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Comptage des instances répétées"
>abstract="Ce paramètre indique si les instances répétées sont comptabilisées dans les rapports.<br/><br/>Remarque : ce paramètre ne s’applique pas aux visualisations de flux ou d’abandons."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Comptage des instances répétées"
>abstract="Ce paramètre indique si les instances répétées sont comptabilisées dans les rapports.<br/>Remarque : ce paramètre ne s’applique pas aux visualisations de flux ou d’abandons."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Autoriser les commentaires"
>abstract="Lorsque cette option est activée, une zone de commentaires est disponible dans le rail de droite du projet dans Analysis Workspace."


Les paramètres du projet fournissent des informations sur le projet actif au niveau du projet.

![Fenêtre Informations et paramètres du projet.](./assets/projectinfo.png)

Les paramètres incluent :

| Paramètre | Description |
|---|---|
| Nom du projet | Nom donné au projet. Double-cliquez dessus pour le modifier. |
| Personne propriétaire | Nom de la personne propriétaire du projet. |
| Dernière modification | Date de la dernière modification du projet. |
| Balises | Répertorie les balises appliquées à un projet afin de faciliter la catégorisation. |
| Description | Une description est utile pour clarifier l’objet d’un projet. Double-cliquez dessus pour la modifier. |
| Comptage des instances répétées | Spécifie si les instances répétées sont comptabilisées dans les rapports. Remarque : ce paramètre ne s’applique pas aux visualisations de flux ou d’abandons. |
| Affichage des annotations | Spécifie si les annotations s’affichent pour ce projet ou non. |
| [Palette de couleurs du projet](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Vous pouvez modifier la palette de couleurs catégoriques utilisée dans Workspace en choisissant parmi les palettes prêtes à l’emploi qui ont été optimisées pour le daltonisme ou en spécifiant votre palette personnalisée. Cette fonction affecte de nombreux éléments dans Workspace, y compris la plupart des visualisations. |
| [Densité d’affichage](/help/analysis-workspace/build-workspace-project/view-density.md) | Vous permet de voir plus de données sur l’écran en réduisant l’espacement vertical du panneau de gauche, des tableaux à structure libre et des tableaux de cohortes. |
| Autoriser les commentaires | Lorsque cette option est activée, une zone de commentaires est disponible dans le rail de droite du projet dans Analysis Workspace. Pour plus d’informations, consultez [Ajouter et gérer des commentaires dans les projets](/help/analysis-workspace/build-workspace-project/comment-projects.md). |



