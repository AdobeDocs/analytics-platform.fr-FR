---
title: Contrôle d’accès de Customer Journey Analytics
description: Découvrez comment mettre en oeuvre le contrôle d’accès dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 1a470345a6a2748b992263c3ad25e4cd7d3daa9e
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 42%

---

# Contrôle d’accès de Customer Journey Analytics

Trois niveaux d’accès ou trois rôles régissent le Customer Journey Analytics : rôle d’administrateur de produit, rôle d’administrateur de profil de produit et accès au niveau de l’utilisateur. Cette rubrique explique ces rôles de manière plus détaillée.

En outre, cet article décrit des moyens plus granulaires de limiter l’accès, tels que le traitement Workspace et le contrôle d’accès au niveau des lignes, ainsi que au niveau de la valeur.

## Rôle d’administrateur de produit

Les utilisateurs auxquels est affecté le rôle d’administrateur de produit disposent des autorisations nécessaires pour effectuer la plupart des tâches dans Customer Journey Analytics par défaut. Toutefois, certaines tâches requièrent des autorisations supplémentaires.

Pour ajouter un utilisateur en tant qu’administrateur de produit :

1. Accédez à l’ [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Sélectionnez l&#39;onglet [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Admins**] > [!UICONTROL **Ajouter un administrateur**].

   Les utilisateurs que vous avez ajoutés reçoivent les [autorisations par défaut de l’administrateur de produit](#product-admin-default-permissions). Vous pouvez également leur accorder des [autorisations supplémentaires](#product-admin-additional-permissions) si nécessaire.

### Autorisations par défaut de l’administrateur de produit

Les administrateurs de produit sont autorisés à effectuer la plupart des tâches dans Customer Journey Analytics.

Les administrateurs de produit disposent des autorisations nécessaires pour effectuer par défaut les tâches suivantes :

* Créer, mettre à jour et supprimer des vues de données
* Mise à jour et suppression de projets, filtres, mesures calculées, audiences, annotations ou filtres créés par d’autres utilisateurs
* Partager des projets Workspace avec tous les utilisateurs.
* Gérer l’activité de création de rapports dans le [Gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exporter des tables complètes](/help/analysis-workspace/export/export-cloud.md) depuis Analysis Workspace

### Autorisations supplémentaires pour l’administrateur de produit

En plus d’être ajouté en tant qu’administrateur de produit dans le **profil de produit Customer Journey Analytics** de l’ [Admin Console](https://adminconsole.adobe.com/enterprise/), des autorisations supplémentaires sont nécessaires pour effectuer les tâches suivantes dans Customer Journey Analytics :

* Créer, mettre à jour et supprimer des données [Connexions](/help/connections/overview.md)

  Pour effectuer cette tâche, les utilisateurs doivent faire partie d’un **profil de produit Experience Platform** qui fournit les autorisations suivantes :
   * Modélisation des données : Afficher les schémas, Gérer les schémas
   * Gestion des données : Afficher les jeux de données, Gérer les jeux de données
   * Ingestion des données : Gérer les sources
   * Afficher des espaces de noms d’identités

     Pour plus d’informations sur les autorisations Experience Platform, voir [Contrôle d’accès dans Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home).

* Exporter des jeux de données vers le cloud [Destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=fr)

  Pour effectuer cette tâche, les utilisateurs ont besoin des autorisations Experience Platform suivantes :

   * Gestion des destinations
   * Activation des destinations

     Pour plus d’informations sur les autorisations de destinations Experience Platform, consultez la [présentation des destinations](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/home).

* Utilisation de l’ [extension BI](../data-views/bi-extension.md)

  Pour que les utilisateurs utilisent l’extension BI, un administrateur de produit

   * doit s’assurer que les autorisations d’Experience Platform pour l’utilisateur incluent un rôle disposant de la ressource Query Service avec les options Gérer les requêtes et Gérer l’intégration de Query Service . Voir [Gestion des autorisations pour un profil de produit](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).
   * doit s’assurer des autorisations de Customer Journey Analytics appropriées pour l’utilisateur :
      * autorisation d’accès aux vues de données pertinentes. Reportez-vous à la section Vues de données dans les [autorisations de Customer Journey Analytics dans Admin Console](#customer-journey-analytics-permissions-in-admin-console).
      * autorisation d’accès à l’extension CJA BI. Reportez-vous à la section Outils de vue de données dans les [autorisations de Customer Journey Analytics dans Admin Console](#customer-journey-analytics-permissions-in-admin-console).

## Rôle d’administrateur de profil de produit

Un profil de produit est un ensemble d’autorisations. Les administrateurs de profil de produit peuvent

* Créez et gérez des profils de produit individuels. comme l’ajout de nouveaux utilisateurs ou la gestion de groupes d’utilisateurs et de leurs profils de produits associés.

* Dans Customer Journey Analytics, modifiez les vues de données qui font partie d’un profil de produit qu’elles gèrent. Ils ne peuvent pas créer de vues de données.

## Accès au niveau utilisateur

Le tableau ci-dessous décrit les principales autorisations d’accès pour différentes fonctionnalités de Customer Journey Analytics pour les administrateurs de produits non liés aux produits et les administrateurs de produits Customer Journey Analytics. La compréhension de ces autorisations permet aux utilisateurs de naviguer et d’utiliser efficacement le Customer Journey Analytics en fonction de leur rôle et de leurs responsabilités au sein de l’entreprise.

| Fonctionnalité du produit | Administrateurs non liés aux produits (utilisateurs) | Administrateurs de produit |
| --- | --- | --- |
| **Vues de données** | Impossible d’afficher/mettre à jour/créer/supprimer | Peut créer/mettre à jour/supprimer |
| **Connexions** | Impossible d’afficher/mettre à jour/créer/supprimer | Peut créer/mettre à jour/supprimer |
| **Filtres** | Peut créer | Peut créer |
| **Projets** | Peut créer | Peut créer/mettre à jour/supprimer |
| **Audiences** | Peut créer avec des autorisations spéciales dans Admin Console | Peut créer |
| **Mesures calculées** | Peut créer avec des autorisations spéciales dans Admin Console | Peut créer |

{style="table-layout:auto"}

## Traitement du projet Workspace

Un autre niveau de contrôle d’accès peut être utilisé au niveau des rapports Workspace. Vous pouvez limiter l’accès à des composants spécifiques pour certains utilisateurs. Pour plus d’informations sur la façon de limiter les composants (dimensions, mesures, filtres, plages de dates) au niveau du projet Workspace et de déterminer comment le traitement est lié aux vues de données, voir [Traitement des projets](/help/analysis-workspace/curate-share/curate.md).

## Accorder l’accès à des mesures ou dimensions individuelles

Vous ne pouvez pas accorder ni refuser des autorisations concernant des mesures ou des dimensions individuelles dans Customer Journey Analytics comme le permet la version standard d’Adobe Analytics. Les mesures et dimensions peuvent être modifiées dans [vues de données](/help/data-views/data-views.md) et peuvent donc faire l’objet de modifications dans Customer Journey Analytics. Cette modification permet également de modifier rétroactivement les rapports.

## Cas d’utilisation

Voici quelques cas d’utilisation qui illustrent comment le contrôle d’accès peut être utilisé dans des scénarios réels.

### Accès tiers

Un tiers avec lequel votre entreprise travaille dispose d’un chef d’équipe qui peut être nommé administrateur de profil de produit. Cet administrateur peut ajouter des utilisateurs de l’équipe de l’entreprise à ce profil de produit. Cet administrateur peut donner accès à des vues de données spécifiques et ajouter d’autres utilisateurs à ce profil de produit. Il peut également modifier les vues de données sur lesquelles il a le contrôle pour répondre aux besoins de son équipe.

### Contrôle d’accès au niveau de la ligne

Supposons que vous souhaitiez donner aux utilisateurs un accès aux données pour un seul jour. Voici comment limiter l’accès à ces lignes spécifiques :

1. Créez un filtre dans Customer Journey Analytics où **[!UICONTROL Day]** correspond à la date à laquelle vous souhaitez qu’ils aient accès aux données.
1. Dans [!UICONTROL Vues des données] > [!UICONTROL Paramètres], ajoutez ce filtre à la vue de données.
1. Enregistrez la vue de données et appliquez automatiquement le filtre au jeu de données. Toutes les lignes qui ne correspondent pas à la définition du filtre sont désormais automatiquement exclues de la vue de données modifiée.
1. Créez un profil de produit dans Admin Console, ajoutez-y des utilisateurs et limitez leur accès à cette vue de données.

### Contrôle d’accès au niveau de la valeur

Les utilisateurs qui ont accès à une vue de données ne peuvent travailler qu’avec les mesures et dimensions incluses par l’administrateur dans cette vue de données. Les administrateurs peuvent utiliser la [fonctionnalité d’inclusion/exclusion](/help/data-views/component-settings/include-exclude-values.md) dans les vues de données pour, par exemple, exclure certaines valeurs de dimension d’une vue de données.

Voici un exemple relatif à la santé : supposons que vous créiez une mesure appelée « Hypertension » dans une vue de données à partir d’un jeu de données qui inclut ces données. Le fait qu’il s’agisse d’une mesure vous permettrait de voir la valeur agrégée de cette mesure, mais pas les patients individuels qui en font partie.

## Autorisations des Customer Journey Analytics dans Admin Console

L’onglet **[!UICONTROL Autorisations]** fait partie de chaque profil de produit dans [Admin Console](https://adminconsole.adobe.com/enterprise/). Vous pouvez ajouter des utilisateurs à des profils de produit spécifiques. Ensuite, vous attribuez des droits à des vues de données spécifiques et spécifiez les autorisations dont disposent les utilisateurs dans un profil de produits. Voici les autorisations spécifiques au Customer Journey Analytics :

![autorisations d’Admin Console](assets/permissions.png)

| Autorisation | Définition |
| --- | --- |
| **[!UICONTROL Vues des données]** | Si vous mettez **[!UICONTROL Inclure automatiquement]** sur **[!UICONTROL Activé]**, les utilisateurs qui font partie de ce profil de produit peuvent afficher toutes les vues de données existantes et nouvellement créées. Si ce paramètre est défini sur **[!UICONTROL Désactivé]**, vous pouvez sélectionner des vues de données spécifiques auxquelles les utilisateurs ont accès. |
| **[!UICONTROL Outils de création de rapports]** : |   |
| **[!UICONTROL Accès aux journaux d’audit]** | Cette autorisation applique la vérification des autorisations sur l’[API](https://www.adobe.io/cja-apis/docs/endpoints/auditlogs/) et l’interface utilisateur des journaux d’audit. |
| **[!UICONTROL Accès à Analysis Workspace]** | Permet aux utilisateurs d’accéder à Analysis Workspace dans Customer Journey Analytics. |
| [!UICONTROL **Accès à l’analyse guidée**] | Permet aux utilisateurs de créer des [projets d’analyse guidée](/help/guided-analysis/overview.md). |
| [!UICONTROL **Prévisions**] | Autoriser les utilisateurs à accéder à la fonction Prévisions dans Analysis Workspace |
| **[!UICONTROL Administrateur d’utilisation des rapports]** | Permet aux utilisateurs d’afficher et de supprimer tout rapport exécuté dans leur société. |
| **[!UICONTROL Affichage de l’utilisation des rapports]** | Permet aux utilisateurs d’afficher toutes les demandes de création de rapports simultanées. |
| [!UICONTROL **Exportation de table complète**] | Laissez les utilisateurs [exporter des tables complètes vers le cloud](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL Création des mesures calculées]** | Permet aux utilisateurs de créer des [mesures calculées](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Création de filtres]** | Permet aux utilisateurs de créer des [filtres](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Accès aux laboratoires]** | Permet aux utilisateurs d’accéder à l’onglet [Labs](/help/labs/labs.md) dans Customer Journey Analytics. |
| **[!UICONTROL Création d’annotation]** | Permet aux utilisateurs de créer des [annotations](/help/components/annotations/overview.md). |
| **[!UICONTROL Création dʼaudiences]** | Permet aux utilisateurs de créer des [audiences](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Affichage de lʼaudience]** | Permet aux utilisateurs d’afficher [audiences](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL **Partager Des Liens De Projet Avec N’Importe Qui**] | Laissez les utilisateurs [ partager des projets avec n&#39;importe qui.](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| **[!UICONTROL Outils de vues de données]** : |   |
| [!UICONTROL **Exportation de table complète**] | Laissez les utilisateurs [exporter des tables complètes vers le cloud](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL [!UICONTROL Extension CJA BI]]** | Laissez les utilisateurs utiliser l’ [extension BI](../data-views/bi-extension.md). |

{style="table-layout:auto"}
