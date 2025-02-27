---
title: Cas dʼutilisation des exports de données
description: Comprendre divers cas d’utilisation d’exportation de données pour Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: efb961c571ddcde1017e6bf2080fc2a97c28bb13
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 1%

---

# Cas dʼutilisation des exports de données {#data-export-use-cases}

<!-- This contextual help is for the upgrade checklist -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds-step"
>title="Utiliser des fonctionnalités d’exportation similaires aux flux de données"
>abstract="Aucun remplacement exact des flux de données n’est encore disponible dans Customer Journey Analytics. Cependant, des fonctionnalités similaires peuvent être obtenues avec des fonctionnalités telles que l’exportation de table complète, l’exportation de jeux de données Platform, l’intégration de l’outil BI et l’API de création de rapports."

<!-- markdownlint-enable MD034 -->

Cette section présente les cas d’utilisation d’exportation de données et la manière de les implémenter avec une ou plusieurs fonctionnalités de Customer Journey Analytics ou d’Experience Platform. Chaque fonctionnalité est décrite plus en détail dans un article distinct.

## Introduction

L’une des différences uniques entre Adobe Analytics et Customer Journey Analytics est liée au traitement des données pour l’attribution et la sessionnalisation. Voir [Comparer le traitement des données dans Adobe Analytics et Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) pour plus d’informations.

### Adobe Analytics : attribution de l’heure de collecte et sessionnalisation.

Dans Adobe Analytics, tous les événements sont traités en direct et dans l’ordre par identifiant d’appareil, ce qui permet à Adobe de générer, de stocker et d’exporter des données de parcours de navigation avec des valeurs persistantes ou attribuées au moment de la collecte, notamment :

* Persistance de Dimension (par exemple, codes de suivi de campagne qui expirent après 90 jours).
* Nombre de visites et sessionnalisation.
* Valeurs Dimension, calculées par les règles de traitement et VISTA.

Cela a un impact sur l’exportation des données à partir d’Adobe Analytics :

* Le traitement des données est statique après la collecte initiale.
* Les flux de données incluent des colonnes « post », qui reflètent le traitement au moment de la collecte.


### Customer Journey Analytics : attribution et sessionnalisation au moment de la requête

Dans Customer Journey Analytics, les événements ne sont pas collectés dans l’ordre et un ID de personne est utilisé au lieu d’un ID d’appareil, ce qui permet à Customer Journey Analytics de mettre à jour l’attribution et la sessionnalisation au moment du rapport. Ce type de collecte de données offre une certaine flexibilité, notamment :

* L’assemblage peut _relire_ des données quotidiennes ou hebdomadaires, associant des événements anonymes à des événements connus. Voir [ Assemblage ](../../stitching/overview.md) pour plus d’informations.
* La sessionnalisation et les valeurs persistantes changent à chaque fois
   * de nouvelles données sont collectées ou
   * l’assemblage ajoute des événements à l’historique d’une personne.

Le traitement de la période de rapport a un impact sur l’exportation des données depuis Customer Journey Analytics. Les exportations qui incluent des valeurs persistantes, ne correspondent pas aux rapports Customer Journey Analytics et les valeurs disparaîtront au fil du temps.

Pour la cohérence des mesures, il est préférable d’utiliser les nouvelles fonctionnalités de Customer Journey Analytics. En règle générale, la fonctionnalité d’exportation des données d’Experience Platform et de Customer Journey Analytics dépasse celle des flux de données d’Adobe Analytics. Experience Platform et Customer Journey Analytics fournissent :

* nouvelles sources de données et traitement soumis à l’exportation des données

   * inclure des sources de données non numériques,
   * appliquer une attribution et une sessionnalisation personnalisées en fonction des règles d’entreprise ; et
   * mettez à jour les parcours clients en les regroupant.

* réalisation de cas d&#39;utilisation d&#39;export de données sur mesure

   * d’exporter des données vers l’emplacement où vous en avez besoin, y compris vers les outils Business Intelligence (BI) et les destinations cloud,
   * conserver les données synchronisées avec Analysis Workspace grâce à l’intégration des outils de BI,
   * pas besoin de répliquer la logique de traitement dans vos propres systèmes,
   * nouvelle prise en charge des mesures calculées, des champs dérivés et de la segmentation, et

* prise en compte de la sécurité et de la gouvernance des données dès la conception

   * surveiller toutes les exportations de données par utilisateur et par destination,
   * définir des limites sur les données disponibles à l’exportation, et
   * définissez des alertes pour les problèmes de diffusion et les limites des fenêtres de diffusion planifiées.


## Cas d’utilisation et fonctionnalités

En général, l’exportation de données prend en charge un certain nombre de cas d’utilisation. Chaque cas d’utilisation est différent en termes de données requises et de méthode d’accès et d’exportation de ces données. Experience Platform et Customer Journey Analytics offrent un certain nombre de fonctionnalités qui, soit indépendamment, soit combinées, peuvent résoudre les différents cas d’utilisation. Le tableau ci-dessous présente un aperçu des cas d’utilisation d’exportation de données identifiés et des fonctionnalités d’Experience Platform et de Customer Journey Analytics permettant de mettre en œuvre ces cas d’utilisation.

| Cas dʼutilisation des exports de données | Fonctionnalités d’Experience Platform et de Customer Journey Analytics |
|---|---|
| **Sauvegarde des données**<br/> Conservez une copie complète de vos données numériques à des fins de conformité ou à des fins réglementaires. | **Experience Platform** : [**Exporter des jeux de données**](export-datasets.md)<br/> Exporter les données collectées dans Experience Platform directement vers des destinations cloud selon un planning ou ad hoc. |
| **Validation des données**<br/>&#x200B;Évaluez les données de parcours de navigation pour garantir la précision de la collecte de données. | **Experience Platform** : [**Query Service (Data Distiller) et Export datasets**](queryservice-export-datasets.md)<br/> interface Interactive PostgreSQL pour exécuter des requêtes SQL ad hoc à l’aide de votre outil SQL préféré pour valider les données de vos jeux de données.<br/><br/>**Customer Journey Analytics** : [**Exporter le tableau complet**](export-full-table.md)<br/> Valider les données traitées de CJA avec attribution et sessionnalisation appliquées. |
| **Lac de données, Data Warehouse ou outils de BI**<br/> Insérez des données numériques dans vos propres outils de BI ou lac de données pour les utiliser avec des jeux de données supplémentaires. | **Customer Journey Analytics** : [**Extension BI**](bi-extension.md)<br/> ajoutez des mesures traitées de Customer Journey Analytics aux outils de visualisation de données tels que Power BI et combinez-les avec des données supplémentaires pour les rapports personnalisés.<br/><br/>**Experience Platform**: [**Query Service (Data Distiller) et Export datasets**](queryservice-export-datasets.md)<br> générez des données de parcours de navigation personnalisées à l’aide de SQL à diffuser vers des destinations cloud. |
| **Préparation à l’IA/ML**<br/> améliorer les modèles et tâches d’intelligence artificielle/de machine learning avec des données Customer Journey Analytics. | **Customer Journey Analytics** : [**Exporter le tableau complet**](export-full-table.md)<br/> Exporter les dimensions et mesures traitées de Customer Journey Analytics vers des destinations cloud de manière unique ou récurrente, y compris les mesures calculées et la segmentation.<br/><br/>**Experience Platform** : [**Query Service (Data Distiller) et exporter des jeux de données**](queryservice-export-datasets.md)<br/> Générer des données de parcours de navigation personnalisées à l’aide de SQL pour enrichir les modèles d’IA/ML. |
