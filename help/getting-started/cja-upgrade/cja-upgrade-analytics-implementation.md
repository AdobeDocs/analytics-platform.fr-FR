---
title: Comprendre votre implémentation d’Adobe Analytics et son incidence sur la mise à niveau vers Customer Journey Analytics
description: En savoir plus sur le chemin recommandé lors de la mise à niveau à partir d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '939'
ht-degree: 100%

---

# Comprendre votre implémentation d’Adobe Analytics et son incidence sur la mise à niveau vers Customer Journey Analytics {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement (fichier JS manuel)"
>abstract="Mise en œuvre JavaScript qui charge AppMeasurement.js sur une page et envoie des données à Adobe à l’aide de l’objet s (par exemple, s.eVar1)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Extension Adobe Analytics (Tags)"
>abstract="Mise en œuvre de balises qui charge la collecte de données Adobe Experience Platform (anciennement appelée Launch). L’extension Adobe Analytics est installée sur la balise."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="SDK web (alloy.js)"
>abstract="Mise en œuvre JavaScript qui charge la bibliothèque du SDK web (alloy.js) sur une page et envoie des données à Adobe à l’aide d’une payload JSON."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Extension SDK web (Tags)"
>abstract="Mise en œuvre de balises qui charge la collecte de données Adobe Experience Platform (anciennement appelée Launch). L’extension SDK web est installée sur la balise."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="API dʼinsertion des données"
>abstract="Mise en œuvre qui utilise l’API d’insertion de données ou l’API d’insertion de données en bloc."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="SDK mobile"
>abstract="Mise en œuvre qui utilise le SDK mobile Adobe Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-third-party"
>title="AppMeasurement utilisant un outil de gestion de balises tiers"
>abstract="Implémentation qui utilise un outil de gestion de balises tiers."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="Mise en œuvre inconnue"
>abstract="Si vous n’êtes pas la personne qui gère votre mise en œuvre, vous pouvez temporairement sélectionner cette option."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-determine-implementation"
>title="Déterminer votre type d’implémentation existant"
>abstract="Travaillez en interne au sein de votre organisation pour déterminer le type d’implémentation que vous utilisez actuellement pour envoyer des données à Adobe Analytics. Lorsque vous effectuez une mise à niveau vers Customer Journey Analytics, collaborez avec la personne ou l’équipe qui connaît ces informations.<br><br>Une fois que vous avez déterminé le type d’implémentation utilisé par votre organisation, modifiez votre réponse dans le Guide de mise à niveau de Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics peut être implémenté de différentes manières. Lors de la mise à niveau vers Customer Journey Analytics, tous les chemins de mise à niveau ne sont pas disponibles pour toutes les implémentations d’Adobe Analytics. Cependant, le chemin de mise à niveau recommandé est disponible quelle que soit la manière dont Adobe Analytics est implémenté dans votre organisation.

Utilisez les informations ci-dessous pour en savoir plus sur votre implémentation Adobe Analytics actuelle et sur les chemins de mise à niveau disponibles pour votre organisation.

Contactez votre représentant ou représentante Adobe si vous avez besoin d’assistance ou de conseils plus précis.

| Implémentation existante dʼAdobe Analytics | Description | Chemins de mise à niveau disponibles |
|---------|----------|----------|
| AppMeasurement | AppMeasurement pour JavaScript a toujours été une méthode courante de mise en œuvre d’Adobe Analytics.<p>Pour plus d’informations sur ce type d’implémentation, consultez [Implémentation d’Adobe Analytics avec AppMeasurement for JavaScript](https://experienceleague.adobe.com/fr/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Recommandé) Nouvelle implémentation du SDK web Experience Platform pour la collecte de données en cours, et du connecteur source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle implémentation du SDK web Experience Platform](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrer Adobe Analytics vers le SDK web](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Extension Adobe Analytics (balises) | <p>Les balises dans Adobe Experience Platform représentent une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site.</p><p>Pour plus d’informations sur ce type d’implémentation, consultez [Implémentation d’Adobe Analytics à l’aide de l’extension Analytics](https://experienceleague.adobe.com/fr/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Recommandé) Nouvelle implémentation du SDK web Experience Platform pour la collecte de données en cours ; connecteur source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle implémentation du SDK web Experience Platform](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrer Adobe Analytics vers le SDK web](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| SDK web Experience Platform (alloy.js) | Le SDK web Experience Platform est la méthode actuellement recommandée par Adobe pour implémenter Adobe Analytics. Le réseau Adobe Experience Platform Edge Network vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. <p>Pour plus d’informations sur ce type d’implémentation, consultez [Implémentation d’Adobe Analytics avec Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Recommandé) Nouvelle implémentation du SDK web Experience Platform pour la collecte de données en cours ; connecteur source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle implémentation du SDK web Experience Platform](/help/data-ingestion/aepwebsdk.md) </li><li>[Configurer l’implémentation du SDK web Adobe Analytics pour envoyer des données à Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Extension SDK web Experience Platform (balises) | Le SDK web Experience Platform est la méthode actuellement recommandée par Adobe pour implémenter Adobe Analytics pour les données web. Le réseau Adobe Experience Platform Edge Network vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. <p>Pour plus d’informations sur ce type d’implémentation, voir [Implémentation d’Adobe Analytics à l’aide du SDK web Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Recommandé) Nouvelle implémentation du SDK web Experience Platform pour la collecte de données en cours ; connecteur source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle implémentation du SDK web Experience Platform](/help/data-ingestion/aepwebsdk.md)</li><li>[Configurer l’implémentation du SDK web Adobe Analytics pour envoyer des données à Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| SDK mobile Experience Platform | Le SDK mobile Experience Platform est la méthode actuellement recommandée par Adobe pour implémenter Adobe Analytics pour les données mobiles. Le réseau Adobe Experience Platform Edge Network vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé.<p>Le SDK mobile Adobe Experience Platform permet d’optimiser les solutions et services Experience Cloud d’Adobe dans vos applications mobiles. </p><p>Pour plus d’informations sur ce type d’implémentation, voir [Implémentation d’Adobe Analytics à l’aide du SDK mobile Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Recommandé) Nouvelle implémentation du SDK web Experience Platform pour la collecte de données en cours ; connecteur source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle implémentation du SDK web Experience Platform](/help/data-ingestion/aepwebsdk.md) </li><li>[Configurer l’implémentation du SDK web Adobe Analytics pour envoyer des données à Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| API Bulk Data Insertion | L’API Bulk Data Insertion (BDIA) est une fonctionnalité d’Adobe Analytics qui vous permet de charger des données d’appels serveurs par lots de fichiers, au lieu d’utiliser des bibliothèques côté client telles qu’AppMeasurement. </p><p>Pour plus d’informations sur ce type d’implémentation, consultez [API Bulk Data Insertion](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Recommandé) Nouvelle implémentation du SDK web Experience Platform pour la collecte de données en cours, et du connecteur source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nouvelle implémentation du SDK web Experience Platform](/help/data-ingestion/aepwebsdk.md)</li><li>[API Adobe Experience Platform Edge Network Server et Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}


