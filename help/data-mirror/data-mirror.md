---
title: Présentation de Data Mirror
description: Comprendre comment synchroniser les données entre les solutions natives de l’entrepôt de données et Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: dc3aa31c280c1a8ee8a0187edeca9bd34a2c9e2e
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Présentation d’Experience Platform Data Mirror

{{release-limited-testing}}

Data Mirror est une fonctionnalité d’Experience Platform qui permet l’ingestion de modifications au niveau des lignes de bases de données externes dans le lac de données à l’aide de schémas relationnels. Il préserve les relations de données, applique l’unicité et prend en charge le contrôle de version sans nécessiter de processus d’extraction, de transformation et de chargement (ETL) en amont.

Utilisez Experience Platform Data Mirror pour synchroniser les insertions, les mises à jour et les suppressions (données modifiables) de solutions natives d’entrepôt de données externes ([!DNL Snowflake], [!DNL Azure Databricks] ou [!DNL Google BigQuery]) directement avec les données d’Experience Platform. Data Mirror vous aide à préserver la structure du modèle de base de données et l’intégrité des données lorsque vous importez des données dans Experience Platform.

## Fonctionnalités et avantages

Data Mirror offre les fonctionnalités essentielles suivantes pour la synchronisation des bases de données :

* **Application de la clé de Principal.** Garantit l’unicité dans les jeux de données et empêche les enregistrements en double lors de l’ingestion.
* **Ingestion des modifications au niveau des lignes.** Prend en charge les modifications de données granulaires, notamment les upserts et les suppressions avec contrôle de précision.
* **Relations de schéma.** Active les relations de clés étrangères et primaires entre les jeux de données via des descripteurs.
* **Gestion des événements dans le désordre.** Les processus modifient les événements à l’aide des descripteurs de version et d’horodatage, même s’ils arrivent hors séquence.
* **Intégration d’entrepôt direct.** Se connecte aux entrepôts de données cloud pris en charge pour la synchronisation des modifications en temps réel.

Utilisez Data Mirror pour ingérer des modifications directement à partir de vos systèmes sources, appliquer l’intégrité des schémas et rendre les données disponibles pour les workflows d’analyse, d’orchestration des parcours et de conformité. Data Mirror élimine les processus ETL en amont complexes et accélère la mise en œuvre en permettant la mise en miroir directe des modèles de base de données existants. Cette élimination peut améliorer la gouvernance des données grâce à un contrôle précis des suppressions et des opérations d’hygiène des données.

Consultez également la [documentation d’Experience Platform sur Data Mirror](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}.

## Data Mirror pour Customer Journey Analytics

>[!NOTE]
>
>Data Mirror est une fonctionnalité actuellement en version bêta qui prend en charge la synchronisation des données de certains entrepôts de données à l’aide de la capture de données de modification (CDC) pour analyse dans Customer Journey Analytics.<br/>Cette fonctionnalité sera disponible pour Customer Journey Analytics le 18 juin 2026. Reportez-vous à la Description du produit applicable pour comprendre comment cela pourrait affecter la consommation limite d’ingestion annuelle à l’avenir. Veuillez noter que votre organisation continuera à avoir accès à la fonctionnalité lorsque Data Mirror passera de la version bêta à la disponibilité générale.
>

Experience Platform Data Mirror for Customer Journey Analytics est disponible pour certaines solutions natives d’entrepôt de données ([!DNL Azure Databricks], [!DNL Google BigQuery] et [!DNL Snowflake]). La version Customer Journey Analytics d’Experience Platform Data Mirror nécessite la configuration appropriée des applications ou composants suivants :

* [Solutions natives de l’entrepôt de données](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>Guide de démarrage rapide de [Data Mirror : mise en miroir et utilisation des données relationnelles](relational.md)
>[Data Mirror (documentation Experience Platform)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[Schémas relationnels (documentation Experience Platform)](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/relational)
