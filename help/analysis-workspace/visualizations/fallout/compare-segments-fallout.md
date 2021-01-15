---
description: Dans Analysis Workspace, vous pouvez créer des segments d’après un point de contact, ajouter des segments comme point de contact et comparer des processus clés pour plusieurs segments.
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: Application de filtres dans l’analyse des abandons
translation-type: tm+mt
source-git-commit: ab1ea4c75c4c28f196c6793a819ce4dbe656d52c
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 23%

---


# Application de filtres dans l’analyse des abandons

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

Vous pouvez créer des filtres à partir d’un point de contact, ajouter des segments en tant que point de contact et comparer des workflows clés sur différents filtres de Analysis Workspace.

>[!IMPORTANT]
>
>Les filtres utilisés comme points de contrôle dans Abandon doivent utiliser un conteneur qui se trouve à un niveau inférieur au contexte global de la visualisation Abandons. Dans le cas d’un abandon en contexte de visiteur, les filtres utilisés comme points de contrôle doivent être des filtres basés sur les visites ou les accès. Dans le cas d’un abandon en contexte de visite, les filtres utilisés comme point de contrôle doivent être des segments basés sur les accès. Si vous utilisez une combinaison non valide, les abandons seront de 100 %. Nous avons ajouté un avertissement à la visualisation Abandons qui s’affiche lorsque vous ajoutez un filtre incompatible en tant que point de contact. Certaines combinaisons de conteneurs de filtre non valides conduiront à des diagrammes d&#39;abandons non valides, tels que :

* Utilisation d’un filtre basé sur un visiteur en tant que point de contact dans une visualisation Abandons en contexte visiteur
* Utilisation d’un filtre basé sur un visiteur en tant que point de contact dans une visualisation d’abandons contextuelle de visite
* Utilisation d’un filtre basé sur les visites en tant que point de contact dans une visualisation d’abandons contextuelle de visite

## Créer un filtre à partir d’un point de contact {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Créez un filtre à partir d’un point de contact spécifique qui vous intéresse particulièrement et qui peut s’avérer utile à appliquer à d’autres rapports. Pour ce faire, cliquez avec le bouton droit sur le point de contact et sélectionnez **[!UICONTROL Créer un filtre à partir du point de contact]**.

   ![](assets/segment-from-touchpoint.png)

   Le Créateur de filtres s’ouvre, prérenseigné avec le filtre séquentiel préconstruit qui correspond au point de contact que vous avez sélectionné :

   ![](assets/segment-builder.png)

1. Donnez au filtre un titre et une description et enregistrez-le.

   Vous pouvez désormais utiliser ce filtre dans n’importe quel projet.

## Ajouter un filtre en tant que point de contact {#section_17611C1A07444BE891DC21EE8FC03EFC}

Si vous souhaitez voir, par exemple, comment vos utilisateurs américains suivent les tendances et affectent les abandons, il vous suffit de faire glisser le filtre des utilisateurs américains dans les abandons :

![](assets/segment-touchpoint.png)

Vous pouvez également créer un point de contact ET en faisant glisser le filtre des utilisateurs américains sur un autre point de contrôle.

## Comparer les filtres dans les abandons {#section_E0B761A69B1545908B52E05379277B56}

Vous pouvez comparer un nombre illimité de filtres dans la visualisation Abandons.

1. Sélectionnez les segments à comparer dans le rail [!UICONTROL Filtrer] situé à gauche. Dans notre exemple, nous avons sélectionné deux segments : Utilisateurs aux États-Unis et Utilisateurs hors des États-Unis.
1. Faites-les glisser dans la zone de dépôt Filtre située en haut de l’écran.

   ![](assets/segment-drop.png)

1. Facultatif : vous pouvez conserver le conteneur par défaut Toutes les visites ou le supprimer.

   ![](assets/seg-compare.png)

1. Vous pouvez maintenant comparer les abandons entre les deux filtres, par exemple lorsqu’un filtre est plus performant qu’un autre, ou d’autres informations.
