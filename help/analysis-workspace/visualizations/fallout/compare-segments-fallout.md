---
description: Dans Analysis Workspace, vous pouvez créer des filtres à partir d’un point de contact, ajouter des filtres comme point de contact et comparer des workflows clés entre différents filtres.
keywords: abandons et filtres ; filtres dans l’analyse des abandons ; comparer des filtres dans les abandons
title: Application de filtres dans l’analyse des abandons
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 45%

---

# Application de filtres dans l’analyse des abandons

Dans Analysis Workspace, vous pouvez créer des filtres à partir d’un point de contact, ajouter des filtres comme point de contact et comparer des workflows clés entre différents filtres.

>[!IMPORTANT]
>
>Les filtres utilisés comme points de contrôle dans les abandons doivent utiliser un conteneur qui se trouve à un niveau inférieur par rapport au contexte global de la visualisation des abandons. Avec une Abandon contextuelle sur la personne, les filtres utilisés comme points de contrôle doivent être des filtres basés sur les visites ou les événements. Dans le cas d’une visualisation Abandons sur base de la visite, les filtres utilisés comme point de contrôle doivent être des filtres basés sur un événement. Si vous utilisez une combinaison non valide, l’abandon est de 100 %. Un avertissement s’affiche pour la visualisation Abandons lorsque vous ajoutez un filtre incompatible comme point de contact. Certaines combinaisons de conteneurs de filtres non valides génèrent des diagrammes d’abandons non valides, tels que :

* Utilisation d’un filtre basé sur les personnes comme point de contact dans une visualisation Abandons sur base individuelle
* Utilisation d’un filtre basé sur les personnes comme point de contact dans une visualisation Abandons sur base de la visite
* Utilisation d’un filtre basé sur les visites comme point de contact dans une visualisation des abandons avec contexte de visite.

## Création d’un filtre à partir d’un point de contact

1. Créez un filtre à partir d’un point de contact donné qui vous intéresse particulièrement et qu’il pourrait être utile d’appliquer à d’autres rapports. Cliquez avec le bouton droit sur le point de contact et sélectionnez **[!UICONTROL Créer un filtre d’après le point de contact]**.

   ![Menu déroulant du point de contact avec l’option Créer un segment d’après le point de contact mise en surbrillance.](assets/fallout-createfilter.png)

   Le [!UICONTROL Créateur de filtres] s’ouvre, prérenseigné avec le filtre séquentiel prédéfini correspondant au point de contact que vous avez sélectionné :

   ![Le Créateur de filtres affiche le filtre séquentiel prérempli et prédéfini.](assets/fallout-definefilter.png)

1. Donnez un titre et une description au filtre et enregistrez-le.

   Vous pouvez maintenant utiliser ce filtre dans le projet de votre choix.

## Ajout d’un filtre comme point de contact

Si, par exemple, vous souhaitez connaître les tendances qui se dégagent pour vos utilisateurs aux États-Unis et de quelle façon les abandons sont affectés, faites glisser le filtre correspondant à ces utilisateurs sur les abandons :

![Le filtre Utilisateurs des États-Unis sélectionné et mis en surbrillance pour le faire glisser dans l’abandon.](assets/fallout-addfilter.png)

Vous pouvez aussi créer un point de contact AND en faisant glisser le filtre des utilisateurs aux États-Unis sur un autre point de contrôle.

## Comparaison des filtres dans la visualisation des abandons

Vous pouvez comparer un nombre illimité de filtres dans la visualisation des abandons.

1. Sélectionnez les filtres à comparer dans le panneau [!UICONTROL Filtre] situé à gauche. Dans l’exemple, trois filtres sont sélectionnés : *Détails du vol : Page Version A*, *Détails du vol : Page Version B* et *Détails du vol : Page Version C*.
1. Faites glisser les trois filtres sur la zone de dépôt Filtre située en haut de la visualisation.


1. Facultatif : vous pouvez conserver *Toutes les visites* comme conteneur par défaut ou supprimer le conteneur.

   ![Abandon présentant toutes les visites avec les deux filtres déplacés à l’étape précédente.](assets/fallout-multiplefilters.png)

1. Vous pouvez désormais comparer les abandons entre les trois filtres, par exemple lorsqu’un filtre est plus performant qu’un autre, ou d’autres informations.
