---
title: Annulation des demandes de création de rapports dans le Gestionnaire d’activités de création de rapports
description: Découvrez comment utiliser le gestionnaire des activités de rapport pour diagnostiquer et corriger les problèmes de capacité pendant les heures de pointe de la création de rapports.
solution: Customer Journey Analytics
feature: Basics
exl-id: 87da2447-f114-432a-9f63-e660c2541d0f
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '1473'
ht-degree: 14%

---

# Annulation des demandes de création de rapports dans le Gestionnaire d’activités de création de rapports

La variable [!UICONTROL Gestionnaire des activités de création de rapports] permet aux administrateurs de diagnostiquer et d’annuler rapidement les demandes de création de rapports afin de corriger les problèmes de capacité de création de rapports pendant les heures de pointe de la création de rapports.

Tenez compte des points suivants lors de l’annulation de demandes de création de rapports :

* Vous pouvez annuler des requêtes spécifiques, annuler toutes les requêtes d’un utilisateur spécifique ou annuler toutes les requêtes liées à un projet spécifique.

* Lorsque vous annulez des requêtes, vous pouvez également choisir de limiter les requêtes suivantes pour une période donnée.

  Lorsque vous limitez une requête suivante, l’action est enregistrée dans la variable [Journal d’audit](/help/privacy/audit-log.md) avec le nom de l’action EMBARGO.

* Vous ne pouvez pas annuler une requête si la variable [!UICONTROL **Utilisateur**] la colonne d’une requête s’affiche comme [!UICONTROL **Non reconnu**]. Dans ce cas, cela signifie que l’utilisateur se trouve dans une société de connexion dans laquelle vous ne disposez pas des autorisations d’administration.

Pour plus d’informations sur la gestion des activités de création de rapports, y compris les principaux avantages et les exigences en matière d’autorisation, voir [Présentation d’Activity Manager dans les rapports](/help/reporting-activity-manager/reporting-activity-overview.md).

## Annulation de requêtes spécifiques

Vous pouvez annuler des requêtes individuelles qui consomment une grande capacité de création de rapports. Lorsque vous annulez une requête, vous pouvez choisir de la restreindre davantage pour une période donnée.

1. En Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire des activités de création de rapports]**.

1. Sélectionnez la connexion pour laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles sur cette page, voir [Afficher l’activité de création de rapports dans le Gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez la variable [!UICONTROL **Demandes**] , puis sélectionnez une ou plusieurs requêtes.

   <!-- add screenshot -->

1. Sélectionner [!UICONTROL **Annulation des requêtes**].

   La variable [!UICONTROL **Annuler _x_ requêtes de rapport**] s’affiche.

1. Le champ Message d’annulation affiche le message qui s’affiche aux utilisateurs lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour limiter les demandes futures pour une période donnée :

   1. Activez l’option pour [!UICONTROL **Limitation des requêtes suivantes**].

      ![Requête Annuler 1 affichant Restreindre les requêtes sélectionnées et le message Annulation .](assets/restrict-subsequent-requests.png)

   1. Choisissez l’une des options suivantes :

      | Option | Fonction |
      |---------|----------|
      | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les utilisateurs et utilisatrices associés aux demandes sélectionnées seront temporairement limités dans l’exécution des demandes de rapport pour les projets associés. |
      | [!UICONTROL **Utilisateur**] | Les utilisateurs et utilisatrices associés aux demandes sélectionnées ne pourront temporairement pas effectuer des demandes de rapports. |
      | [!UICONTROL **Projet**] | Les projets associés aux demandes sélectionnées seront temporairement exclus de toutes les demandes de rapports. |
      | [!UICONTROL **Réservé à**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!-- double-check this --><p>Une fois définie, vous ne pouvez pas supprimer une restriction plus tôt.</p> |

      {style="table-layout:auto"}

1. Sélectionner [!UICONTROL **Continuer avec annulation**].

   Une notification s’affiche dans Analysis Workspace pour informer les utilisateurs que la demande a été annulée. Pour plus d’informations sur la façon dont cela apparaît dans Analysis Workspace, voir [Expérience lorsque les utilisateurs accèdent à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Annulation des requêtes par l’utilisateur

Vous pouvez annuler toutes les requêtes associées à un ou plusieurs utilisateurs. Lors de l’annulation de requêtes associées à un utilisateur, vous pouvez choisir de restreindre davantage les requêtes de cet utilisateur pendant une période donnée.

1. En Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire des activités de création de rapports]**.

1. Sélectionnez la connexion pour laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles sur cette page, voir [Afficher l’activité de création de rapports dans le Gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez la variable [!UICONTROL **Utilisateurs**] , puis sélectionnez un ou plusieurs utilisateurs.

   <!-- add screenshot -->

1. Sélectionner [!UICONTROL **Annulation des requêtes**].

   La variable [!UICONTROL **Annuler _x_ requêtes de rapport de x utilisateurs**] s’affiche.

1. Le champ Message d’annulation affiche le message qui s’affiche aux utilisateurs lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour limiter les demandes futures pour une période donnée :

   1. Activez l’option pour [!UICONTROL **Limitation des requêtes suivantes**]

      ![Requête Annuler 1 affichant l’option Restreindre les requêtes suivantes sélectionnée par l’utilisateur.](assets/restrict-subsequent-requests-user.png)

   1. Choisissez l’une des options suivantes :

      | Option | Fonction |
      |---------|----------|
      | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les utilisateurs et utilisatrices sélectionnés ne pourront temporairement pas faire de demandes de rapport pour les projets associés. <p>Il s’agit de l’option la moins restrictive.</p> |
      | [!UICONTROL **Utilisateur**] | Les utilisateurs et utilisatrices sélectionnés ne pourront temporairement pas faire de demandes de rapport. |
      | [!UICONTROL **Projet**] | Les projets associés aux utilisateurs et utilisatrices sélectionnés ne pourront pas faire l’objet de demandes de rapports d’un utilisateur ou d’une utilisatrice. |
      | [!UICONTROL **Réservé à**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!--double-check this--> <p>Une fois définie, vous ne pouvez pas supprimer une restriction plus tôt.</p> |

      {style="table-layout:auto"}

1. Sélectionner [!UICONTROL **Continuer avec annulation**].

   Une notification s’affiche dans Analysis Workspace pour informer les utilisateurs que la demande a été annulée. Pour plus d’informations sur la façon dont cela apparaît dans Analysis Workspace, voir [Expérience lorsque les utilisateurs accèdent à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Annulation des demandes par projet

Vous pouvez annuler toutes les requêtes associées à un ou plusieurs projets. Lors de l’annulation de requêtes associées à un projet, vous pouvez choisir de restreindre davantage les requêtes associées à ce projet pour une période donnée.

1. En Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire des activités de création de rapports]**.

1. Sélectionnez la connexion pour laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles sur cette page, voir [Afficher l’activité de création de rapports dans le Gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez la variable [!UICONTROL **Projets**] , puis sélectionnez un ou plusieurs projets.

   <!-- add screenshot -->

1. Sélectionner [!UICONTROL **Annulation des requêtes**].

   La variable [!UICONTROL **Annuler _x_ requêtes de rapport provenant de x projets**] s’affiche.

1. Le champ Message d’annulation affiche le message qui s’affiche aux utilisateurs lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour limiter les demandes futures pour une période donnée :

   1. Activez l’option pour [!UICONTROL **Limitation des requêtes suivantes**].

      ![Requête Annuler 1 affichant Restreindre les requêtes suivantes par projet](assets/restrict-subsequent-requests-project.png)

   1. Choisissez l’une des options suivantes :

      | Option | Fonction |
      |---------|----------|
      | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les projets sélectionnés seront temporairement exclus de toute demande de rapport de la part des utilisateurs et utilisatrices associés.<p>Il s’agit de l’option la moins restrictive.</p> |
      | [!UICONTROL **Utilisateur**] | Les utilisateurs et utilisatrices associés aux projets sélectionnés ne pourront temporairement pas effectuer des demandes de rapports. |
      | [!UICONTROL **Projet**] | Les projets sélectionnés seront temporairement limités aux demandes de création de rapports effectuées par n’importe quel utilisateur. |
      | [!UICONTROL **Réservé à**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!--double-check this--> <p>Une fois définie, vous ne pouvez pas supprimer une restriction plus tôt.</p> |

      {style="table-layout:auto"}

1. Sélectionner [!UICONTROL **Continuer avec annulation**].

   Une notification s’affiche dans Analysis Workspace pour informer les utilisateurs que la demande a été annulée. Pour plus d’informations sur la façon dont cela apparaît dans Analysis Workspace, voir [Expérience lorsque les utilisateurs accèdent à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Annulation des demandes par demande

Vous pouvez annuler toutes les requêtes associées à une ou plusieurs applications. Lorsque vous annulez des requêtes associées à une application, vous pouvez choisir de restreindre davantage les requêtes associées à cette application pour une période donnée.

Les applications comprennent les éléments suivants :

* Interface utilisateur d’Analysis Workspace
* Projets planifiés d’espace de travail
* Report Builder
* Interface utilisateur de Builder : Segment, Mesures calculées, Annotations, Audiences, etc.
* Appels API de l’API 2.0
* Alertes intelligentes
* Export table complète
* Partager avec n’importe qui lien
* Analyse guidée
* Toute autre application qui interroge le moteur de reporting Analytics

Pour annuler des demandes par application :

1. En Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire des activités de création de rapports]**.

1. Sélectionnez la connexion pour laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles sur cette page, voir [Afficher l’activité de création de rapports dans le Gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez la variable [!UICONTROL **Applications**] , puis sélectionnez une ou plusieurs applications.

   <!-- add screenshot -->

1. Sélectionner [!UICONTROL **Annulation des requêtes**].

   La variable [!UICONTROL **Annuler _x_ requêtes de rapport provenant de x projets**] s’affiche.

1. Le champ Message d’annulation affiche le message qui s’affiche aux utilisateurs lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour limiter les demandes futures pour une période donnée :

   1. Activez l’option pour [!UICONTROL **Limitation des requêtes suivantes**]

      ![Annuler 1 requête affichant l’option Restreindre les requêtes suivantes par application sélectionnée.](assets/restrict-subsequent-requests-application.png)

   1. Choisissez l’une des options suivantes :

      | Option | Fonction |
      |---------|----------|
      | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les applications sélectionnées seront temporairement limitées aux demandes de création de rapports effectuées par les utilisateurs et les projets associés.<p>Il s’agit de l’option la moins restrictive.</p> |
      | [!UICONTROL **Utilisateur**] | Les utilisateurs associés aux applications sélectionnées ne pourront pas effectuer de requêtes de création de rapports. |
      | [!UICONTROL **Projet**] | Les projets associés aux applications sélectionnées seront limités aux demandes de création de rapports effectuées par n’importe quel utilisateur. |
      | [!UICONTROL **Réservé à**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!--double-check this--> <p>Une fois définie, vous ne pouvez pas supprimer une restriction plus tôt.</p> |

      {style="table-layout:auto"}

1. Sélectionner [!UICONTROL **Continuer avec annulation**].

   Une notification s’affiche dans l’application (dans Analysis Workspace, par exemple) pour informer les utilisateurs que la demande a été annulée. Pour plus d’informations sur la façon dont cela apparaît dans Analysis Workspace, voir [Expérience lorsque les utilisateurs accèdent à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Expérience lorsque les utilisateurs accèdent à un rapport annulé

Dans Analysis Workspace, les utilisateurs voient les messages suivants lorsqu’ils tentent d’accéder à un rapport ou à une visualisation qui est affecté par une annulation :

### Message sur le projet

Lorsque les utilisateurs tentent d’accéder à un projet qui est affecté par une annulation, un message les informe que le rapport est temporairement limité :

![Message d’annulation du projet](assets/workspace-canceled-report.png)

### Message sur la visualisation

Lorsque les utilisateurs tentent d’accéder à une visualisation affectée par une annulation, ils reçoivent un message les informant que le traitement des données pour le rapport est temporairement limité :

![Message d&#39;annulation de la visualisation](assets/workspace-cancelled-visualization.png)
