---
title: Domaines utilisés par Customer Journey Analytics
description: Si le pare-feu de votre entreprise bloque les adresses IP qui proviennent d’Adobe, utilisez cette liste pour mettre à jour les paramètres du pare-feu.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
autotag-review: '2026-05-19T09:27:11.172Z'
TQID: 'https://experienceleague.adobe.com/y3FgZsfqtozN8IaJlBvmfybUIH3s7fiiw2Rc4iNLyGI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 163
ht-degree: 16%

---

# Domaines utilisés par Customer Journey Analytics

Certaines configurations de pare-feu bloquent les domaines sur lesquels Customer Journey Analytics s’appuie pour son interface de produit. Vous pouvez utiliser cette liste de domaines pour modifier les paramètres réseau de votre organisation afin d’autoriser l’accès aux produits depuis votre organisation. Adobe recommande d’autoriser ces domaines par le biais du pare-feu de votre entreprise pour une expérience optimale.

| Technologie | Domaine |
| --- | --- |
| Domaines Customer Journey Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| ® Stockage d’objets blob Azure | `awaascicdprodva7.blob.core.windows.net` |
| ® réseau CDN Azure | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Domaines d’entreprise CX

Outre les domaines ci-dessus, CX Enterprise s’appuie sur plusieurs domaines pour la collecte de données et l’exportation de rapports. Voir [Domaines utilisés par CX Enterprise](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains) pour cette liste de domaines.

>[!MORELIKETHIS]
>
>[Adresses IP utilisées par Customer Journey Analytics](ip-addresses.md)
>
>[Domaines utilisés par CX Enterprise](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)
