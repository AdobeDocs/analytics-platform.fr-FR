---
title: Configurer une collection de médias en streaming pour Customer Journey Analytics
description: Découvrez comment configurer Streaming Media Collection pour Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b807099d-a61d-48f9-9fec-94ecc6b76213
source-git-commit: 380ed5c9ee0c21ea9855a41728afec040637ce65
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 20%

---

# Configurer une collection de médias en streaming pour Customer Journey Analytics {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Configurer et implémenter Media Edge"
>abstract="Si vous envisagez d’utiliser la collection de médias en streaming avec Customer Journey Analytics, vous devez effectuer des sélections spécifiques à certaines étapes du processus de mise à niveau. Par exemple, vous devez ajouter le groupe de champs Détails des interactions Media Analytics à votre schéma, activer Media Analytics dans le train de données, etc."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Comme dans Adobe Analytics, la collection de médias en flux continu peut être utilisée pour collecter des données de médias en flux continu à utiliser dans Customer Journey Analytics. Si vous utilisez Streaming Media Collection avec Adobe Analytics, vous devez l’inclure dans vos plans de mise à niveau vers Customer Journey Analytics.

Au fur et à mesure que vous passez en revue les étapes de mise à niveau d’Adobe Analytics vers Customer Journey Analytics, effectuez les sélections suivantes pour tenir compte des données de collecte de médias en flux continu :

* Lors de la création du schéma pour Customer Journey Analytics, incluez le groupe de champs `MediaAnalytics Interaction Details`.

  Pour plus d’informations sur l’ajout de ce groupe de champs, voir [Configurer le schéma dans Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) dans le Guide de collecte de médias en flux continu.

  Pour plus d’informations sur la création du schéma, voir [Création d’un schéma personnalisé à utiliser avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* Lors de la configuration du flux de données pour Customer Journey Analytics, activez Media Analytics.

  Pour plus d’informations sur l’activation de cette option, voir [Configurer un flux de données dans Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) dans le Guide de collecte de médias en flux continu.

  Pour plus d’informations sur la création du flux de données, voir [Créer un flux de données à utiliser avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

  >[!NOTE]
  >
  >Si votre mise en œuvre Adobe Analytics utilise déjà Experience Platform Web SDK, cette étape n’est pas nécessaire.

* Lors de la création d’une vue de données pour Customer Journey Analytics, incluez les champs de schéma requis pour la collection de médias en flux continu.

  Veillez à mapper ces champs de schéma aux valeurs correctes dans l’objet XDM.

  Pour plus d’informations sur les champs obligatoires, voir [Création d’une vue de données dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) dans le Guide de collecte de médias en flux continu.

  Pour plus d’informations sur la création de la vue de données, voir [Création d’une vue de données dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

<!--

------------------

The steps for implementing the Streaming Media Collection in Customer Journey Analytics differ depending on your current Streaming Media Collection implementation in Adobe Analytics. 

Streaming Media Collection can be implemented in Adobe Analytics in either of the following ways:

* [Edge Network implementations for the Streaming Media Collection](#edge-network-implementations)

* [Adobe Analytics-only implementations for the Streaming Media Collection](#adobe-analytics-only-implementations)

For more information about the differences between these implementation methods, see [Implement the Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) in the Streaming Media Collection Guide.

## Edge Network implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using the Edge Network in your Adobe Analytics implementation](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods), this means that some steps that are required to upgrade the Streaming Media Collection to Customer Journey Analytics have already been completed as part of your Adobe Analytics implementation. Following are the completed steps:

* [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Create a dataset in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

The following additional steps need to be completed as part of the upgrade to Customer Journey Analytics:

>[!NOTE]
>
>As you complete the Customer Journey Analytics upgrade steps, make sure you use the schema, dataset, and datastream from your Streaming Media Collection implementation in Adobe Analytics.

* [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Adobe Analytics-only implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using an Adobe Analytics-only implementation in your Adobe Analytics environment](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), this means that Streaming Media data is not yet going to Edge Network. 

As you create the schema, dataset, datastream, connection, and data view as part of your upgrade from Adobe Analytics to Customer Journey Analytics, make the following selections to account for Streaming Media Collection data:

* When creating the schema for Customer Journey Analytics, include the `MediaAnalytics Interaction Details` field group.

  For more information about adding this field group, see [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the schema, see [Create a custom schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* When configuring the datastream for Customer Journey Analytics, enable Media Analytics. 

  For more information about enabling this option, see [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the datastream, see [Create a datastream to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* When creating a data view for Customer Journey Analytics, include the required schema fields for the Streaming Media Collection.

  Make sure you map these schema fieldds to the correct values in the XDM object.

  For more information about the required fields, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) in the Streaming Media Collection Guide.

  For information about creating the data view, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

  -->
