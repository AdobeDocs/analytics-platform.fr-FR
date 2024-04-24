---
title: Remplacement des flux de données et des Data Warehouse lors de la migration vers Customer Journey Analytics
description: Planification de la migration d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 3a99aed3-26b9-494f-aaf9-f8eaa2c2d88f
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 4%

---

# Étape 8 : Remplacement des flux de données et des Data Warehouse lors de la migration vers Customer Journey Analytics

+++Développez cette section pour voir où les informations de cette page s’inscrivent dans le processus de migration plus vaste. Vérifiez que toutes les étapes de migration précédentes sont terminées.

Avant de poursuivre cette section, assurez-vous d’avoir effectué toutes les tâches de migration précédentes.

Les informations de cette page couvrent l’étape 8, comme indiqué dans le tableau ci-dessous :

| Tâche de migration | Détails |
|---------|----------|
| **Étape 1 : [Prise en main de la migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Découvrez les avantages de la migration vers Adobe Analytics et le processus de migration de base. |
| **Étape 2 : [Choix du chemin de migration](/help/getting-started/cja-migration/cja-migration-path.md)** | Différentes méthodes sont disponibles pour la migration vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise. |
| **Étape 3 : [Mappage des données au schéma XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Schémas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) sont utilisées dans Adobe Experience Platform pour décrire la structure des données de manière cohérente et réutilisable. En définissant les données de manière cohérente sur l’ensemble des systèmes, il est plus simple de leur donner du sens et donc d’en tirer profit.<p>La plupart des chemins de migration nécessitent que vous créiez un nouveau schéma XDM ou que vous mappiez votre schéma Adobe Analytics existant avec XDM à l’aide du mappage de flux de données.</p> |
| **Étape 4 : [Envoi de données à Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction du chemin de migration que vous avez choisi à l’étape 2. |
| **Étape 5 : [Conserver les données historiques](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La plupart des entreprises doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour ce faire. |
| **Étape 6 : [Planification de l’intégration des utilisateurs](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Donnez à vos utilisateurs suffisamment de temps (3 à 6 mois) pour se familiariser avec les différences clés d’Analysis Workspace dans Customer Journey Analytics. |
| **Étape 7 : [Port de l’utilisation de l’API de création de rapports](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API de création de rapports du Customer Journey Analytics est au même format, mais utilise un point de terminaison différent. Transférez l’utilisation de l’API de création de rapports d’Adobe Analytics vers l’API de création de rapports du Customer Journey Analytics. |
| <span class="preview">**Étape 8 : [Remplacement des flux de données et du Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)**</span> | <span class="preview">Choisissez comment utiliser les options d’exportation disponibles dans Customer Journey Analytics pour remplacer les flux de données et les fonctionnalités de Data Warehouse que vous utilisiez dans Adobe Analytics.</span> |
| **Étape 9 : [Migration de projets et de composants](/help/getting-started/cja-migration/cja-migration-projects.md)** | La zone de migration Composant d’Adobe Analytics vous permet de migrer les projets et leurs composants associés d’Adobe Analytics vers Customer Journey Analytics. |
| **Étape 10 : [Exécution de tâches post-migration](/help/getting-started/cja-getting-started.md)** | Une fois la migration terminée, vous devez effectuer diverses tâches, notamment importer d’autres données dans Experience Platform, créer des connexions entre les jeux de données Platform et Customer Journey Analytics, créer des vues de données et apprendre à créer des rapports sur les données cross-canal dans Analysis Workspace. |

{style="table-layout:auto"}

+++

Si vous utilisez actuellement des flux de données ou des Data Warehouse dans Adobe Analytics, utilisez le tableau suivant pour en savoir plus sur les différentes options d’exportation disponibles dans Customer Journey Analytics :

| Adobe Analytics | Customer Journey Analytics |
|---------|----------|
| Flux de données | Évaluez les cas d’utilisation de vos flux de données, puis utilisez toute combinaison de méthodes d’exportation alternatives disponibles dans Customer Journey Analytics : <ul><li>Pour exporter des jeux de données bruts, procédez comme suit : [exportation de jeux de données vers des destinations de stockage dans le cloud ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)&#x200B;</li><li>Pour les exportations au niveau de l’audience ou de l’événement utilisant l’ID de personne ou l’horodatage, utilisez [Exportation de tableau complet](/help/analysis-workspace/export/export-cloud.md)&#x200B;</li><li>Pour une intégration directe avec Power BI et Tableau, utilisez la méthode [Extension Customer Journey Analytics BI](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension)&#x200B;</li><li>Pour un accès SQL direct aux données dans Adobe Experience Platform, utilisez la méthode [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/home).</li></ul> |
| Data Warehouse | Modifier les exportations Adobe Analytics Data Warehouse pour utiliser [Exportation de tableau complet](/help/analysis-workspace/export/export-cloud.md) en Customer Journey Analytics.<p>L’exportation de tableau complet Customer Journey Analytics est l’évolution des rapports de Data Warehouse dans Adobe Analytics, avec de nombreuses nouvelles fonctionnalités souvent demandées qui ne sont pas disponibles dans Data Warehouse aujourd’hui.</p> |

{style="table-layout:auto"}

## Ensuite, migrez les projets et les composants.

Utilisez la zone de migration Composant dans Adobe Analytics pour [migration de projets et de leurs composants associés](/help/getting-started/cja-migration/cja-migration-projects.md) d’Adobe Analytics à Customer Journey Analytics.
