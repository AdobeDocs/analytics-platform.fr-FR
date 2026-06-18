---
title: Configuration d’Experience Platform
description: Découvrez comment configurer des schémas et des jeux de données pour Experience Platform Data Mirror for Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
autotag-review: '2026-05-19T07:18:47.007Z'
TQID: 'https://experienceleague.adobe.com/nAfDMtaQvsVRAEm31fRwleirW8LaS-yS0tGTdReux0Y'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 571
ht-degree: 6%

---

# Configuration d’Experience Platform

Experience Platform Data Mirror for Customer Journey Analytics nécessite la configuration appropriée de plusieurs composants Experience Platform :

* schéma
* Jeu de données
* connecteur source

Vous trouverez ci-dessous des détails à prendre en compte lors de la configuration de chacun de ces composants.

## Schéma

Vous devez créer un [schéma relationnel](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/relational){target="_blank"} qui est la table native de l’entrepôt de données que vous souhaitez mettre en miroir. Lorsque vous créez le schéma relationnel, assurez-vous que les exigences suivantes sont remplies :

* Lorsque vous êtes invité à indiquer le type de schéma relationnel, veillez à sélectionner l’option manuelle .
* Sélectionnez le schéma approprié pour le type de données. Notez qu’Experience Platform Data Mirror est principalement utilisé pour les données de série temporelle (par exemple, les données d’événement), mais peut également être utilisé pour les données basées sur des enregistrements (recherche et profil).

* Définir les champs de votre schéma et leurs attributs
* Configurez les attributs requis pour les champs dans un schéma relationnel :

   * **Clé de Principal**.
   * **Descripteur de version**, qui doit être configuré sous la forme d’un numéro séquentiel (type de champ Entier) ou d’un type de champ Date et heure. Lorsque vous utilisez un type de champ DateTime, le descripteur de version définit la date et l’heure d’une modification des données, par exemple pour contenir une date et une heure de la dernière modification.
   * **descripteur d’horodatage** (pour les données de série temporelle), qui définit l’horodatage non modifiable au moment où un événement est capturé. Le descripteur d’horodatage n’est pas obligatoire pour un schéma relationnel basé sur des enregistrements.



## Jeu de données

Vous pouvez configurer d’avance un jeu de données pour votre schéma ou créer un jeu de données lors de la configuration de votre connecteur source.
Lorsque vous créez un jeu de données à l’avance ou sélectionnez un jeu de données, assurez-vous que les données utilisent un [schéma](#schema) relationnel que vous avez créé précédemment.


## Connecteur source

Pour configurer le connecteur source vers les solutions natives d’entrepôt de données prises en charge, utilisez le workflow Sources qui vous guide tout au long de la configuration. Ce workflow comprend les étapes suivantes :

### Authentification

Pour l’authentification par rapport à la solution native d’entrepôt de données prise en charge, consultez la documentation Experience Platform appropriée :

* [Azure Databricks](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/databases/snowflake)


### Sélectionner les données

Une fois la connexion à votre solution native d’entrepôt de données établie, sélectionnez la table dans la solution native d’entrepôt de données que vous souhaitez utiliser pour le miroir de données. Une fois sélectionné, un aperçu du contenu des données s’affiche.


### Détails du flux de données

Assurez-vous d’activer la capture des données de modification. Un panneau d’informations s’affiche, expliquant les exigences relatives à la capture de données de modification.

Spécifiez un jeu de données nouveau ou existant basé sur le schéma relationnel que vous avez créé précédemment. Spécifiez et sélectionnez d’autres options dans l’interface Détails du flux de données.


### Mappage

Mappez les champs de la table dans la solution native de l’entrepôt de données aux champs que vous avez spécifiés pour le schéma relationnel.


### Planification

Définissez une planification pour mettre en miroir les données du tableau dans la solution native de l’entrepôt de données vers le jeu de données dans Experience Platform.


### Réviser

Examinez les paramètres du connecteur source vers la solution native de l’entrepôt de données qui prend en charge la mise en miroir des données et la capture de données modifiée.


Une fois la configuration du connecteur source terminée, un flux de données est créé. À partir de ce moment, les modifications de données (insertions, mises à jour, suppressions) dans la solution native de l’entrepôt de données sont mises en miroir dans le jeu de données spécifié.


>[!MORELIKETHIS]
>
>Guide de démarrage rapide de [Data Mirror : mise en miroir et utilisation des données relationnelles](relational.md)
>[Data Mirror (documentation Experience Platform)](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/data-mirror/overview)
>[Schémas relationnels (documentation Experience Platform)](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/relational)
