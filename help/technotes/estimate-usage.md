---
title: Gestion de l’utilisation de Customer Journey Analytics
description: Explique comment gérer l’utilisation de Customer Journey Analytics.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
autotag-review: '2026-05-19T09:30:13.855Z'
TQID: 'https://experienceleague.adobe.com/SWjkycY-YwNFMXRXwBypDtTL2ffFn40-Fp88vSxv-74'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
    internal-label: Connections
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 37%
---
# Gestion de l’utilisation de Customer Journey Analytics

>[!TIP]
>
>Utilisez l’interface [**[!UICONTROL Utilisation &#x200B;]**](/help/connections/manage-connections.md#usage) pour **&#x200B; afficher &#x200B;** l’utilisation des lignes ingérées et à signaler sur toutes les connexions dans Customer Journey Analytics.



Vous pouvez gérer l’utilisation de Customer Journey Analytics dans l’interface [**[!UICONTROL Connexions &#x200B;]**](/help/connections/create-connection.md). Dans cette interface, vous pouvez définir la conservation des données de Customer Journey Analytics sous la forme d’une fenêtre dynamique en mois (1 mois, 3 mois, 6 mois, etc.), au niveau de la connexion.

Le principal avantage est que vous stockez ou utilisez dans vos rapports uniquement les données pertinentes et utiles, et supprimez les données plus anciennes qui ne sont plus utiles. Elle vous aide à rester dans les limites de votre contrat et réduit le risque de surcoût.

Si vous laissez la valeur par défaut (non cochée), la période de conservation sera remplacée par le paramètre de conservation des données d’Adobe Experience Platform. Si vous disposez de 25 mois de données dans Experience Platform, Customer Journey Analytics obtiendra 25 mois de données par renvoi. Si vous avez supprimé 10 de ces mois dans Platform, Customer Journey Analytics conserve les 15 mois restants.

La conservation des données est basée sur les dates et heures et s’applique uniquement aux jeux de données d’événement et de résumé. Aucun paramètre de fenêtre dynamique de conservation des données nʼexiste pour les jeux de données de profil ou de recherche, car il nʼexiste aucun horodatage applicable. Si votre connexion inclut des jeux de données de profil ou de recherche, étant donné qu’ils sont associés à des jeux de données d’événement, les données sont conservées dans Customer Journey Analytics en fonction de vos paramètres de conservation des données sur les dates et heures du jeu de données d’événement.


>[!MORELIKETHIS]
>
>[Afficher l’utilisation de Customer Journey Analytics](/help/connections/manage-connections.md#usage)

