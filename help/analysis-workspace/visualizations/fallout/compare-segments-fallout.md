---
description: Dans Analysis Workspace, vous pouvez créer des segments d’après un point de contact, ajouter des segments comme point de contact et comparer des processus clés pour plusieurs segments.
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: Application de segments dans l’analyse des abandons
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 16%

---


# Appliquer des filtres dans l&#39;analyse des abandons

>[!NOTE] Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

Vous pouvez créer des filtres à partir d’un point de contact, ajouter des segments en tant que point de contact et comparer des workflows clés sur différents filtres dans l’Analysis Workspace.

>[!IMPORTANT] Les Filtres utilisés comme points de contrôle dans Abandon doivent utiliser un conteneur qui se trouve à un niveau inférieur au contexte global de la visualisation Abandons. Dans le cas d’un abandon en contexte de visiteur, les filtres utilisés comme points de contrôle doivent être des filtres basés sur les visites ou les accès. Dans le cas d’un abandon en contexte de visite, les filtres utilisés comme point de contrôle doivent être des segments basés sur les accès. Si vous utilisez une combinaison non valide, les abandons seront de 100 %. Nous avons ajouté un avertissement à la visualisation Abandons qui s’affiche lorsque vous ajoutez un filtre incompatible en tant que point de contact. Certaines combinaisons de conteneurs de filtre non valides conduiront à des diagrammes d&#39;abandons non valides, tels que :

* Utilisation d’un filtre basé sur un visiteur en tant que point de contact dans une visualisation Abandons en contexte visiteur
* Utilisation d’un filtre basé sur un visiteur en tant que point de contact dans une visualisation d’abandons contextuelle de visite
* Utilisation d’un filtre basé sur les visites en tant que point de contact dans une visualisation d’abandons contextuelle de visite

## Create a filter from a touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Créez un filtre à partir d’un point de contact spécifique qui vous intéresse particulièrement et qui peut s’avérer utile à appliquer à d’autres rapports. You do this by right-clicking the touchpoint and selecting **[!UICONTROL Create filter from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   Le Créateur de filtres s’ouvre, prérenseigné avec le filtre séquentiel préconstruit qui correspond au point de contact que vous avez sélectionné :

   ![](assets/segment-builder.png)

1. Donnez au filtre un titre et une description et enregistrez-le.

   Vous pouvez désormais utiliser ce filtre dans n’importe quel projet.

## Add a filter as a touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

Si vous souhaitez voir, par exemple, comment vos utilisateurs américains suivent les tendances et affectent les abandons, il vous suffit de faire glisser le filtre des utilisateurs américains dans les abandons :

![](assets/segment-touchpoint.png)

Vous pouvez également créer un point de contact ET en faisant glisser le filtre des utilisateurs américains sur un autre point de contrôle.

## Compare filters in fallout {#section_E0B761A69B1545908B52E05379277B56}

Vous pouvez comparer un nombre illimité de filtres dans la visualisation Abandons.

1. Select the segments you want to compare from the [!UICONTROL Filter] rail on the left. Dans notre exemple, nous avons sélectionné deux segments : Utilisateurs aux États-Unis et Utilisateurs hors des États-Unis.
1. Faites-les glisser dans la zone de dépôt Filtre située en haut de l’écran.

   ![](assets/segment-drop.png)

1. Facultatif : vous pouvez conserver le conteneur par défaut Toutes les visites ou le supprimer.

   ![](assets/seg-compare.png)

1. Vous pouvez maintenant comparer les abandons entre les deux filtres, par exemple lorsqu’un filtre est plus performant qu’un autre, ou d’autres informations.
