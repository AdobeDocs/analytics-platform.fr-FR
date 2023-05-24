---
description: Dans Analysis Workspace, vous pouvez créer des filtres à partir d’un point de contact, ajouter des filtres comme point de contact et comparer des workflows clés entre différents filtres.
keywords: abandons et filtres ; filtres dans l’analyse des abandons ; comparer des filtres dans les abandons
title: Application de filtres dans l’analyse des abandons
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 87%

---

# Application de filtres dans l’analyse des abandons

Dans Analysis Workspace, vous pouvez créer des filtres à partir d’un point de contact, ajouter des filtres comme point de contact et comparer des workflows clés entre différents filtres.

>[!IMPORTANT]
>
>Les filtres utilisés comme points de contrôle dans les abandons doivent utiliser un conteneur qui se trouve à un niveau inférieur par rapport au contexte global de la visualisation des abandons. Avec une Abandon contextuelle sur la personne, les filtres utilisés comme points de contrôle doivent être des filtres basés sur les visites ou les événements. Dans le cas d’une visualisation Abandons sur base de la visite, les filtres utilisés comme point de contrôle doivent être des filtres basés sur un événement. Si vous utilisez une combinaison non valide, les abandons sont de 100 %. Nous avons ajouté un avertissement à la visualisation des abandons qui s’affiche lorsque vous ajoutez un filtre incompatible comme point de contact. Certaines combinaisons de conteneurs de filtres non valides entraînent des diagrammes d’abandons non valides, par exemple :

* Utilisation d’un filtre basé sur les personnes comme point de contact dans une visualisation Abandons sur base individuelle
* Utilisation d’un filtre basé sur les personnes comme point de contact dans une visualisation Abandons sur base de la visite
* Utilisation d’un filtre basé sur les visites comme point de contact dans une visualisation des abandons avec contexte de visite.

## Création d’un filtre à partir d’un point de contact {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Créez un filtre à partir d’un point de contact donné qui vous intéresse particulièrement et qu’il pourrait être utile d’appliquer à d’autres rapports. Pour ce faire, cliquez avec le bouton droit sur le point de contact, puis sélectionnez **[!UICONTROL Créer un filtre à partir du point de contact]**.

   ![](assets/segment-from-touchpoint.png)

   Le créateur de filtres s’ouvre. Il est prérempli avec le filtre séquentiel préconfiguré qui correspond au point de contact que vous avez sélectionné :

   ![](assets/segment-builder.png)

1. Donnez un titre et une description au filtre et enregistrez-le.

   Vous pouvez maintenant utiliser ce filtre dans le projet de votre choix.

## Ajout d’un filtre comme point de contact {#section_17611C1A07444BE891DC21EE8FC03EFC}

Si, par exemple, vous souhaitez connaître les tendances qui se dégagent pour vos utilisateurs aux États-Unis et de quelle façon les abandons sont affectés, faites glisser le filtre correspondant à ces utilisateurs sur les abandons :

![](assets/segment-touchpoint.png)

Vous pouvez aussi créer un point de contact AND en faisant glisser le filtre des utilisateurs aux États-Unis sur un autre point de contrôle.

## Comparaison des filtres dans la visualisation des abandons {#section_E0B761A69B1545908B52E05379277B56}

Vous pouvez comparer un nombre illimité de filtres dans la visualisation des abandons.

1. Sélectionnez les filtres que vous souhaitez comparer dans le rail de [!UICONTROL filtres] sur la gauche. Dans notre exemple, nous avons sélectionné deux filtres : Utilisateurs aux États-Unis et Utilisateurs hors des États-Unis.
1. Faites-les glisser dans la zone de dépôt des filtres en haut de l’écran.

   ![](assets/segment-drop.png)

1. Facultatif : vous pouvez conserver « Toutes les visites » comme conteneur par défaut ou le supprimer.

   ![](assets/seg-compare.png)

1. Vous pouvez maintenant comparer les abandons entre les deux filtres, par exemple pour savoir quand un filtre est plus performant qu’un autre, ou obtenir d’autres informations.
