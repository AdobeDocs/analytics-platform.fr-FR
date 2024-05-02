---
title: Envoi de données à Adobe Experience Platform lors de la migration vers Customer Journey Analytics
description: Envoi de données à Adobe Experience Platform lors de la migration vers Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 1%

---

# Étape 3 : envoi de données à Adobe Experience Platform lors de la mise à niveau

+++Développez cette section pour voir où les informations de cette page s’inscrivent dans le processus de mise à niveau plus vaste. Vérifiez que toutes les étapes de mise à niveau précédentes sont terminées.

Avant de poursuivre cette section, assurez-vous d’avoir effectué toutes les tâches de mise à niveau précédentes.

Les informations de cette page couvrent l’étape 3 du processus de mise à niveau, comme indiqué dans le tableau ci-dessous :

| Tâche de mise à niveau | Détails |
|---------|----------|
| **Étape 1 : [Prise en main de la mise à niveau](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Découvrez les avantages de la mise à niveau vers Customer Journey Analytics et le processus de mise à niveau de base. |
| **Étape 2 : [Choix du chemin de mise à niveau](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Plusieurs méthodes sont disponibles pour la mise à niveau vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise. |
| <span class="preview">**Étape 3 : envoi de données à Adobe Experience Platform**</span> | <span class="preview">Le processus d’envoi de données à Adobe Experience Platform varie en fonction du chemin de mise à niveau que vous avez choisi à l’étape 2.</span> |
| **Étape 4 : [Conserver les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La plupart des entreprises doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour ce faire. |
| **Étape 5 : [Exécution de tâches de mise en oeuvre supplémentaires](/help/getting-started/cja-getting-started.md)** | À ce stade du processus de mise à niveau, vous devez effectuer diverses tâches avant que votre environnement de Customer Journey Analytics ne soit prêt à l’emploi.<p>Ces tâches supplémentaires s’appliquent aux mises à niveau d’Adobe Analytics ainsi qu’aux nouvelles mises en oeuvre de Customer Journey Analytics.</p><p>Ces tâches incluent :</p><ul><li>Importation d’autres données dans Experience Platform</li><li>Création de connexions entre les jeux de données Platform et Customer Journey Analytics</li><li>Création de vues de données</li><li>Portage de l’utilisation de l’API de création de rapports</li><li>Prise en compte des flux de données et du Data Warehouse</li><li>Migration de projets et de composants</li><li>Planification de l’intégration des utilisateurs</li></ul> <p>Pour plus d’informations, voir [Prise en main du Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++


Après vous [choisissez le chemin de mise à niveau](/help/getting-started/cja-upgrade/cja-upgrade-path.md) , ce qui est préférable pour votre entreprise, vous pouvez commencer à envoyer des données à Adobe Experience Platform afin de les rendre disponibles dans Customer Journey Analytics.

Le processus d’envoi de données à l’Experience Platform pour chaque chemin de mise à niveau est illustré ci-dessous. Suivez les liens du tableau pour obtenir des informations de configuration détaillées.

| Chemin de mise à niveau | Processus d’envoi de données à Platform | Informations supplémentaires |
|---------|----------|----------|
| Nouvelle mise en oeuvre du SDK Web Experience Platform | <ol><li>Créez un schéma XDM pour votre organisation.<p>Contactez votre équipe de données pour identifier la conception de schéma idéale de votre entreprise pour Customer Journey Analytics.</p></li><li>Mettez en oeuvre le SDK Web Experience Platform.</li><li>Envoyez des données à Platform.</li></ol><p>Pour plus d’informations sur chacune de ces étapes, voir [Ingestion de données via le SDK Web de Adobe Experience Platform](/help/data-ingestion/aepwebsdk.md). | Puisqu’il s’agit d’une nouvelle implémentation du SDK Web Experience Platform, le mappage de schéma n’est pas nécessaire, car vous devez créer le schéma comme l’une des premières étapes de l’implémentation. |
| Migration de votre mise en oeuvre Adobe Analytics pour utiliser le SDK Web | <ol><li>Déplacez votre mise en oeuvre Adobe Analytics existante vers le SDK Web Experience Platform, puis validez que tout fonctionne dans Adobe Analytics.<p>Pour plus d’informations sur la procédure à suivre, utilisez les ressources suivantes, selon que votre mise en oeuvre actuelle est l’extension ou l’AppMeasurement de balises Analytics :</p><ul><li>Si vous utilisez l’extension de balise Analytics, voir [Migration de l’extension de balise Adobe Analytics vers l’extension de balise SDK Web](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>Si vous utilisez AppMeasurement, voir [Migration d’AppMeasurement vers le SDK Web](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Création d’un schéma XDM pour votre organisation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Contactez votre équipe de données pour identifier la conception de schéma idéale de votre entreprise pour Customer Journey Analytics.</p></li><li>[Utilisez Data Prep pour mapper tous les champs de l’objet de données à votre schéma XDM.](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li><li>Commencez à envoyer des données à Platform en [configuration d’un flux de données](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Configuration de votre mise en oeuvre SDK Web Adobe Analytics existante pour envoyer des données à Customer Journey Analytics | <ol><li>Commencez à envoyer des données à Platform en [configuration d’un flux de données](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).<p>Comme votre mise en oeuvre Adobe Analytics utilise déjà le SDK Web Experience Platform, vous pouvez ignorer les autres sections de la section [Ingestion de données via le SDK Web de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</li><li>(Facultatif) [Création d’un schéma XDM pour votre organisation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Contactez votre équipe de données pour identifier la conception de schéma idéale de votre entreprise pour Customer Journey Analytics.</p><p>Remarque : Pour plus d’informations sur les avantages de la création d’un schéma XDM, voir [Choix du schéma](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).</li><li>(Conditionnel) Si vous avez créé un schéma XDM, [Utilisez la préparation de données pour mapper tous les champs de l’objet de données à votre schéma XDM.](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li></ol> |
| Utilisation du connecteur source Analytics | [Ingérer et utiliser des données à partir d’Adobe Analytics classique](/help/data-ingestion/analytics.md) | Les données Adobe Analytics sont automatiquement mappées au schéma XDM lorsque vous utilisez Analytics Source Connector. Aucun mappage supplémentaire n’est requis. |

## Ensuite, conservez les données historiques

Ensuite, déterminez comment vous allez [conserver les données Adobe Analytics historiques ;](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md).
