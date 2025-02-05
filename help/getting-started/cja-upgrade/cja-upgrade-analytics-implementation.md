---
title: Découvrez votre implémentation Adobe Analytics et comment elle affecte votre mise à niveau vers Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: a462bdbff59e8d83d6948ef882e66690624c4847
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 11%

---

# Découvrez votre implémentation Adobe Analytics et comment elle affecte votre mise à niveau vers Customer Journey Analytics {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement (fichier JS manuel)"
>abstract="Implémentation de JavaScript qui charge AppMeasurement.js sur une page et envoie des données à Adobe à l’aide de l’objet s (par exemple, s.eVar 1)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Extension Adobe Analytics (balises)"
>abstract="Implémentation de balises qui charge la collecte de données Adobe Experience Platform (anciennement appelée Launch). L’extension Adobe Analytics est installée sur la balise."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="Web SDK (alloy.js)"
>abstract="Implémentation de JavaScript qui charge la bibliothèque SDK Web (alloy.js) sur une page et envoie des données à l’Adobe à l’aide d’une payload JSON."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Extension Web SDK (balises)"
>abstract="Implémentation de balises qui charge la collecte de données Adobe Experience Platform (anciennement appelée Launch). L’extension Web SDK est installée sur la balise."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="API dʼinsertion des données"
>abstract="Une implémentation qui utilise l’API d’insertion de données ou l’API d’insertion de données en bloc."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="SDK mobile"
>abstract="Implémentation qui utilise Adobe Experience Platform Mobile SDK."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="Implémentation inconnue"
>abstract="Si vous n’êtes pas la personne qui gère votre implémentation, vous pouvez temporairement sélectionner cette option."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Utilisez les informations de cette page pour répondre aux questions de la liste de contrôle de mise à niveau du Customer Journey Analytics [](https://gigazelle.github.io/cja-ttv/).

Adobe Analytics peut être implémenté de différentes manières. Lors de la mise à niveau vers Customer Journey Analytics, tous les chemins de mise à niveau ne sont pas disponibles pour toutes les implémentations d’Adobe Analytics. Cependant, le chemin de mise à niveau recommandé est disponible quelle que soit la manière dont Adobe Analytics est implémenté dans votre organisation.

Utilisez les informations ci-dessous pour en savoir plus sur votre implémentation Adobe Analytics actuelle et sur les chemins de mise à niveau disponibles pour votre organisation.

Contactez votre représentant ou représentante Adobe si vous avez besoin d’assistance ou de conseils plus précis.

| Implémentation existante dʼAdobe Analytics | Description | Chemins de mise à niveau disponibles |
|---------|----------|----------|
| AppMeasurement | L’AppMeasurement pour JavaScript a toujours été une méthode courante pour mettre en œuvre Adobe Analytics.<p>Pour plus d’informations sur ce type d’implémentation, voir [ Implémentation d’Adobe Analytics avec AppMeasurement for JavaScript ](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Recommandé) Nouvelle mise en œuvre du SDK Web Experience Platform pour la collecte de données en cours ; connecteur Source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle mise en œuvre du SDK Web Experience Platform ](/help/data-ingestion/aepwebsdk.md) </li><li>Migrer Adobe Analytics vers le SDK web</li><li>[ Connecteur Source Analytics ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Extension Adobe Analytics (balises) | <p>Les balises dans Adobe Experience Platform représentent une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site.</p><p>Pour plus d’informations sur ce type d’implémentation, voir [ Implémentation d’Adobe Analytics à l’aide de l’extension Analytics ](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Recommandé) Nouvelle mise en œuvre du SDK Web Experience Platform pour la collecte de données en cours ; connecteur Source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle mise en œuvre du SDK Web Experience Platform ](/help/data-ingestion/aepwebsdk.md) </li><li>Migrer Adobe Analytics vers le SDK web</li><li>[ Connecteur Source Analytics ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| SDK Web Experience Platform (alloy.js) | Le SDK Web Experience Platform est la méthode actuellement recommandée par Adobe pour implémenter Adobe Analytics. L’Edge Network Adobe Experience Platform vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. <p>Pour plus d’informations sur ce type d’implémentation, voir [Implémentation d’Adobe Analytics avec Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Recommandé) Nouvelle mise en œuvre du SDK Web Experience Platform pour la collecte de données en cours ; connecteur Source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle mise en œuvre du SDK Web Experience Platform ](/help/data-ingestion/aepwebsdk.md) </li><li>Configurez l’implémentation d’Adobe Analytics Web SDK pour envoyer des données à Platform</li></ul> |
| Extension Experience Platform Web SDK (balises) | Le SDK Web Experience Platform est la méthode actuellement recommandée par Adobe pour implémenter Adobe Analytics pour les données web. L’Edge Network Adobe Experience Platform vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. <p>Pour plus d’informations sur ce type d’implémentation, voir [ Implémentation d’Adobe Analytics à l’aide de Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Recommandé) Nouvelle mise en œuvre du SDK Web Experience Platform pour la collecte de données en cours ; connecteur Source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle mise en œuvre du SDK Web Experience Platform ](/help/data-ingestion/aepwebsdk.md)</li><li>Configurez l’implémentation d’Adobe Analytics Web SDK pour envoyer des données à Platform</li></ul> |
| Experience Platform Mobile SDK | Le SDK mobile Experience Platform est la méthode actuellement recommandée par Adobe pour implémenter Adobe Analytics pour les données mobiles. L’Edge Network Adobe Experience Platform vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé.<p>Adobe Experience Platform Mobile SDK permet d’optimiser les solutions et services Experience Cloud d’Adobe dans vos applications mobiles. </p><p>Pour plus d’informations sur ce type d’implémentation, voir [ Implémentation d’Adobe Analytics à l’aide de Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Recommandé) Nouvelle mise en œuvre du SDK Web Experience Platform pour la collecte de données en cours ; connecteur Source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle mise en œuvre du SDK Web Experience Platform ](/help/data-ingestion/aepwebsdk.md) </li><li>Configurez l’implémentation d’Adobe Analytics Web SDK pour envoyer des données à Platform</li></ul> |
| API Bulk Data Insertion | L’API Bulk Data Insertion (BDIA) est une fonctionnalité d’Adobe Analytics qui vous permet de télécharger des données d’appels serveurs par lots de fichiers, au lieu d’utiliser des bibliothèques côté client telles que AppMeasurement. </p><p>Pour plus d’informations sur ce type d’implémentation, voir [API Bulk Data Insertion](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Recommandé) Nouvelle mise en œuvre du SDK Web Experience Platform pour la collecte de données en cours ; connecteur Source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle mise en œuvre du SDK Web Experience Platform ](/help/data-ingestion/aepwebsdk.md)</li><li>[API et Edge Network du serveur Adobe Experience Platform Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}
