---
title: Analyse des données de politique de consentement dans Customer Journey Analytics
description: Découvrez comment utiliser les dimensions, mesures et modèles de politique de consentement pour créer des rapports sur l’appartenance à une politique de consentement des visiteurs dans Analysis Workspace.
solution: Customer Journey Analytics
feature: Privacy
role: Admin, User
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 388
ht-degree: 2%

---

# Analyse des données de la politique de consentement

Vous pouvez ingérer des données de politique de consentement à partir de jeux de données Profil Experience Platform dans une connexion Customer Journey Analytics.

Après avoir [créé une configuration de création de rapports et de filtrage de consentement](/help/connections/consent-reporting-filtering/consent-configure.md) et activé la création de rapports, les données de politique de consentement sont disponibles sous la forme de nouveaux composants dans les vues de données sous la connexion configurée. Vous pouvez utiliser ces composants n’importe où dans Analysis Workspace si vous avez accès à une vue de données où ils existent.

## Composants de la politique de consentement

La création de rapports de consentement ajoute les composants suivants à vos vues de données. Ces composants sont lus à partir du champ `consentPoliciesIDMap` de votre jeu de données Profil, et les noms et descriptions des politiques proviennent du jeu de données de recherche de politique de consentement .

### Dimensions

| Dimension | Description |
|---------|----------|
| **[!UICONTROL ID de la politique de consentement]** | Identifiant d’une politique de consentement à laquelle un visiteur ou une visiteuse correspond. |
| **[!UICONTROL Nom de la stratégie]** | Nom convivial de la politique de consentement, à partir du jeu de données de recherche de politique de consentement. |
| **[!UICONTROL Description de la politique]** | Description de la politique de consentement à partir du jeu de données de recherche de politique de consentement. |

### Mesures

| Mesure | Description |
|---------|----------|
| **[!UICONTROL Visiteurs avec consentement]** | Nombre de visiteurs et visiteuses qui correspondent à une politique de consentement. |
| **[!UICONTROL Événements avec consentement]** | Nombre d’événements associés aux visiteurs et visiteuses qui correspondent à une politique de consentement. |
| **[!UICONTROL Politiques de consentement uniques]** | Nombre de politiques de consentement distinctes représentées dans la fenêtre de création de rapports. |

### Champs dérivés

Un champ dérivé fait référence au champ `consentPoliciesIDMap` pour extraire les identifiants de politique de consentement. Vous pouvez utiliser ce champ dérivé comme base pour d’autres dimensions basées sur le consentement. Pour plus d’informations sur les champs dérivés, voir [Champs dérivés](/help/data-views/derived-fields/derived-fields.md).

## Utilisation des composants de politique de consentement dans Analysis Workspace

Pour créer un rapport sur l’appartenance à une politique de consentement :

1. Dans Analysis Workspace, ouvrez un projet qui utilise une vue de données configurée pour les rapports de consentement.

1. À partir du panneau Composants, faites glisser une dimension de politique de consentement, telle que **[!UICONTROL Nom de la politique]**, dans un tableau à structure libre.

1. Ajoutez une mesure de consentement, telle que **[!UICONTROL Visiteurs avec consentement]** au tableau.

1. Ventilez les résultats en fonction de toute autre dimension, telle que Page ou Canal, pour comprendre le comportement des visiteurs et visiteuses consentants.

## Utiliser le modèle d’analyse des politiques de consentement

Lorsqu’une vue de données est configurée pour les rapports de consentement, Customer Journey Analytics rend automatiquement disponible un modèle d’analyse des politiques de consentement dans Analysis Workspace. Ce modèle fournit un point de départ pour la création de rapports sur l’appartenance à une politique de consentement des visiteurs.

Pour plus d’informations sur l’accès aux modèles, voir [Accès et exécution d’un modèle](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template).
