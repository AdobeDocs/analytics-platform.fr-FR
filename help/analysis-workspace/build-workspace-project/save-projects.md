---
description: Découvrez les différentes options d’enregistrement, notamment l’enregistrement automatique, l’enregistrement sous, l’enregistrement en tant que modèle et ouvrez les versions précédentes.
title: Enregistrement des projets
feature: CJA Workspace Basics
role: User, Admin
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
source-git-commit: 702d03b95b6689e1441fbdd8b2ef3a5a3fcfbad0
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 100%

---

# Enregistrement des projets

Pour enregistrer vos modifications dans un projet, accédez au menu **[!UICONTROL Projet]** de Espace de travail. Espace de travail enregistre également automatiquement les projets dans certains cas.

## Options d’enregistrement des projets {#Save}

Il existe différentes actions d’enregistrement que vous pouvez effectuer sous le menu **[!UICONTROL Projet]**, selon la manière dont vous souhaitez accéder à votre analyse à l’avenir.

| Action | Description |
|---|---|
| **[!UICONTROL Enregistrer]** | Enregistrez les modifications apportées au projet. Si le projet est partagé, les destinataires du projet verront également les modifications. Lorsque vous enregistrez le projet pour la première fois, vous êtes invité à lui attribuer un nom, une description (facultative) et à ajouter des balises (facultatives). |
| **[!UICONTROL Enregistrer avec les notes]** | Avant l’enregistrement de votre projet, ajoutez des notes sur les modifications apportées au projet. Les notes sont stockées avec la version du projet et sont disponibles pour tous les éditeurs sous [!UICONTROL Projet] > [!UICONTROL Ouvrir la version précédente]. |
| **[!UICONTROL Enregistrer sous]** | Créez un doublon du projet. Le projet d’origine ne sera pas affecté. |
| **[!UICONTROL Enregistrer en tant que modèle]** | Enregistrez votre projet comme [modèle personnalisé](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=fr) disponible pour votre entreprise sous **[!UICONTROL Projet > Nouveau]** |

![](assets/save-project.png)

## Enregistrement automatique {#Autosave}

Les projets existants, c’est-à-dire les projets enregistrés au moins une fois auparavant, sont automatiquement enregistrés toutes les deux minutes sur votre ordinateur local. Les nouveaux projets qui n’ont jamais été enregistrés ne sont pas enregistrés automatiquement.

Plusieurs scénarios permettent d’éviter les modifications non enregistrées d’un projet. Différentes actions s’offrent alors à vous.

### Ouverture d’un autre projet Espace de travail

Adobe permet d’enregistrer avant de quitter la page. Après avoir quitté un projet existant, la copie locale enregistrée automatiquement est supprimée.

![](assets/existing-save.png)

### Quitter ou fermer un onglet

Le navigateur signale que les modifications non enregistrées seront perdues. Vous pouvez choisir de quitter ou d’annuler.

![](assets/browser-image.png)

### Blocage du navigateur ou expiration d’une session

Pour les projets **existants**, lorsque vous revenez à Espace de travail, une fenêtre modale de **récupération du projet** s’affiche. Sélectionnez « Oui » pour restaurer le projet à partir de la copie locale enregistrée automatiquement. Sélectionnez « Non » pour supprimer la copie locale enregistrée automatiquement et ouvrir la dernière version du projet enregistrée par l’utilisateur.

![](assets/project-recovery.png)

Pour les **nouveaux** projets qui n’ont jamais été enregistrés, les modifications non enregistrées ne sont pas récupérables.

## Ouvrir la version précédente {#previous-version}

Pour ouvrir une version précédente d’un projet :

1. Accédez à **[!UICONTROL Projet]** > **[!UICONTROL Ouvrir la version précédente]**

   ![](assets/previous-versions.png)

1. Consultez la liste des versions antérieures disponibles.
   [!UICONTROL Date et heure] et [!UICONTROL Éditeur] s’affichent, en plus des [!UICONTROL Notes] s’ils ont été ajoutés lorsque l’[!UICONTROL Éditeur] a été enregistré. Les versions sans notes sont stockées pendant 90 jours. Les versions avec notes sont stockées pendant 1 an.
1. Sélectionnez une version précédente et cliquez sur **[!UICONTROL Charger]**.
La version précédente se charge ensuite avec une notification. La version précédente ne devient pas la version enregistrée actuelle de votre projet tant que vous n’avez pas cliqué sur **[!UICONTROL Enregistrer]**. Si vous quittez la version chargée, lorsque vous revenez, la dernière version enregistrée du projet s’affiche.
