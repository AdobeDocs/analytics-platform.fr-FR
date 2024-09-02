---
title: Contrôle d’accès de Customer Journey Analytics
description: Découvrez comment mettre en oeuvre le contrôle d’accès dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: fb106077949cc5a1a2fbaf7702bd0c872152499f
workflow-type: tm+mt
source-wordcount: '1465'
ht-degree: 22%

---

# Contrôle d’accès

Le Customer Journey Analytics est régi par trois niveaux d’accès ou trois rôles : rôle d’administrateur de produit, rôle d’administrateur de profil de produit et accès au niveau utilisateur. Cette rubrique explique ces rôles de manière plus détaillée.

En outre, cet article décrit des moyens plus granulaires de limiter l’accès, tels que le traitement Workspace et le contrôle d’accès au niveau des lignes, ainsi que au niveau de la valeur.

## Contrôle d’accès en fonction du rôle

Les niveaux de contrôle d’accès basés sur les rôles suivants sont disponibles.

### Rôle administrateur de produit

Les utilisateurs auxquels est affecté le rôle d’administrateur de produit disposent des autorisations nécessaires pour effectuer la plupart des tâches dans Customer Journey Analytics par défaut. Toutefois, certaines tâches requièrent des autorisations supplémentaires.

Pour ajouter un utilisateur en tant qu’administrateur de produit :

1. Accédez à l’ [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Sélectionnez l&#39;onglet [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Admins**] > [!UICONTROL **Ajouter un administrateur**].

   Les utilisateurs que vous avez ajoutés reçoivent les [ autorisations par défaut de l’administrateur de produit](#product-admin-default-permissions). Vous pouvez également leur accorder des [autorisations supplémentaires](#product-admin-additional-permissions) si nécessaire.

#### Autorisations par défaut de l’administrateur de produit

Les administrateurs de produit sont autorisés à effectuer la plupart des tâches dans Customer Journey Analytics.

Les administrateurs de produit disposent des autorisations nécessaires pour effectuer par défaut les tâches suivantes :

* Créer, mettre à jour et supprimer des vues de données
* Mise à jour et suppression de projets, filtres, mesures calculées, audiences, annotations ou filtres créés par d’autres utilisateurs
* Partager des projets Workspace avec tous les utilisateurs.
* Gérer l’activité de création de rapports dans le [Gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exporter des tables complètes](/help/analysis-workspace/export/export-cloud.md) depuis Analysis Workspace

#### Autorisations supplémentaires de l’administrateur de produit

Outre l’ajout d’autorisations supplémentaires en tant qu’administrateur de produit dans le **profil de produit Customer Journey Analytics** de l’ [Admin Console](https://adminconsole.adobe.com/enterprise/), des autorisations supplémentaires sont nécessaires pour effectuer les tâches suivantes dans Customer Journey Analytics :

* Créer, mettre à jour et supprimer des données [Connexions](/help/connections/overview.md)

  Pour effectuer cette tâche, les utilisateurs doivent faire partie d’un **profil de produit Experience Platform** qui fournit les autorisations suivantes :

  | Catégorie | Autorisation | Description |
  |---|---|---|
  | [!UICONTROL Modélisation de données] | [!UICONTROL Affichage des schémas] | Accès en lecture seule aux schémas et aux ressources associées. |
  | [!UICONTROL Modélisation de données] | [!UICONTROL Gestion des schémas] | Accès pour lire, créer, modifier et supprimer des schémas et des ressources associées. |
  | [!UICONTROL Gestion des données] | [!UICONTROL Affichage des jeux de données] | Accès en lecture seule aux jeux de données et aux schémas. |
  | [!UICONTROL Gestion des données] | [!UICONTROL Gestion des jeux de données] | Accès à la lecture, la création, la modification et la suppression des jeux de données. Accès en lecture seule aux schémas. |
  | [!UICONTROL Ingestion des données] | [!UICONTROL Gestion des sources] | Accès à la lecture, la création, la modification et la désactivation des sources. |
  | [!UICONTROL Identity Management] | [!UICONTROL Affichages des espaces de noms d’identité] | Accès en lecture seule aux espaces de noms d’identité. |

  Pour plus d’informations sur les autorisations d’Experience Platform, voir [Gestion des autorisations pour un profil de produit](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

* Exporter des jeux de données vers [destinations](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)

  Pour effectuer cette tâche, les utilisateurs doivent faire partie d’un **profil de produit Experience Platform** qui fournit les autorisations suivantes :

  | Catégorie | Autorisation | Description |
  |---|---|---|
  | [!UICONTROL Destinations] | [!UICONTROL Gérer les destinations] | Accès à la lecture, la création et la suppression des connexions de destination et des comptes de destination. |
  | [!UICONTROL Destinations] | [!UICONTROL Activation des destinations] | Permet aux utilisateurs d’activer des segments vers des destinations existantes. Active l’étape de mappage dans le workflow d’activation. Cette autorisation nécessite également l’autorisation Afficher les destinations pour être accordée à l’utilisateur qui souhaite activer les données vers les destinations. |

  Pour plus d’informations sur les autorisations d’Experience Platform, voir [Gestion des autorisations pour un profil de produit](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

* Utilisation de l’ [extension BI](../data-views/bi-extension.md)

  Pour que les utilisateurs utilisent l’extension BI, un administrateur de produit

   * doit s’assurer que les autorisations d’Experience Platform pour l’utilisateur incluent un rôle disposant de la ressource Query Service avec les options Gérer les requêtes et Gérer l’intégration de Query Service . Pour plus d’informations sur les autorisations d’Experience Platform, voir [Gestion des autorisations pour un profil de produit](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

     | Catégorie | Autorisation | Description |
     |---|---|---| 
     | [!UICONTROL Query Service] | [!UICONTROL Gestion des requêtes] | Accès à la lecture, la création, la modification et la suppression des requêtes SQL structurées pour les données Platform. |
     | [!UICONTROL Query Service] | [!UICONTROL Gestion de lʼintégration de Query Service] | Accès à la création, la mise à jour et la suppression des informations dʼidentification sans date dʼexpiration pour lʼaccès à Query Service. |

   * doit s’assurer des autorisations de Customer Journey Analytics appropriées pour l’utilisateur :
      * autorisation d’accès aux vues de données pertinentes. Voir [!UICONTROL Vues de données] dans [Accès au niveau de l’utilisateur](#user-level-access).
      * autorisation d’accéder à l’extension Customer Journey Analytics BI. Voir [!UICONTROL Outils de vue de données] dans [Accès au niveau de l’utilisateur](#user-level-access).

## Rôle administrateur de profil de produit

Un profil de produit est un ensemble d’autorisations. Les administrateurs de produit créent des profils de produit et peuvent affecter des administrateurs de profil de produit pour gérer un ou plusieurs profils de produit. Un administrateur de profil de produit peut alors :

* Gérez les profils de produit affectés. Par exemple, ajouter ou supprimer des utilisateurs ou des groupes d’utilisateurs et modifier les autorisations des profils de produits.

* Dans Customer Journey Analytics, modifiez les vues de données qui font partie d’un profil de produit attribué. Les administrateurs de profil de produit ne peuvent pas créer de vues de données.

## Accès au niveau utilisateur

Le tableau ci-dessous décrit les principales autorisations d’accès pour les différentes fonctionnalités de Customer Journey Analytics que vous pouvez configurer pour les utilisateurs appropriés. Vous pouvez gérer différents niveaux d’accès des utilisateurs par le biais de profils de produit. Un profil de produit combine plusieurs autorisations que vous pouvez ensuite affecter à des utilisateurs ou groupes d’utilisateurs individuels.

L’onglet **[!UICONTROL Autorisations]** fait partie de chaque profil de produit dans l’ [Admin Console](https://adminconsole.adobe.com/enterprise/).

![autorisations d’Admin Console](assets/permissions.png)

| Catégorie | Autorisation | Description |
| --- | --- | ---|
| [!UICONTROL Vues des données] | *nom d’une vue de données* | Si vous mettez **[!UICONTROL Inclure automatiquement]** sur **[!UICONTROL Activé]**, les utilisateurs qui font partie de ce profil de produit peuvent afficher toutes les vues de données existantes et nouvellement créées. Si ce paramètre est défini sur **[!UICONTROL Désactivé]**, vous pouvez sélectionner des vues de données spécifiques auxquelles les utilisateurs ont accès. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Accès à Analysis Workspace] | Autoriser les utilisateurs à accéder à [Analysis Workspace](/help/analysis-workspace/home.md). |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Accès à l’analyse guidée] | Autoriser les utilisateurs à accéder à l’ [analyse guidée](/help/guided-analysis/overview.md). |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Création des mesures calculées] | Permet aux utilisateurs de créer des [mesures calculées](/help/components/calc-metrics/calc-metr-overview.md). Les utilisateurs peuvent baliser, partager, supprimer, renommer, approuver ou annuler l’approbation des seules mesures calculées qu’ils créent ou des mesures calculées partagées avec eux. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Création de filtres] | Permet aux utilisateurs de créer des [filtres](/help/components/filters/filters-overview.md). Les utilisateurs peuvent baliser, partager, supprimer, renommer, approuver ou annuler l’approbation uniquement des filtres qu’ils créent ou des filtres partagés avec eux. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Accès aux laboratoires] | Permet aux utilisateurs d’accéder à l’onglet [Labs](/help/labs/labs.md) dans Customer Journey Analytics. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Création d’annotation] | Permet aux utilisateurs de créer des [annotations](/help/components/annotations/overview.md). Les utilisateurs peuvent baliser, partager, supprimer et renommer uniquement les annotations qu’ils créent ou les annotations partagées avec eux. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Création dʼaudiences] | Permet aux utilisateurs de créer des [audiences](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Accès aux journaux d’audit] | Application de la vérification des autorisations sur l’ [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) et l’interface utilisateur des journaux d’audit. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Partager Des Liens De Projet Avec N’Importe Qui] | Laissez les utilisateurs [ partager des projets avec n&#39;importe qui.](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Prévisions] | Autoriser les utilisateurs à accéder à la fonction [Prévisionnel](../analysis-workspace/c-forecast/forecasting.md) dans Analysis Workspace |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Assistant d’IA : connaissance du produit] | Permettre aux utilisateurs d’accéder à l’ [assistant d’IA](../ai-assistant.md) pour consulter leurs connaissances sur les produits. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Légendes intelligentes] | Permettent aux utilisateurs d’accéder aux [sous-titres intelligents](/help/analysis-workspace/visualizations/intelligent-captions.md). |
| [!UICONTROL  Outils de vue de données] | [!UICONTROL Exportation de table complète] | Laissez les utilisateurs [exporter des tables complètes vers le cloud](/help/analysis-workspace/export/export-cloud.md). |
| [!UICONTROL  Outils de vue de données] | [!UICONTROL Extension CJA BI] | Laissez les utilisateurs utiliser l’ [extension BI](../data-views/bi-extension.md). |

{style="table-layout:auto"}

## Traitement du projet Workspace

Un autre niveau de contrôle d’accès peut être utilisé au niveau des rapports Workspace. Vous pouvez limiter l’accès à des composants spécifiques pour certains utilisateurs. Pour plus d’informations sur la façon de limiter les composants (dimensions, mesures, filtres, plages de dates) au niveau du projet Workspace et de déterminer comment le traitement est lié aux vues de données, voir [Traitement des projets](/help/analysis-workspace/curate-share/curate.md).

## Accorder l’accès à des mesures ou dimensions individuelles

Vous ne pouvez pas accorder ni refuser des autorisations concernant des mesures ou des dimensions individuelles dans Customer Journey Analytics comme le permet la version standard d’Adobe Analytics. Les mesures et dimensions peuvent être modifiées dans [vues de données](/help/data-views/data-views.md) et peuvent donc faire l’objet de modifications dans Customer Journey Analytics. Cette modification permet également de modifier rétroactivement les rapports.

## Cas d’utilisation

Voici quelques cas d’utilisation qui illustrent comment le contrôle d’accès peut être utilisé dans des scénarios réels.

### Accès tiers

Vous pouvez accorder l’accès à l’administration des profils de produit à un chef d’équipe d’un tiers que votre entreprise travaille. Cet administrateur peut ajouter des utilisateurs de l’équipe de l’entreprise à ce profil de produit. Cet administrateur de profil de produit peut donner accès à des vues de données spécifiques et ajouter d’autres utilisateurs au sein d’un tiers à ce profil de produit. L’administrateur de profil de produit peut modifier les vues de données en fonction des exigences de l’équipe tierce.

### Contrôle d’accès au niveau de la ligne

Imaginons que vous souhaitiez donner aux utilisateurs un accès aux données à partir d’un seul jour. Voici comment limiter l’accès à ces lignes spécifiques :

1. Créez un filtre dans [!UICONTROL Paramètres] d’une vue de données spécifique, où [!UICONTROL Jour] correspond à la date à laquelle vous souhaitez qu’ils aient accès aux données. Voir [Création d’une vue de données](/help/data-views/create-dataview.md#settings-filters) pour plus d’informations.
1. Enregistrez la vue de données, qui applique le filtre à la partie données des jeux de données dans la connexion sous-jacente. Toutes les lignes qui ne correspondent pas à la définition de filtre sont automatiquement exclues de la vue de données et ne sont pas disponibles pour Analysis Workspace lors de l’utilisation de cette vue de données.
1. Créez un [profil de produit](#product-profile-admin-role) dans l’Admin Console, ajoutez des utilisateurs au profil de produit et incluez uniquement cette vue de données spécifique au profil de produit.

### Contrôle d’accès au niveau de la valeur

Les utilisateurs qui ont accès à une vue de données ne peuvent travailler qu’avec les mesures et dimensions incluses par l’administrateur dans cette vue de données. Les administrateurs peuvent utiliser les paramètres du composant [Inclure/Exclure](/help/data-views/component-settings/include-exclude-values.md) ou [Regroupement de valeurs](../data-views/component-settings/value-bucketing.md) dans une vue de données pour exclure ou agréger certaines valeurs de dimension d’une vue de données.

Par exemple : vous créez une mesure appelée *Hypertension* dans une vue de données à partir d’un composant qui contient des données de patients individuels du jeu de données. Vous utilisez le regroupement de valeurs pour fournir uniquement l’accès aux valeurs regroupées, de sorte que les utilisateurs des données ne voient pas les données individuelles des patients.


