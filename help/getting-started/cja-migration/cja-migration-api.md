---
title: Port de l’utilisation de l’API de création de rapports lors de la migration vers Customer Journey Analytics
description: Découvrez comment transférer l’utilisation de l’API d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 3%

---

# Étape 7 : port de l’utilisation de l’API de création de rapports lors de la migration vers Customer Journey Analytics

+++Les informations de cette page font partie d’un processus de migration plus vaste. Développez cette section pour voir où ces informations s’inscrivent dans le processus de migration. </br></br>Vous devez effectuer toutes les étapes de migration précédentes avant de continuer avec les informations de cette page.

Avant de poursuivre cette section, assurez-vous d’avoir effectué toutes les tâches de migration précédentes.

Les informations de cette page couvrent l’étape 7, comme indiqué dans le tableau ci-dessous :

| Tâche de migration | Détails |
|---------|----------|
| **Étape 1 : [Prise en main de la migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Découvrez les avantages de la migration vers Adobe Analytics et le processus de migration de base. |
| **Étape 2 : [Choisissez la méthode de migration](/help/getting-started/cja-migration/cja-migration-method.md)** | Différentes méthodes sont disponibles pour la migration vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise. |
| **Étape 3 : [Envoi de données à Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction de la méthode de migration choisie à l’étape 1. |
| **Étape 4 : [Planification du mappage des données au schéma XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Schémas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) sont utilisées dans Adobe Experience Platform pour décrire la structure des données de manière cohérente et réutilisable. En définissant les données de manière cohérente sur l’ensemble des systèmes, il est plus simple de leur donner du sens et donc d’en tirer profit.<p>La plupart des méthodes de migration exigent que vous créiez un nouveau schéma XDM ou que vous mappiez votre schéma Adobe Analytics existant avec XDM à l’aide du mappage de flux de données.</p> |
| **Étape 5 : [Conserver les données historiques](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La plupart des entreprises doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour ce faire. |
| **Étape 6 : [Planification de l’intégration des utilisateurs](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Donnez à vos utilisateurs suffisamment de temps (3 à 6 mois) pour se familiariser avec les différences clés d’Analysis Workspace dans Customer Journey Analytics. |
| <span class="preview">**Étape 7 : [Port de l’utilisation de l’API de création de rapports](/help/getting-started/cja-migration/cja-migration-api.md)**</span> | <span class="preview">L’API de création de rapports du Customer Journey Analytics est au même format, mais utilise un point de terminaison différent. Transférez l’utilisation de l’API de création de rapports d’Adobe Analytics vers l’API de création de rapports du Customer Journey Analytics.</span> |
| **Étape 8 : [Remplacement des flux de données et du Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Choisissez comment utiliser les options d’exportation disponibles dans Customer Journey Analytics pour remplacer les flux de données et les fonctionnalités de Data Warehouse que vous utilisiez dans Adobe Analytics. |
| **Étape 9 : [Migration de projets et de composants](/help/getting-started/cja-migration/cja-migration-projects.md)** | La zone de migration Composant d’Adobe Analytics vous permet de migrer les projets et leurs composants associés d’Adobe Analytics vers Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Transférez l’utilisation de l’API de création de rapports d’Adobe Analytics vers l’API de création de rapports du Customer Journey Analytics.

L’API de création de rapports du Customer Journey Analytics est au même format, mais utilise un point de terminaison différent.

## Ensuite, remplacez Flux de données et Data Warehouse

Déterminez comment utiliser les options d’exportation disponibles dans Customer Journey Analytics pour [remplacer les fonctions Flux de données et Data Warehouse ;](/help/getting-started/cja-migration/cja-migration-export-options.md) vous utilisiez dans Adobe Analytics.