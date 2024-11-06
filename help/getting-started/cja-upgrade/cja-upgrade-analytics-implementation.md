---
title: Comprendre votre mise en oeuvre Adobe Analytics et son impact sur votre mise à niveau vers Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 21%

---

# Comprendre votre mise en oeuvre Adobe Analytics et son impact sur votre mise à niveau vers Customer Journey Analytics

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes de mise à niveau précédentes effectuées. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement pour votre organisation avec le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

Il existe plusieurs façons de mettre à niveau vers Customer Journey Analytics, mais tous les chemins de mise à niveau ne sont pas disponibles pour chaque type de mise en oeuvre d’Adobe Analytics. Cependant, le chemin de mise à niveau recommandé est disponible quelle que soit la manière dont Adobe Analytics est mis en oeuvre dans votre entreprise.

Utilisez les informations ci-dessous pour vous aider à comprendre les chemins de mise à niveau disponibles pour votre entreprise.

Contactez votre représentant ou représentante Adobe si vous avez besoin d’assistance ou de conseils plus précis.

| Implémentation existante dʼAdobe Analytics | Description | Chemins de mise à niveau disponibles |
|---------|----------|----------|
| AppMeasurement | L’AppMeasurement pour JavaScript a toujours été une méthode courante de mise en oeuvre d’Adobe Analytics.<p>Pour plus d’informations sur ce type d’implémentation, voir [Mise en oeuvre d’Adobe Analytics avec AppMeasurement pour JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>(Recommandé) Nouvelle mise en oeuvre du SDK Web Experience Platform avec Analytics Source Connector.</li><li>Nouvelle implémentation du SDK web Experience Platform</li><li>Migrer Adobe Analytics vers le SDK web</li><li>Connecteur source Analytics</li></ul> |
| Extension Adobe Analytics (balises) | <p>Les balises dans Adobe Experience Platform représentent une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site.</p><p>Pour plus d’informations sur ce type d’implémentation, voir [Mise en oeuvre d’Adobe Analytics à l’aide de l’extension Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>(Recommandé) Nouvelle mise en oeuvre du SDK Web Experience Platform avec Analytics Source Connector.</li><li>Nouvelle implémentation du SDK web Experience Platform</li><li>Migrer Adobe Analytics vers le SDK web</li><li>Connecteur source Analytics</li></ul> |
| SDK Web (alloy.js) | Le SDK Web Experience Platform est la méthode actuellement recommandée par l’Adobe pour mettre en oeuvre Adobe Analytics. L’Edge Network Adobe Experience Platform vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. <p>Pour plus d’informations sur ce type d’implémentation, voir [Mise en oeuvre d’Adobe Analytics avec l’Edge Network Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Recommandé) Nouvelle mise en oeuvre du SDK Web Experience Platform avec Analytics Source Connector.</li><li>Configuration de l’implémentation du SDK Web Adobe Analytics pour envoyer des données à Platform</li></ul> |
| Extension SDK Web (balises) | Le SDK Web Experience Platform est la méthode actuellement recommandée par l’Adobe pour mettre en oeuvre Adobe Analytics. L’Edge Network Adobe Experience Platform vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. <p>Pour plus d’informations sur ce type d’implémentation, voir [Mise en oeuvre d’Adobe Analytics avec l’Edge Network Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Recommandé) Nouvelle mise en oeuvre du SDK Web Experience Platform avec Analytics Source Connector.</li><li>Configuration de l’implémentation du SDK Web Adobe Analytics pour envoyer des données à Platform</li></ul> |

{style="table-layout:auto"}

