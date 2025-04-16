---
title: Gestion de l’utilisation de Customer Journey Analytics
description: Explique comment gérer l’utilisation de Customer Journey Analytics.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 5311106f486a30dbc7f06b3ef60dc7e666d2fe03
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 42%

---

# Gestion de l’utilisation de Customer Journey Analytics

>[!TIP]
>
>Utilisez l’interface [**[!UICONTROL Utilisation ]**](/help/connections/manage-connections.md#usage) pour** afficher **l’utilisation des lignes ingérées et à signaler sur toutes les connexions dans Customer Journey Analytics.



Vous pouvez gérer l’utilisation de Customer Journey Analytics dans l’interface [**[!UICONTROL Connexions ]**](/help/connections/create-connection.md). Dans cette interface, vous pouvez définir la conservation des données de Customer Journey Analytics sous la forme d’une fenêtre dynamique en mois (1 mois, 3 mois, 6 mois, etc.), au niveau de la connexion.

Lʼavantage principal est que vous ne stockez ou ne créez des rapports que sur les données applicables et utiles, et supprimez les données plus anciennes qui ne sont plus utiles. Elle vous aide à rester dans les limites de votre contrat et réduit le risque de surcoût.

Si vous laissez la valeur par défaut (non cochée), la période de conservation sera remplacée par le paramètre de conservation des données d’Adobe Experience Platform. Si vous disposez de 25 mois de données dans Experience Platform, Customer Journey Analytics obtiendra 25 mois de données par renvoi. Si vous avez supprimé 10 de ces mois dans Platform, Customer Journey Analytics conserve les 15 mois restants.

La conservation des données est basée sur les horodatages des jeux de données dʼévénement et sʼapplique uniquement aux jeux de données dʼévénement. Aucun paramètre de fenêtre dynamique de conservation des données nʼexiste pour les jeux de données de profil ou de recherche, car il nʼexiste aucun horodatage applicable. Si votre connexion inclut des jeux de données de profil ou de recherche, étant donné qu’ils sont associés à des jeux de données d’événement, les données sont conservées dans Customer Journey Analytics en fonction de vos paramètres de conservation des données sur les dates et heures du jeu de données d’événement.


>[!MORELIKETHIS]
>
>[Afficher l’utilisation de Customer Journey Analytics](/help/connections/manage-connections.md#usage)

