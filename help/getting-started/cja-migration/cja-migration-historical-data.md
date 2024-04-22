---
title: Conserver les données historiques lors de la migration vers Customer Journey Analytics
description: Découvrez comment conserver les données historiques lors de la migration vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 2%

---

# Étape 5 : conservation des données historiques lors de la migration vers Customer Journey Analytics

+++Les informations de cette page font partie d’un processus de migration plus vaste. Développez cette section pour voir où ces informations s’inscrivent dans le processus de migration. </br></br>Vous devez effectuer toutes les étapes de migration précédentes avant de continuer avec les informations de cette page.

Avant de poursuivre cette section, assurez-vous d’avoir effectué toutes les tâches de migration précédentes.

Les informations de cette page couvrent l’étape 5, comme indiqué dans le tableau ci-dessous :

| Tâche de migration | Détails |
|---------|----------|
| **Étape 1 : [Prise en main de la migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Découvrez les avantages de la migration vers Adobe Analytics et le processus de migration de base. |
| **Étape 2 : [Choisissez la méthode de migration](/help/getting-started/cja-migration/cja-migration-method.md)** | Différentes méthodes sont disponibles pour la migration vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise. |
| **Étape 3 : [Envoi de données à Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction de la méthode de migration choisie à l’étape 1. |
| **Étape 4 : [Planification du mappage des données au schéma XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Schémas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) sont utilisées dans Adobe Experience Platform pour décrire la structure des données de manière cohérente et réutilisable. En définissant les données de manière cohérente sur l’ensemble des systèmes, il est plus simple de leur donner du sens et donc d’en tirer profit.<p>La plupart des méthodes de migration exigent que vous créiez un nouveau schéma XDM ou que vous mappiez votre schéma Adobe Analytics existant avec XDM à l’aide du mappage de flux de données.</p> |
| <span class="preview">**Étape 5 : [Conserver les données historiques](/help/getting-started/cja-migration/cja-migration-historical-data.md)**</span> | <span class="preview">La plupart des entreprises doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour ce faire.</span> |
| **Étape 6 : [Planification de l’intégration des utilisateurs](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Donnez à vos utilisateurs suffisamment de temps (3 à 6 mois) pour se familiariser avec les différences clés d’Analysis Workspace dans Customer Journey Analytics. |
| **Étape 7 : [Port de l’utilisation de l’API de création de rapports](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API de création de rapports du Customer Journey Analytics est au même format, mais utilise un point de terminaison différent. Transférez l’utilisation de l’API de création de rapports d’Adobe Analytics vers l’API de création de rapports du Customer Journey Analytics. |
| **Étape 8 : [Remplacement des flux de données et du Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Choisissez comment utiliser les options d’exportation disponibles dans Customer Journey Analytics pour remplacer les flux de données et les fonctionnalités de Data Warehouse que vous utilisiez dans Adobe Analytics. |
| **Étape 9 : [Migration de projets et de composants](/help/getting-started/cja-migration/cja-migration-projects.md)** | La zone de migration Composant d’Adobe Analytics vous permet de migrer les projets et leurs composants associés d’Adobe Analytics vers Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Choisissez l’une des options suivantes pour conserver les données historiques lors du passage d’Adobe Analytics à Customer Journey Analytics :

## Utilisation du connecteur source Analytics

Vous pouvez utiliser la variable [Connecteur source Analytics](/help/data-ingestion/analytics.md) pour conserver les données historiques. Quelle que soit la méthode de migration choisie (même si vous migrez à l’aide du SDK Web), vous pouvez utiliser Analytics Source Connector pour conserver les données historiques de votre environnement Adobe Analytics.

Vous pouvez utiliser Analytics Source Connector pour conserver les données historiques de la manière suivante :

* Insérez les données historiques dans leur propre emplacement dédié, en les séparant de vos données actives.

* Mappez les données historiques de manière à les lier à vos nouvelles données. <!-- Possible? Explain -->

## Conserver votre implémentation Adobe Analytics existante

Vous pouvez conserver votre mise en oeuvre Adobe Analytics existante avec votre nouvelle mise en oeuvre de Customer Journey Analytics pour une période spécifique (par exemple, 1 an). Lorsque vous choisissez cette option, vous devez prévoir de désactiver la mise en oeuvre d’Adobe Analytics une fois que vous disposez de suffisamment de données dans Customer Journey Analytics.

Contactez votre représentant du compte d’Adobe pour déterminer le prix de cette option.

## Ensuite, planifiez l’intégration des utilisateurs

[Planification de l’intégration des utilisateurs à Customer Journey Analytics](/help/getting-started/cja-migration/cja-migration-onboarding.md). Donnez à vos utilisateurs suffisamment de temps (3 à 6 mois) pour se familiariser avec les différences clés d’Analysis Workspace dans Customer Journey Analytics.
