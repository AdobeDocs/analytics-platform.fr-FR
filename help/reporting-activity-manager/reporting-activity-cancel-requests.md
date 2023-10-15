---
title: Annulation des demandes de création de rapports dans le Gestionnaire d’activités de création de rapports
description: Découvrez comment utiliser le gestionnaire des activités de rapport pour diagnostiquer et corriger les problèmes de capacité pendant les heures de pointe de la création de rapports.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 57124124254f5ca9eb2a9f63a7478cd288c19b0e
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 7%

---

# Annulation des demandes de création de rapports dans le Gestionnaire d’activités de création de rapports

{{release-limited-testing}}

La variable [!UICONTROL Gestionnaire des activités de création de rapports] permet aux administrateurs de diagnostiquer et d’annuler rapidement les demandes de création de rapports afin de corriger les problèmes de capacité de création de rapports pendant les heures de pointe de la création de rapports.

Tenez compte des points suivants lors de l’annulation de demandes de création de rapports :

* Vous pouvez annuler des requêtes spécifiques, annuler toutes les requêtes d’un utilisateur spécifique ou annuler toutes les requêtes liées à un projet spécifique.

* Lorsque vous annulez des requêtes, vous pouvez également choisir de limiter les requêtes suivantes pour une période donnée.

* Vous ne pouvez pas annuler une requête si la variable [!UICONTROL **Utilisateur**] la colonne d’une requête s’affiche comme [!UICONTROL **Non reconnu**]. Dans ce cas, cela signifie que l’utilisateur se trouve dans une société de connexion dans laquelle vous ne disposez pas des autorisations d’administration.

Pour plus d’informations sur la gestion des activités de création de rapports, y compris les principaux avantages et les exigences en matière d’autorisation, voir [Présentation d’Activity Manager dans les rapports](/help/reporting-activity-manager/reporting-activity-overview.md).

## Annulation de requêtes spécifiques

Vous pouvez annuler des requêtes individuelles qui consomment une grande capacité de création de rapports.

1. En Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire des activités de création de rapports]**.

1. Sélectionnez la connexion pour laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles sur cette page, voir [Afficher l’activité de création de rapports dans le Gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez la variable [!UICONTROL **Demandes**] , puis sélectionnez une ou plusieurs requêtes.

   <!-- add screenshot -->

1. Sélectionner [!UICONTROL **Annulation des requêtes**].

   La variable [!UICONTROL **Annuler _x_ requêtes de rapport**] s’affiche.

1. Le champ Message d’annulation affiche le message qui s’affiche aux utilisateurs lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour limiter les demandes futures pour une période donnée, activez l’option permettant de [!UICONTROL **Limitation des requêtes suivantes**], puis choisissez l’une des options suivantes :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les utilisateurs associés aux requêtes sélectionnées ne pourront temporairement pas exécuter de requêtes de création de rapports pour les projets associés. |
   | [!UICONTROL **Utilisateur**] | Les utilisateurs et utilisatrices associés aux demandes sélectionnées ne pourront temporairement pas effectuer des demandes de rapports. |
   | [!UICONTROL **Projet**] | Les projets associés aux demandes sélectionnées seront temporairement exclus de toutes les demandes de rapports. |
   | [!UICONTROL **Réservé à**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!-- double-check this --><p>Une fois définie, vous ne pouvez pas supprimer une restriction plus tôt.</p> |

   {style="table-layout:auto"}

1. Sélectionner [!UICONTROL **Continuer avec annulation**].

   Une notification s’affiche dans Analysis Workspace pour informer les utilisateurs que la demande a été annulée. Pour plus d’informations sur la façon dont cela apparaît dans Analysis Workspace, voir [Expérience lorsque les utilisateurs accèdent à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Annulation des requêtes par l’utilisateur

Vous pouvez annuler toutes les requêtes associées à un ou plusieurs utilisateurs.

1. En Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire des activités de création de rapports]**.

1. Sélectionnez la connexion pour laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles sur cette page, voir [Afficher l’activité de création de rapports dans le Gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez la variable [!UICONTROL **Utilisateurs**] , puis sélectionnez un ou plusieurs utilisateurs.

   <!-- add screenshot -->

1. Sélectionner [!UICONTROL **Annulation des requêtes**].

   La variable [!UICONTROL **Annuler _x_ requêtes de rapport de x utilisateurs**] s’affiche.

1. Le champ Message d’annulation affiche le message qui s’affiche aux utilisateurs lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour limiter les demandes futures pour une période donnée, activez l’option permettant de [!UICONTROL **Limitation des requêtes suivantes**], puis choisissez l’une des options suivantes :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les utilisateurs sélectionnés ne seront temporairement pas autorisés à effectuer des requêtes de création de rapports pour les projets associés. |
   | [!UICONTROL **Utilisateur**] | Les utilisateurs sélectionnés seront temporairement empêchés d’effectuer toute demande de création de rapports. |
   | [!UICONTROL **Projet**] | Les projets associés aux utilisateurs sélectionnés seront limités aux demandes de création de rapports effectuées par n’importe quel utilisateur. |
   | [!UICONTROL **Réservé à**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!--double-check this--> <p>Une fois définie, vous ne pouvez pas supprimer une restriction plus tôt.</p> |

   {style="table-layout:auto"}

1. Sélectionner [!UICONTROL **Continuer avec annulation**].

   Une notification s’affiche dans Analysis Workspace pour informer les utilisateurs que la demande a été annulée. Pour plus d’informations sur la façon dont cela apparaît dans Analysis Workspace, voir [Expérience lorsque les utilisateurs accèdent à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Annulation des demandes par projet

Vous pouvez annuler toutes les requêtes associées à un ou plusieurs projets.

1. En Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire des activités de création de rapports]**.

1. Sélectionnez la connexion pour laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles sur cette page, voir [Afficher l’activité de création de rapports dans le Gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez la variable [!UICONTROL **Projets**] , puis sélectionnez un ou plusieurs projets.

   <!-- add screenshot -->

1. Sélectionner [!UICONTROL **Annulation des requêtes**].

   La variable [!UICONTROL **Annuler _x_ requêtes de rapport provenant de x projets**] s’affiche.

1. Le champ Message d’annulation affiche le message qui s’affiche aux utilisateurs lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour limiter les demandes futures pour une période donnée, activez l’option permettant de [!UICONTROL **Limitation des requêtes suivantes**], puis choisissez l’une des options suivantes :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les projets sélectionnés seront temporairement limités aux demandes de création de rapports effectuées par les utilisateurs associés. |
   | [!UICONTROL **Utilisateur**] | Les utilisateurs associés aux projets sélectionnés ne pourront pas effectuer de requêtes de création de rapports. |
   | [!UICONTROL **Projet**] | Les projets sélectionnés seront temporairement limités aux demandes de création de rapports effectuées par n’importe quel utilisateur. |
   | [!UICONTROL **Réservé à**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!--double-check this--> <p>Une fois définie, vous ne pouvez pas supprimer une restriction plus tôt.</p> |

   {style="table-layout:auto"}

1. Sélectionner [!UICONTROL **Continuer avec annulation**].

   Une notification s’affiche dans Analysis Workspace pour informer les utilisateurs que la demande a été annulée. Pour plus d’informations sur la façon dont cela apparaît dans Analysis Workspace, voir [Expérience lorsque les utilisateurs accèdent à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Expérience lorsque les utilisateurs accèdent à un rapport annulé

<!-- Update for CJA and AA -->

Dans Analysis Workspace, les utilisateurs voient s’afficher le message suivant lorsqu’ils tentent d’accéder à un rapport qui a été annulé par un administrateur :

![avertissement-utilisateur-annulation](assets/cancel-user-facing.png)