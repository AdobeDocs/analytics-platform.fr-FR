---
description: Utilisez des filtres ad hoc dans Analysis Workspace.
title: Filtres de projet ad hoc
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: 6627c8e8f6e88fd93ffaad12b38e5e1dbbc844a8
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 100%

---

# Filtres de projet ad hoc

Les filtres de projet ad hoc vous permettent de faire glisser et de déposer n’importe quel composant directement dans la zone de dépôt du panneau pour créer un filtre. Le filtre devient un paramètre local [filtre au niveau du projet](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html?lang=fr) du projet en cours.

Voici une vidéo sur la création de filtres de projet ad hoc :

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)


1. Déplacez un type de composant (dimension, élément de dimension, événement, mesure, Filtre, modèle de segments, période) dans la zone de dépôt du filtre en haut dʼun panneau. S’ils sont compatibles, les types de composants sont automatiquement convertis en filtres ad hoc ou [Filtres rapides](/help/components/filters/quick-filters.md).

   Voici un exemple de création d’un filtre pour le domaine référent Twitter :

   ![](assets/ad-hoc1.png)

   Ce filtre est automatiquement appliqué à votre panneau. Vous pouvez afficher instantanément les résultats.

1. Vous pouvez ajouter un nombre illimité de filtres à un panneau.
1. Si vous décidez d’enregistrer ce filtre, reportez-vous à la section ci-dessous.

Remarque :

* Vous **ne pouvez pas** déposer les types de composants suivants dans une zone de filtre : les mesures calculées et les dimensions/mesures à partir desquelles vous ne pouvez pas créer de filtres.
* Pour l’intégralité des dimensions et événements, Analysis Workspace crée des segments de filtres « existe ». Exemples : `Hit where eVar1 exists` ou `Hit where event1 exists`.
* Si des éléments de type « non spécifié » ou « aucun » sont déposés dans la zone de dépôt, ils sont automatiquement transformés en filtre « n’existe pas » afin d’être traités correctement.

## Enregistrer les filtres de projet ad hoc {#ad-hoc-save}

Pour enregistrer ces filtres, procédez comme suit :

1. Pointez sur le filtre de la zone de dépôt, puis cliquez sur l’icône « i ».
1. Cliquez sur le crayon de modification pour accéder au Créateur de filtres.
1. Cochez **[!UICONTROL Rendre disponible pour tous vos projets et ajouter l’élément à votre liste de composants]**.
1. Cliquez sur **[!UICONTROL ENREGISTRER]**.

Une fois enregistré, le filtre est disponible dans la liste des composants du rail de gauche et peut être partagé avec d’autres utilisateurs à partir du Gestionnaire de filtres.

