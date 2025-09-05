---
title: Utilisation du groupement
description: Comment utiliser le piquage
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: true
hidefromtoc: true
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: c4aea74807be15af56413522d9e6fbf5f18a37a0
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 3%

---

# Utilisation du groupement

Vous pouvez activer le regroupement sur un ou plusieurs jeux de données d’événement que vous avez configurés dans le cadre de votre connexion. Le nombre de jeux de données d’événements que vous pouvez activer pour le groupement est déterminé par le package Customer Journey Analytics sous licence que vous possédez.

Vous pouvez activer le groupement dans le cadre de l’[paramètres du jeu de données](/help/connections/create-connection.md#dataset-settings) pour un jeu de données d’événement lorsque vous [créez une connexion](/help/connections/create-connection.md) ou lorsque vous [modifiez une connexion](/help/connections/manage-connections.md#edit-a-connection).

Pour activer le groupement, dans la section Jeu de données d’événement de la boîte de dialogue **[!UICONTROL Ajouter des jeux de données]** ou **[!UICONTROL Modifier le jeu de données]** :

![Options de combinaison d’identités lorsque vous activez cette fonction](assets/identity-stitching-ui.png)

1. Sélectionnez **[!UICONTROL Activer la combinaison d’identités]**.

   Si vous activez le groupement pour un jeu de données d’événement existant, la boîte de dialogue **[!UICONTROL Modifier l’ID de personne]** affiche les implications d’une modification de l’ID de personne due à l’utilisation du groupement. Sélectionnez **[!UICONTROL Continuer]** pour continuer.

   La boîte de dialogue **[!UICONTROL Activer la combinaison d’identités]** résume les conséquences de la combinaison d’identités. Sélectionnez **[!UICONTROL Continuer]** pour continuer.

1. Sélectionnez un ID persistant dans le menu déroulant **[!UICONTROL ID persistant]**.

   Si vous sélectionnez **[!UICONTROL Mappage d’identités]** pour l’identifiant persistant, vous devez sélectionner un espace de noms . Vous disposez de deux options :

   * Activez **[!UICONTROL Utiliser l’espace de noms d’identité principal]** pour utiliser l’espace de noms d’identité principal.
   * Sélectionnez un espace de noms dans le menu déroulant **[!UICONTROL Espace de noms]**.

1. Sélectionnez un ID de personne dans le menu déroulant **[!UICONTROL ID de personne]**.

   Si vous sélectionnez **[!UICONTROL Mappage d’identités]** pour l’ID de personne, vous devez sélectionner un espace de noms. Vous disposez de deux options :

   * Activez **[!UICONTROL Utiliser l’espace de noms d’identité principal]** pour utiliser l’espace de noms d’identité principal.
   * Sélectionnez un espace de noms dans le menu déroulant **[!UICONTROL Espace de noms]**.


   Si vous sélectionnez **[!UICONTROL Graphique d’identités]** pour l’ID de personne, vous devez sélectionner un espace de noms.

   >[!NOTE]
   >
   >Vous devez être autorisé à utiliser le graphique d’identité.
   >

   Avant cela, une boîte de dialogue **[!UICONTROL Modifier en graphique d’identité]** s’affiche pour vous assurer que vous avez [terminé la configuration du graphique d’identité pour le jeu de données](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) avant d’utiliser le graphique d’identité pour le groupement. Sélectionnez **[!UICONTROL Continuer]** pour continuer.

   * Sélectionnez un espace de noms dans le menu déroulant **[!UICONTROL Espace de noms]**.


1. Sélectionnez un intervalle de recherche en amont dans le menu déroulant **[!UICONTROL Intervalle de recherche en amont]**. Les options disponibles dépendent du package Customer Journey Analytics auquel vous avez droit.

Une fois que vous avez enregistré une connexion contenant des jeux de données activés pour la combinaison d’identités, le processus de combinaison de chaque jeu de données commence lorsque l’ingestion des données de ce jeu de données commence.