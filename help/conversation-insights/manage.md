---
title: Gérer la configuration des informations de conversation
description: Découvrez comment gérer les configurations de Conversation Insights.
solution: Customer Journey Analytics
feature: AI Tools
role: Admin, User
autotag-review: '2026-10-02T07:03:36.851Z'
TQID: 'https://experienceleague.adobe.com/D2nrhtN2SaHoAw0PU7yJtabvx-q0L5FHtBFu1sORfaI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
  - id: d7a261eb-f9ac-4dd6-bd60-1637efcd3d36
    internal-label: ''
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: b58d1768aef87f01bb3c20b01102d08a17e973ef
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 6%
---
# Gestion des configurations

Après avoir [créé des configurations de conversation insights](/help/conversation-insights/configure.md), vous pouvez les afficher, les modifier ou les supprimer.

Seuls les administrateurs système peuvent gérer les configurations de Conversation Insights.

Pour plus d’informations sur les informations sur la conversation, voir [Présentation des informations sur la conversation](/help/conversation-insights/overview.md).


## Affichage et filtrage des configurations existantes

Pour afficher vos configurations Conversation Insights existantes :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Configuration des informations sur les conversations]**.

   ![Présentation des configurations des informations de conversation](assets/conversation-insights-configurations.png)

   Les colonnes d’informations suivantes sont disponibles pour chaque configuration :

   * **[!UICONTROL Name]** : nom de la configuration des informations de conversation.
   * **[!UICONTROL Créé par]** : utilisateur qui a créé la configuration.

   * **[!UICONTROL Sandbox]** : sandbox Experience Platform contenant le jeu de données de profil que vous avez ajouté à votre connexion.

   * **[!UICONTROL Connexion]** : la connexion que vous avez ajoutée à votre configuration.

   * **[!UICONTROL Date de création]** : date et heure auxquelles la configuration a été créée.

   * **[!UICONTROL Dernière modification]** : date de la dernière modification de la configuration.

   * **[!UICONTROL Statut]** : le statut de la configuration. Les valeurs possibles sont les suivantes :
     ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**, ![StatusBlue](/help/assets/icons/StatusBlue.svg) **[!UICONTROL Pending]** ou ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Failed]**.

   Pour configurer les colonnes à afficher dans le tableau, sélectionnez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). Dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]**, sélectionnez les colonnes à afficher. Sélectionnez ensuite **[!UICONTROL Appliquer]**.

1. (Facultatif) Pour filtrer la liste des configurations, sélectionnez ![Filtrer](/help/assets/icons/Filter.svg), puis filtrez selon l’un des critères suivants :

   * **[!UICONTROL Connexion]**

   * **[!UICONTROL Créé par]**

   * **[!UICONTROL Sandbox]**

   * **[!UICONTROL Statut]**

## Création d’une configuration

Pour créer une configuration Insights de conversation :

1. Sélectionnez **[!UICONTROL Créer une configuration]**.
1. Utilisez la boîte de dialogue [**[!UICONTROL Créer une configuration]**](./configure.md) pour configurer les informations de conversation.

## Modification d’une configuration

Pour modifier une configuration Insights de conversation existante :

1. Effectuez l’une des opérations suivantes :

   * Sélectionnez le nom de la configuration que vous souhaitez modifier.
   * Cochez la case en regard de la configuration à modifier, puis sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** dans la barre d’actions bleue.
   * Sélectionnez ![Plus](/help/assets/icons/More.svg) pour la configuration que vous souhaitez modifier. Dans le menu contextuel, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]**.

1. Utilisez la boîte de dialogue [**[!UICONTROL Configuration/_nom de la configuration_]**](./configure.md) pour gérer les informations de conversation.

## Suppression d’une configuration

Pour supprimer une configuration Insights de conversation existante :

1. Effectuez l’une des opérations suivantes :

   * Cochez la case en regard de la configuration à supprimer, puis sélectionnez ![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]** dans la barre d’actions bleue.
   * Sélectionnez ![Plus](/help/assets/icons/More.svg) pour la configuration que vous souhaitez modifier. Dans le menu contextuel, sélectionnez ![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]**.

1. Dans la boîte de dialogue **[!UICONTROL Supprimer la configuration]**, sélectionnez **[!UICONTROL Supprimer]** pour supprimer la configuration. Sélectionnez **[!UICONTROL Annuler]** pour annuler.
