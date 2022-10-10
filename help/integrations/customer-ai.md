---
description: Découvrez comment les données AEP Customer AI s’intègrent à Workspace dans CJA.
title: Intégration des données Customer AI à CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: 305bcd46df033f2f69a1161657d8d46793187225
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Intégration des données Customer AI à CJA

>[!NOTE]
>
>Cette fonctionnalité se trouve actuellement dans [test limité](/help/release-notes/releases.md) et non disponibles en général.

L’[IA dédiée aux clients](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=fr), en tant que composant des services Adobe Experience Platform intelligents, permet aux professionnel du marketing de générer des prédictions client au niveau individuel.

À l’aide de facteurs d’influence, Customer AI peut vous indiquer ce qu’un client est susceptible de faire et pourquoi. De plus, les professionnels du marketing peuvent tirer parti des prédictions et des informations de Customer AI pour personnaliser les expériences client en diffusant les offres et les messages les plus appropriés.

L’IA dédiée aux clients repose sur des données comportementales individuelles et sur des données de profil pour le score de propension. L’IA dédiée aux clients est flexible dans la mesure où elle peut intégrer plusieurs sources de données, notamment Adobe Analytics, Adobe Audience Manager, des données d’événement d’expérience client et des données d’événement d’expérience. Si vous utilisez le connecteur source Experience Platform pour importer les données Adobe Audience Manager et Adobe Analytics, le modèle sélectionne automatiquement les types d’événements standard pour entraîner et noter le modèle. Si vous importez votre propre jeu de données d’événement d’expérience sans types d’événement standard, tous les champs pertinents devront être mappés en tant qu’événements personnalisés ou attributs de profil si vous souhaitez les utiliser dans le modèle. Vous pouvez le faire à l’étape de configuration de l’IA dédiée aux clients dans Experience Platform.

L’IA dédiée aux clients s’intègre à Customer Journey Analytics (CJA) dans la mesure où les jeux de données compatibles avec elle peuvent être utilisés dans les vues de données et les rapports dans CJA. Avec cette intégration, vous pouvez :

* **Suivre les scores de propension pour un segment d’utilisateurs au fil du temps**. Exemple de cas pratique : Quelle est la probabilité qu&#39;un client de l&#39;hôtel achète un ticket de spectacle sur la salle de concert de l&#39;hôtel ?
* **Analyser les événements ou attributs de succès associés aux scores de propension**.Exemple de cas d’utilisation : Je veux comprendre les attributs ou les événements de succès associés aux scores de propension.
* **Suivez le flux d’entrée pour la propension des clients sur différentes exécutions de scores**. Exemple de cas pratique : J&#39;aimerais comprendre les personnes qui étaient initialement des utilisateurs à faible propension et qui, au fil du temps, sont devenus des utilisateurs à forte propension. &#x200B;
* **Examiner la répartition de la propension**. Cas pratique : J’aimerais comprendre la distribution des scores de propension afin d’être plus précis avec mes segments. &#x200B;Exemple : un détaillant souhaite exécuter une promotion spécifique de 50 $ sur un produit. Il est possible qu’il souhaite n’exécuter qu’une promotion très limitée en raison du budget, etc. Il analyse les données et décide de ne cibler que les clients atteignant au moins un score de 80 %.
* **Examiner la propension pour accomplir une action visant une cohorte particulière au fil du temps**. Cas pratique : Je voudrais suivre une cohorte spécifique au fil du temps. Ce cas est similaire au premier, sauf que vous pouvez suivre une cohorte spécifique au fil du temps. Exemple pour le domaine de l’hébergement : un spécialiste du marketing peut comparer son niveau bronze à son niveau argent ou encore son niveau argent par rapport à son niveau or au fil du temps. Ensuite, il peut voir la propension de chaque cohorte à réserver l’hôtel au fil du temps.

Certaines des étapes sont effectuées dans Adobe Experience Platform avant d’utiliser la sortie dans CJA.

## Étape 1 : Configurer une instance IA dédiée aux clients

Une fois vos données préparées et vos informations d’identification et schémas en place, commencez par suivre le guide [Configurer une instance IA dédiée aux clients](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=fr) dans Adobe Experience Platform.

## Étape 2 : Configurer une connexion CJA à des jeux de données IA dédiée aux clients

Dans CJA, vous pouvez désormais [établir une ou plusieurs connexions](/help/connections/create-connection.md) aux jeux de données Experience Platform créés pour l’IA dédiée aux clients. Chaque prédiction, telle que « Probabilité de mise à niveau du compte » équivaut à un jeu de données. Ces jeux de données s’affichent avec le préfixe « Scores de l’IA dédiée aux clients au format EE - nom_de_l’application ».

>[!IMPORTANT]
>
>Chaque instance IA dédiée aux clients possède deux jeux de données de sortie si le bouton (bascule) est activé pour activer les scores pour CJA lors de la configuration à l’étape 1. Un jeu de données de sortie apparaît au format Profil et un autre au format XDM Experience Event.

![Scores CAI](assets/cai-scores.png)

![Établir une connexion](assets/create-conn.png)

Voici un exemple de schéma XDM que CJA apporterait dans le cadre d’un jeu de données existant ou nouveau :

![Schéma CAI](assets/cai-schema.png)

(Notez que l’exemple est un jeu de données de profil ; le même ensemble d’objets de schéma ferait partie d’un jeu de données d’événement d’expérience dont CJA s’emparerait. Le jeu de données Événement d’expérience inclurait des horodatages comme la date du score.) Chaque client noté dans ce modèle aurait un score, une date de score, etc.  associé.

## Étape 3 : Créer des vues de données basées sur ces connexions

Dans CJA, vous pouvez maintenant [créer des vues de données](/help/data-views/create-dataview.md) avec les dimensions (score, date de score, probabilité, etc.) et les mesures introduites dans le cadre de la connexion que vous avez établie.

![Créer une vue de données](assets/create-dataview.png)

## Étape 4 : Établir des rapports sur les scores CAI dans Workspace

Dans CJA Workspace, créez un nouveau projet et extrayez des visualisations.

### Établir une tendance des scores de propension

Voici un exemple de projet Workspace avec des données CAI qui calcule la tendance des scores de propension d’un segment d’utilisateurs au fil du temps, sous la forme d’un graphique à barres empilées :

![Intervalles de scores](assets/workspace-scores.png)

### Tableau avec codes de motif

Voici un tableau qui présente les codes de motif pour lesquels un segment présente une propension élevée ou faible :

![Codes de motif](assets/reason-codes.png)

### Flux d’entrée pour la propension des clients

Ce diagramme de flux présente le flux d’entrée de la propension des clients sur différentes exécutions de scores :

![Flux d’entrée](assets/flow.png)

### Répartition des scores de propension

Ce graphique à barres présente la répartition des scores de propension :

![Répartition](assets/distribution.png)

### Superpositions de propension

Ce diagramme de Venn présente les superpositions de propension sur différentes exécutions de scores :

![Superpositions de propension](assets/venn.png)
