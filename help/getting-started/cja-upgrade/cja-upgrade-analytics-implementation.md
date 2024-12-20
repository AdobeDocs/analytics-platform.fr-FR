---
title: Comprendre votre mise en oeuvre Adobe Analytics et son impact sur votre mise à niveau vers Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 19%

---

# Comprendre votre mise en oeuvre Adobe Analytics et son impact sur votre mise à niveau vers Customer Journey Analytics

>[!NOTE]
> 
>Utilisez les informations de cette page pour répondre aux questions de la [liste de contrôle de mise à niveau des Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Adobe Analytics peut être implémenté de différentes manières. Lors de la mise à niveau vers Customer Journey Analytics, tous les chemins de mise à niveau ne sont pas disponibles pour toutes les implémentations Adobe Analytics. Cependant, le chemin de mise à niveau recommandé est disponible quelle que soit la manière dont Adobe Analytics est mis en oeuvre dans votre entreprise.

Utilisez les informations ci-dessous pour en savoir plus sur votre mise en oeuvre actuelle d’Adobe Analytics et sur les chemins de mise à niveau disponibles pour votre entreprise.

Contactez votre représentant ou représentante Adobe si vous avez besoin d’assistance ou de conseils plus précis.

| Implémentation existante dʼAdobe Analytics | Description | Chemins de mise à niveau disponibles |
|---------|----------|----------|
| AppMeasurement | L’AppMeasurement pour JavaScript a toujours été une méthode courante de mise en oeuvre d’Adobe Analytics.<p>Pour plus d’informations sur ce type d’implémentation, voir [Mise en oeuvre d’Adobe Analytics avec AppMeasurement pour JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>(Recommandé) Nouvelle mise en oeuvre du SDK Web Experience Platform avec Analytics Source Connector.</li><li>Nouvelle implémentation du SDK web Experience Platform</li><li>Migrer Adobe Analytics vers le SDK web</li><li>Connecteur source Analytics</li></ul> |
| Extension Adobe Analytics (balises) | <p>Les balises dans Adobe Experience Platform représentent une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site.</p><p>Pour plus d’informations sur ce type d’implémentation, voir [Mise en oeuvre d’Adobe Analytics à l’aide de l’extension Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>(Recommandé) Nouvelle mise en oeuvre du SDK Web Experience Platform avec Analytics Source Connector.</li><li>Nouvelle implémentation du SDK web Experience Platform</li><li>Migrer Adobe Analytics vers le SDK web</li><li>Connecteur source Analytics</li></ul> |
| SDK Web Experience Platform (alloy.js) | Le SDK Web Experience Platform est la méthode actuellement recommandée par l’Adobe pour mettre en oeuvre Adobe Analytics. L’Edge Network Adobe Experience Platform vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. <p>Pour plus d’informations sur ce type d’implémentation, voir [Mise en oeuvre d’Adobe Analytics avec l’Edge Network Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Recommandé) Nouvelle mise en oeuvre du SDK Web Experience Platform avec Analytics Source Connector.</li><li>Configuration de l’implémentation du SDK Web Adobe Analytics pour envoyer des données à Platform</li></ul> |
| Extension SDK Web Experience Platform (balises) | Le SDK Web Experience Platform est la méthode actuellement recommandée par l’Adobe pour mettre en oeuvre Adobe Analytics pour les données web. L’Edge Network Adobe Experience Platform vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. <p>Pour plus d’informations sur ce type d’implémentation, voir [Mise en oeuvre d’Adobe Analytics à l’aide du SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>(Recommandé) Nouvelle mise en oeuvre du SDK Web Experience Platform avec Analytics Source Connector.</li><li>Configuration de l’implémentation du SDK Web Adobe Analytics pour envoyer des données à Platform</li></ul> |
| Experience Platform Mobile SDK | Le SDK Mobile Experience Platform est la méthode actuellement recommandée par l’Adobe pour mettre en oeuvre Adobe Analytics pour les données mobiles. L’Edge Network Adobe Experience Platform vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé.<p>Le SDK Adobe Experience Platform Mobile permet d’optimiser les solutions et services Experience Cloud de l’Adobe dans vos applications mobiles. </p><p>Pour plus d’informations sur ce type d’implémentation, voir [Mise en oeuvre d’Adobe Analytics à l’aide du SDK Adobe Experience Platform Mobile](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>(Recommandé) Nouvelle mise en oeuvre du SDK Web Experience Platform avec Analytics Source Connector.</li><li>Configuration de l’implémentation du SDK Web Adobe Analytics pour envoyer des données à Platform</li></ul> |

{style="table-layout:auto"}
