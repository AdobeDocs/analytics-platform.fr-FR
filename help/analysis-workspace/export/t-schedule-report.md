---
description: Découvrez comment envoyer un projet Analysis Workspace directement ou selon un planning de diffusion par e-mail.
keywords: Analysis Workspace
title: Envoyer Et Planifier Des Projets
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: c91ee21a3d4e20e3bdaeb75f2011ede6eee6cba0
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 50%

---

# Envoyer et planifier des projets

Vous pouvez envoyer des projets Customer Journey Analytics sous forme de fichiers à des utilisateurs sélectionnés par e-mail. Vous pouvez envoyer des fichiers ad hoc ou configurer les projets à envoyer selon un planning. Les projets peuvent être envoyés au format CSV ou PDF.

Toutes les balises appliquées au projet sont automatiquement appliquées à l’export.

D’autres méthodes d’export des données Customer Journey Analytics sont également disponibles, comme décrit dans la section [Vue d’ensemble de l’export](/help/analysis-workspace/export/export-project-overview.md).

![Envoyer un fichier](assets/send-file.png)

## Envoyer le fichier

Pour envoyer un fichier aux destinataires par e-mail :

1. Sélectionnez **[!UICONTROL Partager] > [!UICONTROL Envoyer le fichier]**.
1. Spécifiez le type de fichier :
   * [!UICONTROL **CSV**] : choisissez cette option si vous souhaitez des données en texte brut.
   * [!UICONTROL **PDF**] : choisissez cette option si vous souhaitez que le fichier téléchargé contienne tous les tableaux et visualisations affichés (visibles) dans le projet.
1. (Facultatif) Utilisez **[!UICONTROL Description]** pour ajouter une description à inclure dans l’e-mail.
1. Ajoutez des destinataires ou des groupes. Vous pouvez également saisir des adresses e-mail.
1. (Uniquement pour les clients Healthcare Shield) Indiquez un mot de passe pour [protéger par mot de passe un rapport planifié](#password-protect-a-new-scheduled-project).
1. (Facultatif) Sélectionnez **[!UICONTROL Afficher les options de planification]** pour [planifier une exportation de fichier](#schedule-file-export).
1. Cliquez sur **[!UICONTROL Envoyer maintenant]**. Sélectionnez **[!UICONTROL Annuler]** pour annuler.


## Planifier l’export de fichier {#schedule}

Pour envoyer un fichier selon un planning aux destinataires par e-mail

1. Sélectionnez **[!UICONTROL Partager] > [!UICONTROL Planifier l’exportation de fichier]**.
1. Spécifiez le type de fichier :
   * [!UICONTROL **CSV**] : choisissez cette option si vous souhaitez des données en texte brut.
   * [!UICONTROL **PDF**] : choisissez cette option si vous souhaitez que le fichier téléchargé contienne tous les tableaux et visualisations affichés (visibles) dans le projet.
1. (Facultatif) Utilisez **[!UICONTROL Description]** pour ajouter une description à inclure dans l’e-mail.
1. Ajoutez des destinataires ou des groupes. Vous pouvez également saisir des adresses e-mail.
1. (Uniquement pour les clients Healthcare Shield) Indiquez un mot de passe pour [protéger par mot de passe un rapport planifié](#password-protect-a-new-scheduled-project).
1. Assurez-vous que **[!UICONTROL Afficher les options de planification]** est sélectionné.
1. Sélectionnez une **[!UICONTROL Fréquence]**. Vous pouvez choisir entre :

   | Fréquence | Options |
   |---|---|
   | **[!UICONTROL Envoyer par heure]** | Saisissez une valeur pour **[!UICONTROL Envoyer toutes les heures]**. |
   | **[!UICONTROL Envoyer quotidiennement]** | Sélectionnez une **[!UICONTROL Fréquence quotidienne]** : **[!UICONTROL Envoyer tous les jours]**, **[!UICONTROL Envoyer tous les jours de la semaine]** ou **[!UICONTROL Fréquence personnalisée]**.<br/>Si vous sélectionnez **[!UICONTROL Fréquence personnalisée]**, saisissez une valeur pour **[!UICONTROL Envoyer tous les jours]**. |
   | **[!UICONTROL Envoyer une fois par semaine]** | Saisissez une valeur pour **[!UICONTROL Envoyer toutes les semaines]**. Sélectionnez ensuite un **[!UICONTROL Jour de la semaine]**. |
   | **[!UICONTROL Envoyer mensuellement par jour de la semaine]** | Sélectionnez un **[!UICONTROL Jour de la semaine]** et un **[!UICONTROL Semaine du mois]**. |
   | **[!UICONTROL Envoyer mensuellement par jour du mois]** | Sélectionnez une valeur dans **[!UICONTROL Envoyer ce jour du mois]**. |
   | **[!UICONTROL Envoyer annuellement par jour du mois]** | Sélectionnez un **[!UICONTROL Jour de la semaine]**, une **[!UICONTROL Semaine du mois]** et une **[!UICONTROL Mensuel de l’année]**. |
   | **[!UICONTROL Envoyer annuellement par date spécifique]** | Sélectionnez un **[!UICONTROL Mois de l’année]** et sélectionnez une valeur dans **[!UICONTROL Envoyer ce jour du mois]**. |

1. Saisissez une date de début dans **[!UICONTROL À partir du]**. Vous pouvez également sélectionner ![Calendrier](/help/assets/icons/Calendar.svg) pour choisir une date de début dans le calendrier.

1. Saisissez une date de fin dans **[!UICONTROL Se terminant le]**. Vous pouvez également sélectionner ![Calendrier](/help/assets/icons/Calendar.svg) pour choisir une date de fin dans le calendrier.
1. Sélectionnez **[!UICONTROL Envoyer selon le calendrier]**. Sélectionnez **[!UICONTROL Annuler]** pour annuler.


## Protéger un projet planifié par mot de passe {#password}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_sendfile_password"
>title="Chiffrement de mot de passe"
>abstract="Le mot de passe fourni sera utilisé pour chiffrer le fichier pour le projet planifié. Les exigences de sécurité de votre entreprise nécessitent un chiffrement par mot de passe."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>L’option de protection par mot de passe d’un projet planifié s’affiche uniquement pour les clientes et clients CJA qui ont acheté le module complémentaire [Healthcare Shield](https://business.adobe.com/solutions/industries/healthcare.html).

Adobe utilise le mot de passe pour chiffrer les projets planifiés, qu’ils soient envoyés au format .pdf ou .csv.

Une fois que votre entreprise a acheté et activé le SKU Healthcare Shield, l’invitation à créer un mot de passe pour un projet planifié s’affiche dans les cas suivants :

* Lorsqu’une personne crée un projet planifié.

* Lorsqu’un projet planifié existant est sur le point d’être envoyé. Le projet actuellement planifié sera désactivé jusqu’à la mise en place de la protection par mot de passe. La personne propriétaire du projet planifié reçoit un e-mail l’informant de cette exigence.

### Exigences relatives au mot de passe

Les exigences relatives au mot de passe sont conformes à la norme Adobe, qui requiert un minimum de 8 caractères avec au moins un nombre et un caractère spécial.

### Protéger un nouveau projet planifié par mot de passe

1. Une fois le projet enregistré, accédez à **[!UICONTROL Partager]** > **[!UICONTROL Envoyer le fichier maintenant]** ou **[!UICONTROL Partager]** > **[!UICONTROL Envoyer le fichier selon le calendrier]**.
1. Suivez les instructions ci-dessus, sous [Envoyer le fichier maintenant](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/t-schedule-report.html?lang=fr#now) ou [Envoyer le fichier selon le calendrier](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/t-schedule-report.html?lang=fr#schedule).

### Protéger un projet planifié existant par mot de passe

Lorsque vous protégez par mot de passe un projet planifié existant, le propriétaire du projet reçoit un e-mail similaire à celui-ci :

![Notification par e-mail de Customer Journey Analytics indiquant que le chiffrement du mot de passe est requis pour votre organisation.](assets/email-password.png)

1. Connectez-vous à Customer Journey Analytics.
1. Sélectionnez **[!UICONTROL Afficher le projet planifié]**.
1. Dans la boîte de dialogue **[!UICONTROL Modifier le projet planifié]**, saisissez un mot de passe et saisissez-le à nouveau.
1. Partagez ce mot de passe avec les destinataires du projet planifié. Ne distribuez pas le mot de passe aux personnes qui ne sont pas destinataires du projet planifié.



## Gestionnaire de projets planifiés {#manager}

Les projets Analysis Workspace planifiés peuvent être gérés à partir de l’interface principale, en utilisant **[!UICONTROL Composants]** > **[!UICONTROL Projets planifiés]**. Pour plus d’informations, consultez [Projets planifiés](/help/components/scheduled-projects-manager.md).
