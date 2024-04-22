---
title: Prise en main de la migration vers Customer Journey Analytics
description: Planification de la migration d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a23322ab189e6469783a179e2de7aa0195eda737
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 11%

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
Cette page représente l’étape 1 de la migration, comme le montre le tableau suivant. Suivez toutes les étapes de ce tableau pour migrer d’Adobe Analytics vers Customer Journey Analytics.

| Tâche | Détails |
|---------|----------|
| **Étape 1 : [Prise en main de la migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Découvrez les avantages de la migration vers Adobe Analytics et le processus de migration de base. |
| **Étape 2 : [Choisissez la méthode de migration](/help/getting-started/cja-migration/cja-migration-method.md)** | Différentes méthodes sont disponibles pour la migration vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise. |
| **Étape 3 : [Envoi de données à Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction de la méthode de migration choisie à l’étape 1. |
| **Étape 4 : [Planification du mappage des données au schéma XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Schémas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) sont utilisées dans Adobe Experience Platform pour décrire la structure des données de manière cohérente et réutilisable. En définissant les données de manière cohérente sur l’ensemble des systèmes, il est plus simple de leur donner du sens et donc d’en tirer profit.<p>La plupart des méthodes de migration exigent que vous créiez un nouveau schéma XDM ou que vous mappiez votre schéma Adobe Analytics existant avec XDM à l’aide du mappage de flux de données.</p> |
| **Étape 5 : [Conserver les données historiques](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La plupart des entreprises doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour ce faire. |
| **Étape 6 : [Planification de l’intégration des utilisateurs](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Donnez à vos utilisateurs suffisamment de temps (3 à 6 mois) pour se familiariser avec les différences clés d’Analysis Workspace dans Customer Journey Analytics. |
| **Étape 7 : [Port de l’utilisation de l’API de création de rapports](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API de création de rapports du Customer Journey Analytics est au même format, mais utilise un point de terminaison différent. Transférez l’utilisation de l’API de création de rapports d’Adobe Analytics vers l’API de création de rapports du Customer Journey Analytics. |
| **Étape 8 : [Remplacement des flux de données et du Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Choisissez comment utiliser les options d’exportation disponibles dans Customer Journey Analytics pour remplacer les flux de données et les fonctionnalités de Data Warehouse que vous utilisiez dans Adobe Analytics. |
| **Étape 9 : [Migration de projets et de composants](/help/getting-started/cja-migration/cja-migration-projects.md)** | La zone de migration Composant d’Adobe Analytics vous permet de migrer les projets et leurs composants associés d’Adobe Analytics vers Customer Journey Analytics. |

{style="table-layout:auto"}

## Tout d’abord, choisissez la méthode de migration.

Différentes méthodes sont disponibles pour la migration vers Customer Journey Analytics. [Choisissez la méthode qui convient le mieux à votre entreprise.](/help/getting-started/cja-migration/cja-migration-method.md).

La méthode de migration choisie dépend de l’environnement Adobe Analytics actuel de votre entreprise et des objectifs à long terme.