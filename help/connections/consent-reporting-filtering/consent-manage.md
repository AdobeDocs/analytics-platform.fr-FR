---
title: Gérer les configurations de filtrage et de création de rapports de consentement
description: Découvrez comment afficher, modifier et supprimer des configurations de création de rapports et de filtrage de consentement et comment le jeu de données de recherche de politique de consentement reste synchronisé dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 5%

---

# Gérer les configurations de filtrage et de création de rapports relatives au consentement

Après avoir [créé une configuration de rapport et de filtrage de consentement](/help/connections/consent-reporting-filtering/consent-configure.md), vous pouvez l’afficher, la modifier ou la supprimer.

Seuls les administrateurs système peuvent gérer les configurations de filtrage et de création de rapports de consentement.

Pour plus d’informations, voir [Présentation des rapports et du filtrage de consentement](/help/connections/consent-reporting-filtering/consent-overview.md).

## Affichage des configurations existantes

Pour afficher vos configurations existantes :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Rapports et filtrage de consentement]**.

   Les colonnes d’informations suivantes sont disponibles pour chaque configuration :

   * **[!UICONTROL Créé par]** : utilisateur qui a créé la configuration.

   * **[!UICONTROL Sandbox]** : sandbox Experience Platform contenant le jeu de données Profil.

   * **[!UICONTROL Connexion]** : connexion à laquelle la configuration est appliquée.

   * **[!UICONTROL Filtrage]** : les actions marketing pour lesquelles le filtrage est activé, le cas échéant.

   * **[!UICONTROL Date de création]** : date à laquelle la configuration a été créée.

   * **[!UICONTROL Dernière modification]** : date de la dernière modification de la configuration.

   * **[!UICONTROL Statut]** : le statut de la configuration.

   Vous pouvez masquer des colonnes en sélectionnant l’icône Colonne ![icône Colonne](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg), en désactivant les colonnes à masquer, puis en sélectionnant **[!UICONTROL Appliquer]**.

1. (Facultatif) Pour filtrer la liste des configurations, sélectionnez l’icône **Filtrer** ![Filtrer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), puis filtrez selon l’un des critères suivants :

   * **[!UICONTROL Connexion]**

   * **[!UICONTROL Créé par]**

   * **[!UICONTROL Sandbox]**

   * **[!UICONTROL Statut]**

## Modification d’une configuration

>[!IMPORTANT]
>
>Les modifications apportées au filtrage n’affectent que les données ingérées après l’enregistrement des modifications apportées à la configuration. L’activation du filtrage ne supprime pas les données de visiteurs non consentants ingérées avant la modification et la désactivation du filtrage ne récupère pas les données qui ont été exclues lors de l’activation du filtrage.

Pour modifier une configuration existante, procédez comme suit :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Rapports et filtrage de consentement]**.

1. Sélectionnez le nom de la configuration que vous souhaitez modifier.

   Ou

   Cochez la case en regard de la configuration à modifier, puis sélectionnez **[!UICONTROL Modifier]**.

1. Apportez vos modifications, puis sélectionnez **[!UICONTROL Enregistrer]**.

## Suppression d’une configuration

Pour supprimer une configuration existante :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Rapports et filtrage de consentement]**.

1. Cochez la case en regard de la configuration à supprimer, puis sélectionnez **[!UICONTROL Supprimer]**.

## Comment le jeu de données de recherche de la politique de consentement reste synchronisé

Customer Journey Analytics synchronise automatiquement le jeu de données de recherche de politique de consentement avec Experience Platform. Lorsqu’une politique de consentement est créée, mise à jour, renommée ou supprimée dans Experience Platform, le nom et la description de la politique correspondants dans le jeu de données de recherche sont mis à jour.

Gardez à l’esprit les points suivants :

* Il existe au maximum un jeu de données de recherche de politique de consentement par sandbox. Plusieurs configurations dans le même sandbox partagent ce jeu de données de recherche.
* Comme les noms et descriptions des politiques proviennent d’Experience Platform, mettez à jour les métadonnées des politiques dans Experience Platform plutôt que de modifier directement le jeu de données de recherche.
