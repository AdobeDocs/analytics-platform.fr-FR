---
title: Prise en main de la migration vers Customer Journey Analytics
description: Planification de la migration d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: d734e5daf9b5c9a559c0390622ab5aa15f2aa7a2
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 10%

---

# Étape 1 : Prise en main de la migration vers Customer Journey Analytics

Customer Journey Analytics est la nouvelle génération d’analyses. Il permet la collecte de données multicanaux (données en ligne et hors ligne), associée à une puissante fonctionnalité de traitement de la période de rapport (par le biais de la définition de composants et de champs dérivés dans les vues de données).

Avant de commencer le processus de migration d’Adobe Analytics vers Customer Journey Analytics, vous devez comprendre les avantages de Customer Journey Analytics, ainsi que les étapes requises pour réussir la migration.

## Comprendre les avantages de Customer Journey Analytics

Voici quelques-uns des avantages clés : (Pour obtenir une liste complète, ainsi que des informations supplémentaires sur chacune de ces fonctions clés, voir [Fonctionnalités disponibles uniquement dans Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

* [Création de rapports multicanaux](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics est associé à la capacité d’Experience Platform à contenir tous types et schémas de données. Collectez et créez des rapports sur les données de plusieurs canaux, tels que les systèmes numériques (web), de point de vente, les systèmes mobiles, CRM, etc.

* [Conversion des rapports en temps réel dans les vues de données](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Les vues de données dans Customer Journey Analytics vous permettent d’interpréter plus en détail les données d’une connexion. Vous pouvez modifier ou supprimer des données sans modifier votre implémentation, utiliser des sous-chaînes pour manipuler des dimensions, créer des mesures à partir de n’importe quelle valeur, filtrer les événements ou utiliser des champs dérivés. Toutes ces transformations sont non destructives.

* [Les transformations s’appliquent aux données historiques et nouvelles.](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  La manipulation des vues de données peut être appliquée de manière non destructive aux données historiques et nouvelles.

* [Champs dérivés](/help/data-views/derived-fields/derived-fields.md)

  Les champs dérivés permettent des transformations de l’heure des rapports selon vos données. Les données peuvent être combinées, corrigées ou créées à la volée et s’appliquer rétroactivement à tous les rapports.

* [Les vues de données remplacent les suites de rapports virtuelles](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  Les vues de données prennent le concept de suites de rapports virtuelles telles qu’elles existent aujourd’hui et le développent afin d’activer des contrôles supplémentaires sur les données mises à disposition par les connexions. Ces modifications rendent les paramètres généraux tels que le fuseau horaire et les intervalles de délai d’expiration de session configurables et rétroactifs.

* [Dimensions et mesures client illimitées](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  Les valeurs peuvent être numériques, textuelles, objets, listes ou mélanges de tous. Les Dimensions peuvent être imbriquées ou hiérarchiques.

## Comprendre le processus de migration

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
Les informations de cette page couvrent l’étape 1 de la migration, comme indiqué dans le tableau ci-dessous. Suivez toutes les étapes de ce tableau pour migrer d’Adobe Analytics vers Customer Journey Analytics.

| Tâche de migration | Détails |
|---------|----------|
| <span class="preview">**Etape 1 : Prise en main de la migration**</span> | <span class="preview">Découvrez les avantages de la migration vers Adobe Analytics et le processus de migration de base.</span> |
| **Étape 2 : [Choix du chemin de migration](/help/getting-started/cja-migration/cja-migration-path.md)** | Différentes méthodes sont disponibles pour la migration vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise. |
| **Étape 3 : [Envoi de données à Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction du chemin de migration que vous avez choisi à l’étape 2. |
| **Étape 4 : [Conserver les données historiques](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La plupart des entreprises doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour ce faire. |
| **Étape 5 : [Exécution de tâches de mise en oeuvre supplémentaires](/help/getting-started/cja-getting-started.md)** | À ce stade du processus de migration, vous devez effectuer diverses tâches avant que votre environnement de Customer Journey Analytics ne soit prêt à l’emploi.<p>Ces tâches supplémentaires s’appliquent aux migrations à partir d’Adobe Analytics, ainsi qu’aux nouvelles implémentations de Customer Journey Analytics.</p><p>Ces tâches incluent :</p><ul><li>Importation d’autres données dans Experience Platform</li><li>Création de connexions entre les jeux de données Platform et Customer Journey Analytics</li><li>Création de vues de données</li><li>Portage de l’utilisation de l’API de création de rapports</li><li>Prise en compte des flux de données et du Data Warehouse</li><li>Migration de projets et de composants</li><li>Planification de l’intégration des utilisateurs</li></ul> <p>Pour plus d’informations, voir [Prise en main du Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## Tout d’abord, sélectionnez le chemin de migration.

Différentes méthodes sont disponibles pour la migration vers Customer Journey Analytics. [Choisissez la méthode qui convient le mieux à votre entreprise.](/help/getting-started/cja-migration/cja-migration-path.md).

Le chemin de migration que vous choisissez dépend de l’environnement Adobe Analytics actuel de votre entreprise et des objectifs à long terme.
