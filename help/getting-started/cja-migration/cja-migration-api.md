---
title: Port de l’utilisation de l’API de création de rapports lors de la migration vers Customer Journey Analytics
description: Découvrez comment transférer l’utilisation de l’API d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d26a6956-870f-44f2-9c32-f732bff17737
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Étape 7 : port de l’utilisation de l’API de création de rapports lors de la migration vers Customer Journey Analytics

+++Développez cette section pour voir où les informations de cette page s’inscrivent dans le processus de migration plus vaste. Vérifiez que toutes les étapes de migration précédentes sont terminées.

Avant de poursuivre cette section, assurez-vous d’avoir effectué toutes les tâches de migration précédentes.

Les informations de cette page couvrent l’étape 7, comme indiqué dans le tableau ci-dessous :

| Tâche de migration | Détails |
|---------|----------|
| **Étape 1 : [Prise en main de la migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Découvrez les avantages de la migration vers Adobe Analytics et le processus de migration de base. |
| **Étape 2 : [Choix du chemin de migration](/help/getting-started/cja-migration/cja-migration-path.md)** | Différentes méthodes sont disponibles pour la migration vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise. |
| **Étape 3 : [Envoi de données à Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction du chemin de migration que vous avez choisi à l’étape 2. |
| **Étape 4 : [Conserver les données historiques](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La plupart des entreprises doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour ce faire. |
| **Étape 5 : [Exécution de tâches de mise en oeuvre supplémentaires](/help/getting-started/cja-getting-started.md)** | À ce stade du processus de migration, vous devez effectuer diverses tâches avant que votre environnement de Customer Journey Analytics ne soit prêt à l’emploi.<p>Ces tâches supplémentaires s’appliquent aux migrations à partir d’Adobe Analytics, ainsi qu’aux nouvelles implémentations de Customer Journey Analytics.</p><p>Ces tâches incluent :</p><ul><li>Importation d’autres données dans Experience Platform</li><li>Création de connexions entre les jeux de données Platform et Customer Journey Analytics</li><li>Création de vues de données</li><li>Portage de l’utilisation de l’API de création de rapports</li><li>Prise en compte des flux de données et du Data Warehouse</li><li>Migration de projets et de composants</li><li>Planification de l’intégration des utilisateurs</li></ul> <p>Pour plus d’informations, voir [Prise en main du Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Transférez l’utilisation de l’API de création de rapports d’Adobe Analytics vers l’API de création de rapports du Customer Journey Analytics.

L’API de création de rapports du Customer Journey Analytics est au même format, mais utilise un sous-domaine différent.

Consultez le guide de point de terminaison pour Adobe Analytics et Customer Journey Analytics.

La plupart des appels API peuvent être facilement traduits d’Adobe Analytics vers Customer Journey Analytics.

Ajoutez l’API du Customer Journey Analytics à son projet d’API.

Ajoutez l’ID d’organisation IMS à l’en-tête de leurs appels API.

cja.adobe.io par rapport à analytics.adobe.io

En-têtes supplémentaires

## Ensuite, remplacez Flux de données et Data Warehouse

Déterminez comment utiliser les options d’exportation disponibles dans Customer Journey Analytics pour [remplacer les fonctions Flux de données et Data Warehouse ;](/help/getting-started/cja-migration/cja-migration-export-options.md) vous utilisiez dans Adobe Analytics.
