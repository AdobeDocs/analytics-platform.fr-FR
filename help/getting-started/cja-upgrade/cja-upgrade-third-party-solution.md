---
title: Mettre à niveau une solution d’analyse tierce vers Customer Journey Analytics
description: Découvrez comment mettre à niveau une solution d’analyse tierce vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 87df2fb92f238ce051ac5f6cc90e218737279471
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 20%

---

# Mettre à niveau une solution d’analyse tierce vers Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Un produit d’analyse tiers"
>abstract="Mise en œuvre qui collecte des données pour un produit d’analyse tiers, tel que Google Analytics. La sélection de cette option désactive plusieurs options du questionnaire qui ne s’appliquent pas lors de la mise à niveau vers Customer Journey Analytics à partir d’un produit d’analyse tiers."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Utilisez les informations de cette page pour répondre aux questions de la liste de contrôle de mise à niveau de [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Le processus recommandé de mise à niveau d’une solution d’analyse tierce vers Customer Journey Analytics est une nouvelle implémentation d’Experience Platform Web SDK, qui est la méthode de collecte de données préférée pour Customer Journey Analytics. En conjonction avec le Web SDK, Adobe recommande également d’ingérer des données historiques provenant de la solution d’analyse tierce dans Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Procédez comme suit lorsque vous passez à Customer Journey Analytics à partir d’une solution d’analyse tierce, telle que Google Analytics :

1. ...


Contactez votre représentant ou représentante Adobe si vous avez besoin d’assistance ou de conseils plus précis.

| Solution d’analyse existante | Description | Chemins de mise à niveau disponibles |
|---------|----------|----------|
| AppMeasurement | AppMeasurement pour JavaScript est une méthode courante depuis toujours pour implémenter Adobe Analytics.<p>Pour plus d’informations sur ce type d’implémentation, voir [ Implémentation d’Adobe Analytics avec AppMeasurement for JavaScript ](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Recommandé) Nouvelle implémentation d’Experience Platform Web SDK pour la collecte de données en cours ; connecteur Source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle implémentation d’Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrer Adobe Analytics vers le SDK web</li><li>[ Connecteur Source Analytics ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Extension Adobe Analytics (balises) | <p>Les balises dans Adobe Experience Platform représentent une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site.</p><p>Pour plus d’informations sur ce type d’implémentation, voir [ Implémentation d’Adobe Analytics à l’aide de l’extension Analytics ](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Recommandé) Nouvelle implémentation d’Experience Platform Web SDK pour la collecte de données en cours ; connecteur Source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle implémentation d’Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrer Adobe Analytics vers le SDK web</li><li>[ Connecteur Source Analytics ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK est la méthode actuellement recommandée par Adobe pour implémenter Adobe Analytics. Adobe Experience Platform Edge Network vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. <p>Pour plus d’informations sur ce type d’implémentation, voir [ Implémentation d’Adobe Analytics avec Adobe Experience Platform Edge Network ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Recommandé) Nouvelle implémentation d’Experience Platform Web SDK pour la collecte de données en cours ; connecteur Source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle implémentation d’Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configurez l’implémentation d’Adobe Analytics Web SDK pour envoyer des données à Platform</li></ul> |
| Extension Experience Platform Web SDK (balises) | Experience Platform Web SDK est la méthode actuellement recommandée par Adobe pour implémenter Adobe Analytics pour les données web. Adobe Experience Platform Edge Network vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. <p>Pour plus d’informations sur ce type d’implémentation, voir [ Implémentation d’Adobe Analytics à l’aide de Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Recommandé) Nouvelle implémentation d’Experience Platform Web SDK pour la collecte de données en cours ; connecteur Source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle implémentation d’Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>Configurez l’implémentation d’Adobe Analytics Web SDK pour envoyer des données à Platform</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK est la méthode actuellement recommandée par Adobe pour implémenter Adobe Analytics pour les données mobiles. Adobe Experience Platform Edge Network vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé.<p>Adobe Experience Platform Mobile SDK permet d’optimiser les solutions et services Experience Cloud d’Adobe dans vos applications mobiles. </p><p>Pour plus d’informations sur ce type d’implémentation, voir [ Implémentation d’Adobe Analytics à l’aide de Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Recommandé) Nouvelle implémentation d’Experience Platform Web SDK pour la collecte de données en cours ; connecteur Source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle implémentation d’Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configurez l’implémentation d’Adobe Analytics Web SDK pour envoyer des données à Platform</li></ul> |
| API Bulk Data Insertion | L’API Bulk Data Insertion (BDIA) est une fonctionnalité d’Adobe Analytics qui vous permet de télécharger des données d’appels serveurs par lots de fichiers, au lieu d’utiliser des bibliothèques côté client telles qu’AppMeasurement. </p><p>Pour plus d’informations sur ce type d’implémentation, voir [API Bulk Data Insertion](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Recommandé) Nouvelle implémentation d’Experience Platform Web SDK pour la collecte de données en cours ; connecteur Source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle implémentation d’Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[API Adobe Experience Platform Edge Network Server et Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}
