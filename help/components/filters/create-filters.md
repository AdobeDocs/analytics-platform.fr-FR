---
title: Création de filtres
description: Découvrez l’interface utilisateur de la création de filtres.
exl-id: b6a921d5-7dd3-4230-88b8-5f1cd313b791
translation-type: ht
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: ht
source-wordcount: '372'
ht-degree: 100%

---

# Création de filtres

Le Créateur de filtres propose un canevas permettant de faire glisser et de déposer des mesures, des dimensions, des filtres et des événements afin de filtrer les visiteurs en fonction d’opérateurs, de règles et d’une logique de hiérarchie de conteneurs. Cet outil de développement intégré vous permet de créer et d’enregistrer des filtres simples ou complexes qui identifient les attributs et actions des visiteurs entre les visites et accès aux pages.

Vous pouvez créer des filtres instantanés en déposant un type de composants (dimension, élément de dimension, événement, mesure, filtre, modèle de filtres, période) dans la zone de dépôt des filtres en haut dʼun panneau.

Les types de composants sont automatiquement transformés en filtres. Sinon, vous pouvez cliquer sur le signe « + » dans la zone de dépôt **[!UICONTROL Ajouter un filtre]**.

Gardez les éléments suivants à l’esprit :

* Vous **ne pouvez pas** déposer les types de composants suivants dans une zone de filtre : les mesures calculées et les dimensions/mesures à partir desquelles vous ne pouvez pas créer de filtres.
* Pour l’intégralité des dimensions et événements, Analysis Workspace crée des segments de filtres « existe ». Exemples : « Déposer où eVar1 existe » ou « Déposer où event1 existe ».
* Si des éléments de type « non spécifié » ou « aucun » sont déposés dans la zone de dépose, ils sont automatiquement transformés en filtre « n’existe pas » afin d’être traités correctement.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Les filtres créés de cette façon sont internes au projet.

Pour rendre ces filtres publics (globaux), procédez comme suit :

1. Pointez sur le filtre de la zone de dépôt, puis cliquez sur l’icône « i ».
1. Dans le panneau Informations qui s’affiche, cliquez sur **[!UICONTROL Rendre public]**.

   ![](assets/segment-info.png)

## Autres méthodes d’application de filtres

Plusieurs autres méthodes permettent d’appliquer des filtres à un projet :

| Action | Description |
|--- |--- |
| Création d’un filtre d’après une sélection | Créez un filtre incorporé. Sélectionnez des lignes, cliquez avec le bouton droit de la souris sur la sélection, puis créez un filtre incorporé. Ce filtre s’applique uniquement au projet ouvert et n’est pas enregistré comme un filtre CJA. 1. Sélectionnez des lignes.  2. Cliquez avec le bouton de la souris sur la sélection.  3. Cliquez sur *Créer un filtre d’après la sélection*. |
| Composants > Nouveau filtre | Ouvre le créateur de filtres. Voir [Créateur de filtre](https://docs.adobe.com/content/help/fr-FR/analytics/components/segmentation/segmentation-workflow/seg-build.html) pour en savoir plus sur le filtrage. |
| Partager > Partager le projet ou Partager > Traiter les données du projet | Dans l’outil [Traiter et partager](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), découvrez comment les filtres que vous appliquez au projet sont disponibles dans l’analyse partagée avec le destinataire. |
| Utiliser les filtres comme dimensions | Vidéo : Utilisation de filtres comme dimensions dans Analysis Workspace. |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
