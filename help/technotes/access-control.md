---
title: Contrôle d’accès de Customer Journey Analytics
description: Découvrez comment mettre en œuvre le contrôle d’accès dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 81e08ecb593b6ba789c479d0e648cbe7ba0a82d6
workflow-type: tm+mt
source-wordcount: '1554'
ht-degree: 96%

---

# Contrôle d’accès

Customer Journey Analytics est régi par trois niveaux d’accès ou trois rôles : le rôle d’administration de produit, le rôle d’administration de profil de produit et l’accès au niveau des utilisateurs et utilisatrices. Cette rubrique explique ces rôles de manière plus détaillée.

En outre, cet article aborde des méthodes plus détaillées sur la limite d’accès, telles que le traitement de Workspace ainsi que le contrôle d’accès au niveau des lignes et au niveau de la valeur.

## Contrôle d’accès en fonction du rôle

Les niveaux de contrôle d’accès en fonction du rôle suivants sont disponibles.

### Rôle d’administration de produit

Les personnes dotées du rôle d’administration de produit disposent par défaut des autorisations nécessaires pour effectuer la plupart des tâches dans Customer Journey Analytics. Cependant, certaines tâches nécessitent des autorisations supplémentaires.

Pour ajouter une personne en tant qu’administratrice de produit :

1. Accédez à [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Sélectionnez [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Onglet Admins**] > [!UICONTROL **Ajouter un administrateur ou une administratrice**].

   Les personnes que vous avez ajoutées disposent des [autorisations par défaut pour l’administration de produit](#product-admin-default-permissions). Vous pouvez également leur accorder des [autorisations supplémentaires](#product-admin-additional-permissions) si nécessaire.

#### Autorisations par défaut pour l’administration de de produit

Les administrateurs et administratrices de produit sont autorisés à effectuer la plupart des tâches dans Customer Journey Analytics.

Les administrateurs et administratrices de produit disposent par défaut des autorisations nécessaires pour effectuer les tâches suivantes :

* Mettre à jour et supprimer des projets, des segments, des mesures calculées, des audiences, des annotations ou des segments créés par d’autres personnes
* Partager des projets Workspace avec tous les utilisateurs et utilisatrices
* Gérer l’activité de reporting dans le [Gestionnaire des activités de rapport](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exporter des tableaux complets](/help/analysis-workspace/export/export-cloud.md) depuis Analysis Workspace

#### Autorisations supplémentaires pour l’administration de produit

En plus de l’ajout en tant qu’administrateur ou administratrice de produit dans le profil de produit **Customer Journey Analytics** de l’[Admin Console](https://adminconsole.adobe.com/enterprise/), vous devez disposer d’autorisations supplémentaires pour effectuer les tâches suivantes dans Customer Journey Analytics :

* Créer, mettre à jour et supprimer des [vues de données](/help/data-views/data-views.md)
* Créer, mettre à jour et supprimer des [connexions](/help/connections/overview.md)

  Pour effectuer cette tâche, il est nécessaire de faire partie d’un **profil de produit Experience Platform** qui fournit les autorisations suivantes :

  | Catégorie | Autorisation | Description |
  |---|---|---|
  | [!UICONTROL Sandbox] | [!UICONTROL Au moins une] | Accès aux sandbox appropriés pour les connexions. |
  | [!UICONTROL Modélisation des données] | [!UICONTROL Affichage des schémas] | Accès en lecture seule aux schémas et aux ressources associées. |
  | [!UICONTROL Modélisation des données] | [!UICONTROL Gestion des schémas] | Accès pour lire, créer, modifier et supprimer des schémas et des ressources associées. |
  | [!UICONTROL Gestion des données] | [!UICONTROL Affichage des jeux de données] | Accès en lecture seule aux jeux de données et aux schémas. |
  | [!UICONTROL Identity Management] | [!UICONTROL Affichage des espaces de noms d’identité] | Accès en lecture seule aux espaces de noms d’identité. |

  Pour plus d’informations sur les autorisations Experience Platform, voir [Gestion des autorisations pour un profil de produit](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/ui/permissions).


* Si Journey Optimizer est intégré à Customer Journey Analytics où il existe des connexions Journey Optimizer, les autorisations de parcours doivent également être ajoutées pour accéder aux connexions :

  | Catégorie | Autorisation | Description |
  |---|---|---|
  | [!UICONTROL Parcours] | [!UICONTROL Afficher les événements de parcours, les sources de données et les actions] | Accès en lecture seule aux événements de parcours, aux actions personnalisées de parcours et aux sources de données de parcours. |
  | [!UICONTROL Parcours] | [!UICONTROL Gérer les événements de parcours, les sources de données et les actions] | Lecture, création, modification et suppression des événements, des sources ou des actions. |
  | [!UICONTROL Parcours] | [!UICONTROL Afficher les parcours] | Accès en lecture seule aux parcours. |
  | [!UICONTROL Parcours] | [!UICONTROL Gérer les parcours] | Lecture, création, modification et suppression des parcours. |

* Exporter des jeux de données vers des [destinations](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/ui/activate/export-datasets)

  Pour effectuer cette tâche, il est nécessaire de faire partie d’un **profil de produit Experience Platform** qui fournit les autorisations suivantes :

  | Catégorie | Autorisation | Description |
  |---|---|---|
  | [!UICONTROL Destinations] | [!UICONTROL Gérer les destinations] | Accès à la lecture, à la création et à la suppression des connexions de destination et des comptes de destination. |
  | [!UICONTROL Destinations] | [!UICONTROL Activer les destinations] | Permet aux utilisateurs et utilisatrices d’activer des segments vers des destinations existantes. Active l’étape de mappage dans le workflow d’activation. Cette autorisation nécessite également que le droit Afficher les destinations soit accordé à la personne qui souhaite activer les données vers des destinations. |

  Pour plus d’informations sur les autorisations Experience Platform, voir [Gestion des autorisations pour un profil de produit](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/ui/permissions).

* Utiliser l’[extension BI](../data-views/bi-extension.md)

  Pour que les personnes puissent utiliser l’extension BI, un administrateur ou une administration de produit

   * doit s’assurer que les autorisations Experience Platform de la personne incluent un rôle disposant de la ressource Service de requête avec les options Gérer les requêtes et Gérer l’intégration du service de requête. Pour plus d’informations sur les autorisations Experience Platform, voir [Gestion des autorisations pour un profil de produit](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/ui/permissions).

     | Catégorie | Autorisation | Description |
     |---|---|---|
     | [!UICONTROL Service de requêtes] | [!UICONTROL Gestion des requêtes] | Accès à la lecture, la création, la modification et la suppression des requêtes SQL structurées pour les données Platform. |
     | [!UICONTROL Service de requêtes] | [!UICONTROL Gestion de lʼintégration du service de requête] | Accès à la création, la mise à jour et la suppression des informations dʼidentification sans date dʼexpiration pour lʼaccès au service de requête. |

   * doit s’assurer que la personne dispose des autorisations Customer Journey Analytics appropriées :
      * autorisation d’accéder aux vues de données appropriées. Voir [!UICONTROL Vues de données] dans [Accès au niveau utilisateur et utilisatrice](#user-level-access).
      * autorisation d’accéder à l’extension BI de Customer Journey Analytics. Voir [!UICONTROL Outils de vues de données] dans [Accès au niveau utilisateur et utilisatrice](#user-level-access).

### Rôle d’administration de profil de produit

Un profil de produit est un ensemble d’autorisations. Les administrateurs et administratrices de produit créent des profils de produit et peuvent affecter des personnes à la gestion d’un ou de plusieurs profils de produit. Un administrateur ou une administratrice de profil de produit peut alors :

* Gérer les profils de produit attribués. Par exemple, ajouter ou supprimer des personnes ou des groupes et modifier les autorisations pour les profils de produit.

* Dans Customer Journey Analytics, modifier les vues de données qui font partie d’un profil de produit attribué. Les administrateurs et administratrices de profil de produit ne peuvent pas créer de vues de données.

### Accès au niveau utilisateur

Le tableau ci-dessous décrit les principales autorisations d’accès pour différentes fonctionnalités de Customer Journey Analytics que vous pouvez configurer pour les personnes appropriées. Vous pouvez gérer différents niveaux d’accès d’utilisation par le biais de profils de produit. Un profil de produit combine un certain nombre d’autorisations que vous pouvez ensuite attribuer à des personnes individuelles ou à des groupes.

L’onglet **[!UICONTROL Autorisations]** s’affiche sur chaque profil de produit dans [Admin Console](https://adminconsole.adobe.com/enterprise/).

![autorisations d’Admin Console](assets/permissions.png)

| Catégorie | Autorisation | Description |
| --- | --- | ---|
| [!UICONTROL Vues des données] | *nom de la vue de données* | Si vous définissez **[!UICONTROL Inclure automatiquement]** sur **[!UICONTROL Activé]**, les personnes qui font partie de ce profil de produit peuvent afficher toutes les vues de données existantes et nouvellement créées. Si ce paramètre est défini sur **[!UICONTROL Désactivé]**, vous pouvez sélectionner des vues de données spécifiques auxquelles les utilisateurs ont accès. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Accès aux analyses guidées] | Autoriser l’accès aux [Analyses guidées](/help/guided-analysis/overview.md). |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Création des mesures calculées] | Autoriser la création des [mesures calculées](/help/components/calc-metrics/calc-metr-overview.md). Les utilisateurs peuvent baliser, partager, supprimer et renommer uniquement les mesures calculées qu’ils créent ou les mesures calculées partagées avec eux. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Création de segment] | Autoriser la création des [segments](/help/components/segments/seg-overview.md). Les utilisateurs peuvent baliser, partager, supprimer et renommer uniquement les segments qu’ils créent ou les segments qu’ils partagent. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Accès aux laboratoires] | Autoriser l’accès à l’onglet [Labs](/help/labs/labs.md) dans Customer Journey Analytics. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Création d’annotation] | Autoriser la création des [annotations](/help/components/annotations/overview.md). Les personnes peuvent uniquement baliser, partager, supprimer et renommer les annotations qu’elles créent ou auxquelles elles ont accès. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Affichage de lʼaudience] | Autoriser l’affichage des [audiences](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Création dʼaudiences] | Autoriser les utilisateurs à créer des [audiences](/help/components/audiences/audiences-overview.md) Nécessite [Gérer les segments](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/home) dans Adobe Experience Platform. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Mise en récit des données] | Autoriser à [générer des présentations de diapositives basées sur des projets Workspace.](/help/analysis-workspace/curate-share/generate-slides.md) |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Accès aux journaux d’audit] | Appliquer la vérification des autorisations sur l’[API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) et l’interface d’utilisation des journaux d’audit. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Partager les liens du projet avec tout le monde] | Autoriser le [partage du projet avec tout le monde.](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Prévisions] | Autoriser l’accès à la fonctionnalité [Prévision](../analysis-workspace/c-forecast/forecasting.md) d’Analysis Workspace |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Assistant IA : connaissances du produit] | Autoriser l’accès à l’[assistant AI](../ai-assistant.md) pour acquérir des connaissances sur les produits. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Agent Data Insights] | Autoriser les utilisateurs à accéder à [Data Insights Agent](../data-analysis-ai.md) pour les informations de données pilotées par l’IA. |
| [!UICONTROL Outils de création de rapports] | [!UICONTROL Légendes intelligentes] | Autoriser l’accès aux [légendes intelligentes](/help/analysis-workspace/visualizations/intelligent-captions.md). |
| [!UICONTROL Outils des vues de données] | [!UICONTROL Export du tableau complet] | Autorise l’[export des tableaux complets dans le cloud](/help/analysis-workspace/export/export-cloud.md) |
| [!UICONTROL Outils des vues de données] | [!UICONTROL Extension BI de CJA] | Autoriser l’utilisation de l’extension [BI](../data-views/bi-extension.md). |

{style="table-layout:auto"}

## Traitement du projet Workspace

Un autre niveau de contrôle d’accès peut être utilisé au niveau des rapports Workspace. Vous pouvez limiter l’accès à des composants spécifiques pour certains utilisateurs. Pour plus d’informations sur la façon de limiter les composants (dimensions, mesures, segments, périodes) au niveau du projet Workspace et sur la manière dont le traitement est lié aux vues de données, voir [Traiter les projets](/help/analysis-workspace/curate-share/curate.md).

## Accorder l’accès à des mesures ou dimensions individuelles

Vous ne pouvez pas accorder ni refuser des autorisations concernant des mesures ou des dimensions individuelles dans Customer Journey Analytics comme le permet la version standard d’Adobe Analytics. Les mesures et dimensions peuvent être modifiées dans les [vues de données](/help/data-views/data-views.md) et sont susceptibles d’être modifiées dans Customer Journey Analytics. Cette modification permet également de modifier rétroactivement les rapports.

## Cas d’utilisation

Voici quelques cas d’utilisation qui illustrent comment le contrôle d’accès peut être utilisé dans des scénarios réels.

### Accès tiers

Vous pouvez fournir un accès d’administration de profil de produit à un chef ou une cheffe d’équipe d’une tierce personne au sein duquel votre entreprise travaille. Cette dernière peut ensuite ajouter des personnes de son équipe à ce profil de produit. La personne administrant le profil de produit peut donner accès à des vues de données spécifiques et ajouter d’autres personnes à ce profil de produit. Elle peut modifier les vues de données pour les adapter aux besoins de l’équipe tierce.

### Contrôle d’accès au niveau de la ligne

Vous souhaitez octroyer un accès aux données pour un seul jour. Voici comment limiter l’accès à ces lignes spécifiques :

1. Créez un segment dans [!UICONTROL Paramètres] d’une vue de données spécifique, où [!UICONTROL Jour] correspond à la date à laquelle octroyer l’accès aux données. Consultez [Créer une vue de données](/help/data-views/create-dataview.md#settings-filters) pour plus d’informations.
1. Enregistrez la vue de données, qui applique le segment à la partie de données des jeux de données dans la connexion sous-jacente. Toutes les lignes qui ne correspondent pas à la définition de segment sont automatiquement exclues de la vue de données et ne sont pas disponibles pour Analysis Workspace lors de l’utilisation de cette vue de données.
1. Créez un [profil de produit](#product-profile-admin-role) dans Admin Console, ajoutez-y des utilisateurs et utilisatrices et incluez uniquement cette vue de données spécifique au profil de produit.

### Contrôle d’accès au niveau de la valeur

Les personnes qui ont accès à une vue de données ne peuvent travailler qu’avec les mesures et dimensions incluses par l’administrateur ou l’administratrice dans cette vue de données. Les administrateurs et administratrices peuvent utiliser la [fonctionnalité Inclure/Exclure](/help/data-views/component-settings/include-exclude-values.md) ou les paramètres de composant [Groupement des valeurs](../data-views/component-settings/value-bucketing.md) dans les vues de données pour exclure ou agréger certaines valeurs de dimension d’une vue de données.

Par exemple : vous créez une mesure appelée *Hypertension* dans une vue de données à partir d’un composant qui contient les données individuelles d’une patiente ou d’un patient à partir du jeu de données. Le groupement des valeurs sert à fournir l’accès uniquement aux valeurs groupées, de sorte que les utilisateurs et utilisatrices des données ne voient pas les données individuelles des patientes et patients.
