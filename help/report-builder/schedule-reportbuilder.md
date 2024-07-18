---
title: Comment planifier des classeurs à l’aide de Report Builder dans Customer Journey Analytics
description: Découvrez comment utiliser la fonction de planification dans Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 7429d8f9-1e8f-4fbd-8b04-cbe7adbff3e2
source-git-commit: cbb48623212c2f3d8968dc6daca491761e2f4a9e
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 84%

---

# Planification de classeurs

Une fois le classeur enregistré et l’analyse terminée, vous pouvez facilement le partager avec d’autres membres de l’équipe à l’aide de la fonction de planification. La fonction Planification vous permet de créer une planification qui actualise automatiquement les données du classeur et d’envoyer par e-mail le fichier .xlsx du classeur Excel en tant que pièce jointe à une audience spécifiée à une date et une heure spécifiques. La configuration d’une planification permet aux destinataires de recevoir automatiquement des mises à jour régulières. Vous pouvez également utiliser la fonction de planification pour envoyer le classeur une seule fois sans planifier de mises à jour automatiques.

Vous pouvez créer plusieurs planifications pour un seul classeur. Par exemple, vous pouvez envoyer un classeur à votre équipe sur une base quotidienne et l’envoyer à votre responsable une fois par semaine en créant deux planifications différentes.

La fonction Planification vous permet également de configurer la protection par mot de passe d’un classeur et de modifier les classeurs planifiés précédemment.

>[!VIDEO](https://video.tv.adobe.com/v/3413079/?quality=12&learn=on)

## Planifier un classeur

Utilisez le bouton Planifier la tâche dans le centre Report Builder pour créer rapidement une planification afin de pouvoir distribuer automatiquement un fichier Excel de classeur (.xlsx) à un individu ou à un groupe.

1. Cliquez sur le bouton Planifier dans le centre Report Builder.

   ![Cliquez sur le bouton Planifier pour créer une planification.](./assets/schedule-button.png){width="55%"}

1. Cliquez sur Planifier un classeur ou sur le bouton Plus dans le coin supérieur gauche pour créer un classeur planifié.

   ![Fenêtre Planifier les classeurs.](./assets/schedule-workbook.png){width="55%"}

   Le volet de planification affiche des informations prédéfinies sur le classeur, telles que le nom du classeur et la date de la dernière modification.

   ![Le volet de planification.](./assets/schedule-pane.png){width="55%"}

1. (Facultatif) Saisissez un nom de fichier.

   Par défaut, le nom de fichier du classeur correspond au nom du classeur, mais vous pouvez le modifier si vous le souhaitez. Si vous envoyez le même classeur à plusieurs audiences et que vous souhaitez lui donner un nom un peu plus convivial pour une audience particulière, vous pouvez changer son nom.

1. (Facultatif) Sélectionnez **Ajouter un horodatage au nom du fichier**.

   Vous pouvez ajouter un horodatage au nom du fichier pour indiquer la date à laquelle le classeur a été mis à jour. Ceci est utile pour vérifier rapidement quelle version d’un classeur a été envoyée à une date spécifique. L’**Aperçu du nom de fichier** permet de voir la manière dont le nom de fichier du classeur apparaîtra dans l’e-mail lors de la distribution du classeur. Le format d’horodatage est AAAA-MM-JJ.

1. (Facultatif) Sélectionnez **compression .zip** pour compresser le fichier et configurer sa protection par mot de passe.

   Lorsque vous effectuez cette sélection, vous êtes invité à saisir un mot de passe pour ouvrir le fichier. Ceci est utile si vous avez des inquiétudes concernant la sécurité des données et que vous souhaitez protéger le classeur par mot de passe. Pour protéger le fichier avec un mot de passe, vous devez sélectionner **compression .zip**. Le mot de passe doit contenir au moins 8 caractères, un chiffre et un caractère spécial.

   ![Saisissez un mot de passe dans le champ Protection du classeur par mot de passe.](./assets/zip-compression.png){width="55%"}

1. Saisissez les **Destinataires**. Vous pouvez saisir le nom d’une personne reconnue dans votre organisation ou saisir l’adresse e-mail d’une personne interne ou externe à votre organisation.

1. Saisissez l’**Objet** de l’e-mail et une description pour vos destinataires. Par défaut, l’objet correspond au nom de fichier du classeur, mais vous pouvez modifier l’objet si nécessaire. Vous pouvez ajouter des détails dans la section de description.

   ![Entrez un objet dans le champ Objet.](./assets/recipients-subject.png){width="55%"}

1. Configurez les options de planification pour définir la date et l’heure auxquelles le classeur doit être envoyé par e-mail aux destinataires.

   Sélectionnez les dates et périodes de début et de fin. Il peut s’agir de la date d’aujourd’hui ou d’une date ultérieure.

   Choisissez la **Fréquence** dans le menu déroulant. Vous pouvez choisir une fréquence horaire, quotidienne, hebdomadaire, mensuelle ou annuelle pour un jour spécifique. Par exemple, vous pouvez configurer une planification pour envoyer le classeur le premier dimanche soir du mois afin que vos destinataires voient l’e-mail dans leur boîte de réception à la première heure le lundi matin.

   ![Sélectionnez la fréquence de planification de votre rapport.](./assets/frequency.png){width="55%"}

1. Une fois la planification définie, cliquez sur **Envoyer selon le calendrier**.

   ![Cliquez sur Envoyer selon le calendrier.](./assets/send-on-schedule.png){width="55%"}

   Un toast de confirmation s’affiche au bas du centre Report Builder et le classeur planifié est répertorié sous l’onglet Classeurs.

   ![Toast de confirmation](./assets/confirmation-toast.png){width="55%"}

## Envoyer le classeur une seule fois

Vous pouvez également envoyer le classeur une seule fois.

1. Désélectionnez **Afficher les options de planification**.

   ![ Cliquez sur Désélectionner Afficher les options de planification pour envoyer un classeur une fois.](./assets/send-now.png){width="40%"}

1. Cliquez sur **Envoyer maintenant**.

## Afficher et modifier les classeurs planifiés

Vous pouvez afficher et gérer tous les classeurs planifiés au même endroit sous l’onglet Classeurs.

1. Dans la section Planification du centre Report Builder, cliquez sur l’onglet Classeurs. Utilisez cette vue pour afficher la liste de tous les classeurs planifiés.

1. Sélectionnez un classeur. Plusieurs outils s’affichent pour vous permettre de modifier le classeur, de modifier la tâche de planification, de suspendre et de redémarrer la tâche de planification, de télécharger un rapport de tâche planifiée ou de supprimer la tâche de planification.

   ![Capture d&#39;écran montrant les icônes de planification du classeur.](./assets/schedule-icons.png){width="20%"}

* (Facultatif) Cliquez sur l’icône représentant un crayon pour modifier la tâche de planification du classeur.

* (Facultatif) Cliquez sur l’icône d’horloge pour afficher l’historique de chaque tâche planifiée.

* (Facultatif) Cliquez sur l’icône de pause pour suspendre et redémarrer la tâche de planification de distribution. Cela s’avère utile si vous devez modifier le classeur avant son envoi. Cliquez de nouveau sur l’icône de pause lorsque vous souhaitez redémarrer la distribution.

* (Facultatif) Cliquez sur l’icône de téléchargement pour télécharger une copie de la tâche de planification du classeur.

* (Facultatif) Cliquez sur la corbeille pour supprimer la tâche de planification.

  ![Capture d&#39;écran montrant la liste des tâches de planification.](./assets/selected-workbook.png){width="40%"}

## Vérifier l’état des tâches planifiées

L’affichage de l’historique vous permet de consulter l’état de chaque tâche planifiée. Une ligne distincte documente le changement d’état pour chaque tâche planifiée. Dans l’exemple ci-dessous, la *Nouvelle planification horaire* a été lancée le 5 janvier à 15 h 04. À 15 h 05, elle a été actualisée et envoyée aux destinataires. Une erreur s’est produite lors de l’actualisation du classeur suivant : *Classeur incorrect*. En cas d’échec de l’envoi d’un classeur, l’onglet Historique vous aide à résoudre les problèmes en indiquant le stade du processus où l’erreur s’est produite. Dans ce cas, il s’agit probablement d’une erreur de bloc de données, par exemple un composant manquant, qui a empêché l’actualisation du classeur.

Une coche verte indique que le classeur a bien été envoyé. Un point d’exclamation dans un triangle rouge indique qu’une erreur s’est produite.

Vous pouvez choisir les colonnes à afficher dans l’onglet Historique en cliquant sur l’icône de paramétrage des colonnes située à droite de la barre de recherche.

![Cliquez sur l’icône de colonne pour afficher ou masquer des colonnes spécifiques.](./assets/history.png){width="55%"}

Vous pouvez filtrer l’historique pour n’afficher que celui d’un seul classeur planifié en vous rendant dans l’onglet des classeurs, en le sélectionnant et en cliquant sur l’icône d’historique.

Vous pouvez également afficher l’historique d’un classeur spécifique à partir de l’onglet Classeurs. Dans l’onglet Classeurs, sélectionnez le classeur, puis cliquez sur l’icône d’historique.

![Icône Historique des classeurs](./assets/history2.png){width="55%"}

Le filtre du classeur s’affiche alors en haut de l’historique. Pour afficher à nouveau l’historique de toutes les tâches planifiées, cliquez sur le x en regard du filtre.

![Filtre du classeur.](./assets/history3.png){width="55%"}
