---
title: Cas d’utilisation d’exportation de données
description: Présentation de divers cas d’utilisation d’exportation de données pour Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: 40e4c3bd8f3c37e9a6143200b85ffe0ac4bcb2ca
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 0%

---

# Cas d’utilisation d’exportation de données

Cette section présente des cas pratiques d’exportation de données et explique comment mettre en oeuvre ces cas pratiques avec une ou plusieurs fonctionnalités de Customer Journey Analytics ou d’Experience Platform. Chaque fonctionnalité est détaillée dans un article distinct.

## Introduction

L’une des différences uniques entre Adobe Analytics et Customer Journey Analytics est liée au traitement des données pour l’attribution et la session. Pour plus d’informations, voir [Comparaison du traitement des données dans Adobe Analytics et Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) .

### Adobe Analytics : attribution et sessionisation du temps de collecte.

Dans Adobe Analytics, tous les événements sont traités en direct et dans l’ordre par identifiant d’appareil, ce qui permet à l’Adobe de générer, de stocker et d’exporter des données de parcours de navigation avec des valeurs persistantes ou attribuées au moment de la collecte, notamment :

* Persistance des Dimensions (par exemple, les codes de suivi de campagne qui expirent après 90 jours).
* Nombre de visites et sessionisation.
* Valeurs de Dimension, calculées par les règles de traitement et VISTA.

Cela a un impact sur l’exportation des données à partir d’Adobe Analytics :

* Le traitement des données est statique après la collecte initiale.
* Les flux de données comprennent des colonnes &quot;post&quot;, qui reflètent le traitement de la période de collecte.


### Customer Journey Analytics : attribution et sessionisation de l’heure de requête

Dans Customer Journey Analytics, les événements ne sont pas collectés dans l’ordre et un ID de personne est utilisé à la place d’un ID d’appareil, ce qui permet au Customer Journey Analytics de mettre à jour l’attribution et la session au moment du rapport. Ce type de collecte de données offre une certaine flexibilité, comme par exemple :

* L’assemblage peut _relayer_ des données tous les jours ou toutes les semaines, en associant des événements anonymes à des événements connus. Voir [Assemblage](../../stitching/overview.md) pour plus d’informations.
* La sessionisation et les valeurs persistantes changent à chaque fois.
   * de nouvelles données sont collectées ou
   * Le groupement ajoute des événements à l’historique d’une personne.

Le traitement de la période de rapport a un impact sur l’exportation des données du Customer Journey Analytics. Les exportations qui incluent des valeurs persistantes ne correspondront pas aux rapports et valeurs du Customer Journey Analytics s’éloigneront progressivement.

Pour assurer la cohérence des mesures, il est préférable d’utiliser les nouvelles fonctionnalités de Customer Journey Analytics. En règle générale, la fonctionnalité d’exportation des données d’Experience Platform et de Customer Journey Analytics dépasse la fonctionnalité de flux de données d’Adobe Analytics. Experience Platform et Customer Journey Analytics fournissent les éléments suivants :

* nouvelles sources de données et traitement soumis à l’exportation des données

   * inclure des sources de données non numériques,
   * appliquer une attribution et une session personnalisées basées sur des règles de fonctionnement ;
   * conserver les parcours client mis à jour avec l’assemblage ;

* réalisation de cas d’utilisation d’exportation de données personnalisés

   * exporter des données vers l’emplacement où vous en avez besoin, y compris les outils Business Intelligence (BI) et les destinations cloud,
   * conserver les données synchronisées avec Analysis Workspace par le biais de l’intégration des outils de BI ;
   * pas besoin de répliquer la logique de traitement dans vos propres systèmes,
   * nouvelle prise en charge des mesures calculées, des champs dérivés et de la segmentation, et

* prise en compte de la sécurité et de la gouvernance des données par conception

   * surveiller l’exportation de toutes les données par utilisateur et par destination ;
   * définir des limites sur les données disponibles à l’exportation, et
   * définir des alertes pour les problèmes de diffusion et des limites sur les fenêtres de diffusion planifiées ;


## Cas d’utilisation et fonctionnalités

En règle générale, l’exportation de données prend en charge un certain nombre de cas d’utilisation. Chaque cas d’utilisation est différent en termes de données requises et de la manière d’accéder à ces données et de les exporter. Experience Platform et Customer Journey Analytics fournissent un certain nombre de fonctionnalités qui, indépendamment ou combinées, peuvent résoudre les différents cas d’utilisation. Le tableau ci-dessous présente un aperçu des cas d’utilisation d’exportation de données identifiés et des fonctionnalités Experience Platform et Customer Journey Analytics pour mettre en oeuvre ces cas d’utilisation.

| Cas d’utilisation d’exportation de données | Fonctionnalités Experience Platform et Customer Journey Analytics |
|---|---|
| **Sauvegarde de données**<br/> Conservez une copie complète de vos données numériques à des fins de conformité ou de réglementation. | **Experience Platform** : [**Exporter des jeux de données**](export-datasets.md)<br/> Exporter les données collectées dans Experience Platform directement vers les destinations cloud sur une planification ou ad hoc.<br/>*La version actuellement limitée, la version complète pour les clients Customer Journey Analytics est attendue en juin 2024.* |
| **Validation des données**<br/>&#x200B;Évaluez les données du parcours de navigation pour obtenir la précision de la collecte de données. | **Experience Platform** : [**Query Service (Data Distiller) &amp; Export datasets**](queryservice-export-datasets.md)<br/> Interface PostgreSQL interactive pour exécuter des requêtes SQL ad hoc à l’aide de votre outil SQL préféré pour valider les données de vos jeux de données.<br/><br/>**Customer Journey Analytics** : [**Exportez la table complète**](export-full-table.md)<br/> Validez les données traitées de CJA avec attribution et sessionisation appliquées. |
| **Lac de données, Data Warehouse ou outils de BI**<br/> Importez des données numériques dans vos propres outils de BI ou lac de données pour les utiliser avec des jeux de données supplémentaires. | **Customer Journey Analytics** : [**Extension BI**](bi-extension.md)<br/> Ajoutez des mesures traitées par Customer Journey Analytics aux outils de visualisation de données tels que Power BI et combinez-les à des données supplémentaires pour les rapports personnalisés <br/><br/>**Experience Platform** : [**Query Service (Data Distiller) &amp; Exporter des jeux de données**](queryservice-export-datasets.md)<br> Générer des données de parcours de navigation personnalisées à l’aide de SQL pour être diffusées vers des destinations cloud. |
| **Préparation pour l’IA / ML**<br/> Améliorez l’intelligence artificielle / les modèles d’apprentissage automatique et les tâches avec des données de Customer Journey Analytics. | **Customer Journey Analytics** : [**Exporter la table complète**](export-full-table.md)<br/> Exporter les dimensions et les mesures traitées par le Customer Journey Analytics vers les destinations cloud une fois ou de manière récurrente, y compris les mesures calculées et la segmentation.<br/><br/>**Experience Platform** : [**Query Service (Data Distiller) &amp; Export datasets**](queryservice-export-datasets.md)<br/> Générer des données de parcours de navigation personnalisées à l’aide de SQL pour enrichir les modèles AI/ML. |
