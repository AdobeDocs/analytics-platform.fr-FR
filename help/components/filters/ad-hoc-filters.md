---
description: Utilisez des filtres ad hoc dans Analysis Workspace.
title: Filtres de projet ad hoc
feature: Workspace Basics
role: User, Admin
source-git-commit: 275c552b14a4c2a47e00d0600ac3eae6811beae9
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 17%

---


# Filtres de projet ad hoc

Voici une vidéo sur la création de filtres de projet ad hoc :

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Vous pouvez créer des filtres de projet ad hoc si vous souhaitez explorer rapidement la manière dont un filtre peut affecter votre projet, sans passer par le créateur de segments. Considérez ces filtres comme des filtres temporaires au niveau du projet. Ils ne font généralement pas partie de votre &quot;bibliothèque&quot; de filtre comme les filtres de composant dans le rail de gauche. Vous pouvez toutefois les enregistrer, comme illustré ci-dessous.

Pour une comparaison des effets des filtres de projet ad hoc par rapport aux filtres au niveau des composants complets, voir [ici](/help/components/filters/filters-overview.md).

1. Déposez tout type de composant (dimension, élément de dimension, événement, mesure, filtre, modèle de filtre, période) dans la zone de dépôt des filtres située en haut d’un panneau. Les types de composants sont automatiquement transformés en filtres.
Voici un exemple de création d’un filtre pour le domaine référent Twitter :

   ![](assets/ad-hoc1.png)

   Ce filtre est automatiquement appliqué à votre panneau. Vous pouvez afficher instantanément les résultats.

1. Vous pouvez ajouter un nombre illimité de composants à un panneau.
1. Si vous décidez d&#39;enregistrer ce filtre, reportez-vous à la section ci-dessous.

Remarque :

* Vous **ne pouvez pas** déposer les types de composants suivants dans une zone de filtre : les mesures calculées et les dimensions/mesures à partir desquelles vous ne pouvez pas créer de filtres.
* Pour l’intégralité des dimensions et événements, Analysis Workspace crée des segments de filtres « existe ». Exemples : `Hit where eVar1 exists` ou `Hit where event1 exists`.
* Si &quot;non spécifié&quot; ou &quot;aucun&quot; est déposé dans la zone de dépôt du filtre, il est automatiquement converti en filtre &quot;n’existe pas&quot; afin d’être traité correctement dans le filtrage.

>[!NOTE]
>
>Les segments créés de cette façon sont internes au projet.

## Enregistrement des filtres de projet ad hoc {#ad-hoc-save}

Vous pouvez choisir d’enregistrer ces filtres en procédant comme suit :

1. Pointez sur le filtre de la zone de dépôt, puis cliquez sur l’icône « i ».
1. Dans le panneau d’informations qui s’affiche, cliquez sur **[!UICONTROL Enregistrer]**.

   ![](assets/segment-info.png)

## Que sont les filtres de projet uniquement ?

Les filtres Projet uniquement sont des filtres rapides ou des filtres de projet Workspace ad hoc. Lorsque vous les modifiez ou les ouvrez dans le créateur de filtres, la zone Projet uniquement s’affiche. S’ils APPLIQUENT un filtre rapide dans le créateur mais ne cochent pas la case rendre disponible, il s’agit toujours d’un filtre de projet uniquement, mais il ne peut plus être ouvert dans le créateur QS. S’ils cochent la case et l’ENREGISTRER, il s’agit désormais d’un filtre de liste de composants.