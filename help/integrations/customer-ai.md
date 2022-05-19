---
description: Découvrez comment AEP Customer AI s’intègre à Workspace dans CJA.
title: Intégration de Customer AI à CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: 5d22437ec6514196146283af311b6661c1f2e45b
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 9%

---

# Intégration de Customer AI à CJA

>[!NOTE]
>
>Cette fonctionnalité sera publiée le 25 mai 2022.

[Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en), dans le cadre des services intelligents de Adobe Experience Platform, permet aux marketeurs de générer des prédictions client au niveau individuel.

À l’aide de facteurs d’influence, Customer AI peut vous indiquer ce qu’un client est susceptible de faire et pourquoi. De plus, les professionnels du marketing peuvent tirer parti des prédictions et des informations de Customer AI pour personnaliser les expériences client en diffusant les offres et les messages les plus appropriés.

Customer AI analyse un ou plusieurs des jeux de données suivants pour prédire les scores de propension à l’attrition ou à la conversion :

* Données Adobe Analytics à l’aide du connecteur source Analytics
* Données Adobe Audience Manager à l’aide du connecteur source d’Audience Manager
* Jeu de données d’événement d’expérience (EE)
* Jeu de données d’événements d’expérience client (CEE)

Customer AI s’intègre à Customer Journey Analytics (CJA) dans la mesure où les jeux de données compatibles avec Customer AI peuvent être utilisés dans les vues de données et les rapports dans CJA.

## Processus

Certaines des étapes sont effectuées dans Adobe Experience Platform avant d’utiliser la sortie dans CJA.

### Étape 1 : Configuration d’une instance Customer AI

Une fois vos données préparées et vos informations d’identification et schémas en place, commencez par suivre la [Configuration d’une instance Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) guide.

### Étape 2 : Configurer une connexion CJA aux jeux de données Customer AI

Dans CJA, vous pouvez désormais [créer une ou plusieurs connexions](/help/connections/create-connection.md) aux jeux de données Experience Platform créés pour Customer AI. Ces jeux de données s’affichent avec le préfixe &quot;scores Customer AI&quot;, comme illustré ici :

![Scores CAI](assets/cai-scores.png)

Chaque prédiction, telle que &quot;Probabilité de mise à niveau du compte&quot;, correspond à un jeu de données.

Voici un exemple de schéma XDM que CJA apporterait dans le cadre d’un jeu de données existant ou nouveau :

![Schéma CAI](assets/cai-schema.png)

(Notez que l’exemple est un jeu de données de profil ; le même ensemble d’objets de schéma ferait partie d’un jeu de données d’événement d’expérience que CJA attraperait. Le jeu de données Événement d’expérience inclurait des horodatages comme date de score.) Chaque client noté dans ce modèle aurait un score, un scoreDate, etc. qui leur sont associés.

### Étape 3 : Créer des vues de données basées sur ces connexions

Dans CJA, vous pouvez maintenant passer à [création de vues de données](/help/data-views/create-dataview.md) avec les dimensions (score, date de score, probabilité, etc.) et les mesures introduites dans le cadre de la connexion que vous avez établie.

### Étape 4 : Rapport sur les scores CAI dans Workspace

Voici un exemple de projet Workspace avec des données de l’interface utilisateur graphique (CAI) qui affiche les dates de score dans un graphique à barres empilé :

![Blocs de score](assets/workspace-scores.png)

