---
title: Domaines utilisés par Customer Journey Analytics
description: Si le pare-feu de votre entreprise bloque les adresses IP qui proviennent d’Adobe, utilisez cette liste pour mettre à jour les paramètres du pare-feu.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
source-git-commit: 8ffbca5dd83987a90d7b744d236e0556314000dd
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 20%

---

# Domaines utilisés par Customer Journey Analytics

Certaines configurations de pare-feu bloquent les domaines sur lesquels Customer Journey Analytics s’appuie pour son interface de produit. Vous pouvez utiliser cette liste de domaines pour modifier les paramètres réseau de votre entreprise afin d’autoriser l’accès aux produits au sein de votre entreprise. Adobe recommande d’autoriser ces domaines à travers le pare-feu de votre entreprise pour une expérience optimale.

| Technologie | Domaine |
| --- | --- |
| Domaines Customer Journey Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Stockage Azure Blob de Microsoft® | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft® Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Domaines Adobe Experience Cloud

Outre les domaines ci-dessus, le Adobe Experience Cloud s’appuie sur plusieurs domaines pour la collecte de données et l’exportation de rapports. Voir [Domaines utilisés par Adobe Experience Cloud](https://experienceleague.adobe.com/fr/docs/core-services/interface/data-collection/domains) pour cette liste de domaines.

>[!MORELIKETHIS]
>
>[Adresses IP utilisées par le Customer Journey Analytics](ip-addresses.md)
>
>[Domaines utilisés par Adobe Experience Cloud](https://experienceleague.adobe.com/fr/docs/core-services/interface/data-collection/domains)
