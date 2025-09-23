---
title: Configuration de Customer Journey Analytics
description: Découvrez comment configurer des connexions, des vues de données et des projets Customer Journey Analytics pour Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
source-git-commit: 9bd124ad651274b48052edc56bfb72358aa2d79a
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---


# Configuration de Customer Journey Analytics

Pour utiliser la fonction Experience Platform Data Mirror pour Customer Journey Analytics, vous devez créer ou mettre à jour des connexions, des vues de données et des projets d’espace de travail afin d’utiliser des données basées sur des modèles.

## Connexions

Dans votre connexion, ajoutez les jeux de données basés sur des modèles qui représentent les données des solutions natives de l’entrepôt de données. Ces jeux de données sont dotés du type de jeu de données Modèle .

Lorsque vous ajoutez un jeu de données basé sur un modèle qui contient des données mises en miroir à partir d’une solution native de Data Warehouse, ces données sont généralement des données d’événement. Veillez à sélectionner les paramètres corrects pour le jeu de données. Par exemple, sélectionnez le type de jeu de données correct, le champ pour l’identité et le champ pour l’horodatage.


## Vues des données

Définissez les champs du schéma basé sur un modèle en tant que composants (mesures et dimensions) dans votre vue de données. Les champs de données mis en miroir sont disponibles dans le sous-dossier **[!UICONTROL Champs ad hoc et basés sur un modèle]** du dossier **[!UICONTROL Jeux de données d’événement]**. Utilisez des fonctionnalités telles que [champs dérivés](/help/data-views/derived-fields/derived-fields.md) ou [paramètres de composant](/help/data-views/component-settings/overview.md) pour modifier les composants basés sur des champs basés sur un modèle.


## Projets Workspace

Configurez des projets Workspace qui utilisent des mesures et des dimensions à partir de vos données basées sur modèle. Composants qui sont finalement basés sur les données de votre solution native d’entrepôt de données. et sont mis à jour en fonction des fonctionnalités de mise en miroir de données que vous avez configurées.

>[!MORELIKETHIS]
>
>Guide de démarrage rapide de [Data Mirror : mise en miroir et utilisation de données basées sur des modèles](data-mirror.md)
>