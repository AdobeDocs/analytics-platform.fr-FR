---
description: Découvrez comment créer un projet dans Analysis Workspace.
title: Créer des projets
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
TQID: https://experienceleague.adobe.com/DWTWJ2Bd9iEPO2awiiOLcUzUGPc-clZul3dNFcyWvxk
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: fa6ac035-8403-478b-9ce1-3fe29d211fca
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 459
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
>abstract="Indique si les instances répétées sont comptabilisées dans les rapports.<br/><br/>Note : ce paramètre ne s’applique pas aux visualisations Flux ou Abandons."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Comptage des instances répétées"
>abstract="Indique si les instances répétées sont comptabilisées dans les rapports.<br/>Note : ce paramètre ne s’applique pas aux visualisations Flux ou Abandons."


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



