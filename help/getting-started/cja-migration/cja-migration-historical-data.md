---
title: Conserver les données historiques lors de la migration vers Customer Journey Analytics
description: Découvrez comment conserver les données historiques lors de la migration vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 7bc4425f11980780ab64a201029cd63e4bd7849c
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Étape 5 : conservation des données historiques lors de la migration

+++Développez cette section pour voir où les informations de cette page s’inscrivent dans le processus de migration plus vaste. Vérifiez que toutes les étapes de migration précédentes sont terminées.

Avant de poursuivre cette section, assurez-vous d’avoir effectué toutes les tâches de migration précédentes.

Les informations de cette page couvrent l’étape 4 de la section **migration**, comme indiqué dans le tableau ci-dessous :

| Tâche de migration | Détails |
|---------|----------|
| **Étape 1 : [Prise en main de la migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Découvrez les avantages de la migration vers Adobe Analytics et le processus de migration de base. |
| **Étape 2 : [Choix du chemin de migration](/help/getting-started/cja-migration/cja-migration-path.md)** | Différentes méthodes sont disponibles pour la migration vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise. |
| **Étape 4 : [Envoi de données à Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction du chemin de migration que vous avez choisi à l’étape 2. |
| <span class="preview">**Étape 4 : conservation des données historiques**</span> | <span class="preview">La plupart des entreprises doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour ce faire.</span> |
| **Étape 5 : [Exécution de tâches de mise en oeuvre supplémentaires](/help/getting-started/cja-getting-started.md)** | À ce stade du processus de migration, vous devez effectuer diverses tâches avant que votre environnement de Customer Journey Analytics ne soit prêt à l’emploi.<p>Ces tâches supplémentaires s’appliquent aux migrations à partir d’Adobe Analytics, ainsi qu’aux nouvelles implémentations de Customer Journey Analytics.</p><p>Ces tâches incluent :</p><ul><li>Importation d’autres données dans Experience Platform</li><li>Création de connexions entre les jeux de données Platform et Customer Journey Analytics</li><li>Création de vues de données</li><li>Portage de l’utilisation de l’API de création de rapports</li><li>Prise en compte des flux de données et du Data Warehouse</li><li>Migration de projets et de composants</li><li>Planification de l’intégration des utilisateurs</li></ul> <p>Pour plus d’informations, voir [Prise en main du Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Choisissez l’une des options suivantes pour conserver les données historiques lors du passage d’Adobe Analytics à Customer Journey Analytics :

>[!IMPORTANT]
>
>Lorsque vous choisissez comment conserver des données historiques, contactez le représentant de votre compte d’Adobe pour déterminer le prix.

## Utilisation du connecteur source Analytics

Vous pouvez utiliser la variable [Connecteur source Analytics](/help/data-ingestion/analytics.md) pour conserver les données historiques. Quel que soit le chemin de migration choisi (même si vous migrez à l’aide du SDK Web), vous pouvez utiliser le connecteur source Analytics pour conserver les données historiques de votre environnement Adobe Analytics.

Vous pouvez utiliser Analytics Source Connector pour conserver les données historiques en introduisant les données historiques dans leur propre emplacement dédié, en les séparant de vos données actives.

Le connecteur source Analytics doit fonctionner aussi longtemps que vous avez besoin d’accéder aux données historiques.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Conserver votre implémentation Adobe Analytics existante

Vous pouvez conserver votre mise en oeuvre Adobe Analytics existante avec votre nouvelle mise en oeuvre de Customer Journey Analytics pour une période spécifique (par exemple, 1 an). Lorsque vous choisissez cette option, tenez compte des points suivants :

* Les données ne seraient pas disponibles dans Experience Platform.

* Vous devriez prévoir de désactiver la mise en oeuvre d’Adobe Analytics une fois que vous aurez suffisamment de données dans Customer Journey Analytics.

## Ensuite, effectuez d’autres tâches de mise en oeuvre.

À ce stade du processus de migration, vous devez effectuer diverses tâches d’implémentation avant que votre environnement de Customer Journey Analytics ne soit prêt à l’emploi.

Ces tâches supplémentaires s’appliquent aux migrations à partir d’Adobe Analytics, ainsi qu’aux nouvelles implémentations de Customer Journey Analytics.

Ces tâches incluent :

* Importation d’autres données dans Experience Platform

* Création de connexions entre les jeux de données Platform et Customer Journey Analytics

* Création de vues de données

* Portage de l’utilisation de l’API de création de rapports

* Prise en compte des flux de données et des cas d’utilisation des Data Warehouse

* Migration de projets et de composants

* Planification de l’intégration des utilisateurs

Pour plus d’informations, commencez à l’étape 2 de la section [Prise en main du Customer Journey Analytics](/help/getting-started/cja-getting-started.md).
