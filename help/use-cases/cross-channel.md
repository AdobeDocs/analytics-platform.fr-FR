---
title: Analyse du Parcours cross-canal
description: Analysez et obtenez des informations à partir des interactions des clients sur lʼensemble du parcours client.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
source-git-commit: 68ca5b1ee9d695f53b22c821cec481cc116dcdb3
workflow-type: ht
source-wordcount: '433'
ht-degree: 100%

---

# Analyse du Parcours cross-canal

Affichez une vue consolidée unique du comportement des clients sur plusieurs canaux, en procédant à lʼunification des données issues de différentes propriétés Web, mobiles et hors ligne. Vous pouvez, par exemple, vous servir de cette vue consolidée pour analyser les interactions clients réalisées sur les ordinateurs de bureau et les appareils mobiles. Cela vous permettra de mieux comprendre le comportement des clients et dʼextraire des informations afin dʼoptimiser les expériences numériques des clients. Vous pouvez également analyser les interactions clients sur lʼensemble des canaux, y compris numériques et hors ligne, comme les interactions avec le service dʼassistance et les achats en magasin, afin de mieux comprendre et optimiser le parcours client.

## Architecture

![Architecture cross-canal](assets/cross-channel-architecture.svg)

## Procédure de mise en œuvre

1. [Créez des schémas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=fr) pour les données à ingérer.
1. [Créez des jeux de données](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=fr) pour les données à ingérer.
1. [Ingestion de données dans Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=fr).
1. Utilisez un identifiant dʼespace de noms commun à tous les jeux de données ou utilisez la fonctionnalité dʼ[Analyse cross-canal](/help/connections/cca/overview.md) pour établir un lien entre les personnes. Notez que Customer Journey Analytics nʼutilise actuellement pas les services Experience Platform Profile ou Identity pour lʼassemblage.
1. Effectuez toute préparation de données personnalisée nécessaire afin de garantir une clé commune à tous les jeux de données de la série temporelle à ingérer dans Customer Journey Analytics.
1. Assignez un identifiant principal aux données de recherche qui peut être relié à un champ dans les données dʼévénement. Compte comme des lignes dans les licences.
1. Définissez le même identifiant principal pour les données de profil que l’identifiant principal des données d’événement.
1. Configurez une connexion aux données pour ingérer des données d’Experience Platform vers Customer Journey Analytics.
1. [Créez une vue de données](/help/data-views/create-dataview.md) sur la connexion pour sélectionner les dimensions et mesures spécifiques à inclure dans la vue. Les paramètres d’attribution sont également configurés dans la vue de données. Ces paramètres sont calculés au moment du rapport.
1. Créez un projet pour configurer des tableaux de bord et des rapports dans Analysis Workspace.

## Considérations

Lors de la création de ce processus, veillez à tenir compte des points suivants.

* L’analyse des données sur l’ensemble des canaux nécessite le même espace de noms d’identifiant pour chaque enregistrement.
* Le processus d’union de jeux de données disparates nécessite une clé personne/entité principale commune dans les jeux de données.
* Les unions basées sur des clés secondaires ne sont actuellement pas prises en charge.
* Le processus d’assemblage d’identités basé sur les champs permet de recomposer les identités dans les lignes en fonction des enregistrements d’identifiants transitoires suivants (identifiant d’authentification par exemple). Cela permet de résoudre des enregistrements disparates en un seul identifiant pour une analyse au niveau de la personne plutôt qu’au niveau de l’appareil ou du cookie.
* Les objets et les attributs du même champ XDM fusionnent en une dimension dans Customer Journey Analytics. Pour fusionner plusieurs attributs de différents jeux de données dans la même dimension de Customer Journey Analytics, les jeux de données doivent référencer le même champ ou schéma XDM.
