---
title: Présentation de l’utilisation du produit
description: Affichez des informations et des rapports sur la manière dont votre entreprise utilise Customer Journey Analytics.
source-git-commit: 7d22c512e8e96963b288567704d2245e64411b10
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 6%

---

# Présentation de l’utilisation du produit

{{release-limited-testing}}

L’utilisation du produit permet à votre entreprise d’afficher des données d’analyse sur la manière dont votre entreprise utilise Customer Journey Analytics. Il est disponible pour toutes les organisations qui utilisent Customer Journey Analytics. Une fois activés, les composants Adobe Experience Platform suivants sont automatiquement créés et connectés pour vous. Ces composants sont tous détenus par le système, en lecture seule et ne peuvent pas être modifiés.

* Un schéma dans Adobe Experience Platform
* Jeu de données dans Adobe Experience Platform
* Une connexion en Customer Journey Analytics
* Une vue de données dans Customer Journey Analytics

Toute la collecte et la configuration des données sont automatiquement configurées pour vous une fois qu’elles sont activées. Chaque fois qu’un utilisateur effectue une action dans Analysis Workspace, cette action est suivie et disponible pour la création de rapports.

>[!IMPORTANT]
>
>Cette fonctionnalité est incluse dans vos limites de lignes contractuelles dans Adobe Experience Platform. Assurez-vous que votre entreprise peut prendre en charge les données générées par cette fonctionnalité avant de l’activer.

## Dimensions disponibles

Lorsque vous activez l’utilisation du produit, les dimensions suivantes sont disponibles. Si vous souhaitez modifier les paramètres de dimension, créez une copie de la vue de données appartenant au système et utilisez la vue de données copiée dans Analysis Workspace.

| Dimension | Description |
| --- | --- |
| Nom de l’action | Type d’action effectuée par l’utilisateur. Vous pouvez utiliser cette dimension comme mesure de votre choix en créant une copie dans les paramètres de vue de données. |
| Modèle d’attribution utilisé | Le type de modèle d’attribution utilisé par le composant. |
| Composant | Champ dérivé qui comprend le type et le nom du composant. |
| Type de composant | Le type de composant ajouté, supprimé ou modifié. |
| Utilisateur ou utilisatrice de la connexion | L’utilisateur qui a effectué l’action. |
| Panneau utilisé | Panneau dans lequel le composant a été ajouté, supprimé ou modifié. |
| Nom du projet | Nom convivial du projet. |
| Type de projet | Type de projet. |
| Identifiant utilisateur | ID utilisateur qui a déclenché l’événement. |
| Visualisation utilisée | Visualisation qui a été ajoutée, supprimée ou modifiée. |

L’utilisation du produit ne suit pas les composants de projet individuels lorsqu’un projet est simplement ouvert ou affiché. L’action de l’utilisateur lors de l’ouverture d’un projet est toutefois suivie.
