---
title: Cas pratiques des flux de données
description: Présentation de divers cas d’utilisation d’exportation de données pour Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 19018e31bb2a46e88a27643fe10c388b40de243e
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 0%

---


# Cas d’utilisation d’exportation de données

Cette section présente des cas pratiques d’exportation de données. Chaque cas d’utilisation est décrit dans son propre article. Pour certains cas d’utilisation, plusieurs solutions sont fournies.

## Introduction

L’une des différences uniques entre Adobe Analytics et Customer Journey Analytics est liée au traitement des données pour l’attribution et la session. Voir [Comparaison du traitement des données dans Adobe Analytics et Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) pour plus d’informations.

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

* Possibilité d’assemblage _relecture_ données quotidiennes ou hebdomadaires, en associant des événements anonymes à des événements connus. Voir [Assemblage](../../stitching/overview.md) pour plus d’informations.
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


## Cas d’utilisation et solutions

En règle générale, l’exportation de données prend en charge un certain nombre de cas d’utilisation. Chaque cas d’utilisation est différent en termes de données requises et de la manière d’accéder à ces données et de les exporter. Experience Platform et Customer Journey Analytics fournissent un certain nombre de fonctionnalités qui, indépendamment ou combinées, peuvent résoudre les différents cas d’utilisation. Le tableau ci-dessous présente un aperçu des cas d’utilisation d’exportation de données identifiés et des fonctionnalités Experience Platform et Customer Journey Analytics pour mettre en oeuvre ces cas d’utilisation.

| Cas d’utilisation d’exportation de données | Fonctionnalités Experience Platform et Customer Journey Analytics |
|---|---|
| **Sauvegarde de données**<br/> Conservez une copie complète de vos données numériques à des fins de conformité ou de réglementation. | **Experience Platform**: [**Exportation de jeux de données**](export-datasets.md)<br/> Exportez les données collectées dans Experience Platform directement vers les destinations cloud selon un calendrier ou ad hoc.<br/>*Actuellement, une version limitée et complète pour les clients Customer Journey Analytics est prévue pour juin 2024.* |
| **Validation des données**<br/>&#x200B;Évaluez les données du parcours de navigation pour en déterminer la précision. | **Experience Platform**: [**Query Service (Data Distiller) et exportation de jeux de données**](queryservice-export-datasets.md)<br/> Interface PostgreSQL interactive pour exécuter des requêtes SQL ad hoc à l’aide de votre outil SQL préféré pour valider les données de vos jeux de données.<br/><br/>**Customer Journey Analytics**: [**Exporter le tableau complet**](export-full-table.md)<br/> Validez les données traitées de CJA avec attribution et sessionisation appliquées. |
| **Outils de lac de données, de Data Warehouse ou de BI**<br/> Apportez des données numériques dans vos propres outils de BI ou lac de données pour les utiliser avec des jeux de données supplémentaires. | **Customer Journey Analytics**: [**Extension BI**](bi-extension.md)<br/> Ajout de mesures traitées par Customer Journey Analytics aux outils de visualisation de données tels que Power BI et combinaison de données supplémentaires pour les rapports personnalisés <br/><br/>**Experience Platform**: [**Query Service (Data Distiller) et exportation de jeux de données**](queryservice-export-datasets.md)<br> Générez des données de parcours de navigation personnalisées à l’aide de SQL à diffuser vers les destinations cloud. |
| **Préparation à l’IA/ML**<br/> Améliorez les modèles et les tâches d’intelligence artificielle/d’apprentissage automatique à l’aide de données de Customer Journey Analytics. | **Customer Journey Analytics**: [**Exporter le tableau complet**](export-full-table.md)<br/> Exportez ponctuellement ou de manière récurrente les dimensions et mesures traitées par les Customer Journey Analytics vers les destinations cloud, y compris les mesures calculées et la segmentation.<br/><br/>**Experience Platform**: [**Query Service (Data Distiller) et exportation de jeux de données**](queryservice-export-datasets.md)<br/> Générez des données de parcours de navigation personnalisées à l’aide de SQL pour enrichir les modèles AI/ML. |

