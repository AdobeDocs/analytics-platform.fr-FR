---
title: Configuration d’Experience Platform
description: Découvrez comment configurer des schémas et des jeux de données pour Experience Platform Data Mirror for Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
source-git-commit: b2a13524760f9d466696534bc8b9691f3b4dfb8a
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 3%

---

# Configuration d’Experience Platform

{{release-limited-testing}}

Experience Platform Data Mirror for Customer Journey Analytics nécessite la configuration appropriée de plusieurs composants Experience Platform :

* schéma
* jeu de données
* connecteur source

Vous trouverez ci-dessous des détails à prendre en compte lors de la configuration de chacun de ces composants.

## Schéma

Vous devez créer un [schéma relationnel](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/relational){target="_blank"} qui est la table native de l’entrepôt de données que vous souhaitez mettre en miroir. Lorsque vous créez le schéma relationnel, assurez-vous que les exigences suivantes sont remplies :

* Lorsque vous êtes invité à indiquer le type de schéma relationnel, veillez à sélectionner l’option manuelle .
* Sélectionnez le schéma approprié pour le type de données. Notez qu’Experience Platform Data Mirror est principalement utilisé pour les données de série temporelle (par exemple, les données d’événement).

* Définir les champs de votre schéma et leurs attributs
* Configurez les attributs requis pour les champs dans un schéma relationnel :

   * clé primaire
   * identifiant de version
   * identifiant de date et heure (pour les données de série temporelle).

## Jeu de données

Vous pouvez configurer d’avance un jeu de données pour votre schéma ou créer un jeu de données lors de la configuration de votre connecteur source.
Lorsque vous créez un jeu de données à l’avance ou sélectionnez un jeu de données, assurez-vous que les données utilisent un [schéma](#schema) relationnel que vous avez créé précédemment.


## Connecteur source

Pour configurer le connecteur source vers les solutions natives d’entrepôt de données prises en charge, utilisez le workflow Sources qui vous guide tout au long de la configuration. Ce workflow comprend les étapes suivantes :

### Authentification

Pour l’authentification par rapport à la solution native d’entrepôt de données prise en charge, consultez la documentation Experience Platform appropriée :

* [briques de données Azure](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/snowflake)


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
>[Data Mirror (documentation Experience Platform)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[Schémas relationnels (documentation Experience Platform)](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/relational)
