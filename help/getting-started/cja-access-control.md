---
title: Contrôle d’accès CJA
description: Découvrez comment mettre en œuvre le contrôle d’accès dans CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: 04957adebd848739b8b3609eb35366d8296ee752
workflow-type: ht
source-wordcount: '945'
ht-degree: 100%

---

# Contrôle d’accès CJA

Customer Journey Analytics (CJA) est régi par trois niveaux d’accès ou trois rôles : le rôle d’administrateur de produit, le rôle d’administrateur de profil de produit et l’accès au niveau utilisateur. Cette rubrique explique ces rôles de manière plus détaillée.

En outre, nous discutons de méthodes plus granulaires pour limiter l’accès, telles que le traitement de Workspace ainsi que le contrôle d’accès au niveau des lignes et au niveau de la valeur.

## Rôle d’administrateur de produit

Les administrateurs de produit sont autorisés à effectuer toute tâche nécessaire dans CJA. Vous devez être ajouté en tant qu’administrateur de produit au **profil de produit de Customer Journey Analytics** dans [Admin Console](https://adminconsole.adobe.com/enterprise/) sous [!UICONTROL Customer Journey Analytics] > Onglet [!UICONTROL Admins] > [!UICONTROL Ajouter un administrateur]. Les autorisations suivantes sont accordées aux administrateurs de produits :

* Créer/mettre à jour/supprimer des connexions ou des vues de données.
* Mettre à jour/supprimer des projets, des filtres, des mesures calculées, des audiences, des annotations ou des filtres créés par dʼautres utilisateurs
* Partager des projets Workspace avec tous les utilisateurs.

Le statut d’administrateur de produit dans Customer Journey Analytics ne suffit pas pour pouvoir créer, mettre à jour ou supprimer une [connexion](/help/connections/overview.md). Pour créer une connexion à un jeu de données Experience Platform, vous avez également besoin d’autorisations Experience Platform. En particulier, vous devez faire partie d’un **profil de produit Experience Platform** qui vous donne les autorisations suivantes :

* Modélisation des données : Afficher les schémas, Gérer les schémas
* Gestion des données : Afficher les jeux de données, Gérer les jeux de données
* Ingestion des données : Gérer les sources
* Afficher des espaces de noms d’identités

Pour plus d’informations sur les autorisations Experience Platform, voir [Contrôle d’accès dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=fr).

## Rôle d’administrateur de profil de produit

Un profil de produit est un ensemble d’autorisations. Les administrateurs de profil de produit peuvent

* Créer et gérer des profils de produit individuels, comme ajouter de nouveaux utilisateurs ou gérer des groupes d’utilisateurs et leurs profils de produit associés.

* Dans CJA, modifier les vues de données qui font partie d’un profil de produit qu’ils gèrent. Ils ne peuvent pas créer de vues de données.

## Accès au niveau utilisateur

Les utilisateurs dans Customer Journey Analytics ne peuvent pas créer, modifier ou afficher des vues de données ou des connexions. Les utilisateurs peuvent créer des filtres, des projets, des audiences et des mesures calculées avec des autorisations spéciales dans Admin Console.

## Traitement du projet Workspace

Un autre niveau de contrôle d’accès peut être utilisé au niveau des rapports Workspace. Vous pouvez limiter l’accès à des composants spécifiques pour certains utilisateurs. Pour plus d’informations sur la façon de limiter les composants (dimensions, mesures, segments, périodes) au niveau du projet Workspace et sur la manière dont le traitement est lié aux vues de données, voir [Traiter les projets](/help/analysis-workspace/curate-share/curate.md).

## Accorder l’accès à des mesures ou dimensions individuelles

Vous ne pouvez pas accorder ni refuser des autorisations concernant des mesures ou des dimensions individuelles dans Customer Journey Analytics comme le permet la version standard d’Adobe Analytics. Les mesures et dimensions peuvent être modifiées dans les [vues de données](/help/data-views/data-views.md) et sont susceptibles d’être modifiées dans CJA. Cette modification permet également de modifier rétroactivement les rapports.

## Cas d’utilisation

Voici quelques cas d’utilisation qui illustrent comment le contrôle d’accès peut être utilisé dans des scénarios réels.

### Accès tiers

Un tiers avec lequel votre entreprise travaille dispose d’un chef d’équipe qui peut être nommé administrateur de profil de produit. Cet administrateur peut ensuite ajouter des utilisateurs de son équipe à ce profil de produit. Cet administrateur peut donner accès à des vues de données spécifiques et ajouter d’autres utilisateurs à ce profil de produit. Il peut également modifier les vues de données sur lesquelles il a le contrôle pour répondre aux besoins de son équipe.

### Contrôle d’accès au niveau de la ligne

Supposons que vous souhaitiez donner aux utilisateurs un accès aux données pour un seul jour. Voici comment limiter l’accès à ces lignes spécifiques :

1. Créez un filtre dans CJA où **[!UICONTROL Jour]** est égal à la date à laquelle vous souhaitez qu’ils aient accès aux données.
1. Dans [!UICONTROL Vues des données] > [!UICONTROL Paramètres], ajoutez ce filtre à la vue de données.
1. Enregistrez la vue de données et appliquez automatiquement le filtre au jeu de données. Toutes les lignes qui ne correspondent pas à la définition du filtre sont désormais automatiquement exclues de la vue de données modifiée.
1. Créez un profil de produit dans Admin Console, ajoutez-y des utilisateurs et limitez leur accès à cette vue de données.

### Contrôle d’accès au niveau de la valeur

Les utilisateurs qui ont accès à une vue de données ne peuvent travailler qu’avec les mesures et dimensions incluses par l’administrateur dans cette vue de données. Les administrateurs peuvent utiliser la [fonctionnalité d’inclusion/exclusion](/help/data-views/component-settings/include-exclude-values.md) dans les vues de données pour, par exemple, exclure certaines valeurs de dimension d’une vue de données.

Voici un exemple relatif à la santé : supposons que vous créiez une mesure appelée « Hypertension » dans une vue de données à partir d’un jeu de données qui inclut ces données. Le fait qu’il s’agisse d’une mesure vous permettrait de voir la valeur agrégée de cette mesure, mais pas les patients individuels qui en font partie.

## Autorisations CJA dans Admin Console

L’onglet **[!UICONTROL Autorisations]** fait partie de chaque profil de produit dans [Admin Console](https://adminconsole.adobe.com/enterprise/). Vous pouvez ajouter des utilisateurs à des profils de produit spécifiques. Ensuite, vous attribuez des droits à des vues de données spécifiques et spécifiez les autorisations dont disposent les utilisateurs dans un profil de produits. Voici les autorisations spécifiques à CJA :

![autorisations d’Admin Console](assets/permissions.png)

| Autorisation | Définition |
| --- | --- |
| **[!UICONTROL Vues des données]** | Si vous mettez **[!UICONTROL Inclure automatiquement]** sur **[!UICONTROL Activé]**, les utilisateurs qui font partie de ce profil de produit peuvent afficher toutes les vues de données existantes et nouvellement créées. Si ce paramètre est défini sur **[!UICONTROL Désactivé]**, vous pouvez sélectionner des vues de données spécifiques auxquelles les utilisateurs ont accès. |
| **[!UICONTROL Outils de création de rapports]** : |  |
| **[!UICONTROL Accès aux journaux d’audit]** | Actuellement, les [journaux d’audit](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) sont disponibles uniquement via l’API. Cette autorisation applique la vérification des autorisations sur l’API et une interface utilisateur des journaux d’audit à venir. |
| **[!UICONTROL Administrateur d’utilisation des rapports]** | Permet aux utilisateurs d’afficher et de supprimer tout rapport exécuté dans leur entreprise. (La fonctionnalité d’utilisation des rapports n’est pas encore disponible.) |
| **[!UICONTROL Affichage de l’utilisation des rapports]** | Permet aux utilisateurs d’afficher toutes les demandes de création de rapports simultanées. (La fonctionnalité d’utilisation des rapports n’est pas encore disponible.) |
| **[!UICONTROL Création des mesures calculées]** | Permet aux utilisateurs de créer des [mesures calculées](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Création de filtres]** | Permet aux utilisateurs de créer des [filtres](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Accès aux laboratoires]** | Permet aux utilisateurs d’accéder à l’onglet [Labs](/help/labs/labs.md) dans CJA. |
| **[!UICONTROL Création d’annotation]** | Permet aux utilisateurs de créer des [annotations](/help/components/annotations/overview.md). |
| **[!UICONTROL Création dʼaudiences]** | Permet aux utilisateurs de créer des [audiences](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Affichage de lʼaudience]** | Permet aux utilisateurs d’afficher des [audiences](/help/components/audiences/audiences-overview.md). |

{style=&quot;table-layout:auto&quot;}
