---
title: Considérations relatives à Data Mirror
description: Comprenez les points supplémentaires à prendre en compte lorsque vous souhaitez synchroniser les données entre les solutions natives d’entrepôt de données et Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
hide: true
source-git-commit: 93f38f57021bf66cacd700ce6fbc46338fd6a034
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 1%

---

# Considérations relatives à Experience Platform Data Mirror

Cet article décrit les facteurs à prendre en compte lors de la configuration de jeux de données Data Mirror.

## Nouvelle colonne dans le tableau source

Lorsqu’une nouvelle colonne est ajoutée à une table source dans un jeu de données mis en miroir compatible avec CDC, cette modification peut déclencher des mises à jour pour toutes les lignes existantes. Ces mises à jour sont traitées sous forme de modifications par le biais du CDC, qui :

* Peut se comporter comme une réécriture de table complète du point de vue des coûts.
* peut augmenter considérablement le volume d’ingestion, en particulier avec une tarification future *multiplicateur de changement* (par exemple, les opérations de fusion peuvent être facturées à des taux plus élevés) ;

Stratégie recommandée pour les colonnes du tableau source :

* Assurez-vous que la plupart, voire toutes les colonnes pertinentes sont définies initialement.
* Mappez chaque colonne dont vous pensez avoir besoin au départ.

Cette stratégie :

* Évite une évolution coûteuse du schéma ultérieurement (mises à jour en masse lors de l’ajout de colonnes).
* Permet de mieux prévoir le volume des modifications par rapport à l’ajout ou la modification ultérieure des colonnes.
* Cela peut entraîner des coûts de calcul supplémentaires du côté de la base de données externe, car l’entrepôt de données peut interpréter toutes les colonnes comme des mises à jour.

Pour gérer les nouvelles colonnes des tables de l’entrepôt de données externe, procédez comme suit :

1. Créez un schéma avec la colonne ajoutée.
1. Configurez un nouveau connecteur source qui introduit les données.
1. Chargez le renvoi de manière appropriée.
1. Utilisez les modifications du CDC à l’avenir.

Cette approche minimise l&#39;impact sur les deux parties.

## Privacy Service

Les demandes d’accès à des informations personnelles doivent se produire de la même manière que les demandes d’accès à des informations personnelles sont traitées aujourd’hui pour les schémas non relationnels, car les demandes d’accès à des informations personnelles sont indifférentes à la structure des données.

Les données mises en miroir dans un jeu de données à partir de données externes basées sur un schéma relationnel font partie de l’écosystème Adobe et peuvent être partagées de différentes manières. Par exemple, via la publication d’audiences.

Par conséquent, les demandes d’accès à des informations personnelles ne doivent pas être limitées au jeu de données mis en miroir, mais doivent également impliquer des mises à jour des données sources dans la base de données externe.

## Comportement en matière d&#39;hygiène

Le service d’hygiène fonctionne sur des *identités principales*, mais les tables de la base de données externe mises en miroir ont des *clés principales* et non des identités principales.

La différence entre les identités principales et les clés primaires a pour conséquence que les suppressions d’hygiène ne peuvent pas être exécutées directement sur ces tables relationnelles. Par conséquent, vous devez :

* Supprimez les données dans leurs propres tables source au sein de la solution Data Warehouse et assurez-vous que les opérations de suppression sont effectuées via CDC (ou la colonne de modification manuelle).
* Envoyez des demandes d’hygiène et de confidentialité dans Adobe pour tous les jeux de données basés sur XDM en aval avec des informations d’identité (par exemple : vues Customer Journey Analytics, jeux de données Real-Time Customer Data Platform, jeux de données spécifiques à Adobe Journey Optimizer, etc.).

La différence entre l’identité principale et la clé principale introduit un modèle de responsabilité partagée :

* Adobe traite l’hygiène là où les identités sont présentes.
* En tant que client, c’est à vous qu’il revient d’aligner vos propres processus d’hygiène dans la base de données source sur les demandes d’hygiène envoyées à Adobe.

## Différences de gouvernance

Dans XDM [schémas](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition) et les concepts sous-jacents tels que [groupes de champs](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field-group), un [champ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field) défini au sein d’un groupe de champs propage ses libellés dans tous les jeux de données où le groupe de champs est utilisé. Par exemple, un champ d’e-mail `emailID` dans un `identities` de groupe de champs est libellé de la même manière dans tous les jeux de données où le `identities` de groupe de champs est utilisé.

Dans un schéma relationnel, le nom d’une colonne est indépendant. Une colonne nommée `email` dans le tableau `customers` est indépendante et distincte d&#39;une colonne nommée `email` dans un tableau `prospects`. Ce comportement implique que les libellés (tels que les libellés d’utilisation DULE et les politiques) doivent être appliqués individuellement aux champs des jeux de données mis en miroir. En fonction de l’exemple ci-dessus, vous devez appliquer des libellés à la fois au champ `email` du jeu de données `customers` et au champ `email` du jeu de données `prospects`.

La différence de gouvernance a l’impact suivant :

* Une gouvernance et une configuration plus manuelles fonctionnent pour vous en tant que client.
* Vous aurez peut-être besoin de conseils explicites. Vous ne supposez donc pas que l’étiquetage unique via des groupes de champs est suffisant pour une bonne gouvernance.
