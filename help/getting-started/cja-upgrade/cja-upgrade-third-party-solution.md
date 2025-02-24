---
title: Mettre à niveau une solution d’analyse tierce vers Customer Journey Analytics
description: Découvrez comment mettre à niveau une solution d’analyse tierce vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: d2d945724e7972bd4a29fa13291577bb76288229
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 14%

---

# Mettre à niveau une solution d’analyse tierce vers Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Un produit autre qu’Adobe Analytics"
>abstract="Implémentation qui collecte des données pour un produit autre qu’Adobe Analytics, tel que Google Analytics. La sélection de cette option désactive plusieurs options du questionnaire qui ne s’appliquent pas lors de la mise à niveau vers Customer Journey Analytics à partir d’un produit non-Adobe Analytics."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Utilisez les informations de cette page pour répondre aux questions de la liste de contrôle de mise à niveau de [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Le processus recommandé de mise à niveau d’une solution d’analyse autre qu’Adobe Analytics vers Customer Journey Analytics est une nouvelle implémentation d’Experience Platform Web SDK, qui est la méthode de collecte de données préférée pour Customer Journey Analytics. En conjonction avec le Web SDK, Adobe recommande également d’ingérer des données historiques provenant de la solution d’analyse tierce dans Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Procédez comme suit lorsque vous passez à Customer Journey Analytics à partir d’une solution d’analyse tierce, telle que Google Analytics :

1. Suivez les [étapes de mise à niveau recommandées détaillées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   Ces étapes sont destinées aux organisations qui effectuent une mise à niveau à partir d’Adobe Analytics. Lorsque vous suivez ces étapes, comprenez les points suivants :

   * Vous devez créer un flux de données.

   * Vous ne pouvez pas migrer des projets et des composants à partir d’une solution non Adobe Analytics.

   * Selon votre solution d’analyse, un connecteur source peut être disponible pour ingérer des données historiques. Pour plus d’informations, consultez [Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#analytics) dans la présentation des connecteurs Source [](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home) dans la documentation d’Experience Platform.


Contactez votre représentant ou représentante Adobe si vous avez besoin d’assistance ou de conseils plus précis.

