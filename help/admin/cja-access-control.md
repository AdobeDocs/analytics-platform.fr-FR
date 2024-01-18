---
title: Contrôle d’accès de Customer Journey Analytics
description: Découvrez comment mettre en oeuvre le contrôle d’accès dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 7021e4cfc9275402ce175bf8dfa8a3993ac438dd
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 63%

---

# Contrôle d’accès de Customer Journey Analytics

Customer Journey Analytics est régi par trois niveaux d’accès ou trois rôles : rôle d’administrateur de produit, rôle d’administrateur de profil de produit et accès au niveau de l’utilisateur. Cette rubrique explique ces rôles de manière plus détaillée.

En outre, nous discutons de méthodes plus granulaires pour limiter l’accès, telles que le traitement de Workspace ainsi que le contrôle d’accès au niveau des lignes et au niveau de la valeur.

## Rôle d’administrateur de produit

Les utilisateurs auxquels est affecté le rôle d’administrateur de produit disposent des autorisations nécessaires pour effectuer la plupart des tâches dans Customer Journey Analytics par défaut. Toutefois, certaines tâches requièrent des autorisations supplémentaires.

Pour ajouter un utilisateur en tant qu’administrateur de produit :

1. Accédez au [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Sélectionner [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Administrateurs**] onglet > [!UICONTROL **Ajouter un administrateur**].

   Les utilisateurs que vous avez ajoutés reçoivent la [Autorisations par défaut de l’administrateur de produit](#product-admin-default-permissions). Vous pouvez également leur accorder [autorisations supplémentaires](#product-admin-additional-permissions) si nécessaire.

### Autorisations par défaut de l’administrateur de produit

Les administrateurs de produit sont autorisés à effectuer la plupart des tâches dans Customer Journey Analytics.

Les administrateurs de produit disposent des autorisations nécessaires pour effectuer par défaut les tâches suivantes :

* Créer, mettre à jour et supprimer des vues de données
* Mise à jour et suppression de projets, filtres, mesures calculées, audiences, annotations ou filtres créés par d’autres utilisateurs
* Partager des projets Workspace avec tous les utilisateurs.
* Gestion de l’activité de création de rapports dans [Gestionnaire des activités de création de rapports](/help/reporting-activity-manager/reporting-activity-overview.md)

### Autorisations supplémentaires pour l’administrateur de produit

En plus d’être ajouté en tant qu’administrateur de produit dans la variable **Profil de produit Customer Journey Analytics** dans le [Admin Console](https://adminconsole.adobe.com/enterprise/), des autorisations supplémentaires sont requises pour effectuer les tâches suivantes dans Customer Journey Analytics :

* Créer, mettre à jour et supprimer des données [Connexions](/help/connections/overview.md)

  Pour effectuer cette tâche, les utilisateurs doivent faire partie d’un **Profil de produit Experience Platform** qui fournit les autorisations suivantes :
   * Modélisation des données : Afficher les schémas, Gérer les schémas
   * Gestion des données : Afficher les jeux de données, Gérer les jeux de données
   * Ingestion des données : Gérer les sources
   * Afficher des espaces de noms d’identités

     Pour plus d’informations sur les autorisations Experience Platform, voir [Contrôle d’accès dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=fr).

* Exportation des jeux de données vers le cloud [Destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=fr)

  >[!AVAILABILITY]
  >
  >La fonctionnalité décrite dans cet article se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de mise à jour du Customer Journey Analytics, voir [Versions des fonctionnalités de Customer Journey Analytics](/help/release-notes/releases.md).

  Pour effectuer cette tâche, les utilisateurs ont également besoin des autorisations Experience Platform suivantes :
   * Gestion des destinations
   * Activation des destinations

     Pour plus d’informations sur les autorisations de destinations Experience Platform, voir [Présentation des destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=en#access-controls).

## Rôle d’administrateur de profil de produit

Un profil de produit est un ensemble d’autorisations. Les administrateurs de profil de produit peuvent

* Créer et gérer des profils de produit individuels, comme ajouter de nouveaux utilisateurs ou gérer des groupes d’utilisateurs et leurs profils de produit associés.

* Dans Customer Journey Analytics, modifiez les vues de données qui font partie d’un profil de produit qu’elles gèrent. Ils ne peuvent pas créer de vues de données.

## Accès au niveau utilisateur

Les utilisateurs dans Customer Journey Analytics ne peuvent pas créer, modifier ou afficher des vues de données ou des connexions. Les utilisateurs peuvent créer des filtres, des projets, des audiences et des mesures calculées avec des autorisations spéciales dans Admin Console.

## Traitement du projet Workspace

Un autre niveau de contrôle d’accès peut être utilisé au niveau des rapports Workspace. Vous pouvez limiter l’accès à des composants spécifiques pour certains utilisateurs. Pour plus d’informations sur la façon de limiter les composants (dimensions, mesures, filtres, plages de dates) au niveau du projet Workspace et sur la manière dont le traitement est lié aux vues de données, voir [Traitement des projets](/help/analysis-workspace/curate-share/curate.md).

## Accorder l’accès à des mesures ou dimensions individuelles

Vous ne pouvez pas accorder ni refuser des autorisations concernant des mesures ou des dimensions individuelles dans Customer Journey Analytics comme le permet la version standard d’Adobe Analytics. Les mesures et dimensions peuvent être modifiées dans [vues de données](/help/data-views/data-views.md) et sont donc sujettes à des changements en Customer Journey Analytics. Cette modification permet également de modifier rétroactivement les rapports.

## Cas d’utilisation

Voici quelques cas d’utilisation qui illustrent comment le contrôle d’accès peut être utilisé dans des scénarios réels.

### Accès tiers

Un tiers avec lequel votre entreprise travaille dispose d’un chef d’équipe qui peut être nommé administrateur de profil de produit. Cet administrateur peut ensuite ajouter des utilisateurs de son équipe à ce profil de produit. Cet administrateur peut donner accès à des vues de données spécifiques et ajouter d’autres utilisateurs à ce profil de produit. Il peut également modifier les vues de données sur lesquelles il a le contrôle pour répondre aux besoins de son équipe.

### Contrôle d’accès au niveau de la ligne

Supposons que vous souhaitiez donner aux utilisateurs un accès aux données pour un seul jour. Voici comment limiter l’accès à ces lignes spécifiques :

1. Créez un filtre dans Customer Journey Analytics où **[!UICONTROL Jour]** est égal à la date à laquelle vous souhaitez qu’ils aient accès aux données.
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
| **[!UICONTROL Accès aux journaux d’audit]** | Cette autorisation applique la vérification des autorisations sur l’[API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) et l’interface utilisateur des journaux d’audit. |
| **[!UICONTROL Administrateur d’utilisation des rapports]** | Permet aux utilisateurs et utilisatrices d’afficher et de supprimer tout rapport exécuté dans leur entreprise. |
| **[!UICONTROL Affichage de l’utilisation des rapports]** | Permet aux utilisateurs et utilisatrices d’afficher toutes les requêtes de création de rapports simultanées. |
| [!UICONTROL **Exportation de tableau complet**] | Permet aux utilisateurs [exportation des tables complètes dans le cloud](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL Création des mesures calculées]** | Permet aux utilisateurs de créer des [mesures calculées](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Création de filtres]** | Permet aux utilisateurs de créer des [filtres](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Accès aux laboratoires]** | Permet aux utilisateurs d’accéder au [Labs](/help/labs/labs.md) dans Customer Journey Analytics. |
| **[!UICONTROL Création d’annotation]** | Permet aux utilisateurs de créer des [annotations](/help/components/annotations/overview.md). |
| **[!UICONTROL Création dʼaudiences]** | Permet aux utilisateurs de créer des [audiences](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Affichage de lʼaudience]** | Permet aux utilisateurs d’afficher des [audiences](/help/components/audiences/audiences-overview.md). |

{style="table-layout:auto"}
