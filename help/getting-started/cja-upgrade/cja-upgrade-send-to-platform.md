---
title: Envoyer des données à Adobe Experience Platform lors de la migration vers Customer Journey Analytics
description: Envoyer des données à Adobe Experience Platform lors de la migration vers Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 97d48d88af969705f2664781e7a972f20c1b4239
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 64%

---

# Étape 3 : envoyer des données à Adobe Experience Platform lors de la mise à niveau

+++Développez cette section pour voir où les informations de cette page s’inscrivent dans le processus de mise à niveau plus large. Assurez-vous que toutes les étapes de mise à niveau précédentes sont terminées.

Avant de poursuivre avec cette section, assurez-vous d’abord d’avoir terminé toutes les tâches de mise à niveau précédentes.

Les informations de cette page couvrent l’étape 3 du processus de mise à niveau, comme indiqué dans le tableau ci-dessous :

| Mettre à niveau la tâche | Détails |
|---------|----------|
| **Étape 1 : [Prise en main de la mise à niveau](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Découvrez les avantages de la mise à niveau vers Customer Journey Analytics et le processus de mise à niveau de base. |
| **Étape 2 : [Choisissez le chemin de mise à niveau](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Différentes méthodes sont disponibles pour effectuer la mise à niveau vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise. |
| <span class="preview">**Étape 3 : envoyer les données à Adobe Experience Platform**</span> | <span class="preview">Le processus d’envoi de données à Adobe Experience Platform diffère selon le chemin de mise à niveau choisi à l’étape 2.</span> |
| **Étape 4 : [conserver les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La plupart des organisations doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour cela. |
| **Étape 5 : [exécuter des tâches d’implémentation supplémentaires](/help/getting-started/cja-getting-started.md)** | À ce stade du processus de mise à niveau, vous devez effectuer diverses tâches avant que votre environnement Customer Journey Analytics ne soit prêt à l’emploi.<p>Ces tâches supplémentaires s’appliquent aux mises à niveau d’Adobe Analytics ainsi qu’aux nouvelles implémentations de Customer Journey Analytics.</p><p>Ces tâches comprennent les éléments suivants :</p><ul><li>Importer d’autres données dans Experience Platform</li><li>Créer des connexions entre les jeux de données Platform et Customer Journey Analytics</li><li>Créer des vues de données</li><li>Porter l’utilisation de l’API de création de rapports</li><li>Prendre en compte les flux de données et Data Warehouse</li><li>Migrer des projets et des composants</li><li>Planifier l’intégration des utilisateurs et utilisatrices</li></ul> <p>Pour plus d’informations, voir [Commencer avec Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

<!--

>[!AVAILABILITY]
>
>The information on this page is being replaced with the following more comprehensive upgrade information: <ul><li>**Recommended upgrade steps**<p>For detailed information, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics Upgrade Guide**<p>A new upgrade guide is available that dynamically generates upgrade steps that are tailored for your organization and your unique circumstances.</p><p>To access the guide from Customer Journey Analytics, select the **[!UICONTROL Workspace]** tab, then select **[!UICONTROL Upgrade to Customer Journey Analytics]** in the left panel. Follow the on-screen instructions.</p></li></ul>

-->

Après avoir [choisi le chemin de mise à niveau](/help/getting-started/cja-upgrade/cja-upgrade-path.md) qui convient le mieux à votre organisation, vous pouvez commencer à envoyer des données à Adobe Experience Platform afin de les rendre disponibles dans Customer Journey Analytics.

Le processus d’envoi de données à Experience Platform pour chaque chemin de mise à niveau est illustré ci-dessous. Suivez les liens du tableau pour obtenir des informations de configuration détaillées.

| Chemin de mise à niveau | Processus d’envoi de données à Platform | Informations supplémentaires |
|---------|----------|----------|
| Nouvelle implémentation du SDK web Experience Platform | <ol><li>Créez un schéma XDM pour votre organisation.<p>Travaillez avec votre équipe de données pour identifier la conception de schéma idéale de votre organisation avec Customer Journey Analytics.</p></li><li>Implémentez le SDK web d’Experience Platform.</li><li>Envoyez des données à Platform.</li></ol><p>Pour plus d’informations sur chacune de ces étapes, voir [Ingérer des données via le SDK web d’Adobe Experience Platform](/help/data-ingestion/aepwebsdk.md). | Puisqu’il s’agit d’une nouvelle implémentation du SDK web d’Experience Platform, le mappage de schéma n’est pas nécessaire, puisque le schéma doit être créé dans l’une des premières étapes de l’implémentation. |
| Migrer votre implémentation Adobe Analytics pour utiliser le SDK web | <ol><li>Déplacez votre implémentation Adobe Analytics existante vers le SDK web d’Experience Platform, puis vérifiez que tout fonctionne dans Adobe Analytics.<p>Pour plus d’informations sur la procédure à suivre, utilisez les ressources suivantes, selon que votre implémentation actuelle est l’extension des balises Analytics ou AppMeasurement :</p><ul><li>Si vous utilisez l’extension des balises Analytics, voir [Migrer depuis l’extension des balises Adobe Analytics vers l’extension des balises du SDK web](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk).</li><li>Si vous utilisez AppMeasurement, voir [Migrer depuis AppMeasurement vers le SDK web](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk).</li></ul><li>[Créez un schéma XDM pour votre organisation](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Travaillez avec votre équipe de données pour identifier la conception de schéma idéale de votre organisation avec Customer Journey Analytics.</p></li><li>[Utilisez la Préparation des données pour mapper tous les champs de l’objet de données à votre schéma XDM.](https://experienceleague.adobe.com/fr/docs/experience-platform/data-prep/home).</li><li>Commencez à envoyer des données à Platform en [configurant un flux de données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Configurez votre implémentation Adobe Analytics Web SDK existante pour envoyer des données à Platform | <ol><li>Commencez à envoyer des données à Platform en [configurant un train de données](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream).<p>Comme votre implémentation Adobe Analytics utilise déjà le SDK web d’Experience Platform, vous pouvez ignorer les autres sections dans [Ingérer des données via le SDK web d’Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</p><p>Si vous envoyez déjà des données à Platform avec votre implémentation Adobe Analytics, cette étape n’est pas obligatoire. Il vous suffit de créer une connexion entre les jeux de données Platform et Customer Journey Analytics, comme décrit plus loin dans ce processus.</p></li><li>(Facultatif) [Créez un schéma XDM pour votre organisation](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Travaillez avec votre équipe de données pour identifier la conception de schéma idéale de votre organisation avec Customer Journey Analytics.</p><p>Note : pour plus d’informations sur les avantages de la création d’un schéma XDM, voir [Choisir votre schéma](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).</li><li>(Le cas échéant) Si vous avez créé un schéma XDM, vous pouvez [utiliser la Préparation des données pour mapper tous les champs de l’objet de données à votre schéma XDM](https://experienceleague.adobe.com/fr/docs/experience-platform/data-prep/home).</li></ol> |  |
| Utilisation du connecteur source Analytics | [Ingérer et utiliser des données à partir d’Adobe Analytics classique](/help/data-ingestion/analytics.md) | Les données Adobe Analytics sont automatiquement mappées au schéma XDM lorsque vous utilisez le connecteur source Analytics. Aucun mappage supplémentaire n’est requis. |

## Ensuite, conservez les données historiques.

Puis déterminez comment vous allez [conserver les données Adobe Analytics historiques](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md).
