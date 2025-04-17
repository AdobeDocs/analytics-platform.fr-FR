---
title: Annuler les demandes de rapport dans le gestionnaire des activités de rapport
description: Découvrez comment utiliser le gestionnaire des activités de rapport pour diagnostiquer et corriger les problèmes de capacité pendant les heures de pointe de la création de rapports.
solution: Customer Journey Analytics
feature: Basics
exl-id: 87da2447-f114-432a-9f63-e660c2541d0f
role: Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: ht
source-wordcount: '1497'
ht-degree: 100%

---

# Annuler les demandes de rapport dans le gestionnaire des activités de rapport

Le [!UICONTROL gestionnaire des activités de rapport] permet aux administrateurs et administratrices de diagnostiquer et d’annuler rapidement les demandes de création de rapports afin de résoudre les problèmes de capacité de création de rapports pendant les heures de pointe de la création de rapports.

Tenez compte des points suivants lors de l’annulation de demandes de création de rapports :

* Vous pouvez annuler des demandes spécifiques, annuler toutes les demandes d’une personne spécifique ou annuler toutes les demandes liées à un projet spécifique.

* Lorsque vous annulez des demandes, vous pouvez également choisir de restreindre les demandes suivantes pour une période donnée.

  Lorsque vous restreignez une demande ultérieure, l’action est enregistrée dans le [Journal d’audit](/help/privacy/audit-log.md) avec le nom d’action EMBARGO.

* Vous ne pouvez pas annuler une demande si la colonne [!UICONTROL **Utilisateur ou utilisatrice**] d’une demande indique [!UICONTROL **Non reconnu**]. Dans ce cas, cela signifie que la personne se trouve dans une société de connexion pour laquelle vous ne disposez pas des autorisations administratives.

Pour plus d’informations sur le gestionnaire des activités de rapport, y compris les principaux avantages et les exigences d’autorisation, consultez [Vue d’ensemble du gestionnaire des activités de rapport](/help/reporting-activity-manager/reporting-activity-overview.md).

## Annuler des demandes spécifiques

Vous pouvez annuler des demandes individuelles qui consomment une grande quantité de capacité de création de rapports. Lors de l’annulation d’une demande, vous pouvez choisir de la restreindre davantage pour une période donnée.

1. Dans Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire des activités de rapport]**.

1. Sélectionnez la connexion sur laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles sur cette page, consultez [Afficher l’activité de rapport dans le gestionnaire des activités de rapport](/help/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez l’onglet [!UICONTROL **Demandes**], puis sélectionnez une ou plusieurs demandes.

   <!-- add screenshot -->

1. Sélectionne [!UICONTROL **Annuler les demandes**].

   La boîte de dialogue [!UICONTROL **Annuler _x_ demandes de rapport**] s’affiche.

1. Le champ Message d’annulation indique le message qui s’affiche pour les personnes lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour restreindre les demandes futures pour une période donnée, procédez comme suit :

   1. Activez l’option pour [!UICONTROL **Restreindre les demandes ultérieures**].

      ![Annulation d’1 demande affichant l’option Restreindre les demandes ultérieures sélectionnée et le message d’annulation.](assets/restrict-subsequent-requests.png)

   1. Choisissez l’une des options suivantes :

      | Option | Fonction |
      |---------|----------|
      | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les utilisateurs et utilisatrices associés aux demandes sélectionnées seront temporairement limités dans l’exécution des demandes de rapport pour les projets associés. |
      | [!UICONTROL **Utilisateur ou utilisatrice**] | Les utilisateurs et utilisatrices associés aux demandes sélectionnées ne pourront temporairement pas effectuer des demandes de rapports. |
      | [!UICONTROL **Projet**] | Les projets associés aux demandes sélectionnées seront temporairement exclus de toutes les demandes de rapports. |
      | [!UICONTROL **Réservé à**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!-- double-check this --><p>Vous ne pouvez pas supprimer une restriction plus tôt une fois qu’elle a été définie.</p> |

      {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Continuer avec l’annulation**].

   Une notification s’affiche dans Analysis Workspace pour informer les utilisateurs et utilisatrices que la demande a été annulée. Pour plus d’informations sur la façon dont cela s’affiche dans Analysis Workspace, consultez [Expérience d’accès des utilisateurs et utilisatrices à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Annuler les demandes par personne

Vous pouvez annuler toutes les demandes associées à une ou plusieurs personnes. Lors de l’annulation de demandes associées à une personne, vous pouvez choisir de restreindre davantage les demandes de cette personne pendant une période donnée.

1. Dans Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire des activités de rapport]**.

1. Sélectionnez la connexion sur laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles sur cette page, consultez [Afficher l’activité de rapport dans le gestionnaire des activités de rapport](/help/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez l’onglet [!UICONTROL **Utilisateurs et utilisatrices**], puis sélectionnez une ou plusieurs personnes.

   <!-- add screenshot -->

1. Sélectionnez [!UICONTROL **Annuler les demandes**].

   La boîte de dialogue [!UICONTROL **Annuler _x_ demandes de rapport de x utilisateurs et utilisatrices**] s’affiche.

1. Le champ Message d’annulation indique le message qui s’affiche pour les personnes lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour restreindre les demandes futures pour une période donnée, procédez comme suit :

   1. Activer l’option pour [!UICONTROL **Restreindre les demandes suivantes**]

      ![Annulation d’1 demande affichant l’option Restreindre les demandes suivantes par la personne sélectionnée.](assets/restrict-subsequent-requests-user.png)

   1. Choisissez l’une des options suivantes :

      | Option | Fonction |
      |---------|----------|
      | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les utilisateurs et utilisatrices sélectionnés ne pourront temporairement pas faire de demandes de rapport pour les projets associés. <p>Il s’agit de l’option la moins contraignante.</p> |
      | [!UICONTROL **Utilisateur ou utilisatrice**] | Les utilisateurs et utilisatrices sélectionnés ne pourront temporairement pas faire de demandes de rapport. |
      | [!UICONTROL **Projet**] | Les projets associés aux utilisateurs et utilisatrices sélectionnés ne pourront pas faire l’objet de demandes de rapports d’un utilisateur ou d’une utilisatrice. |
      | [!UICONTROL **Réservé à**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!--double-check this--> <p>Vous ne pouvez pas supprimer une restriction plus tôt une fois qu’elle a été définie.</p> |

      {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Continuer avec l’annulation**].

   Une notification s’affiche dans Analysis Workspace pour informer les utilisateurs et utilisatrices que la demande a été annulée. Pour plus d’informations sur la façon dont cela s’affiche dans Analysis Workspace, consultez [Expérience d’accès des utilisateurs et utilisatrices à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Annuler les demandes par projet

Vous pouvez annuler toutes les demandes associées à un ou plusieurs projets. Lors de l’annulation de demandes associées à un projet, vous pouvez choisir de restreindre davantage les demandes associées à ce projet pour une période donnée.

1. Dans Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire des activités de rapport]**.

1. Sélectionnez la connexion sur laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles sur cette page, consultez [Afficher l’activité de rapport dans le gestionnaire des activités de rapport](/help/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez l’onglet [!UICONTROL **Projets**], puis sélectionnez un ou plusieurs projets.

   <!-- add screenshot -->

1. Sélectionnez [!UICONTROL **Annuler les demandes**].

   La boîte de dialogue [!UICONTROL **Annuler _x_ demandes de rapport de x projets**] s’affiche.

1. Le champ Message d’annulation indique le message qui s’affiche pour les personnes lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour restreindre les demandes futures pour une période donnée, procédez comme suit :

   1. Activez l’option pour [!UICONTROL **Restreindre les demandes ultérieures**].

      ![Annulation d’1 demande affichant l’option Restreindre les demandes ultérieures par projet](assets/restrict-subsequent-requests-project.png)

   1. Choisissez l’une des options suivantes :

      | Option | Fonction |
      |---------|----------|
      | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les projets sélectionnés seront temporairement exclus de toute demande de rapport de la part des utilisateurs et utilisatrices associés.<p>Il s’agit de l’option la moins contraignante.</p> |
      | [!UICONTROL **Utilisateur ou utilisatrice**] | Les utilisateurs et utilisatrices associés aux projets sélectionnés ne pourront temporairement pas effectuer des demandes de rapports. |
      | [!UICONTROL **Projet**] | Les projets sélectionnés seront temporairement exclus de toute demande de rapport émanant d’un utilisateur ou d’une utilisatrice. |
      | [!UICONTROL **Réservé à**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!--double-check this--> <p>Vous ne pouvez pas supprimer une restriction plus tôt une fois qu’elle a été définie.</p> |

      {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Continuer avec l’annulation**].

   Une notification s’affiche dans Analysis Workspace pour informer les utilisateurs et utilisatrices que la demande a été annulée. Pour plus d’informations sur la façon dont cela s’affiche dans Analysis Workspace, consultez [Expérience d’accès des utilisateurs et utilisatrices à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Annuler les demandes par application

Vous pouvez annuler toutes les demandes associées à une ou plusieurs applications. Lors de l’annulation de demandes associées à une application, vous pouvez choisir de restreindre davantage les demandes associées à cette application pendant une période donnée.

Les applications comprennent les suivantes :

* Interface utilisateur d’Analysis Workspace
* Projets planifiés d’espace de travail
* Report Builder
* Interface utilisateur de Builder : Segment, Mesures calculées, Annotations, Audiences, etc.
* Appels API à partir de la version d’API 2.0
* Alertes
* Export du tableau complet
* Liens de partage avec tout le monde
* Analyse guidée
* Toute autre application interrogeant le moteur de création de rapports Analytics

Pour annuler des demandes par application, procédez comme suit :

1. Dans Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire des activités de rapport]**.

1. Sélectionnez la connexion sur laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles sur cette page, consultez [Afficher l’activité de rapport dans le gestionnaire des activités de rapport](/help/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez l’onglet [!UICONTROL **Applications**], puis sélectionnez une ou plusieurs applications.

   <!-- add screenshot -->

1. Sélectionne [!UICONTROL **Annuler les demandes**].

   La boîte de dialogue [!UICONTROL **Annuler _x_ demandes de rapport de x projets**] s’affiche.

1. Le champ Message d’annulation indique le message qui s’affiche pour les personnes lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour restreindre les demandes futures pour une période donnée, procédez comme suit :

   1. Activer l’option pour [!UICONTROL **Restreindre les demandes ultérieures**]

      ![Annulation d’1 demande affichant l’option Restreindre les demandes ultérieures par application sélectionnée.](assets/restrict-subsequent-requests-application.png)

   1. Choisissez l’une des options suivantes :

      | Option | Fonction |
      |---------|----------|
      | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les applications sélectionnées seront temporairement exclues de toute demande de rapport de la part des utilisateurs, utilisatrices et projets associés.<p>Il s’agit de l’option la moins contraignante.</p> |
      | [!UICONTROL **Utilisateur ou utilisatrice**] | Les utilisateurs et utilisatrices associés aux projets sélectionnés ne pourront temporairement pas effectuer de demandes de rapports. |
      | [!UICONTROL **Projet**] | Les projets associés aux utilisateurs et utilisatrices sélectionnés ne pourront pas faire l’objet de demandes de rapports d’un utilisateur ou d’une utilisatrice. |
      | [!UICONTROL **Réservé à**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!--double-check this--> <p>Vous ne pouvez pas supprimer une restriction plus tôt une fois qu’elle a été définie.</p> |

      {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Continuer avec l’annulation**].

   Une notification s’affiche dans l’application (dans Analysis Workspace, par exemple) pour informer les utilisateurs et utilisatrices que la demande a été annulée. Pour plus d’informations sur la façon dont cela s’affiche dans Analysis Workspace, consultez [Expérience d’accès des utilisateurs et utilisatrices à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Expérience d’accès des utilisateurs et utilisatrices à un rapport annulé

Dans Analysis Workspace, les utilisateurs et utilisatrices voient les messages suivants lorsqu’ils tentent d’accéder à un rapport ou à une visualisation faisant l’objet d’une annulation :

### Message sur le projet

Lorsque les utilisateurs et utilisatrices tentent d’accéder à un projet affecté par une annulation, un message les informe que le rapport est temporairement restreint :

![Message d’annulation du projet](assets/workspace-canceled-report.png)

### Message sur la visualisation

Lorsque les utilisateurs et utilisatrices tentent d’accéder à une visualisation affectée par une annulation, un message s’affiche pour les informer que le traitement des données pour le rapport est temporairement restreint :

![Message d’annulation de la visualisation](assets/workspace-cancelled-visualization.png)
