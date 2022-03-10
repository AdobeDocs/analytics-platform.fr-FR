---
title: Comment estimer la taille de connexion CJA
description: Rapport sur votre utilisation actuelle de Customer Journey Analytics
exl-id: 5599b34f-342d-4c68-b7c9-2ac3ea50d078
solution: Customer Journey Analytics
feature: Connections
source-git-commit: cd48a91ca3affc39cf71451bdd8a44ca7669523b
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 51%

---

# Estimation de la taille de connexion

Vous devrez peut-être connaître le nombre de lignes de données actuellement présentes dans [!UICONTROL Customer Journey Analytics]. Pour obtenir un compte précis de l’utilisation des enregistrements de données d’événement (lignes de données) de votre entreprise, procédez comme suit : **pour chacune des connexions créées par votre organisation**.

1. Dans [!UICONTROL Customer Journey Analytics], sélectionnez l’onglet **[!UICONTROL Connexions]**.

   Vous pouvez maintenant voir la liste de toutes vos connexions actuelles.

1. Cliquez sur chaque nom de connexion pour accéder au Gestionnaire de connexions.

1. Ajoutez la variable **[!UICONTROL Enregistrements de données d’événement disponibles]** pour toutes les connexions créées. (Selon la taille de la connexion, l’affichage du nombre peut prendre un certain temps.)

   ![données d’événement](assets/event-data.png)

1. Une fois que vous disposez d’une somme de toutes les lignes de données d’événement, recherchez le droit &quot;Lignes de données&quot; dans le contrat de Customer Journey Analytics que votre société a signé avec votre Adobe.

   Vous obtenez ainsi le nombre maximal de lignes de données autorisées dans la commande de ventes. Si le nombre de lignes de données résultant de l’étape 3 est supérieur à ce nombre, vous rencontrez une surcharge.

1. Pour remédier à cette situation, vous disposez de plusieurs options :

   * Modifiez votre [paramètres de conservation des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=fr#set-rolling-window-for-connection-data-retention).
   * [Supprimer toutes les connexions inutilisées](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=fr#implications-of-deleting-data-components).
   * [Suppression d’un jeu de données dans AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components).
   * Contactez votre gestionnaire de compte d’Adobe pour obtenir des licences de capacité supplémentaire.

## À propos des dépassements d’utilisation

Les limites d’utilisation sont strictement surveillées et appliquées par Adobe, sur une base quotidienne. &quot;Lignes de données&quot; désigne les lignes de données quotidiennes moyennes disponibles pour l’analyse dans Customer Journey Analytics.

Supposons que votre contrat limite le nombre de lignes à 1 million. Supposons que le jour 1 de l’utilisation de Customer Journey Analytics, vous chargiez 2 millions de lignes de données. Le jour 2, vous supprimez 1 million de lignes et maintenez votre utilisation à ce maximum engagé. Vous continuerez à encourir des frais d’utilisation pour le Jour 1.

## Diagnostic des incohérences

Dans certains cas, vous remarquerez peut-être que le nombre total dʼévénements ingérés par votre connexion est différent du nombre de lignes du jeu de données dans [!UICONTROL Adobe Experience Platform]. Dans cet exemple, le jeu de données « Impression B2B » contient 7 650 lignes, mais le jeu de données contient 3 830 lignes dans [!UICONTROL Adobe Experience Platform]. Il existe plusieurs raisons pour lesquelles des écarts peuvent survenir et les mesures suivantes peuvent être prises pour effectuer un diagnostic :

1. Ventilez cette dimension par **[!UICONTROL identifiant de jeu de données Platform]** et vous remarquerez deux jeux de données de même taille mais différents **[!UICONTROL identifiants de jeu de données Platform]**. Chaque jeu de données contient 3 825 enregistrements. Cela signifie que [!UICONTROL Customer Journey Analytics] a ignoré 5 enregistrements en raison d’identifiants de personne manquants ou d’horodatages manquants :

   ![ventilation](assets/data-size2.png)

1. En outre, si nous archivons [!UICONTROL Adobe Experience Platform], il nʼexiste aucun jeu de données avec lʼidentifiant &quot;5f21c12b732044194bffc1d0&quot;, dʼoù la suppression de ce jeu de données particulier dʼ[!UICONTROL Adobe Experience Platform] lors de la création de la connexion initiale. Par la suite, il a été ajouté à Customer Journey Analytics, mais un autre [!UICONTROL identifiant de jeu de données Platform] a été généré par [!UICONTROL Adobe Experience Platform].

Découvrez-en plus sur les [implications de la suppression du jeu de données et de la connexion](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components) dans [!UICONTROL Customer Journey Analytics] et [!UICONTROL Adobe Experience Platform].
