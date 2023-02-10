---
description: Envoyez un projet Analysis Workspace par courrier électronique ou planifiez une livraison.
keywords: Analysis Workspace
title: Planification de projets
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: b0a1fdcfb2d200d40c308c557c2ddff172c1e18f
workflow-type: ht
source-wordcount: '745'
ht-degree: 100%

---

# Planification de projets

Dans le **menu Partager** de Workspace, vous pouvez envoyer des projets Analysis Workspace par courrier électronique aux destinataires sélectionnés. Les fichiers peuvent être envoyés au format CSV ou PDF.

## Envoyer le fichier maintenant {#now}

Pour envoyer un fichier immédiatement aux destinataires par courrier électronique :

1. Cliquez sur **Partager > Envoyer le fichier maintenant**.
1. Spécifiez le type de fichier (CSV ou PDF).
1. (Facultatif) Ajoutez une description qui sera incluse dans le courrier électronique pour décrire le fichier reçu.
1. Ajoutez des destinataires ou des groupes. Vous pouvez également saisir les adresses électroniques.
1. (Uniquement pour les clients de Healthcare Shield) Indiquez un mot de passe. Voir la section Protection par mot de passe d’un rapport planifié.
1. Cliquez sur **Envoyer maintenant**.
1. (Facultatif) Cliquez sur **Afficher les options de planification** pour planifier une livraison.

![Envoyer le fichier maintenant](assets/send-file-no-scheduling-options.JPG)

## Envoyer le fichier selon le calendrier {#schedule}

Pour envoyer un fichier selon un calendrier récurrent aux destinataires par courrier électronique :

1. Cliquez sur **Partager > Envoyer le fichier selon le calendrier**.
1. Spécifiez le type de fichier (CSV ou PDF).
1. (Facultatif) Ajoutez une description qui sera incluse dans le courrier électronique pour décrire le fichier reçu.
1. Ajoutez des destinataires ou des groupes. Vous pouvez également saisir les adresses électroniques.
1. (Uniquement pour les clients de Healthcare Shield) Indiquez un mot de passe. Voir la section Protection par mot de passe d’un rapport planifié.
1. Précisez la période pendant laquelle la livraison doit être effectuée en modifiant les entrées Début le et Fin le. La date de fin doit se situer dans un délai d’un an à compter du jour de la création ou de la modification de la planification.
1. Spécifiez la fréquence de livraison. Chaque fréquence offre différentes personnalisations.
1. Cliquez sur **Envoyer selon le calendrier**.

![](assets/send-file.JPG)

## Gestionnaire de projets planifiés {#manager}

Les projets Analysis Workspace planifiés peuvent être gérés sous **Analytics > Composants > Projets planifiés**.

Dans le Gestionnaire de projets planifiés, vous pouvez modifier et supprimer les calendriers de projets récurrents. Utilisez la barre de recherche ou les options de filtre dans le rail de gauche pour rechercher un calendrier. Vous pouvez filtrer par balise, calendriers approuvés, propriétaires, etc.

Actions courantes du Gestionnaire de projets planifiés :

| Action | Description |
|---|---|
| **Modifier le planning** | Cliquez sur le titre du planning pour mettre à jour les paramètres de livraison. |
| **Supprimer le planning** | Sélectionnez le projet planifié dans la liste, puis cliquez sur Supprimer dans le menu. Cela supprime le planning sélectionné pour le projet ; le projet lui-même n’est pas supprimé. |
| **Ajout de balises** | Sélectionnez le projet planifié dans la liste, puis « Balise » ou « Approuver » pour organiser vos plannings et faciliter les recherches. |
| **Afficher les plannings échoués** | Accédez au rail de gauche > Autres filtres > Échec pour afficher les plannings qui ont échoué. |
| **Afficher les plannings expirés** | Accédez au rail de gauche > Autres filtres > Expiré pour afficher les plannings qui ont expiré. Cliquez sur le titre du planning pour planifier une nouvelle livraison. |
| **Afficher l’ID de planning** | Accédez aux options relatives aux colonnes dans le coin supérieur droit et ajoutez la colonne ID de planning dans le tableau. L’ID planifié est souvent utile pour le débogage. |

Le Gestionnaire de planification des projets affiche les éléments créés par un utilisateur spécifique. Si le compte d’utilisateur est désactivé dans l’application, toutes les livraisons planifiées sont interrompues.

## Protéger un projet planifié par mot de passe {#password}

>[!NOTE]
>
>L’option de protection par mot de passe d’un projet planifié s’affiche uniquement pour les clients CJA qui ont acheté le module complémentaire [Healthcare Shield](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html?lang=fr).

Adobe utilise le mot de passe pour chiffrer les projets planifiés, qu’ils soient envoyés au format .pdf ou .csv.

Une fois que votre entreprise a acheté et activé le SKU Healthcare Shield, l’invitation à créer un mot de passe pour un projet planifié s’affiche dans deux cas :

* Lorsqu’une personne crée un projet planifié.

* Lorsqu’un projet planifié existant est sur le point d’être envoyé. Le projet actuellement planifié sera désactivé jusqu’à la mise en place de la protection par mot de passe. Le propriétaire du projet planifié recevra un e-mail à cet effet.

![Protection par mot de passe](assets/password.png)

### Exigences relatives au mot de passe

Les exigences relatives au mot de passe sont conformes à la norme Adobe, qui requiert un minimum de 8 caractères avec au moins un nombre et un caractère spécial.

### Protéger un nouveau projet planifié par mot de passe

1. Une fois le projet enregistré, accédez à **[!UICONTROL Partager]** > **[!UICONTROL Envoyer le fichier maintenant]** ou [!UICONTROL Partager] > **[!UICONTROL Envoyer le fichier selon le calendrier]**.
1. Suivez les instructions ci-dessus, sous [Envoyer le fichier maintenant](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=fr#now) ou [Envoyer le fichier selon le calendrier](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=fr#schedule).

### Protéger un projet planifié existant par mot de passe

Avant l’heure de planification d’un projet, le propriétaire du projet recevra un e-mail semblable à celui-ci :

![e-mail](assets/email-password.png)

1. Connectez-vous à nouveau à Customer Journey Analytics.
1. Cliquez sur **[!UICONTROL Afficher le projet planifié]**.
1. Dans la boîte de dialogue **[!UICONTROL Modifier le projet planifié]**, saisissez un mot de passe et saisissez-le à nouveau.
1. Partagez ce mot de passe (uniquement) avec les destinataires du projet planifié.


