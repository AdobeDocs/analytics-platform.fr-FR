---
title: Conserver les données historiques lors de la mise à niveau vers Customer Journey Analytics
description: Découvrir comment conserver les données historiques lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 73%

---

# Étape 4 : conserver les données historiques lors de la mise à niveau

+++Développez cette section pour voir où les informations de cette page s’inscrivent dans le processus de mise à niveau plus général. Vérifiez que toutes les étapes de mise à niveau précédentes sont terminées.

Avant de poursuivre cette section, assurez-vous d’avoir effectué toutes les tâches de mise à niveau précédentes.

Les informations de cette page couvrent l’Étape 4 du processus de mise à niveau, comme indiqué dans le tableau ci-dessous :

| Tâche de mise à niveau | Détails |
|---------|----------|
| **Étape 1 : [commencer avec la mise à niveau](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Découvrez les avantages de la mise à niveau vers Customer Journey Analytics et le processus de mise à niveau de base. |
| **Étape 2 : [choisir le chemin de mise à niveau](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Différentes méthodes sont disponibles pour la mise à niveau vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise. |
| **Étape 3 : [envoyer les données à Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction du chemin de mise à niveau que vous avez choisi à l’Étape 2. |
| <span class="preview">**Étape 4 : conserver les données historiques**</span> | <span class="preview">La plupart des entreprises doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour ce faire.</span> |
| **Étape 5 : [exécuter des tâches d’implémentation supplémentaires](/help/getting-started/cja-getting-started.md)** | À ce stade du processus de mise à niveau, vous devez effectuer diverses tâches avant que votre environnement de Customer Journey Analytics soit prêt à l’emploi.<p>Ces tâches supplémentaires s’appliquent aux mises à niveau à partir d’Adobe Analytics, ainsi qu’aux nouvelles implémentations de Customer Journey Analytics.</p><p>Ces tâches comprennent les éléments suivants :</p><ul><li>Importer d’autres données dans Experience Platform</li><li>Créer des connexions entre les jeux de données Platform et Customer Journey Analytics</li><li>Créer des vues de données</li><li>Porter l’utilisation de l’API de création de rapports</li><li>Prendre en compte les flux de données et Data Warehouse</li><li>Migrer des projets et des composants</li><li>Planifier l’intégration des utilisateurs et utilisatrices</li></ul> <p>Pour plus d’informations, voir [Commencer avec Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>Les informations de cette page sont en cours de remplacement par les informations de mise à niveau plus complètes suivantes : <ul><li>**Étapes de mise à niveau recommandées**<p>Pour plus d’informations, voir [Chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Guide de mise à niveau de Customer Journey Analytics**<p>Un nouveau guide de mise à niveau est disponible pour générer dynamiquement des étapes de mise à niveau adaptées à votre entreprise et à vos circonstances uniques.</p><p>Pour accéder au guide à partir de Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Workspace]**, puis sélectionnez **[!UICONTROL Mettre à niveau vers Customer Journey Analytics]** dans le panneau de gauche. Suivez les instructions à l’écran.</p></li></ul>

Choisissez l’une des options suivantes pour conserver les données historiques lors du passage d’Adobe Analytics à Customer Journey Analytics :

>[!IMPORTANT]
>
>Lorsque vous choisissez comment conserver les données historiques, contactez le représentant ou la représentante de votre compte Adobe pour déterminer le prix.

## Utilisation du connecteur source Analytics

Vous pouvez utiliser le [connecteur source Analytics](/help/data-ingestion/analytics.md) pour conserver les données historiques. Quel que soit le chemin de mise à niveau choisi (même si vous effectuez une mise à niveau à l’aide de Web SDK), vous pouvez utiliser le connecteur source Analytics pour conserver les données historiques de votre environnement Adobe Analytics.

Vous pouvez utiliser le connecteur source Analytics pour conserver les données historiques en apportant les données historiques dans son propre emplacement dédié, distinct de vos données actuelles.

Le connecteur source Analytics doit fonctionner aussi longtemps que vous avez besoin d’accéder aux données historiques.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Conserver votre implémentation Adobe Analytics existante

Vous pouvez conserver votre implémentation Adobe Analytics existante avec votre nouvelle implémentation Customer Journey Analytics pour une période spécifique (par exemple, un an). Lorsque vous choisissez cette option, tenez compte des éléments suivants :

* Les données ne seront pas disponibles dans Experience Platform.

* Vous devriez prévoir de désactiver l’implémentaion Adobe Analytics une fois que vous aurez suffisamment de données dans Customer Journey Analytics.

## Ensuite, effectuez d’autres tâches d’implémentation.

À ce stade du processus de mise à niveau, vous devez effectuer diverses tâches d’implémentation avant que votre environnement Customer Journey Analytics ne soit prêt à l’emploi.

Ces tâches supplémentaires s’appliquent aux mises à niveau à partir d’Adobe Analytics, ainsi qu’aux nouvelles implémentations de Customer Journey Analytics.

Ces tâches comprennent les éléments suivants :

* Importer d’autres données dans Experience Platform

* Créer des connexions entre les jeux de données Platform et Customer Journey Analytics

* Créer des vues de données

* Porter l’utilisation de l’API de création de rapports

* Prendre en compte les cas d’utilisation des flux de données et de Data Warehouse

* Migrer des projets et des composants

* Planifier l’intégration des utilisateurs et utilisatrices

Pour plus d’informations, commencez par l’étape 2 de [Commencer avec Customer Journey Analytics](/help/getting-started/cja-getting-started.md).
