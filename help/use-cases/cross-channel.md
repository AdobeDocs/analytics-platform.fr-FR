---
title: Analyse des Parcours cross-canal
description: Analysez et obtenez des informations à partir des interactions des clients sur lʼensemble du parcours client.
source-git-commit: a6c6620a4f4118755509e534d7d6a12bf08b4b67
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 6%

---


# Analyse des Parcours cross-canal

disposer d’une vue consolidée unique du comportement des clients sur différents canaux en unifiant les données de diverses propriétés web, mobiles et hors ligne ; Vous pouvez, par exemple, utiliser cette vue consolidée pour analyser les interactions des clients sur les ordinateurs de bureau et les appareils mobiles afin de comprendre le comportement des clients et d’extraire des informations afin d’optimiser les expériences client numériques. Vous pouvez également analyser les interactions des clients entre les canaux, y compris numériques et hors ligne, comme les interactions d’assistance et les achats en magasin, afin de mieux comprendre et optimiser le parcours client.

## Architecture

![Architecture cross-canal](assets/cross-channel-architecture.svg)

## Procédure de mise en œuvre

1. [Créez ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=fr) des schémas pour les données à ingérer.
1. [Créez ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html) des jeux de données pour les données à ingérer.
1. [Ingestion de données dans Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html).
1. Utilisez un identifiant d’espace de noms commun à tous les jeux de données ou utilisez [Analyses cross-canal](/help/connections/cca/overview.md) pour lier les personnes. Notez que Customer Journey Analytics n’utilise actuellement pas les services Profile ou Identity Experience Platform pour le groupement.
1. Effectuez toute préparation de données personnalisée pour garantir une clé commune à tous les jeux de données de série temporelle à ingérer dans Customer Journey Analytics.
1. Donnez aux données de recherche un Principal ID qui peut se joindre à un champ dans les données d’événement. Compte comme des lignes dans les licences.
1. Définissez le même identifiant Principal pour les données de profil que l’identifiant Principal des données d’événement.
1. Configurez une connexion aux données pour ingérer des données de l’Experience Platform vers Customer Journey Analytics.
1. [Créez une ](/help/data-views/create-dataview.md) vue de données sur la connexion pour sélectionner les dimensions et mesures spécifiques à inclure dans la vue. Les paramètres d’attribution et d’attribution sont également configurés dans la vue de données. Ces paramètres sont calculés au moment du rapport.
1. Créez un projet pour configurer des tableaux de bord et des rapports dans Analysis Workspace.

## Considérations

Lors de la création de ce workflow, veillez à tenir compte des points suivants.

* L’analyse des données entre les canaux nécessite le même espace de noms d’ID pour chaque enregistrement.
* Le processus d’union de jeux de données disparates nécessite une clé personne/entité Principale commune dans les jeux de données.
* Les unions basées sur des clés Secondaires ne sont actuellement pas prises en charge.
* Le processus de combinaison d’identités basé sur les champs permet de recomposer les identités dans les lignes en fonction des enregistrements d’identifiants transitoires suivants, tels qu’un identifiant d’authentification. Cela permet de résoudre des enregistrements disparates sur un seul ID pour une analyse au niveau de la personne plutôt qu’au niveau de l’appareil ou du cookie.
* Les objets et les attributs du même champ XDM fusionnent en une dimension dans Customer Journey Analytics. Pour fusionner plusieurs attributs de différents jeux de données dans la même dimension de Customer Journey Analytics, les jeux de données doivent référencer le même champ ou schéma XDM.
