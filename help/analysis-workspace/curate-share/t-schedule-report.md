---
description: Envoyez un projet Analysis Workspace par courrier électronique ou planifiez une livraison.
keywords: Analysis Workspace
title: Planification de projets
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: 6f3ae14e4d34de17ed64ae30cee4611e4d6f3226
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 79%

---

# Planification de projets

À partir de Workspace **[!UICONTROL Partager]** , vous pouvez envoyer des projets Analysis Workspace par courrier électronique aux destinataires sélectionnés. Les fichiers peuvent être envoyés au format CSV ou PDF.

## Envoyer le fichier maintenant {#now}

Pour envoyer un fichier immédiatement aux destinataires par courrier électronique :

1. Cliquez sur **[!UICONTROL Partager] > [!UICONTROL Exporter le fichier]**.
1. Spécifiez le type de fichier :
   * [!UICONTROL **CSV**]: choisissez cette option si vous souhaitez des données en texte brut.
   * [!UICONTROL **PDF**]: choisissez cette option si vous souhaitez que le fichier téléchargé contienne tous les tableaux et visualisations affichés (visibles) dans le projet.
1. (Facultatif) Ajoutez une description à inclure dans le courrier électronique pour expliquer le fichier reçu.
1. Ajoutez des destinataires ou des groupes. Vous pouvez également saisir les adresses électroniques.
1. (Uniquement pour les clients de Healthcare Shield) Indiquez un mot de passe. Voir la section Protection par mot de passe d’un rapport planifié.
1. Cliquez sur **[!UICONTROL Envoyer maintenant]**.
1. (Facultatif) Cliquez sur **[!UICONTROL Afficher les options de planification]** pour planifier une livraison.

![Envoyer le fichier maintenant](assets/send-file-no-scheduling-options.JPG)

## Envoyer le fichier selon le calendrier {#schedule}

Pour envoyer un fichier selon un calendrier récurrent aux destinataires par courrier électronique :

1. Cliquez sur **[!UICONTROL Partager] > [!UICONTROL Planification de l’exportation du fichier]**.
1. Spécifiez le type de fichier (CSV ou PDF).
1. (Facultatif) Ajoutez une description qui sera incluse dans le courrier électronique pour décrire le fichier reçu.
1. Ajoutez des destinataires ou des groupes. Vous pouvez également saisir les adresses électroniques.
1. (Uniquement pour les clients de Healthcare Shield) Indiquez un mot de passe. Voir la section Protection par mot de passe d’un rapport planifié.
1. Précisez la période pendant laquelle la livraison doit être effectuée en modifiant les entrées Début le et Fin le. La date de fin doit se situer dans un délai d’un an à compter du jour de la création ou de la modification de la planification.
1. Spécifiez la fréquence de livraison. Chaque fréquence offre différentes personnalisations.
1. Cliquez sur **[!UICONTROL Envoyer selon le calendrier]**.

![](assets/send-file.JPG)

## Gestionnaire de projets planifiés {#manager}

Les projets Analysis Workspace planifiés peuvent être gérés sous **[!UICONTROL Analytics] > [!UICONTROL Composants] > [!UICONTROL Projets planifiés]**.

Pour plus d’informations, voir [Projets planifiés](/help/components/scheduled-projects-manager.md)

## Protéger un projet planifié par mot de passe {#password}

>[!NOTE]
>
>L’option de protection par mot de passe d’un projet planifié s’affiche uniquement pour les clients Customer Journey Analytics qui ont acheté le [Bouclier sanitaire](https://business.adobe.com/fr/solutions/experience-cloud-for-healthcare.html) produit complémentaire.

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


