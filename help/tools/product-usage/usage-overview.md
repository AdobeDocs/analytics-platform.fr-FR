---
title: Vue d’ensemble de l’utilisation du produit
description: Affichez des informations et des rapports sur l’utilisation de Customer Journey Analytics par votre organisation.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: 9e29a16fc8d2cfe9a7a2e926b5f592280b2c1c7a
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 6%

---

# Vue d’ensemble de l’utilisation du produit

{{release-limited-testing}}

L’utilisation des produits permet à votre entreprise d’afficher des données d’analyse sur la manière dont votre entreprise utilise Customer Journey Analytics. Elle est disponible pour toutes les organisations qui utilisent Customer Journey Analytics. Une fois activés, les composants Adobe Experience Platform suivants sont automatiquement créés et connectés. Ces composants sont tous détenus par le système, en lecture seule et ne peuvent pas être modifiés.

* Un schéma dans Adobe Experience Platform
* Un jeu de données dans Adobe Experience Platform
* Une connexion dans Customer Journey Analytics
* Une vue de données dans Customer Journey Analytics

Une fois activées, toutes les opérations de collecte et de configuration des données sont automatiquement configurées. Chaque fois qu’un utilisateur effectue une action dans Analysis Workspace, cette action est suivie et disponible pour la création de rapports.

>[!IMPORTANT]
>
>Cette fonctionnalité est prise en compte dans les limites de lignes contractuelles de Adobe Experience Platform. Assurez-vous que votre entreprise peut prendre en charge les données générées par cette fonctionnalité avant de l’activer.

## Activer l’utilisation du produit

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Outils]** > **[!UICONTROL Utilisation du produit]**

En accédant à cette section de l’interface dans le Customer Journey Analytics, vous accédez à [Paramètres des données](data-settings.md) où vous pouvez activer cette fonctionnalité.

## Dimensions disponibles

Lorsque vous activez l’utilisation du produit, les dimensions suivantes sont disponibles. Si vous souhaitez modifier des paramètres de dimension, créez une copie de la vue de données appartenant au système et utilisez la vue de données copiée dans Analysis Workspace.

| Dimension | Description |
| --- | --- |
| Nom de l’action | Type d’action effectué par l’utilisateur. Vous pouvez utiliser cette dimension comme toute mesure souhaitée en créant une copie dans les paramètres de la vue de données. |
| Modèle d’attribution utilisé | Type de modèle d’attribution utilisé par le composant. |
| Composant | Champ dérivé qui inclut le type et le nom du composant. |
| Type de composant | Type de composant ajouté, supprimé ou modifié. |
| Utilisateur ou utilisatrice de la connexion | Utilisateur qui a effectué l’action. |
| Panneau utilisé | Panneau dans lequel le composant a été ajouté, supprimé ou modifié. |
| Nom du projet | Nom convivial du projet. |
| Type de projet | Type de projet. |
| Identifiant utilisateur | Identifiant utilisateur qui a déclenché l’événement. |
| Visualisation utilisée | Visualisation qui a été ajoutée, supprimée ou modifiée. |

L’utilisation du produit ne suit pas les composants individuels d’un projet lorsqu’un projet est simplement ouvert ou affiché. L’action de l’utilisateur ou de l’utilisatrice lors de l’ouverture d’un projet est toutefois suivie.
