---
description: Découvrez comment créer des segments à partir d’un point de contact, ajouter des segments en tant que point de contact et comparer les workflows clés sur différents segments dans une analyse des abandons dans Analysis Workspace.
keywords: abandon et segmentation;segments dans l’analyse d’abandon;comparer les segments dans l’abandon
title: Application De Segments Dans L’Analyse Des Abandons
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
autotag-review: '2026-05-19T08:42:20.474Z'
TQID: 'https://experienceleague.adobe.com/ZJqvJYmUSMfWD-yX3B-qbR5QNq7bjr9xtGN-yPXkl5E'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 33%
---
# Application de segments dans l’analyse des abandons

Dans Analysis Workspace, vous pouvez créer des segments à partir d’un point de contact, ajouter des segments en tant que points de contact et comparer les principaux workflows entre différents segments.

>[!IMPORTANT]
>
>Les segments utilisés comme points de contrôle dans la visualisation Abandons doivent utiliser un conteneur qui se trouve à un niveau inférieur par rapport au contexte global de la visualisation Abandons. Dans le cas d’une visualisation Abandon dans le contexte d’une personne, les segments utilisés comme points de contrôle doivent être des segments basés sur une session ou un événement. Avec une visualisation des abandons en contexte de session, les segments utilisés comme points de contrôle doivent être des segments basés sur un événement. Si vous utilisez une combinaison non valide, l’abandon est de 100 %. Un avertissement s’affiche dans la visualisation des abandons lorsque vous ajoutez un segment incompatible comme point de contact. Certaines combinaisons de conteneurs de segments non valides entraînent des diagrammes d’abandons non valides, par exemple :
>
>* Utilisation d’un segment basé sur les personnes comme point de contact dans une visualisation des abandons avec contexte de personne.
>* Utilisation d’un segment basé sur une personne comme point de contact dans une visualisation des abandons avec contexte de session.
>* Utilisation d’un segment basé sur une session comme point de contact dans une visualisation des abandons avec contexte de session.

<!-- 
Should we add B2B context here?
* [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Usimg a B2B container based segment as a touchpoint inside a non-container based context Fallout visualization.
* 
-->

## Création d’un segment à partir d’un point de contact

1. Créez un segment d’après un point de contact donné qui vous intéresse particulièrement et qu’il peut être utile d’appliquer à d’autres rapports. Cliquez avec le bouton droit sur le point de contact et sélectionnez **[!UICONTROL Créer un segment à partir du point de contact]**.

   ![Menu déroulant Point de contact avec l’option Créer un segment à partir du point de contact mise en surbrillance.](assets/fallout-createsegment.png)

   Le [!UICONTROL créateur de segments] s’ouvre ; il est prérempli avec le segment séquentiel préconfiguré qui correspond au point de contact que vous avez sélectionné :

   ![Le créateur de segments affiche le segment séquentiel prérempli et préconfiguré.](assets/fallout-definesegment.png)

1. Nommez et décrivez le segment, puis enregistrez-le.

   Vous pouvez désormais utiliser ce segment dans le projet de votre choix.

## Ajout d’un segment comme point de contact

Par exemple, si vous souhaitez voir l’évolution de vos utilisateurs américains et leur impact sur les abandons, il vous suffit de faire glisser le segment Utilisateurs américains dans la visualisation Abandon :

![Le segment Utilisateurs des États-Unis sélectionné et mis en surbrillance pour faire glisser dans l’abandon.](assets/fallout-addfilter.png)

Vous pouvez aussi créer un point de contact ET en faisant glisser le segment des utilisateurs aux États-Unis sur un autre point de contrôle.

## Comparer des segments dans la visualisation Abandon

Vous pouvez comparer un nombre illimité de segments dans la visualisation Abandon.

1. Sélectionnez les segments à comparer dans le panneau [!UICONTROL Segment] à gauche. Dans l’exemple, trois segments sont sélectionnés : *Informations de vol : Version de page A*, *Informations de vol : Version de page B* et *Informations de vol : Version de page C*.
1. Faites glisser les trois segments sur la zone de dépôt de segments en haut de la visualisation.


1. Facultatif : vous pouvez conserver *Toutes les personnes* comme conteneur par défaut ou supprimer le conteneur.

   ![Abandon affichant toutes les visites avec les deux segments déplacés à l’étape précédente.](assets/fallout-multiplefilters.png)

1. Vous pouvez maintenant comparer les abandons entre les trois segments, par exemple pour savoir où un segment est plus performant qu’un autre, ou obtenir d’autres informations.
