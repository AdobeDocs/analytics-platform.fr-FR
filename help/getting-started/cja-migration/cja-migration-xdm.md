---
title: Mappage des données au schéma XDM lors de la migration vers Customer Journey Analytics
description: Découvrez comment mapper des données au schéma XDM lors de la migration vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 86ce60cf-b3c7-43b5-aa18-9e16fa942e54
source-git-commit: 923dfac33fcde368392fe29c6530069cc0d8fb9d
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 4%

---

# Étape 4 : mappage des données au schéma XDM lors de la migration vers Customer Journey Analytics

+++Développez cette section pour voir où les informations de cette page s’inscrivent dans le processus de migration plus vaste. Vérifiez que toutes les étapes de migration précédentes sont terminées.

Avant de poursuivre cette section, assurez-vous d’avoir effectué toutes les tâches de migration précédentes.

Les informations de cette page couvrent l’étape 4, comme indiqué dans le tableau ci-dessous :

| Tâche de migration | Détails |
|---------|----------|
| **Étape 1 : [Prise en main de la migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Découvrez les avantages de la migration vers Adobe Analytics et le processus de migration de base. |
| **Étape 2 : [Choisissez la méthode de migration](/help/getting-started/cja-migration/cja-migration-method.md)** | Différentes méthodes sont disponibles pour la migration vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise. |
| **Étape 3 : [Envoi de données à Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction de la méthode de migration choisie à l’étape 1. |
| <span class="preview">**Étape 4 : [Mappage des données au schéma XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)**</span> | <span class="preview">[Schémas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) sont utilisées dans Adobe Experience Platform pour décrire la structure des données de manière cohérente et réutilisable. En définissant les données de manière cohérente sur l’ensemble des systèmes, il est plus simple de leur donner du sens et donc d’en tirer profit.<p>La plupart des méthodes de migration exigent que vous créiez un nouveau schéma XDM ou que vous mappiez votre schéma Adobe Analytics existant avec XDM à l’aide du mappage de flux de données.</p></span> |
| **Étape 5 : [Conserver les données historiques](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La plupart des entreprises doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour ce faire. |
| **Étape 6 : [Planification de l’intégration des utilisateurs](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Donnez à vos utilisateurs suffisamment de temps (3 à 6 mois) pour se familiariser avec les différences clés d’Analysis Workspace dans Customer Journey Analytics. |
| **Étape 7 : [Port de l’utilisation de l’API de création de rapports](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API de création de rapports du Customer Journey Analytics est au même format, mais utilise un point de terminaison différent. Transférez l’utilisation de l’API de création de rapports d’Adobe Analytics vers l’API de création de rapports du Customer Journey Analytics. |
| **Étape 8 : [Remplacement des flux de données et du Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Choisissez comment utiliser les options d’exportation disponibles dans Customer Journey Analytics pour remplacer les flux de données et les fonctionnalités de Data Warehouse que vous utilisiez dans Adobe Analytics. |
| **Étape 9 : [Migration de projets et de composants](/help/getting-started/cja-migration/cja-migration-projects.md)** | La zone de migration Composant d’Adobe Analytics vous permet de migrer les projets et leurs composants associés d’Adobe Analytics vers Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Le tableau suivant montre les méthodes d’implémentation qui nécessitent que vous mappiez des données au schéma XDM :


| Méthode de migration | Mappage XDM requis ? | Informations supplémentaires |
|---------|----------|---------|
| **Nouvelle mise en oeuvre du SDK Web**<p>Les étapes de base sont les suivantes :</p><ol><li>Création d’un schéma XDM pour votre organisation</li><li>Mise en oeuvre du SDK Web</li><li>Envoyer des données à Platform</li></ol> | Non | Un mappage n’est pas requis, car vous avez déjà [configuration d’un nouveau schéma XDM](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) dans le cadre de la nouvelle mise en oeuvre. |
| **Migration de votre mise en oeuvre Adobe Analytics pour utiliser le SDK Web**<p>Les étapes de base sont les suivantes :</p><ol><li>Déplacez votre mise en oeuvre Adobe Analytics existante vers le SDK Web et validez que tout fonctionne là-bas.</li><li>Créez un schéma XDM pour votre entreprise à mesure que vous en aurez le temps.</li><li>Utilisez le mappage de flux de données pour mapper tous les champs de l’objet de données à votre schéma XDM.</li><li>Envoyer des données à Platform</li></ol> | Oui | Collaborez avec votre équipe de données, identifiez la conception de schéma idéale de votre entreprise pour Customer Journey Analytics, puis déterminez la manière dont vous mapperez les eVars et les props à XDM.</br>[Utilisez Data Prep pour mapper tous les champs de l’objet de données à votre schéma XDM.](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Configuration de votre mise en oeuvre SDK Web Adobe Analytics existante pour envoyer des données à Customer Journey Analytics**<p>Les étapes de base sont les suivantes :</p><ol><li>Commencez à envoyer des données à Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Facultatif) Créez un schéma XDM pour votre entreprise à mesure que vous en aurez le temps.</li><li>Utilisez le mappage de flux de données pour mapper tous les champs de l’objet de données à votre schéma XDM.</li></ol> | Oui | Collaborez avec votre équipe de données, identifiez la conception de schéma idéale de votre entreprise pour Customer Journey Analytics, puis déterminez la manière dont vous mapperez les eVars et les props à XDM.</br>[Utilisez Data Prep pour mapper tous les champs de l’objet de données à votre schéma XDM.](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Connecteur source Analytics**</br> Si votre mise en oeuvre Adobe Analytics est AppMeasurement ou l’extension Analytics, vous pouvez commencer à envoyer des données vers une vue de données dans Customer Journey Analytics.<p>Il s’agit de la méthode la plus simple pour obtenir des données vers Customer Journey Analytics, mais elle est la méthode la moins viable à long terme.</p> | Non | Un mappage n’est pas nécessaire, car Analytics Source Connector utilise votre schéma Adobe Analytics existant plutôt que le schéma XDM. |

{style="table-layout:auto"}

<!-- Does it benefit the customer to do this all at the same time if they're using multiple AEP apps? If so, have multiple sections like this. Or can they do CJA first and AJO later?

### Plan data mapping for Customer Journey Analytics


### Plan data mapping for Customer Journey analytics and other Adobe Experience platform applications

-->

## Ensuite, conservez les données historiques

Sélectionnez ensuite la méthode à utiliser pour [conserver les données Adobe Analytics historiques ;](/help/getting-started/cja-migration/cja-migration-historical-data.md).
