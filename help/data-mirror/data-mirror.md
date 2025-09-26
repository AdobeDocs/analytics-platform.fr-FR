---
title: Présentation de Data Mirror
description: Comprendre comment synchroniser les données entre les solutions natives de l’entrepôt de données et Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: 4b11c98d24b131eb32040943e869132c8182747f
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 1%

---

# Présentation d’Experience Platform Data Mirror

{{release-limited-testing}}

Data Mirror est une fonctionnalité d’Experience Platform qui permet l’ingestion de modifications au niveau des lignes de bases de données externes dans le lac de données à l’aide de schémas basés sur des modèles. Il préserve les relations de données, applique l’unicité et prend en charge le contrôle de version sans nécessiter de processus d’extraction, de transformation et de chargement (ETL) en amont.

Utilisez Experience Platform Data Mirror pour synchroniser les insertions, les mises à jour et les suppressions (données modifiables) de solutions natives d’entrepôt de données externes ([!DNL Snowflake], [!DNL Azure Databricks] ou [!DNL Google BigQuery]) directement avec les données d’Experience Platform. Data Mirror vous aide à préserver la structure du modèle de base de données et l’intégrité des données lorsque vous importez des données dans Experience Platform.

## Fonctionnalités et avantages

Data Mirror offre les fonctionnalités essentielles suivantes pour la synchronisation des bases de données :

* **Application de la clé de Principal.** Garantit l’unicité dans les jeux de données et empêche les enregistrements en double lors de l’ingestion.
* **Ingestion des modifications au niveau des lignes.** Prend en charge les modifications de données granulaires, y compris les upserts et les suppressions avec contrôle de précision.
* **Relations de schéma.** Active les relations de clés étrangères et primaires entre les jeux de données par le biais de descripteurs.
* **Gestion des événements dans le désordre.Les processus** changent d’événement à l’aide de descripteurs de version et d’horodatage, même lorsqu’ils arrivent hors séquence.
* **Intégration d’entrepôt direct.** Se connecte aux entrepôts de données cloud pris en charge pour la synchronisation des modifications en temps réel.

Utilisez Data Mirror pour ingérer des modifications directement à partir de vos systèmes sources, appliquer l’intégrité des schémas et rendre les données disponibles pour les workflows d’analyse, d’orchestration des parcours et de conformité. Data Mirror élimine les processus ETL en amont complexes et accélère la mise en œuvre en permettant la mise en miroir directe des modèles de base de données existants. Cette élimination peut améliorer la gouvernance des données grâce à un contrôle précis des suppressions et des opérations d’hygiène des données.

Consultez également la [documentation d’Experience Platform sur Data Mirror](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}.

## Data Mirror pour Customer Journey Analytics

>[!NOTE]
>
>La fonctionnalité Experience Platform Data Mirror pour Customer Journey Analytics est disponible en version bêta **publique** jusqu’au 25 mars 2026.<br/><br/>Pendant la période bêta :<ul><li>Les mises à jour de capture de données modifiées (CDC) sont limitées à 10 millions de droits de modification de lignes par jour pour Customer Journey Analytics.</li><li>Les clients peuvent ingérer jusqu’à 2 millions de lignes de modification par jour dans le lac de données Adobe Experience Platform par le biais de connecteurs source.</li></ul><br/>Adobe se réserve le droit de résilier l’accès bêta à la fonctionnalité Experience Platform Data Mirror si votre organisation dépasse ces limites. <br/>Pour demander l’accès à cette fonctionnalité, contactez l’équipe de votre compte Adobe.
>

Experience Platform Data Mirror for Customer Journey Analytics est disponible pour certaines solutions natives d’entrepôt de données ([!DNL Azure Databricks], [!DNL Google BigQuery] et [!DNL Snowflake]). La version Customer Journey Analytics d’Experience Platform Data Mirror nécessite la configuration appropriée des applications ou composants suivants :

* [Solutions natives Data Warehouse](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>Guide de démarrage rapide de [Data Mirror : mise en miroir et utilisation de données basées sur des modèles](model-based.md)
>&#x200B;>[Data Mirror (documentation Experience Platform)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>&#x200B;>[Schémas basés sur des modèles (documentation Experience Platform)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/model-based)
