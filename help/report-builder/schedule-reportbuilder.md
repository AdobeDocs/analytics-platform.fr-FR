---
title: Comment planifier des classeurs à l’aide de Report Builder dans Customer Journey Analytics
description: Découvrez comment utiliser la fonction de planification dans Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 7429d8f9-1e8f-4fbd-8b04-cbe7adbff3e2
source-git-commit: 6dd8a70293161ff58361953a7e48a98834b7abe0
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 13%

---

# Planification de classeurs

Une fois le classeur enregistré et l’analyse terminée, vous pouvez le partager avec d’autres membres de l’équipe à l’aide de la fonction de planification. La fonction de planification vous permet de créer une planification qui actualise automatiquement les données du classeur. Et envoie par e-mail le fichier de classeur Excel en tant que pièce jointe à une audience spécifiée à une date et une heure spécifiques. La configuration d’une planification permet aux destinataires de recevoir automatiquement des mises à jour régulières. Vous pouvez également utiliser la fonction de planification pour envoyer le classeur une seule fois sans planifier de mises à jour automatiques.

Vous pouvez créer plusieurs planifications pour un seul classeur. Par exemple, vous créez deux planifications pour envoyer un classeur à votre équipe tous les jours et à votre responsable une fois par semaine.

La fonction de planification vous permet également de configurer la protection par mot de passe d’un classeur et de modifier les classeurs planifiés précédemment.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Schedule Workbooks](https://video.tv.adobe.com/v/3413079/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Planifier un classeur

Pour planifier un classeur :

1. Sélectionnez **[!UICONTROL Planification]** dans le hub Report Builder pour créer une planification afin de pouvoir distribuer automatiquement un fichier Excel de classeur (.xlsx) à un individu ou à un groupe.

   ![Cliquez sur le bouton Planifier pour créer une planification.](./assets/schedule.png){zoomable="yes"}

1. Sélectionnez **[!UICONTROL Planifier le classeur]** ou ![Ajouter](/help/assets/icons/Add.svg) pour créer un classeur planifié.

   ![Fenêtre Planifier des classeurs.](./assets/schedule-workbook.png){zoomable="yes"}

   Le volet de planification affiche des informations prédéfinies sur le classeur, telles que le nom du classeur et la date de la dernière modification.

### Fichier

Dans la section **[!UICONTROL Fichier]**, vous fournissez des détails sur le type de fichier, le nom et un mot de passe pour protéger le fichier.

![Volet de planification.](./assets/schedule-pane.png){zoomable="yes"}

1. Utilisez ![TableSelect](/help/assets/icons/TableSelect.svg) pour sélectionner le classeur actif, s’il n’est pas déjà sélectionné.

1. (Facultatif) Saisissez un **[!UICONTROL Nom de fichier]**.

   Par défaut, le nom de fichier du classeur correspond au nom du classeur, mais vous pouvez le modifier si vous le souhaitez.

1. Sélectionnez un **[!UICONTROL Type de fichier]**.

   * **[!UICONTROL Excel]**
   * **[!UICONTROL PDF]**
   * **[!UICONTROL CSV]**

   Lorsque vous sélectionnez **[!UICONTROL CSV]**, sachez que le classeur planifié est envoyé en tant que pièce jointe. Certaines administrations de messagerie d&#39;entreprise peuvent bloquer les e-mails contenant des pièces jointes au format zip. Un avertissement s’affiche en conséquence.

1. (Facultatif) Sélectionnez **[!UICONTROL Ajouter un horodatage au nom du fichier]**.

   Vous pouvez ajouter un horodatage au nom du fichier pour indiquer la date à laquelle le classeur a été mis à jour. Un horodatage est utile pour savoir quelle version d’un classeur a été envoyée à une date spécifique. Lorsque cette option est sélectionnée, vous pouvez choisir entre :

   * **[!UICONTROL Format de date ISO]**, ce qui entraîne l’ajout de `YYYY-MM-DD` au nom de fichier.
   * **[!UICONTROL Format de date ISO + horodatage]**, ce qui entraîne l’ajout de `YYYY-MM-DD_HH-MM-SS` au nom de fichier.

<!-- Does no longer seem to be an option? 
1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){zoomable="yes"}{width="55%"}
-->

1. Saisissez un mot de passe dans **[!UICONTROL Protéger le classeur par mot de passe]**. Un mot de passe valide nécessite au moins 8 caractères, un nombre et un caractère spécial. Sélectionnez ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) pour afficher le mot de passe et ![Visibility](/help/assets/icons/Visibility.svg) pour le masquer (par défaut).


### Adresse électronique

Dans la section **[!UICONTROL E-mail]**, indiquez les destinataires, l’objet et la description de l’e-mail.

![Paramètres de planification de l’e-mail](assets/schedule-email.png){zoomable="yes"}

1. Saisissez les **Destinataires**. Vous pouvez saisir le nom d&#39;une personne reconnue dans votre organisation. Vous pouvez également saisir l’adresse e-mail d’une personne extérieure à votre entreprise.

1. Saisissez l’**Objet** de l’e-mail et une description pour vos destinataires. Par défaut, l’objet correspond au nom de fichier du classeur, mais vous pouvez modifier l’objet si nécessaire. Vous pouvez ajouter des détails dans la section de description.

1. Vous pouvez éventuellement saisir une description dans la zone de texte **[!UICONTROL Description]**.


### Planifier

Dans la section **[!UICONTROL Planifier]**, vous pouvez définir la planification pour envoyer les e-mails avec le classeur à vos destinataires.

![Définition d’horaire](assets/schedule-enable.png){zoomable="yes"}

1. Sélectionnez **[!UICONTROL Afficher les options de planification]** pour définir une planification.

1. Saisissez une date de début dans **[!UICONTROL À partir du]**. Vous pouvez également sélectionner ![Calendrier](/help/assets/icons/Calendar.svg) pour choisir une date de début dans le calendrier.

1. Saisissez une date de fin dans **[!UICONTROL Se terminant le]**. Vous pouvez également sélectionner ![Calendrier](/help/assets/icons/Calendar.svg) pour choisir une date de fin dans le calendrier.

1. Sélectionnez une **[!UICONTROL Fréquence]**. Selon la fréquence sélectionnée, vous disposez d’options supplémentaires. Voir le tableau ci-dessous.

   | Fréquence | Options |
   |---|---|
   | **[!UICONTROL Envoyer par heure]** | Saisissez une valeur pour **[!UICONTROL Envoyer toutes les heures]**. |
   | **[!UICONTROL Envoyer quotidiennement]** | Sélectionnez une **[!UICONTROL Fréquence quotidienne]** : **[!UICONTROL Envoyer tous les jours]**, **[!UICONTROL Envoyer tous les jours de la semaine]** ou **[!UICONTROL Fréquence personnalisée]**.<br/>Si vous sélectionnez **[!UICONTROL Fréquence personnalisée]**, saisissez une valeur pour **[!UICONTROL Envoyer tous les jours]**. |
   | **[!UICONTROL Envoyer une fois par semaine]** | Saisissez une valeur pour **[!UICONTROL Envoyer toutes les semaines]**. Sélectionnez ensuite un **[!UICONTROL Jour de la semaine]**. |
   | **[!UICONTROL Envoyer mensuellement par jour de la semaine]** | Sélectionnez un **[!UICONTROL Jour de la semaine]** et un **[!UICONTROL Semaine du mois]**. |
   | **[!UICONTROL Envoyer mensuellement par jour du mois]** | Sélectionnez une valeur dans **[!UICONTROL Envoyer ce jour du mois]**. |
   | **[!UICONTROL Envoyer annuellement par jour du mois]** | Sélectionnez un **[!UICONTROL Jour de la semaine]**, une **[!UICONTROL Semaine du mois]** et une **[!UICONTROL Mensuel de l’année]**. |
   | **[!UICONTROL Envoyer annuellement par date spécifique]** | Sélectionnez un **[!UICONTROL Mois de l’année]** et sélectionnez une valeur dans **[!UICONTROL Envoyer ce jour du mois]**. |

### Envoyer

Pour envoyer le classeur :

* Si vous n’avez pas défini de planning à l’aide de l’option **[!UICONTROL Afficher les options de planification]**, sélectionnez **[!UICONTROL Envoyer maintenant]** pour envoyer immédiatement le classeur par e-mail.
* Si vous avez défini une planification à l’aide de l’option **[!UICONTROL Afficher les options de planification]**, sélectionnez **[!UICONTROL Envoyer selon le calendrier]** pour envoyer le classeur par e-mail à l’aide de la planification que vous avez définie.

Dans les deux cas, un toast de confirmation s’affiche au bas du hub Report Builder.

Pour annuler l’envoi du classeur, sélectionnez **[!UICONTROL Annuler]**.


## Afficher et gérer les classeurs planifiés

Vous pouvez afficher et gérer tous les classeurs planifiés dans l’onglet **[!UICONTROL Classeurs]**.

1. Sélectionnez **[!UICONTROL Planifier]** dans le hub Report Builder

1. Sélectionnez l’onglet **[!UICONTROL Classeurs]**. La liste de tous les classeurs planifiés s’affiche.

   ![Classeur planifié](assets/scheduled-workbooks.png){zoomable="yes"}

   Vous pouvez placer le pointeur de la souris sur l’icône pour afficher le statut d’un classeur planifié.

   Utilisez ![Rechercher](/help/assets/icons/Search.svg) pour rechercher des classeurs planifiés spécifiques.
Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour définir les colonnes à afficher.

1. Sélectionnez un ou plusieurs classeurs.

   ![Planifier les classeurs sélectionnés](assets/scheduled-workbooks-selected.png){zoomable="yes"}

   Les options disponibles sont les suivantes :

   | Option | Description |
   |---|---|
   | ![Modifier](/help/assets/icons/Edit.svg) | Modifiez la planification d’un classeur sélectionné. |
   | ![Historique](/help/assets/icons/History.svg) | Afficher l’historique des classeurs sélectionnés. |
   | ![ Pause ](/help/assets/icons/Pause.svg) | Mettre en pause le planning des classeurs sélectionnés. |
   | ![Lecture](/help/assets/icons/Play.svg) | Reprenez la planification des classeurs sélectionnés. |
   | ![Télécharger](/help/assets/icons/Download.svg) | Téléchargez le classeur sélectionné dans un nouveau classeur. |
   | ![Supprimer](/help/assets/icons/Delete.svg) | Supprimez la planification des classeurs sélectionnés. |


## Historique et statut des classeurs planifiés

Vous pouvez afficher l’historique et le statut des classeurs planifiés dans l’onglet **[!UICONTROL Historique]**.

1. Sélectionnez **[!UICONTROL Planifier]** dans le hub Report Builder.

1. Sélectionnez l’onglet **[!UICONTROL Historique]**. La liste de tous les classeurs planifiés s’affiche.

   ![Historique planifié](assets/scheduled-workbooks-history.png){zoomable="yes"}

   Utilisez ![Rechercher](/help/assets/icons/Search.svg) pour rechercher des classeurs spécifiques dans la liste.
Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour définir les colonnes à afficher.

   L’onglet **[!UICONTROL Historique]** vous permet de consulter le statut de chaque tâche planifiée. Une ligne distincte documente le changement d’état pour chaque tâche planifiée.

   * Un ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg) indique que le classeur a bien été envoyé.
   * Un ![AlertRed](/help/assets/icons/AlertRed.svg) indique qu&#39;une erreur s&#39;est produite.

Vous pouvez également sélectionner ![Historique](/help/assets/icons/History.svg) pour un ou plusieurs classeurs sélectionnés dans l’onglet **[!UICONTROL Classeurs]**. Cette action affiche l’onglet **[!UICONTROL Historique]** avec une liste filtrée par votre sélection. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer un filtre.
