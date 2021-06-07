---
description: Vous pouvez créer des filtres à partir d’un point de contact, ajouter des filtres comme point de contact et comparer des processus clés sur différents filtres dans Analysis Workspace.
keywords: abandons et filtres;filtres dans l’analyse des abandons;comparer des filtres dans les abandons
title: Application de filtres dans l’analyse des abandons
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 13%

---

# Application de filtres dans l’analyse des abandons

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

Vous pouvez créer des filtres à partir d’un point de contact, ajouter des filtres comme point de contact et comparer des processus clés sur différents filtres dans Analysis Workspace.

>[!IMPORTANT]
>
>Les filtres utilisés comme points de contrôle dans la visualisation Abandons doivent utiliser un conteneur qui se trouve à un niveau inférieur par rapport au contexte global de la visualisation Abandons. Dans le cas d’une visualisation Abandons sur base du visiteur, les filtres utilisés comme points de contrôle doivent être des filtres basés sur les visites ou les accès. Dans le cas d’une visualisation Abandons sur base de la visite, les filtres utilisés comme point de contrôle doivent être des filtres basés sur les accès. Si vous utilisez une combinaison non valide, les abandons seront de 100 %. Nous avons ajouté un avertissement à la visualisation Abandons qui s’affiche lorsque vous ajoutez un filtre incompatible comme point de contact. Certaines combinaisons de conteneurs de filtres non valides génèrent des diagrammes Abandons non valides, tels que :

* Utilisation d’un filtre basé sur les visiteurs comme point de contact dans une visualisation Abandons sur base du visiteur
* Utilisation d’un filtre basé sur les visiteurs comme point de contact dans une visualisation Abandons sur base de la visite
* Utilisation d’un filtre basé sur les visites comme point de contact dans une visualisation Abandons sur base de la visite

## Création d’un filtre d’après un point de contact {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Créez un filtre d’après un point de contact spécifique qui vous intéresse particulièrement et qui peut s’avérer utile pour l’application à d’autres rapports. Pour ce faire, cliquez avec le bouton droit de la souris sur le point de contact, puis sélectionnez **[!UICONTROL Créer un filtre d’après le point de contact]**.

   ![](assets/segment-from-touchpoint.png)

   Le Créateur de filtres s’ouvre. Il est prérenseigné avec le filtre séquentiel prédéfini correspondant au point de contact que vous avez sélectionné :

   ![](assets/segment-builder.png)

1. Donnez au filtre un titre et une description, puis enregistrez-le.

   Vous pouvez désormais utiliser ce filtre dans n’importe quel projet.

## Ajout d’un filtre comme point de contact {#section_17611C1A07444BE891DC21EE8FC03EFC}

Si vous souhaitez, par exemple, connaître les tendances de vos utilisateurs aux États-Unis et leur impact sur l’abandon, faites simplement glisser le filtre Utilisateurs aux États-Unis dans l’abandon :

![](assets/segment-touchpoint.png)

Vous pouvez également créer un point de contact ET en faisant glisser les utilisateurs des États-Unis vers un autre point de contrôle.

## Comparaison des filtres dans les abandons {#section_E0B761A69B1545908B52E05379277B56}

Vous pouvez comparer un nombre illimité de filtres dans la visualisation Abandons.

1. Sélectionnez les filtres à comparer dans le rail [!UICONTROL Filtre] de gauche. Dans notre exemple, nous avons sélectionné deux filtres : Utilisateurs américains et non américains.
1. Faites-les glisser dans la zone de dépôt Filtre située en haut.

   ![](assets/segment-drop.png)

1. Facultatif : vous pouvez conserver le conteneur par défaut Toutes les visites ou le supprimer.

   ![](assets/seg-compare.png)

1. Vous pouvez maintenant comparer les abandons entre les deux filtres, par exemple lorsqu’un filtre est plus performant qu’un autre, ou d’autres informations.
