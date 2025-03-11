---
title: Analyse du Parcours cross-canal
description: Analysez et obtenez des informations à partir des interactions des clients sur lʼensemble du parcours client.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases, Cross-Channel Analysis
role: User
source-git-commit: 5e80e68c6b5d3dca19dae21c6719b040b28afaf9
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 68%

---

# Analyse cross-canal {#cross-channel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-additional-datasets"
>title="Ajouter des jeux de données supplémentaires à votre connexion"
>abstract="Après avoir ajouté des données à un jeu de données dans Adobe Experience Platform, vous pouvez ajouter ce jeu de données à votre connexion dans Customer Journey Analytics. Assurez-vous que, lors de l’ajout de données provenant d’autres canaux, elles respectent le schéma utilisé par votre organisation.<br><br>Chaque jeu de données que vous ajoutez nécessite un travail considérable, en particulier pour s’assurer que l’identifiant unique existe pour chaque événement et que la structure de données globale est conforme au schéma personnalisé de votre organisation. La création de ce workflow peut nécessiter une coordination entre de nombreuses équipes de votre entreprise, sur plusieurs mois."

<!-- markdownlint-enable MD034 -->

L’analyse cross-canal permet d’obtenir une vue consolidée unique du comportement des clients sur différents canaux en unifiant les données de diverses propriétés web, mobiles et hors ligne. Vous pouvez, par exemple, vous servir de cette vue consolidée pour analyser les interactions clients réalisées sur les ordinateurs de bureau et les appareils mobiles. Cela vous permettra de mieux comprendre le comportement des clients et dʼextraire des informations afin dʼoptimiser les expériences numériques des clients. Vous pouvez également analyser les interactions clients sur lʼensemble des canaux, y compris numériques et hors ligne, comme les interactions avec le service dʼassistance et les achats en magasin, afin de mieux comprendre et optimiser le parcours client.

## Procédure de mise en œuvre

![Flux des étapes d’implémentation comme décrit dans cette section.](../assets/cca-architecture.png)

1. [Créez des schémas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=fr) pour les données à ingérer.
1. [Créez des jeux de données](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=fr) pour les données à ingérer.
1. [Ingestion de données dans Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=fr) :
   1. Données basées sur un événement ![event](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg) provenant d’un site web ou d’une application mobile via le connecteur source Edge Network ou Analytics.
   2. Données de profil ![profil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg) (par exemple, à partir d’un système CRM, d’une application de centre d’appels, d’une application de fidélité).
   3. Données de recherche ![recherche](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) (par exemple, nom de produit, catégorie d’un système d’information sur les produits).

1. Utilisez un identifiant d’espace de noms commun aux jeux de données. Utilisez [Assemblage](../../stitching/overview.md) pour élever tout jeu de données basé sur un événement ![actualisation des données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg) par rapport à la fourniture de l’identifiant commun sur chaque ligne. Notez que Customer Journey Analytics nʼutilise actuellement pas les services Experience Platform Profile ou Identity pour lʼassemblage.
1. Effectuez toute préparation de données personnalisée nécessaire afin de garantir une clé commune à tous les jeux de données de la série temporelle à ingérer dans Customer Journey Analytics.
1. Assignez un identifiant principal aux données de recherche qui peut être relié à un champ dans les données dʼévénement. Compte comme des lignes dans les licences.
1. Définissez le même identifiant principal pour les données de profil que l’identifiant principal des données d’événement.
1. [Créez une connexion](../../connections/overview.md) pour ingérer les jeux de données pertinents d’Experience Platform vers Customer Journey Analytics.
1. [Créez une vue de données](/help/data-views/create-dataview.md) sur la connexion pour sélectionner les dimensions et mesures spécifiques à inclure dans la vue. Les paramètres d’attribution sont également configurés dans la vue de données. Ces paramètres sont calculés au moment du rapport.
1. [Créez un projet](/help/analysis-workspace/home.md) pour configurer des tableaux de bord et des rapports dans Analysis Workspace.

## Considérations

Lors de la création de ce processus, veillez à tenir compte des points suivants.

* L’analyse des données sur l’ensemble des canaux nécessite le même espace de noms d’identifiant pour chaque enregistrement.
* Le processus d’union de jeux de données disparates nécessite une clé personne/entité principale commune dans les jeux de données.
* Les unions basées sur des clés secondaires ne sont actuellement pas prises en charge.
* Le processus d’assemblage permet de recomposer les identités dans les lignes en fonction des informations d’ID transitoires (tels qu’un ID d’authentification) à partir des enregistrements partageant le même ID persistant. Cela permet de résoudre des enregistrements disparates en un seul ID assemblé pour une analyse au niveau de la personne, plutôt qu’au niveau de l’appareil ou du cookie.
* Les objets et les attributs du même champ XDM fusionnent en une dimension dans Customer Journey Analytics. Pour fusionner plusieurs attributs de différents jeux de données dans la même dimension de Customer Journey Analytics, les jeux de données doivent référencer le même champ ou schéma XDM.

