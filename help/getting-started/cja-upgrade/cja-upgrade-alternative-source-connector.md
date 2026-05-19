---
title: Utiliser exclusivement le connecteur source Analytics pour effectuer la mise à niveau vers Customer Journey Analytics
description: Découvrir comment créer des champs de mappage et du connecteur source Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
autotag-review: '2026-05-19T08:09:45.448Z'
TQID: 'https://experienceleague.adobe.com/KF-XUA12iIq0wGcSc4P-vGXQV56H5j-jKEgRsxLoUrI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 94%

---

# Alternative de mise à niveau : utiliser exclusivement le connecteur source Analytics pour effectuer la mise à niveau vers Customer Journey Analytics {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Utiliser uniquement le connecteur source Analytics"
>abstract="(Non recommandé) Vous pouvez utiliser le connecteur source Analytics comme seul chemin d’implémentation pour Customer Journey Analytics. <br><br>Cette option permet de gagner du temps d’implémentation en envoyant rapidement des données à Customer Journey Analytics. Elle présente toutefois diverses lacunes, telles qu’une latence plus élevée et la difficulté à quitter Adobe Analytics à l’avenir."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Bien que cela ne soit pas recommandé, vous pouvez utiliser le connecteur source Analytics comme seul chemin d’implémentation pour Customer Journey Analytics. Cependant, en raison des inconvénients inhérents à ce type de mise à niveau, Adobe recommande d’utiliser le connecteur source Analytics conjointement avec une nouvelle implémentation du SDK web Experience Platform. Pour plus d’informations sur le chemin de mise à niveau recommandé, consultez [Chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

## Avantages et inconvénients

Utilisez les informations du tableau ci-dessous pour comprendre les avantages et les inconvénients de l’utilisation exclusive du connecteur source lors de la mise à niveau vers Customer Journey Analytics.

| Avantages | Inconvénients |
|----------|---------|
| <ul><li>Chemin de mise à niveau le moins coûteux en temps et le moins exigeant. <p>Les données sont migrées rapidement et facilement vers Customer Journey Analytics.</p></li></ul> | <ul><li>**Les données ne sont pas envoyées à Edge Network** : <p>Les inconvénients sont les suivants :</p><ul><li>Niveau le plus élevé de [latence](/help/technotes/guardrails.md#latencies) dans les rapports de tous les chemins de mise à niveau ; non optimisé pour les cas d’utilisation de personnalisation en temps réel.</li><li>Les données ne peuvent pas être partagées avec d’autres applications Adobe Experience Platform ; elles sont limitées à Customer Journey Analytics uniquement.</li><li>Dépend de la nomenclature Adobe Analytics (prop, eVar, événement, etc.).</li></ul><li>**Difficulté à migrer vers le SDK web à l’avenir** : à terme, vous souhaiterez probablement accéder aux avantages offerts par le SDK web d’Experience Platform. Pour commencer à utiliser le SDK web Experience Platform, vous devez effectuer une nouvelle implémentation.</li><li>**Utilise le groupe de champs Événement d’expérience Analytics dans votre schéma** : ce groupe de champs ajoute de nombreux événements Adobe Analytics inutiles dans votre schéma de Customer Journey Analytics.  Cela peut générer un schéma plus complexe et encombré que ce qui est nécessaire à Customer Journey Analytics.</li><li>**Nécessite des licences pour Adobe Analytics et Customer Journey Analytics** : l’utilisation du connecteur source Analytics nécessite que vous payiez pour Adobe Analytics et Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}

## Étapes de base

Si vous décidez d’utiliser le connecteur source Analytics comme seul chemin d’implémentation pour Customer Journey Analytics, suivez les étapes d’implémentation décrites dans la section [Ingérer et utiliser des données à l’aide des connecteurs source](/help/data-ingestion/sources.md).

