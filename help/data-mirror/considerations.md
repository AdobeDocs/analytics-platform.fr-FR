---
title: Considérations relatives à Data Mirror
description: Comprenez les points supplémentaires à prendre en compte lorsque vous souhaitez synchroniser les données entre les solutions natives d’entrepôt de données et Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
hide: true
source-git-commit: 664d14beaa6bc8b01169cef9d50b2ca3a2de44d8
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 1%

---

# Considérations relatives à Experience Platform Data Mirror

Cet article décrit les facteurs à prendre en compte lors de la configuration de jeux de données Data Mirror.

## Nouvelle colonne dans le tableau source

Lorsqu’une nouvelle colonne est ajoutée à une table source dans un jeu de données mis en miroir compatible avec CDC, cette modification peut déclencher des mises à jour pour toutes les lignes existantes. Ces mises à jour sont traitées sous forme de modifications par le biais du CDC, qui :

* Peut se comporter comme une réécriture de table complète en progressant.
* Peut augmenter considérablement le volume d’ingestion, ce qui peut entraîner un dépassement de vos droits d’ingestion par la mise à jour.

Stratégie recommandée pour les colonnes du tableau source :

* Assurez-vous que toutes les colonnes pertinentes sont définies initialement.
* Mappez chaque colonne dont vous pensez avoir besoin au départ.
* Si une nouvelle colonne est identifiée comme nécessaire, supprimez le jeu de données actuel et configurez à nouveau le connecteur avec la colonne mise à jour. Cela permet de s’assurer que les données sont renvoyées plus efficacement et plus rapidement.

Cette stratégie :

* Évite une évolution coûteuse du schéma ultérieurement (mises à jour en masse lors de l’ajout de colonnes).
* Permet de mieux prévoir le volume des modifications par rapport à l’ajout ou la modification ultérieure des colonnes.
* Cela permet de limiter les coûts de calcul potentiels du côté de la base de données externe, car l’entrepôt de données peut interpréter la nouvelle colonne comme une mise à jour de toutes les lignes.

Pour gérer les nouvelles colonnes des tables de l’entrepôt de données externe, procédez comme suit :

1. Créez un schéma avec la colonne ajoutée.
1. Configurez un nouveau connecteur source qui introduit les données.
1. Chargez le renvoi de manière appropriée.
1. Utilisez les modifications du CDC à l’avenir.

Cette approche minimise l&#39;impact sur les deux parties.

## Privacy Service

Les demandes d’accès à des informations personnelles doivent se produire de la même manière que les demandes d’accès à des informations personnelles sont traitées aujourd’hui pour les schémas non relationnels, car les demandes d’accès à des informations personnelles sont indifférentes à la structure des données.

Les données mises en miroir à partir d’un schéma relationnel externe font alors partie de l’écosystème Adobe et peuvent être partagées dans l’ensemble de cet écosystème, par exemple via la publication d’audiences Customer Journey Analytics. L’envoi d’une demande d’accès à des informations personnelles garantit que les identités et les données associées sont correctement gérées dans tout l’écosystème Adobe.

Par conséquent, les demandes d’accès à des informations personnelles ne doivent pas être limitées au jeu de données mis en miroir, mais doivent également impliquer des mises à jour des données sources dans la base de données externe.

## Comportement en matière d&#39;hygiène

Le service d’hygiène fonctionne sur des *identités principales*, mais les tables de la base de données externe mises en miroir ont des *clés principales* et non des identités principales.

La différence entre les identités principales et les clés primaires a pour conséquence que les suppressions d’hygiène ne peuvent pas être exécutées directement sur ces tables relationnelles. Par conséquent, vous devez :

* Supprimez les données dans leurs propres tables source au sein de la solution Data Warehouse et assurez-vous que les opérations de suppression sont effectuées via CDC (ou la colonne de modification manuelle).
* Envoyez des demandes d’hygiène et de confidentialité dans Adobe pour tous les jeux de données basés sur XDM en aval avec des informations d’identité (par exemple : vues Customer Journey Analytics, jeux de données Real-Time Customer Data Platform, jeux de données spécifiques à Adobe Journey Optimizer, etc.).

La différence entre l’identité principale et la clé principale introduit un modèle de responsabilité partagée :

* Adobe traite l’hygiène là où les identités sont présentes.
* En tant que client, c’est à vous qu’il revient d’aligner vos propres processus d’hygiène dans la base de données source avec les demandes d’hygiène envoyées à Adobe.

## Différences de gouvernance

Dans XDM [schémas](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition) et les concepts sous-jacents tels que [groupes de champs](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition#field-group), un [champ](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition#field) défini au sein d’un groupe de champs propage ses libellés dans tous les jeux de données où le groupe de champs est utilisé. Par exemple, un champ d’e-mail `emailID` dans un `identities` de groupe de champs est libellé de la même manière dans tous les jeux de données où le `identities` de groupe de champs est utilisé.

Dans un schéma relationnel, le nom d’une colonne est indépendant. Une colonne nommée `email` dans le tableau `customers` est indépendante et distincte d&#39;une colonne nommée `email` dans un tableau `prospects`. Ce comportement implique que les libellés (tels que les libellés d’utilisation DULE et les politiques) doivent être appliqués individuellement aux champs des jeux de données mis en miroir. En fonction de l’exemple ci-dessus, vous devez appliquer des libellés à la fois au champ `email` du jeu de données `customers` et au champ `email` du jeu de données `prospects`.

La différence de gouvernance a l’impact suivant :

* Une gouvernance et une configuration plus manuelles fonctionnent pour vous en tant que client.
* Vous aurez peut-être besoin de conseils explicites. Vous ne supposez donc pas que l’étiquetage unique via des groupes de champs est suffisant pour une bonne gouvernance.

## Groupement

Les schémas relationnels présentent les considérations suivantes en ce qui concerne le groupement :

* Le groupement basé sur les graphiques est partiellement pris en charge. Les schémas relationnels ne peuvent pas être activés pour le profil/la contribution au graphique.
* Le groupement basé sur les champs est entièrement pris en charge.


## Clés système et champs

Les considérations suivantes s’appliquent aux clés et champs système :

* La clé primaire, le descripteur de version et le descripteur d’horodatage doivent être des champs de niveau racine dans le schéma XDM relationnel. Utilisez le [mappage de champs](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema) lors de l’ingestion pour prendre en charge cette exigence.
* Vous pouvez omettre les champs sources appropriés pendant la [phase de mappage](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema).
