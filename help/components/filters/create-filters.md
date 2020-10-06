---
title: Création de filtres
description: Découvrez l’interface utilisateur de la création de filtres.
translation-type: tm+mt
source-git-commit: 1c82c7c2e61c170b6eb05bfda0c7a79e5a13c4e1
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 33%

---


# Création de filtres

Le Créateur de filtres propose un canevas permettant de faire glisser et de déposer des mesures, des dimensions, des filtres et des événements afin de filtrer les visiteurs en fonction d’opérateurs, de règles et d’une logique de hiérarchie de conteneurs. Cet outil de développement intégré vous permet de créer et d’enregistrer des filtres simples ou complexes qui identifient les attributs et actions des visiteurs entre les visites et accès aux pages.

Vous pouvez créer des filtres instantanés en déposant n’importe quel type de composant (dimension, élément de dimension, événement, mesure, segment, modèle de segment, plage de dates) dans la zone de dépôt de filtre située en haut d’un panneau.

Les types de composants sont automatiquement convertis en filtres. Vous pouvez également cliquer sur le signe &quot;+&quot; dans le **[!UICONTROL Filtre Ajoute]** zone de dépôt.

Gardez les éléments suivants à l’esprit :

* You **cannot** déposez les types de composant suivants dans la zone de filtre : mesures calculées et dimensions/mesures à partir desquelles vous ne pouvez pas créer de filtres.
* Pour les dimensions et les événements complets, Analysis Workspace crée des filtres d’accès &quot;existe&quot;. Exemples : « Déposer où eVar1 existe » ou « Déposer où event1 existe ».
* Si &quot;non spécifié&quot; ou &quot;aucun&quot; est déposé dans la zone de dépôt du filtre, il est automatiquement converti en filtre &quot;n’existe pas&quot; afin qu’il soit correctement traité.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Les filtres ainsi créés sont internes au projet.

Vous pouvez choisir de rendre ces filtres publics (globaux) en procédant comme suit :

1. Passez la souris sur le filtre dans la zone de dépôt et cliquez sur l’icône &quot;i&quot;.
1. Dans le panneau Informations qui s’affiche, cliquez sur **[!UICONTROL Rendre public]**.

   ![](assets/segment-info.png)

## Autres méthodes d&#39;application des filtres

Il existe plusieurs autres méthodes pour appliquer des filtres à un projet :

| Action | Description |
|--- |--- |
| Créer un filtre à partir de la sélection | Créez un filtre intégré. Sélectionnez des lignes, cliquez avec le bouton droit de la souris sur la sélection, puis créez un filtre intégré. Ce filtre s’applique uniquement au projet ouvert et n’est pas enregistré en tant que filtre CJA. 1. Sélectionnez des lignes.  2. Cliquez avec le bouton de la souris sur la sélection.  3. Cliquez sur *Créer un filtre à partir de la sélection*. |
| Composants > Nouveau filtre | Affiche le Créateur de filtres. Voir [Créateur de filtres](https://docs.adobe.com/content/help/fr-FR/analytics/components/segmentation/segmentation-workflow/seg-build.html) pour plus d’informations sur le filtrage. |
| Partager > Partager le projet ou Partager > Traiter les données du projet | Dans [Traiter et partager](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), découvrez comment les filtres que vous appliquez au projet sont disponibles dans l’analyse partagée pour le destinataire. |
| Utiliser les filtres comme dimensions | Vidéo : Utilisation de Filtres en tant que Dimensions dans Analysis Workspace<br>>[!VIDEO](https://video.tv.adobe.com/v/23974) |
