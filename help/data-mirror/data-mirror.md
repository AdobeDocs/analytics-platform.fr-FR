---
title: Présentation de Data Mirror
description: Comprendre comment synchroniser les données entre les solutions natives de l’entrepôt de données et Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
source-git-commit: 9bd124ad651274b48052edc56bfb72358aa2d79a
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 1%

---

# Présentation d’Experience Platform Data Mirror

{{release-limited-testing}}

Data Mirror est une fonctionnalité d’Experience Platform qui permet l’ingestion de modifications au niveau des lignes de bases de données externes dans le lac de données à l’aide de schémas basés sur des modèles. Il préserve les relations de données, applique l’unicité et prend en charge le contrôle de version sans nécessiter de processus d’extraction, de transformation et de chargement (ETL) en amont.

Utilisez Data Mirror pour synchroniser les insertions, les mises à jour et les suppressions (données modifiables) à partir de solutions natives d’entrepôt de données externes telles que [!DNL Snowflake], [!DNL Azure Databricks] ou [!DNL Google BigQuery] directement dans Experience Platform. Data Mirror vous aide à préserver la structure du modèle de base de données et l’intégrité des données lorsque vous importez des données dans Experience Platform.


## Fonctionnalités et avantages

Data Mirror offre les fonctionnalités essentielles suivantes pour la synchronisation des bases de données :

* **Application de la clé de Principal**. Garantit l’unicité dans les jeux de données et empêche les enregistrements en double lors de l’ingestion.
* **Ingestion des modifications au niveau des lignes**. Prend en charge les modifications de données granulaires, notamment les upserts et les suppressions avec contrôle de précision.
* **Relations de schéma**. Active les relations de clés étrangères et primaires entre les jeux de données via des descripteurs.
* **Gestion des événements dans le désordre**. Les processus modifient les événements à l’aide des descripteurs de version et d’horodatage, même s’ils arrivent hors séquence.
* **Intégration entrepôt direct**. Se connecte aux entrepôts de données cloud pris en charge pour la synchronisation des modifications en temps réel.

Utilisez Data Mirror pour ingérer des modifications directement à partir de vos systèmes sources, appliquer l’intégrité des schémas et rendre les données disponibles pour les workflows d’analyse, d’orchestration des parcours et de conformité. Data Mirror élimine les processus ETL en amont complexes et accélère la mise en œuvre en permettant la mise en miroir directe des modèles de base de données existants. Cette élimination peut améliorer la gouvernance des données grâce à un contrôle précis des suppressions et des opérations d’hygiène des données.

<!-- Add link when AEP docs are ready... -->

Consultez également la documentation d’Experience Platform sur Data Mirror.


## Data Mirror pour Customer Journey Analytics

>[!NOTE]
>
>La fonctionnalité Experience Platform Data Mirror pour Customer Journey Analytics est disponible en version bêta **publique** jusqu’au 25 mars 2026. Pendant la période bêta, les mises à jour de capture des données de modification (CDC) sont limitées à 0,5 % des lignes mensuelles de données de votre organisation. Les lignes de données mensuelles sont basées sur vos droits annuels pour les lignes de données divisées par 12. Adobe se réserve le droit de mettre fin à l’accès en version bêta de la fonctionnalité Experience Platform Data Mirror for Customer Journey Analytics si votre organisation dépasse cette limite.
>

La fonctionnalité Experience Platform Data Mirror for Customer Journey Analytics est disponible pour certaines solutions natives d’entrepôt de données ([!DNL Azure Databricks], [!DNL Google BigQuery] et [!DNL Snowflake]). La version Customer Journey Analytics de la fonctionnalité Data Mirror nécessite une configuration et un paramétrage appropriés de plusieurs composants :

* [Solution native Data Warehouse](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)


>[!MORELIKETHIS]
>
>Guide de démarrage rapide de [Data Mirror : mise en miroir et utilisation de données basées sur des modèles](data-mirror.md)
>