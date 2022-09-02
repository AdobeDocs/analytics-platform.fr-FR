---
title: Contrôle d’accès CJA
description: Découvrez comment mettre en oeuvre le contrôle d’accès dans CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: 04957adebd848739b8b3609eb35366d8296ee752
workflow-type: tm+mt
source-wordcount: '945'
ht-degree: 29%

---

# Contrôle d’accès CJA

Customer Journey Analytics (CJA) est régi par trois niveaux d’accès ou trois rôles : le rôle d’administrateur de produit, le rôle d’administrateur de profil de produit et l’accès au niveau utilisateur. Cette rubrique explique ces rôles de manière plus détaillée.

En outre, nous discutons de méthodes plus granulaires pour limiter l’accès, telles que le traitement de Workspace et au niveau des lignes, ainsi que le contrôle d’accès au niveau de la valeur.

## Rôle d’administrateur de produit

Les administrateurs de produit sont autorisés à effectuer toute tâche nécessaire dans CJA. Vous devez être ajouté en tant qu’administrateur de produit au **Profil de produit Customer Journey Analytics** dans le [Admin Console](https://adminconsole.adobe.com/enterprise/) under [!UICONTROL Customer Journey Analytics] > [!UICONTROL Administrateurs] onglet > [!UICONTROL Ajouter un administrateur]. Les autorisations suivantes sont accordées aux administrateurs de produits :

* Créer/mettre à jour/supprimer des connexions ou des vues de données.
* Mettre à jour/supprimer des projets, filtres, mesures calculées, audiences, annotations ou filtres créés par d’autres utilisateurs
* Partager des projets de Workspace avec tous les utilisateurs.

Devenir un administrateur de produit dans Customer Journey Analytics seul ne suffit pas à créer, mettre à jour ou supprimer une [connection](/help/connections/overview.md). Pour créer une connexion à un jeu de données Experience Platform, vous avez également besoin d’autorisations Experience Platform. En particulier, vous devez faire partie d’un **profil de produit Experience Platform** qui vous donne les autorisations suivantes :

* Modélisation des données : Afficher les schémas, Gérer les schémas
* Gestion des données : Afficher les jeux de données, Gérer les jeux de données
* Ingestion des données : Gérer les sources
* Afficher des espaces de noms d’identités

Pour plus d’informations sur les autorisations Experience Platform, voir [Contrôle d’accès dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=fr).

## Rôle d’administrateur de profil de produit

Un profil de produit est un ensemble d’autorisations. Les administrateurs de profil de produit peuvent

* Créez et gérez des profils de produit individuels, tels que l’ajout de nouveaux utilisateurs ou la gestion de groupes d’utilisateurs et des profils de produit associés.

* Dans CJA, modifiez les vues de données qui font partie d’un profil de produit qu’elles gèrent. Ils ne peuvent pas créer de vues de données.

## Accès au niveau utilisateur

Les utilisateurs de Customer Journey Analytics ne peuvent pas créer, modifier ni afficher de vues de données ou de connexions. Les utilisateurs peuvent créer des filtres, des projets, des audiences et des mesures calculées avec des autorisations spéciales dans Admin Console.

## Traitement du projet Workspace

Un autre niveau de contrôle d’accès peut être utilisé au niveau des rapports Workspace. Vous pouvez limiter l’accès à des composants spécifiques pour certains utilisateurs. Pour plus d’informations sur la façon de limiter les composants (dimensions, mesures, segments, périodes) au niveau du projet Workspace et sur la manière dont le traitement est lié aux vues de données, voir [Traiter les projets](/help/analysis-workspace/curate-share/curate.md).

## Accorder l’accès à des mesures ou dimensions individuelles

Vous ne pouvez pas accorder ni refuser des autorisations concernant des mesures ou des dimensions individuelles dans Customer Journey Analytics comme le permet la version standard d’Adobe Analytics. Les mesures et dimensions peuvent être modifiées dans [vues de données](/help/data-views/data-views.md) et sont donc sujets à changement dans CJA. La modification permet également de modifier rétroactivement les rapports.

## Cas d’utilisation

Voici quelques cas d’utilisation qui illustrent comment le contrôle d’accès peut être utilisé dans des scénarios réels.

### Accès tiers

Un tiers avec lequel votre entreprise travaille dispose d’un chef d’équipe qui peut être nommé administrateur de profil de produit. Cet administrateur peut ensuite ajouter des utilisateurs de son équipe à ce profil de produit. Cet administrateur peut donner accès à des vues de données spécifiques et ajouter d’autres utilisateurs à ce profil de produit. Ils peuvent également modifier les vues de données sur lesquelles ils ont le contrôle pour répondre aux besoins de leur équipe.

### Contrôle d’accès au niveau ligne

Supposons que vous souhaitiez donner aux utilisateurs un accès aux données à partir d’un seul jour. Voici comment limiter l’accès à ces lignes spécifiques :

1. Créez un filtre dans CJA où **[!UICONTROL Jour]** est égal à la date à laquelle vous souhaitez qu’ils aient accès aux données.
1. Dans [!UICONTROL Vues des données] > [!UICONTROL Paramètres], ajoutez ce filtre à la vue de données.
1. Enregistrez la vue de données et appliquez automatiquement le filtre au jeu de données. Toutes les lignes qui ne correspondent pas à la définition de filtre sont désormais automatiquement exclues de la vue de données modifiée.
1. Créez un profil de produit dans Admin Console, ajoutez-y des utilisateurs et limitez leur accès à cette vue de données.

### Contrôle d’accès de niveau valeur

Les utilisateurs qui ont accès à une vue de données ne peuvent travailler qu’avec les mesures et dimensions incluses par l’administrateur dans cette vue de données. Les administrateurs peuvent utiliser la variable [Fonctionnalité d’inclusion/exclusion](/help/data-views/component-settings/include-exclude-values.md) dans les vues de données pour, par exemple, exclure certaines valeurs de dimension d’une vue de données.

Voici un exemple relatif à la santé : Supposons que vous créiez une mesure appelée &quot;Hypertension&quot; dans une vue de données à partir d’un jeu de données qui inclut ces données. Le fait qu’il s’agisse d’une mesure vous permettrait de voir la valeur globale de cette mesure, mais pas les patients individuels qui en font partie.

## Autorisations CJA dans le Admin Console

Le **[!UICONTROL Autorisations]** fait partie de chaque profil de produit dans [Admin Console](https://adminconsole.adobe.com/enterprise/). Vous pouvez ajouter des utilisateurs à des profils de produit spécifiques. Ensuite, vous attribuez des droits à des vues de données spécifiques et spécifiez les autorisations dont disposent les utilisateurs dans un profil de produits. Voici les autorisations spécifiques à CJA :

![autorisations d’Admin Console](assets/permissions.png)

| Autorisation | Définition |
| --- | --- |
| **[!UICONTROL Vues des données]** | Si vous basculez **[!UICONTROL Inclure automatiquement]** to **[!UICONTROL Activé]**, les utilisateurs qui font partie de ce profil de produit peuvent afficher toutes les vues de données existantes et nouvellement créées. Si ce paramètre est défini sur **[!UICONTROL Off]**, vous pouvez sélectionner des vues de données spécifiques auxquelles les utilisateurs ont accès. |
| **[!UICONTROL Outils de création de rapports]**: |  |
| **[!UICONTROL Accès aux journaux d’audit]** | Actuellement, [journaux d’audit](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) sont disponibles uniquement via l’API . Cette autorisation applique la vérification des autorisations sur l’API et une interface utilisateur des journaux d’audit à venir. |
| **[!UICONTROL Administrateur d’utilisation des rapports]** | Permet aux utilisateurs d’afficher et de supprimer tout rapport exécuté dans leur entreprise. (La fonctionnalité d’utilisation des rapports n’est pas encore disponible.) |
| **[!UICONTROL Affichage de l’utilisation des rapports]** | Permet aux utilisateurs d’afficher toutes les demandes de création de rapports simultanées. (La fonctionnalité d’utilisation des rapports n’est pas encore disponible.) |
| **[!UICONTROL Création de mesures calculées]** | Permet aux utilisateurs de créer [mesures calculées](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Création de filtre]** | Permet aux utilisateurs de créer [filtres](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Accès aux laboratoires]** | Permet aux utilisateurs d’accéder au [Labs](/help/labs/labs.md) dans CJA. |
| **[!UICONTROL Création d’annotation]** | Permet aux utilisateurs de créer [annotations](/help/components/annotations/overview.md). |
| **[!UICONTROL Création de lʼaudience]** | Permet aux utilisateurs de créer [audiences](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Affichage de lʼaudience]** | Permet aux utilisateurs d’afficher [audiences](/help/components/audiences/audiences-overview.md). |

{style=&quot;table-layout:auto&quot;}
