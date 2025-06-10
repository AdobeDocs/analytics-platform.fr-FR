---
title: Contrôle d’accès de Customer Journey Analytics
description: Découvrez comment implémenter le contrôle d’accès dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '1549'
ht-degree: 24%

---

# Contrôle d’accès

Customer Journey Analytics est régi par trois niveaux d’accès ou trois rôles : le rôle d’administrateur de produit, le rôle d’administrateur de profil de produit et l’accès au niveau utilisateur. Cette rubrique explique ces rôles de manière plus détaillée.

En outre, cet article présente des méthodes plus granulaires de limitation de l’accès, telles que le traitement Workspace et le contrôle d’accès au niveau des lignes ainsi qu’au niveau de la valeur.

## Contrôle d’accès en fonction du rôle

Les niveaux de contrôle d’accès en fonction du rôle suivants sont disponibles.

### Rôle d’administrateur de produit

Les utilisateurs dotés du rôle d’administrateur de produit disposent par défaut des autorisations nécessaires pour effectuer la plupart des tâches dans Customer Journey Analytics. Cependant, certaines tâches nécessitent des autorisations supplémentaires.

Pour ajouter un utilisateur en tant qu’administrateur de produit :

1. Accédez à [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Sélectionnez [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Onglet Admins**] > [!UICONTROL **Ajouter un administrateur**].

   Les utilisateurs que vous avez ajoutés disposent des [autorisations par défaut de l’administrateur de produit](#product-admin-default-permissions). Vous pouvez également leur accorder des [autorisations supplémentaires](#product-admin-additional-permissions) si nécessaire.

#### Autorisations par défaut de l’administrateur de produit

Les administrateurs de produit sont autorisés à effectuer la plupart des tâches dans Customer Journey Analytics.

Les administrateurs de produit disposent par défaut des autorisations nécessaires pour effectuer les tâches suivantes :

* Créer, mettre à jour et supprimer des vues de données
* Mettre à jour et supprimer des projets, des segments, des mesures calculées, des audiences, des annotations ou des segments créés par d’autres utilisateurs
* Partager des projets Workspace avec tous les utilisateurs.
* Gérez les activités de rapports dans le [Gestionnaire des activités de rapports](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exporter des tables complètes](/help/analysis-workspace/export/export-cloud.md) depuis Analysis Workspace

#### Autorisations supplémentaires de l’administrateur de produit

En plus d’être ajouté en tant qu’administrateur de produit dans le profil de produit **Customer Journey Analytics** dans [Admin Console](https://adminconsole.adobe.com/enterprise/), vous devez disposer d’autorisations supplémentaires pour effectuer les tâches suivantes dans Customer Journey Analytics :

* Créer, mettre à jour et supprimer des données [Connexions](/help/connections/overview.md)

  Pour effectuer cette tâche, les utilisateurs doivent faire partie d&#39;un **profil de produit Experience Platform** qui fournit les autorisations suivantes :

  | Catégorie | Autorisation | Description |
  |---|---|---|
  | [!UICONTROL Modélisation des données] | [!UICONTROL Affichage des schémas] | Accès en lecture seule aux schémas et aux ressources associées. |
  | [!UICONTROL Modélisation des données] | [!UICONTROL Gestion des schémas] | Accès pour lire, créer, modifier et supprimer des schémas et des ressources associées. |
  | [!UICONTROL Gestion des données] | [!UICONTROL Affichage des jeux de données] | Accès en lecture seule aux jeux de données et aux schémas. |
  | [!UICONTROL Gestion des données] | [!UICONTROL Gestion des jeux de données] | Accès à la lecture, la création, la modification et la suppression des jeux de données. Accès en lecture seule aux schémas. |
  | [!UICONTROL Ingestion des données] | [!UICONTROL Gestion des sources] | Accès à la lecture, la création, la modification et la désactivation des sources. |
  | [!UICONTROL Identity Management] | [!UICONTROL Affichages des espaces de noms d’identité] | Accès en lecture seule aux espaces de noms d’identité. |

  Pour plus d’informations sur les autorisations Experience Platform, voir [Gestion des autorisations pour un profil de produit](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/ui/permissions).


* Si Adobe Journey Optimizer a été intégré à CJA où il existe des connexions AJO, les autorisations Parcours doivent également être ajoutées pour accéder à Connexions :

  | Catégorie | Autorisation | Description |
  |---|---|---|
  | [!UICONTROL Parcours] | [!UICONTROL Afficher les événements de Parcours, les sources de données et les actions] | Accès en lecture seule aux événements de parcours, aux actions personnalisées de parcours et aux sources de données de parcours. |
  | [!UICONTROL Parcours] | [!UICONTROL Gérer les événements Parcours, les sources de données et les actions] | Lire, créer, modifier et supprimer des événements, des sources ou des actions. |
  | [!UICONTROL Parcours] | [!UICONTROL Afficher les Parcours &#x200B;] | Accès en lecture seule aux parcours. |
  | [!UICONTROL Parcours] | [!UICONTROL Gérer les Parcours &#x200B;] | Lecture, création, modification et suppression des parcours. |

* Exporter des jeux de données vers des [destinations](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/ui/activate/export-datasets)

  Pour effectuer cette tâche, les utilisateurs doivent faire partie d&#39;un **profil de produit Experience Platform** qui fournit les autorisations suivantes :

  | Catégorie | Autorisation | Description |
  |---|---|---|
  | [!UICONTROL Destinations] | [!UICONTROL Gérer les destinations] | Accès à la lecture, la création et la suppression des connexions de destination et des comptes de destination. |
  | [!UICONTROL Destinations] | [!UICONTROL Activation des destinations] | Autoriser les utilisateurs à activer des segments vers des destinations existantes. Active l’étape de mappage dans le workflow d’activation. Cette autorisation nécessite également d’accorder l’autorisation Afficher les destinations à l’utilisateur ou l’utilisatrice qui souhaite activer des données vers les destinations. |

  Pour plus d’informations sur les autorisations Experience Platform, voir [Gestion des autorisations pour un profil de produit](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/ui/permissions).

* Utiliser l’extension [BI](../data-views/bi-extension.md)

  Pour que les utilisateurs puissent utiliser l’extension BI, un administrateur de produit

   * doit s’assurer que les autorisations Experience Platform de l’utilisateur incluent un rôle disposant de la ressource Query Service avec les options Gérer les requêtes et Gérer l’intégration de Query Service . Pour plus d’informations sur les autorisations Experience Platform, voir [Gestion des autorisations pour un profil de produit](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/ui/permissions).

     | Catégorie | Autorisation | Description |
     |---|---|---| 
     | [!UICONTROL Query Service] | [!UICONTROL Gestion des requêtes] | Accès à la lecture, la création, la modification et la suppression des requêtes SQL structurées pour les données Platform. |
     | [!UICONTROL Query Service] | [!UICONTROL Gestion de lʼintégration de Query Service] | Accès à la création, la mise à jour et la suppression des informations dʼidentification sans date dʼexpiration pour lʼaccès à Query Service. |

   * doit s’assurer que l’utilisateur dispose des autorisations Customer Journey Analytics appropriées :
      * l’autorisation d’accéder aux vues de données appropriées. Voir [!UICONTROL Vues de données] dans [Accès au niveau utilisateur](#user-level-access).
      * l’autorisation d’accéder à l’extension Customer Journey Analytics BI. Voir [!UICONTROL Outils de vues de données] dans [Accès au niveau utilisateur](#user-level-access).

### Rôle d’administrateur de profil de produit

Un profil de produit est un ensemble d’autorisations. Les administrateurs de produit créent des profils de produit et peuvent affecter des administrateurs de profil de produit à la gestion d’un ou de plusieurs profils de produit. Un administrateur de profil de produit peut alors :

* Gérez les profils de produit attribués. Par exemple, ajouter ou supprimer des utilisateurs ou des groupes d’utilisateurs et modifier les autorisations pour les profils de produit.

* Dans Customer Journey Analytics, modifiez les vues de données qui font partie d’un profil de produit attribué. Les administrateurs de profil de produit ne peuvent pas créer de vues de données.

### Accès au niveau utilisateur

Le tableau ci-dessous décrit les principales autorisations d’accès pour différentes fonctionnalités de Customer Journey Analytics que vous pouvez configurer pour les utilisateurs appropriés. Vous pouvez gérer différents niveaux d’accès utilisateur par le biais de profils de produit. Un profil de produit combine un certain nombre d’autorisations que vous pouvez ensuite attribuer à des utilisateurs individuels ou à des groupes d’utilisateurs.

L’onglet **[!UICONTROL Autorisations]** fait partie de chaque profil de produit dans [Admin Console](https://adminconsole.adobe.com/enterprise/).

![autorisations d’Admin Console](assets/permissions.png)

| Catégorie | Autorisation | Description |
| --- | --- | ---|
| [!UICONTROL Vues des données] | *nom de la vue de données* | Si vous mettez **[!UICONTROL Inclure automatiquement]** sur **[!UICONTROL Activé]**, les utilisateurs qui font partie de ce profil de produit peuvent afficher toutes les vues de données existantes et nouvellement créées. Si ce paramètre est défini sur **[!UICONTROL Désactivé]**, vous pouvez sélectionner des vues de données spécifiques auxquelles les utilisateurs ont accès. |
| [!UICONTROL Outils de reporting] | [!UICONTROL Accès à Analysis Workspace] | Autoriser les utilisateurs à accéder à [Analysis Workspace](/help/analysis-workspace/home.md). |
| [!UICONTROL Outils de reporting] | [!UICONTROL Accès aux analyses guidées] | Autoriser les utilisateurs à accéder à [Analyse guidée](/help/guided-analysis/overview.md). |
| [!UICONTROL Outils de reporting] | [!UICONTROL Création des mesures calculées] | Autoriser les utilisateurs à créer des [mesures calculées](/help/components/calc-metrics/calc-metr-overview.md). Les utilisateurs peuvent baliser, partager, supprimer, renommer, approuver ou annuler l’approbation uniquement des mesures calculées qu’ils créent ou des mesures calculées partagées avec eux. |
| [!UICONTROL Outils de reporting] | [!UICONTROL Création de segment] | Autoriser les utilisateurs à créer des [segments](/help/components/segments/seg-overview.md). Les utilisateurs peuvent baliser, partager, supprimer, renommer, approuver ou désapprouver uniquement les segments qu’ils créent ou les segments qu’ils partagent. |
| [!UICONTROL Outils de reporting] | [!UICONTROL Accès aux laboratoires] | Autoriser les utilisateurs à accéder à l’onglet [Labs](/help/labs/labs.md) dans Customer Journey Analytics. |
| [!UICONTROL Outils de reporting] | [!UICONTROL Création d’annotation] | Autoriser les utilisateurs à créer des [annotations](/help/components/annotations/overview.md). Les utilisateurs peuvent uniquement baliser, partager, supprimer et renommer les annotations qu’ils créent ou les annotations partagées avec eux. |
| [!UICONTROL Outils de reporting] | [!UICONTROL Affichage de lʼaudience] | Autoriser les utilisateurs à afficher les [audiences](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Outils de reporting] | [!UICONTROL Création dʼaudiences] | Autoriser les utilisateurs à créer des [audiences](/help/components/audiences/audiences-overview.md) |
| [!UICONTROL Outils de reporting] | [!UICONTROL Accès aux journaux d’audit] | Appliquez la vérification des autorisations sur l’[API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) et l’interface utilisateur des journaux d’audit. |
| [!UICONTROL Outils de reporting] | [!UICONTROL Partager les liens du projet avec tout le monde] | Autoriser les utilisateurs [à partager des projets avec tout le monde.](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL Outils de reporting] | [!UICONTROL Prévisions] | Autoriser les utilisateurs à accéder à la fonctionnalité [Prévision](../analysis-workspace/c-forecast/forecasting.md) d’Analysis Workspace |
| [!UICONTROL Outils de reporting] | [!UICONTROL Assistant IA : connaissance des produits] | Autoriser les utilisateurs à accéder à l’[assistant AI](../ai-assistant.md) pour acquérir des connaissances sur les produits. |
| [!UICONTROL Outils de reporting] | [!UICONTROL Légendes intelligentes] | Autoriser les utilisateurs à accéder aux [Légendes intelligentes](/help/analysis-workspace/visualizations/intelligent-captions.md). |
| [!UICONTROL Outils de vues de données] | [!UICONTROL Exportation de table complète] | Autoriser les utilisateurs à [exporter des tables complètes vers le cloud](/help/analysis-workspace/export/export-cloud.md). |
| [!UICONTROL Outils de vues de données] | [!UICONTROL Extension CJA BI] | Autoriser les utilisateurs à utiliser l’extension [BI](../data-views/bi-extension.md). |

{style="table-layout:auto"}

## Traitement du projet Workspace

Un autre niveau de contrôle d’accès peut être utilisé au niveau des rapports Workspace. Vous pouvez limiter l’accès à des composants spécifiques pour certains utilisateurs. Pour plus d’informations sur la façon de limiter les composants (dimensions, mesures, segments, périodes) au niveau du projet Workspace et sur la manière dont le traitement est lié aux vues de données, voir [Traiter les projets](/help/analysis-workspace/curate-share/curate.md).

## Accorder l’accès à des mesures ou dimensions individuelles

Vous ne pouvez pas accorder ni refuser des autorisations concernant des mesures ou des dimensions individuelles dans Customer Journey Analytics comme le permet la version standard d’Adobe Analytics. Les mesures et dimensions peuvent être modifiées dans les [vues de données](/help/data-views/data-views.md) et sont susceptibles d’être modifiées dans Customer Journey Analytics. Cette modification permet également de modifier rétroactivement les rapports.

## Cas d’utilisation

Voici quelques cas d’utilisation qui illustrent comment le contrôle d’accès peut être utilisé dans des scénarios réels.

### Accès tiers

Vous pouvez fournir un accès d’administration de profil de produit à un chef d’équipe d’un tiers au sein duquel votre entreprise travaille. Cet administrateur peut ajouter des utilisateurs de l’équipe de l’entreprise à ce profil de produit. Cet administrateur de profil de produit peut donner accès à des vues de données spécifiques et ajouter d’autres utilisateurs tiers à ce profil de produit. L’administrateur du profil de produit peut modifier les vues de données pour les adapter aux besoins de l’équipe tierce.

### Contrôle d’accès au niveau de la ligne

Vous souhaitez donner aux utilisateurs un accès aux données pour un seul jour. Voici comment limiter l’accès à ces lignes spécifiques :

1. Créez un segment dans [!UICONTROL Paramètres] d’une vue de données spécifique, où [!UICONTROL Jour] correspond à la date à laquelle vous souhaitez qu’ils aient accès aux données. Voir [Créer une vue de données](/help/data-views/create-dataview.md#settings-filters) pour plus d’informations.
1. Enregistrez la vue de données, qui applique le segment à la partie de données des jeux de données dans la connexion sous-jacente. Toutes les lignes qui ne correspondent pas à la définition de segment sont automatiquement exclues de la vue de données et ne sont pas disponibles pour Analysis Workspace lors de l’utilisation de cette vue de données.
1. Créez un [profil de produit](#product-profile-admin-role) dans Admin Console, ajoutez des utilisateurs au profil de produit et incluez uniquement cette vue de données spécifique au profil de produit.

### Contrôle d’accès au niveau de la valeur

Les utilisateurs qui ont accès à une vue de données ne peuvent travailler qu’avec les mesures et dimensions incluses par l’administrateur dans cette vue de données. Les administrateurs et administratrices peuvent utiliser la fonctionnalité [Inclure/Exclure](/help/data-views/component-settings/include-exclude-values.md) ou le [Regroupement de valeurs](../data-views/component-settings/value-bucketing.md) des paramètres de composant dans les vues de données pour exclure ou agréger certaines valeurs de dimension d’une vue de données.

Par exemple : vous créez une mesure appelée *Hypertension* dans une vue de données à partir d’un composant qui contient les données individuelles du patient du jeu de données. Vous utilisez le regroupement de valeurs pour fournir uniquement l’accès aux valeurs regroupées, de sorte que les utilisateurs des données ne voient pas les données individuelles des patients.


