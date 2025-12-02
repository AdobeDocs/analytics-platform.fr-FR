---
title: Commencer avec la mise à niveau vers Customer Journey Analytics
description: Planifier la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 100%

---

# Étape 1 : commencer avec la mise à niveau vers Customer Journey Analytics

>[!AVAILABILITY]
>
>Les informations de cette page sont progressivement remplacées par des informations de mise à niveau plus complètes suivantes : <ul><li>**Étapes recommandées pour la mise à niveau**<p>Pour plus d’informations, consultez [Chemin recommandé pour la mise à niveau à partir d’Adobe Analytics vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Guide de mise à niveau de Customer Journey Analytics**<p>Un nouveau guide est disponible pour générer dynamiquement des étapes de mise à niveau adaptées à votre entreprise et à vos circonstances.</p><p>Pour accéder au guide à partir de Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Espace de travail]**, puis sélectionnez **[!UICONTROL Mettre à niveau vers Customer Journey Analytics]** dans le panneau de gauche. Suivez les instructions à l’écran.</p></li></ul>

Customer Journey Analytics est la nouvelle génération d’Analytics. Il permet la collecte de données sur plusieurs canaux (données en ligne et hors ligne) associée à une puissante fonctionnalité de traitement de la période de rapport (par le biais de la définition de composants et de champs dérivés dans les vues de données).

Avant de commencer le processus de mise à niveau d’Adobe Analytics vers Customer Journey Analytics, vous devez comprendre les avantages de Customer Journey Analytics, ainsi que les étapes requises pour réussir la mise à niveau.

## Comprendre les avantages de Customer Journey Analytics

Voici quelques-uns des avantages clés : (Pour obtenir une liste complète, ainsi que des informations supplémentaires sur chacune de ces fonctions clés, voir [Fonctionnalités disponibles uniquement dans Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

* [Création de rapports multicanaux](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics est associé à la capacité d’Experience Platform à contenir tous types et schémas de données. Collectez et créez des rapports sur les données de plusieurs canaux, tels que les systèmes numériques (web), de point de vente, mobiles, CRM, etc.

* [Transformations de la période de rapport dans les vues de données](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Les vues de données dans Customer Journey Analytics vous permettent d’interpréter plus en détail les données d’une connexion. Vous pouvez modifier ou supprimer des données sans modifier l’implémentation, utiliser des sous-chaînes pour manipuler des dimensions, créer des mesures à partir de n’importe quelle valeur, segmenter les sous-événements ou encore utiliser des champs dérivés. Toutes ces transformations sont non destructives.

* [Les transformations s’appliquent aux données historiques et nouvelles.](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  La manipulation des vues des données peut s’appliquer de manière non destructive aux données historiques et nouvelles.

* [Champs dérivés](/help/data-views/derived-fields/derived-fields.md)

  Les champs dérivés permettent des transformations de l’heure des rapports selon vos données. Les données peuvent être combinées, corrigées ou créées à la volée et s’appliquer rétroactivement à tous les rapports.

* [Les vues de données remplacent les suites de rapports virtuelles.](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  Les vues de données reprennent le concept même de suites de rapports virtuelles et l’étendent pour contrôler plus intensément les données découlant des connexions. Ces modifications rendent les paramètres généraux tels que le fuseau horaire et les intervalles d’expiration de session configurables et rétroactifs.

* [Dimensions et mesures client illimitées](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  Les valeurs peuvent être numériques, textuelles, d’objets ou de listes, ou encore un mélange de ces dernières. Les dimensions peuvent être imbriquées ou hiérarchiques.

## Comprendre le processus de mise à niveau

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
Les informations de cette page couvrent l’Étape 1 de la mise à niveau, comme indiqué dans le tableau ci-dessous. Suivez toutes les étapes de ce tableau pour mettre à niveau d’Adobe Analytics vers Customer Journey Analytics.

| Tâche de mise à niveau | Détails |
|---------|----------|
| <span class="preview">**Étape 1 : commencer la mise à niveau**</span> | <span class="preview">Découvrez les avantages de la mise à niveau vers Customer Journey Analytics et le processus de mise à niveau de base.</span> |
| **Étape 2 : [choisir le chemin de mise à niveau](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Différentes méthodes sont disponibles pour la mise à niveau vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise. |
| **Étape 3 : [envoyer les données à Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction du chemin de mise à niveau que vous avez choisi à l’Étape 2. |
| **Étape 4 : [conserver les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La plupart des organisations doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour cela. |
| **Étape 5 : [exécuter des tâches d’implémentation supplémentaires](/help/getting-started/cja-getting-started.md)** | À ce stade du processus de mise à niveau, vous devez effectuer diverses tâches avant que votre environnement de Customer Journey Analytics soit prêt à l’emploi.<p>Ces tâches supplémentaires s’appliquent aux mises à niveau à partir d’Adobe Analytics, ainsi qu’aux nouvelles implémentations de Customer Journey Analytics.</p><p>Ces tâches comprennent les éléments suivants :</p><ul><li>Importer d’autres données dans Experience Platform</li><li>Créer des connexions entre les jeux de données Platform et Customer Journey Analytics</li><li>Créer des vues de données</li><li>Porter l’utilisation de l’API de création de rapports</li><li>Prendre en compte les flux de données et Data Warehouse</li><li>Migrer des projets et des composants</li><li>Planifier l’intégration des utilisateurs et utilisatrices</li></ul> <p>Pour plus d’informations, voir [Commencer avec Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## Tout d’abord, sélectionnez le chemin de mise à niveau.

Différentes méthodes sont disponibles pour la mise à niveau vers Customer Journey Analytics. [Choisissez la méthode qui convient le mieux à votre organisation](/help/getting-started/cja-upgrade/cja-upgrade-path.md).

Le chemin de mise à niveau que vous choisissez dépend de l’environnement Adobe Analytics actuel de votre organisation et des objectifs à long terme.
