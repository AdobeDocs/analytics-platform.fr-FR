---
description: Envoyez un projet Analysis Workspace par e-mail ou planifiez une livraison.
keywords: Analysis Workspace
title: Envoyer des rapports à d’autres personnes par e-mail
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: ht
source-wordcount: '1034'
ht-degree: 100%

---

# Envoyer des fichiers à d’autres personnes

Vous pouvez envoyer des rapports Customer Journey Analytics sous forme de fichiers à des personnes sélectionnées par e-mail. Vous pouvez envoyer des fichiers ad hoc ou configurer les fichiers à envoyer selon un planning. Les fichiers peuvent être envoyés au format CSV ou PDF.

Toutes les balises appliquées au projet sont automatiquement appliquées à l’export.

D’autres méthodes d’export des données Customer Journey Analytics sont également disponibles, comme décrit dans la section [Vue d’ensemble de l’export](/help/analysis-workspace/export/export-project-overview.md).

## Envoyer le fichier maintenant {#now}

Pour envoyer un fichier immédiatement aux destinataires par courrier électronique, procédez comme suit :

1. Cliquez sur **[!UICONTROL Partager] > [!UICONTROL Exporter le fichier]**.
1. Spécifiez le type de fichier :
   * [!UICONTROL **CSV**] : choisissez cette option si vous souhaitez des données en texte brut.
   * [!UICONTROL **PDF**] : choisissez cette option si vous souhaitez que le fichier téléchargé contienne tous les tableaux et visualisations affichés (visibles) dans le projet.
1. (Facultatif) Ajoutez une description qui sera incluse dans l’e-mail pour décrire le fichier reçu.
1. Ajoutez des destinataires ou des groupes. Vous pouvez également saisir les adresses électroniques.
1. (Uniquement pour les clients de Healthcare Shield) Indiquez un mot de passe. Voir la section Protection par mot de passe d’un rapport planifié.
1. (Facultatif) Cliquez sur **[!UICONTROL Afficher les options de planification]** pour planifier une livraison.
1. Cliquez sur **[!UICONTROL Envoyer maintenant]**.

![Fenêtre Envoyer le fichier et bouton Envoyer maintenant.](assets/send-file-no-scheduling-options.JPG)

## Envoyer le fichier selon le calendrier {#schedule}

Pour envoyer un fichier selon un calendrier récurrent aux destinataires par e-mail, procédez comme suit :

1. Cliquez sur **[!UICONTROL Partager] > [!UICONTROL Planifier l’export de fichier]**.
1. Spécifiez le type de fichier (CSV ou PDF).
1. (Facultatif) Ajoutez une description qui sera incluse dans le courrier électronique pour décrire le fichier reçu.
1. Ajoutez des destinataires ou des groupes. Vous pouvez également saisir les adresses électroniques.
1. (Uniquement pour les clients de Healthcare Shield) Indiquez un mot de passe. Voir la section Protection par mot de passe d’un rapport planifié.
1. Précisez la période pendant laquelle la livraison doit être effectuée en modifiant les entrées Début le et Fin le. La date de fin doit se situer dans un délai d’un an à compter du jour de la création ou de la modification de la planification.
1. Spécifiez la fréquence de livraison. Chaque fréquence offre différentes personnalisations.
1. Cliquez sur **[!UICONTROL Envoyer selon le calendrier]**.

![La fenêtre Envoyer le fichier et les options de planification s’affichent pour indiquer les dates de début et de fin, ainsi que les paramètres de fréquence quotidienne.](assets/send-file.JPG)

## Gestionnaire de projets planifiés {#manager}

Les projets Analysis Workspace planifiés peuvent être gérés sous **[!UICONTROL Analytics] > [!UICONTROL Composants] > [!UICONTROL Projets planifiés]**.

Dans le Gestionnaire de projets planifiés, vous pouvez modifier et supprimer les calendriers de projets récurrents. Utilisez la barre de recherche ou les options de filtre dans le panneau de gauche pour rechercher un planning. Vous pouvez filtrer par balise, calendriers approuvés, propriétaires, etc.

| Champ | Description |
| --- | --- |
| [!UICONTROL Favoris] | Sélectionnez l’icône en forme d’étoile pour marquer ce planning comme favori. |
| [!UICONTROL Identifiant de planning] | Cet identifiant est principalement utilisé à des fins de débogage. |
| [!UICONTROL Titre et description] | Titre et description de ce projet. |
| [!UICONTROL Propriétaire] | Personne qui a créé le projet et qui en est propriétaire. |
| [!UICONTROL Balises] | (facultatif) Le balisage est un moyen efficace d’organiser les projets. Tous les utilisateurs peuvent créer des balises et en appliquer une ou plusieurs à un projet. Néanmoins, vous ne pouvez afficher les balises que pour les projets que vous possédez ou qui ont été partagés avec vous. |
| [!UICONTROL Distribué à] | Le ou les personnes destinataires de ce projet planifié. |
| [!UICONTROL Date d’expiration] | Vous pouvez définir des dates d’expiration maximales allant jusqu’à un an pour les projets planifiés, quelle que soit la fréquence de planification. |
| [!UICONTROL Fréquence] | Fréquence à laquelle vous souhaitez envoyer ce projet planifié aux personnes destinataires. |
| [!UICONTROL Heure d’exécution] | Heure à laquelle ce projet planifié est envoyé. |
| [!UICONTROL Nombre de requêtes] | Nombre de requêtes concernant ce projet. |

Actions courantes du Gestionnaire de projets planifiés :

| Action | Description |
|---|---|
| **[!UICONTROL Modifier le planning]** | Cliquez sur le titre du planning pour mettre à jour les paramètres de livraison. |
| **[!UICONTROL Supprimer le planning]** | Sélectionnez le projet planifié dans la liste, puis cliquez sur Supprimer dans le menu. Cela supprime le planning sélectionné pour le projet ; le projet lui-même n’est pas supprimé. |
| **[!UICONTROL Ajout de balises]** | Sélectionnez le projet planifié dans la liste, puis « Balise » ou « Approuver » pour organiser vos plannings et faciliter les recherches. |
| **[!UICONTROL Afficher les plannings échoués]** | Accédez au panneau de gauche > Autres filtres > Échec pour afficher les plannings qui ont échoué. |
| **[!UICONTROL Afficher les plannings expirés]** | Accédez au panneau de gauche > Autres filtres > Expiré pour afficher les plannings qui ont expiré. Cliquez sur le titre du planning pour configurer une nouvelle diffusion. |
| **[!UICONTROL Afficher l’ID de planning]** | Accédez aux options relatives aux colonnes dans le coin supérieur droit et ajoutez la colonne ID de planning dans le tableau. L’ID planifié est souvent utile pour le débogage. |

Le Gestionnaire de planification des projets affiche les éléments créés par un utilisateur spécifique. Si le compte d’utilisateur ou d’utilisatrice est désactivé dans l’application, toutes les diffusions planifiées sont interrompues.
Pour plus d’informations, consultez [Projets planifiés](/help/components/scheduled-projects-manager.md).

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

![Fenêtre Modifier le projet planifié et notification de chiffrement de mot de passe indiquant que votre organisation nécessite un chiffrement de mot de passe.](assets/password.png)

### Exigences relatives au mot de passe

Les exigences relatives au mot de passe sont conformes à la norme Adobe, qui requiert un minimum de 8 caractères avec au moins un nombre et un caractère spécial.

### Protéger un nouveau projet planifié par mot de passe

1. Une fois le projet enregistré, accédez à **[!UICONTROL Partager]** > **[!UICONTROL Envoyer le fichier maintenant]** ou **[!UICONTROL Partager]** > **[!UICONTROL Envoyer le fichier selon le calendrier]**.
1. Suivez les instructions ci-dessus, sous [Envoyer le fichier maintenant](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=fr#now) ou [Envoyer le fichier selon le calendrier](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=fr#schedule).

### Protéger un projet planifié existant par mot de passe

Avant la planification d’un projet, la personne propriétaire du projet reçoit un e-mail semblable à celui-ci :

![Notification par e-mail de Customer Journey Analytics indiquant que le chiffrement du mot de passe est requis pour votre organisation.](assets/email-password.png)

1. Connectez-vous à Customer Journey Analytics.
1. Sélectionnez **[!UICONTROL Afficher le projet planifié]**.
1. Dans la boîte de dialogue **[!UICONTROL Modifier le projet planifié]**, saisissez un mot de passe et saisissez-le à nouveau.
1. Partagez ce mot de passe avec les destinataires du projet planifié. Ne distribuez pas le mot de passe aux personnes qui ne sont pas destinataires du projet planifié.
