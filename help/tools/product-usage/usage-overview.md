---
title: Présentation de l’utilisation du produit
description: Affichez des informations et des rapports sur la manière dont votre entreprise utilise Customer Journey Analytics.
hide: true
hidefromtoc: true
source-git-commit: dcd3ee5f3db5af434b87bfded0e360c66643793e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 6%

---

# Présentation de l’utilisation du produit

{{release-limited-testing}}

L’utilisation du produit permet à votre entreprise d’afficher des données d’analyse sur la manière dont votre entreprise utilise Customer Journey Analytics. Il est disponible pour toutes les organisations qui utilisent Customer Journey Analytics. Une fois activés, les composants Adobe Experience Platform suivants sont automatiquement créés et associés pour vous :

* Un schéma dans Adobe Experience Platform. Ce schéma est en lecture seule et ne peut pas être modifié.
* Jeu de données dans Adobe Experience Platform. Les paramètres de ce jeu de données sont en lecture seule et ne peuvent pas être modifiés.
* Une connexion en Customer Journey Analytics. Les paramètres de cette connexion sont en lecture seule et ne peuvent pas être modifiés.
* Une vue de données dans Customer Journey Analytics. Vous pouvez modifier cette vue de données ou créer d’autres vues de données à l’aide de la même connexion.

Toute la collecte et la configuration des données sont automatiquement configurées pour vous une fois qu’elles sont activées. Chaque fois qu’un utilisateur effectue une action dans Analysis Workspace, cette action est suivie et disponible pour la création de rapports.

>[!IMPORTANT]
>
>Cette fonctionnalité est incluse dans vos limites de lignes contractuelles dans Adobe Experience Platform. Assurez-vous que votre entreprise peut prendre en charge les données générées par cette fonctionnalité avant de l’activer.

## Dimensions disponibles

Lorsque vous activez l’utilisation du produit, les dimensions suivantes sont disponibles :

| Dimension | Description |
| --- | --- |
| Nom de l’action | Type d’action effectuée par l’utilisateur. Vous pouvez utiliser cette dimension comme mesure de votre choix en créant une copie dans les paramètres de vue de données. |
| Modèle d’attribution utilisé | Le type de modèle d’attribution utilisé par le composant actuel. |
| Composant | Champ dérivé. |
| Type de composant | Le type de composant ajouté, supprimé ou modifié. |
| Connexion | La connexion utilisée par le projet. |
| Vue de données | Vue de données utilisée par le projet. |
| Fonctionnalité | Fonction utilisée par le projet. |
| Identifiant | Identifiant unique de l’événement. |
| Utilisateur ou utilisatrice de la connexion | L’utilisateur qui a effectué l’action. |
| Panneau utilisé | Panneau dans lequel le composant a été ajouté, supprimé ou modifié. |
| Projet    | Champ dérivé. |
| Nom du projet | Nom convivial du projet. |
| Type de projet | Type de projet. |
| Identifiant utilisateur | ID utilisateur qui a déclenché l’événement. |
| Visualisation utilisée | Visualisation qui a été ajoutée, supprimée ou modifiée. |

L’utilisation du produit ne suit pas les composants de projet individuels lorsqu’un projet est simplement ouvert ou affiché. L’action de l’utilisateur lors de l’ouverture d’un projet est toutefois suivie.
