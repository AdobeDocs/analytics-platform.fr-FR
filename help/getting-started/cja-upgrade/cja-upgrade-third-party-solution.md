---
title: Mettre à niveau une solution d’analyse tierce vers Customer Journey Analytics
description: Découvrir comment mettre à niveau une solution d’analyse tierce vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '238'
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

