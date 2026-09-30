---
description: Découvrez comment les données de l’IA dédiée aux clients d’Adobe Experience Platform s’intègrent à Workspace dans Customer Journey Analytics.
title: Intégrer les données de l’IA dédiée aux clients
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
feature: Experience Platform Integration
autotag-review: '2026-05-19T09:14:55.236Z'
TQID: 'https://experienceleague.adobe.com/4SG79HyhFS5kr-kXXVGb-cTI8j3St6CwztOW-x1xXi8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: cbde176d-5423-4c67-8a87-bc8faefd3a44
    internal-label: Customer AI integration
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 93%
---
# Intégrer les données de l’IA dédiée aux clients

{{release-limited-testing}}

L’[IA dédiée aux clients](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=fr), en tant que composant des services Adobe Experience Platform intelligents, permet aux spécialiste marketing de générer des prédictions client au niveau individuel.

À l’aide de facteurs d’influence, Customer AI peut vous indiquer ce qu’un client est susceptible de faire et pourquoi. De plus, les spécialistes marketing peuvent tirer parti des prédictions et des informations de Customer AI pour personnaliser les expériences client en diffusant les offres et les messages les plus appropriés.

L’IA dédiée aux clients repose sur des données comportementales individuelles et sur des données de profil pour l’application de scores de propension. L’IA dédiée aux clients est flexible dans la mesure où elle peut utiliser plusieurs sources de données, notamment Adobe Analytics, Adobe Audience Manager, des données d’événement d’expérience client et des données d’événement d’expérience. Si vous utilisez le connecteur source Experience Platform pour importer les données Adobe Audience Manager et Adobe Analytics, le modèle sélectionne automatiquement les types d’événements standard pour entraîner et noter le modèle. Si vous importez votre propre jeu de données d’événement d’expérience sans types d’événement standard, tous les champs pertinents devront être mappés en tant qu’événements personnalisés ou attributs de profil si vous souhaitez les utiliser dans le modèle. Vous pouvez le faire à l’étape de configuration de l’IA dédiée aux clients dans Experience Platform.

L’IA dédiée aux clients peut s’intégrer à Customer Journey Analytics dans la mesure où les jeux de données compatibles avec l’IA dédiée aux clients peuvent être exploités dans les vues de données et les rapports de Customer Journey Analytics. Vous pouvez :

* **suivre les scores de propension pour un segment d’utilisateurs et d’utilisatrices au fil du temps** ;
  * Cas pratique : comprendre la probabilité de conversion des clientes et clients d’un segment spécifique.
  * Exemple : une personne spécialisée dans le marketing d’une chaîne d’hôtels souhaite comprendre la probabilité qu’un client ou une cliente de l’hôtel achète un billet de spectacle pour la salle de concert de l’hôtel.
* **analyser les événements de succès ou les attributs associés aux scores de propension** ;
  * Cas d’utilisation : comprendre les attributs ou les événements de succès associés aux scores de propension.
  * Exemple : une personne spécialisée dans le marketing d’une chaîne d’hôtels souhaite comprendre comment les achats de billets de spectacle pour la salle de concert d’un hôtel sont associés aux scores de propension.
* **suivre le flux d’entrée pour la propension des clientes et clients sur différentes exécutions de scores** ;
  * Cas d’utilisation : comprendre les personnes qui étaient initialement des utilisateurs et utilisatrices à faible propension et qui, au fil du temps, sont devenues des utilisateurs et utilisatrices à forte propension.
  * Exemple : une personne spécialisée dans le marketing d’une chaîne d’hôtels souhaite savoir les clientes et clients d’hôtels qui ont été initialement identifiés comme des clientes et clients ayant une faible propension à acheter un billet de spectacle, mais qui sont devenus au fil du temps des clientes et clients ayant une forte propension à acheter un billet de spectacle.
* **examiner la répartition de la propension** ;
  * Cas d’utilisation : comprendre la distribution des scores de propension pour plus de précision dans la définition des segments.
  * Exemple : un distributeur souhaite lancer une promotion spécifique offrant une remise de 50 $ sur un produit. Il se peut qu’il souhaite n’exécuter qu’une promotion très limitée en raison du budget, etc. Ils analysent les données et décident de ne cibler que les plus de 80 % de leurs clients.
* **examiner la propension pour accomplir une action visant une cohorte particulière au fil du temps**.
  * Cas d’utilisation : suivre une cohorte spécifique au fil du temps.
  * Exemple : un responsable marketing d’une chaîne d’hôtels souhaite suivre dans le temps le niveau Bronze par rapport au niveau Argent, ou le niveau Argent par rapport au niveau Or. Ensuite, elle peut voir la propension de chaque cohorte à réserver l’hôtel au fil du temps.

Pour intégrer concrètement les données de l’IA dédiée aux clients à Customer Journey Analytics, procédez comme suit :

>[!NOTE]
>
>Certaines des étapes sont effectuées dans Adobe Experience Platform avant d’utiliser la sortie dans Customer Journey Analytics.


## Étape 1 : Configurer une instance d’IA dédiée aux clients

Une fois vos données préparées et vos informations d’identification et schémas en place, commencez par suivre le guide [Configurer une instance IA dédiée aux clients](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html) dans Adobe Experience Platform.

## Étape 2 : Configurer une connexion Customer Journey Analytics aux jeux de données de l’IA dédiée aux clients

Dans Customer Journey Analytics, vous pouvez désormais [établir une ou plusieurs connexions](/help/connections/create-connection.md) aux jeux de données Experience Platform créés pour l’IA dédiée aux clientes et clients. Chaque prédiction, telle que « Probabilité de mise à niveau du compte », équivaut à un jeu de données. Ces jeux de données s’affichent avec le préfixe « Customer AI Scores in EE Format – name_of_application ».

>[!IMPORTANT]
>
>Chaque instance de l’IA dédiée aux clients comporte deux jeux de données de sortie si le bouton (bascule) est activé pour permettre l’utilisation des scores dans Customer Journey Analytics lors de la configuration à l’étape 1. Un jeu de données de sortie apparaît au format XDM Profil et un autre au format XDM Événement d’expérience.

![Scores CAI](assets/cai-scores.png)

![Établir une connexion](assets/create-conn.png)

Voici un exemple de schéma XDM que Customer Journey Analytics importerait dans le cadre d’un jeu de données existant ou nouveau :

![Schéma CAI](assets/cai-schema.png)

(Notez que l’exemple est un jeu de données de profil ; le même ensemble d’objets de schéma ferait partie d’un jeu de données d’événement d’expérience dont Customer Journey Analytics s’emparerait. Le jeu de données Événement d’expérience inclurait des horodatages comme la date du score.) Chaque client noté dans ce modèle est associé à un score, une date de score, etc.

## Étape 3 : Créer des vues de données basées sur ces connexions

Dans Customer Journey Analytics, vous pouvez maintenant [créer des vues de données](/help/data-views/create-dataview.md) avec les dimensions (score, date de score, probabilité, etc.) et les mesures introduites dans le cadre de la connexion que vous avez établie.

![Créer une fenêtre de vue de données](assets/create-dataview.png)

## Étape 4 : Créer des rapports sur les scores de l’IA dédiée aux clients (CAI) dans Workspace

Dans Customer Journey Analytics Workspace, créez un nouveau projet et ajoutez des visualisations.

### Établir une tendance des scores de propension

Voici un exemple de projet Workspace avec des données CAI qui calcule la tendance des scores de propension d’un segment d’utilisateurs au fil du temps, sous la forme d’un graphique en barres empilées :

![Intervalles de scores](assets/workspace-scores.png)

### Tableau avec codes de motif

Voici un tableau qui présente les codes de motif pour lesquels un segment présente une propension élevée ou faible :

![Codes de motif](assets/reason-codes.png)

### Flux d’entrée pour la propension des clients

Ce diagramme de flux présente le flux d’entrée de la propension des clients sur différentes exécutions de scores :

![Flux d’entrée](assets/flow.png)

### Répartition des scores de propension

Ce graphique en barres présente la répartition des scores de propension :

![Répartition](assets/distribution.png)

### Superpositions de propension

Ce diagramme de Venn présente les superpositions de propension sur différentes exécutions de scores :

![Superpositions de propension](assets/venn.png)
