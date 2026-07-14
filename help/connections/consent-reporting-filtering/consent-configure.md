---
title: Configuration des rapports et du filtrage de consentement
description: Découvrez comment utiliser l’assistant de mise en service pour activer les rapports de consentement et le filtrage facultatif de la durée d’ingestion pour une connexion dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8did: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 759
ht-degree: 2%

---

# Configuration des rapports et du filtrage liés au consentement

Les administrateurs et administratrices système peuvent activer la création de rapports de consentement et, éventuellement, le filtrage de consentement pour une ou plusieurs connexions. Pour plus d’informations, voir [Présentation des rapports et du filtrage de consentement](/help/connections/consent-reporting-filtering/consent-overview.md).

>[!IMPORTANT]
>
>Le filtrage du consentement exclut les données des visiteurs non consentants au moment de l’ingestion. Les données exclues par le filtrage ne sont pas stockées dans Customer Journey Analytics et ne peuvent pas être récupérées pour les dates passées. Examinez attentivement vos sélections d’actions marketing avant d’activer le filtrage.

## Conditions préalables

Avant de configurer la création de rapports et le filtrage liés au consentement, assurez-vous des points suivants :

* Vous disposez d’autorisations d’administrateur système dans Customer Journey Analytics.
* Le sandbox que vous souhaitez utiliser contient un jeu de données Profil avec des données d’appartenance à une politique de consentement dans le champ `consentPoliciesIDMap` .
* La connexion que vous souhaitez configurer existe déjà. Pour plus d’informations, voir [Créer ou modifier une connexion](/help/connections/create-connection.md).

## Création d’une configuration

Lorsque vous créez une configuration pour les rapports et le filtrage de consentement, vous sélectionnez le sandbox et le jeu de données Profil contenant les données d’appartenance à votre politique de consentement, choisissez la ou les connexions à configurer et choisissez de filtrer ou non les données pour chaque action marketing. Customer Journey Analytics crée ensuite automatiquement le jeu de données de recherche de politique de consentement et les composants de politique de consentement.

Pour créer une configuration de rapport et de filtrage de consentement :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Rapports et filtrage de consentement]**.

1. Sélectionnez **[!UICONTROL Créer une configuration]**.

1. Dans la section **[!UICONTROL Détails]**, spécifiez les informations suivantes :

   | Champ | Description |
   |---------|----------|
   | **[!UICONTROL Nom]** | Attribuez un nom à la configuration. |
   | **[!UICONTROL Sandbox]** | Sélectionnez le sandbox Experience Platform qui contient le jeu de données Profil avec vos données d’appartenance à la politique de consentement. <p>Il existe au maximum un jeu de données de recherche de politique de consentement par sandbox. Plusieurs configurations dans le même sandbox partagent le même jeu de données de recherche.</p> |

1. Dans la section **[!UICONTROL Jeu de données de profil]**, sélectionnez le Jeu de données de profil contenant les données d’appartenance à la politique de consentement (le champ `consentPoliciesIDMap`) sur lesquelles vous souhaitez créer des rapports. Ce jeu de données de profil est ajouté à la connexion que vous sélectionnez.

1. Dans la section **[!UICONTROL Connexion]**, sélectionnez **[!UICONTROL Sélectionner une connexion]**, cochez la case en regard d’une ou de plusieurs connexions à configurer, puis sélectionnez **[!UICONTROL Utiliser la connexion]**.

   Les rapports et le filtrage relatifs au consentement sont appliqués au niveau de la connexion. Toutes les vues de données sous une connexion configurée héritent du même comportement.

1. (Facultatif) Dans la section **[!UICONTROL Filtrage]**, vous pouvez activer le filtrage pour les actions marketing suivantes :

   >[!NOTE]
   >
   >Ne sélectionnez pas les deux bascules pour activer le compte rendu des performances de consentement sans filtrage.
   >
   >Lorsque le filtrage d’une action marketing est activé, Customer Journey Analytics ingère les données d’un visiteur uniquement si celui-ci correspond **toutes** les politiques de consentement qui s’appliquent à cette action marketing. Pour plus d’informations, voir [Filtrage du consentement](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering) dans [Présentation des rapports et du filtrage du consentement](/help/connections/consent-reporting-filtering/consent-overview.md).

   | Action marketing | Description |
   |---------|----------|
   | **[!UICONTROL Analytics]** | Filtrez les données utilisées pour la création de rapports Customer Journey Analytics standard dans Analysis Workspace. |
   | **[!UICONTROL Science des données]** | Filtrez les données utilisées pour les cas d’utilisation d’analyses avancées, de machine learning et de science des données. |

1. Sélectionnez **[!UICONTROL Créer]** pour créer la configuration.

   Customer Journey Analytics automatiquement :

   * Ajoute le jeu de données Profil sélectionné à la connexion.
   * Crée un jeu de données de recherche de politique de consentement pour le sandbox (s’il n’existe pas déjà) et synchronise les noms et descriptions des politiques à partir d’Experience Platform.
   * Ajoute les composants de politique de consentement (dimensions, mesures et champ dérivé) aux vues de données dans la connexion configurée.
   * Applique le libellé interne **consentement** aux nouveaux composants afin que vous puissiez les filtrer dans la vue de données. Pour plus d’informations sur les libellés internes, voir [ Libellés et politiques ](/help/data-views/data-governance.md).

1. Une fois la configuration terminée, [affichez les composants de politique de consentement dans la vue de données](#view-consent-policy-components-in-the-data-view) pour vérifier qu’ils sont disponibles.

## Affichage des composants de politique de consentement dans la vue de données

Après avoir [créé une configuration](#create-a-configuration), vous pouvez vérifier que les composants de politique de consentement ont été ajoutés aux vues de données sous la connexion configurée.

Pour afficher les composants de politique de consentement dans la vue de données, vous devez être un administrateur de profil de produit pour le profil de produit auquel la vue de données est affectée. Pour plus d’informations, voir [Contrôle d’accès](/help/technotes/access-control.md).

Pour afficher les composants de politique de consentement dans la vue de données :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Vues de données]**.

1. Ouvrez une vue de données associée à la connexion configurée.

1. Dans la section **[!UICONTROL Dimensions]** , les dimensions suivantes doivent désormais être disponibles :

   * **[!UICONTROL ID de la politique de consentement]**

   * **[!UICONTROL Nom de la stratégie]**

   * **[!UICONTROL Description de la politique]**

1. Dans la section **[!UICONTROL Mesures]**, les mesures suivantes doivent désormais être disponibles :

   * **[!UICONTROL Visiteurs avec consentement]**

   * **[!UICONTROL Événements avec consentement]**

   * **[!UICONTROL Politiques de consentement uniques]**

   <!-- TODO: Add a screenshot of the consent policy components in the data view (assets/consent-components-dataview.png). -->

1. Utilisez les composants de politique de consentement dans Analysis Workspace.

   Les utilisateurs et utilisatrices qui ont accès à la vue de données dans Analysis Workspace peuvent désormais voir les nouveaux composants et les utiliser dans leurs analyses. Pour plus d’informations sur l’utilisation des composants de politique de consentement dans Analysis Workspace, voir [Analyse des données de politique de consentement](/help/connections/consent-reporting-filtering/consent-analyze.md).
