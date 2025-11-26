---
title: Configuration de Customer Journey Analytics
description: Découvrez comment configurer des connexions, des vues de données et des projets Customer Journey Analytics pour Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
source-git-commit: b2a13524760f9d466696534bc8b9691f3b4dfb8a
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---

# Configuration de Customer Journey Analytics

{{release-limited-testing}}

{{relational-model-based}}

Pour utiliser la fonction Experience Platform Data Mirror pour Customer Journey Analytics, vous devez créer ou mettre à jour des connexions, des vues de données et des projets d’espace de travail afin d’utiliser les données relationnelles.

## Connexions

Dans votre connexion, ajoutez les jeux de données relationnels qui représentent les données des solutions natives de l’entrepôt de données. Ces jeux de données sont dotés du type de jeu de données Relationnel .

Lorsque vous ajoutez un jeu de données relationnel qui contient des données mises en miroir à partir d’une solution native de Data Warehouse, ces données sont généralement des données d’événement. Veillez à sélectionner les paramètres corrects pour le jeu de données. Par exemple, sélectionnez le type de jeu de données correct, le champ pour l’identité et le champ pour l’horodatage.


## Vues des données

Définissez les champs du schéma relationnel en tant que composants (mesures et dimensions) dans votre vue de données. Les champs de données mis en miroir sont disponibles dans le sous-dossier **[!UICONTROL Champs ad hoc et relationnels]** du dossier **[!UICONTROL Jeux de données d’événement]**. Utilisez des fonctionnalités telles que [champs dérivés](/help/data-views/derived-fields/derived-fields.md) ou [paramètres des composants](/help/data-views/component-settings/overview.md) pour modifier les composants basés sur des champs relationnels.


## Projets Workspace

Configurez des projets Workspace qui utilisent des mesures et des dimensions à partir de vos données relationnelles. Composants qui sont finalement basés sur les données de votre solution native d’entrepôt de données. et sont mis à jour en fonction des fonctionnalités de mise en miroir de données que vous avez configurées.

>[!MORELIKETHIS]
>
>Guide de démarrage rapide de [Data Mirror : mettre en miroir et utiliser les données relationnelles](relational.md)
>
