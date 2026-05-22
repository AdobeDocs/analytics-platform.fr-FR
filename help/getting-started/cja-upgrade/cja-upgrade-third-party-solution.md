---
title: Mettre à niveau une solution d’analyse tierce vers Customer Journey Analytics
description: Découvrir comment mettre à niveau une solution d’analyse tierce vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
autotag-review: '2026-05-19T08:20:34.368Z'
TQID: 'https://experienceleague.adobe.com/fwYoa9oeIs2tujyDEWUj-GaAgpZQNBwup-YsHIe-TdU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 261
ht-degree: 100%

---

# Mettre à niveau une solution d’analyse tierce vers Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Un produit autre que Adobe Analytics"
>abstract="Implémentation qui collecte des données pour un produit autre que Adobe Analytics, tel que Google Analytics. La sélection de cette option désactive plusieurs options du guide de mise à niveau qui ne s’appliquent pas lors de la mise à niveau vers Customer Journey Analytics à partir d’un produit autre que Adobe Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Le processus recommandé de mise à niveau à partir d’une solution d’analyse autre qu’Adobe Analytics vers Customer Journey Analytics consiste à implémenter le SDK web Experience Platform, qui est la méthode de collecte de données privilégiée dans Customer Journey Analytics. En conjonction avec le SDK web, Adobe recommande également d’ingérer des données historiques provenant de la solution d’analyse tierce dans Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Procédez comme suit lorsque vous passez à Customer Journey Analytics à partir d’une solution d’analyse tierce, telle que Google Analytics :

1. Suivez les [étapes recommandées de mise à niveau détaillées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   Ces étapes sont destinées aux organisations qui effectuent une mise à niveau à partir d’Adobe Analytics. Avant de suivre ces étapes, tenez compte des points suivants :

   * Vous devez créer un train de données.

   * Vous ne pouvez pas migrer des projets et des composants à partir d’une solution autre qu’Adobe Analytics.

   * Selon votre solution d’analyse, un connecteur source peut être disponible pour ingérer des données historiques. Pour plus d’informations, consultez [Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/home#analytics) dans la [vue d’ensemble des connecteurs source](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/home) de la documentation d’Experience Platform.


Contactez votre représentant ou représentante Adobe si vous avez besoin d’assistance ou de conseils plus précis.

