---
title: Importation de Canaux marketing dans CJA à l’aide du connecteur de données Analytics
description: Utilisez les paramètres appropriés du connecteur de données Analytics pour importer les règles de traitement de Marketing Canal dans Adobe Experience Platform.
translation-type: tm+mt
source-git-commit: 26486c79f6d94db1aa795bf024f581cad74c25f6
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 7%

---


# Importation de Canaux marketing dans CJA à l’aide du connecteur de données Analytics

Si votre entreprise utilise [Analytics Data Connector](https://docs.adobe.com/content/help/fr-FR/experience-platform/sources/connectors/adobe-applications/analytics.html) pour importer les données de la suite de rapports dans CJA, vous pouvez configurer une connexion dans CJA pour créer des rapports sur les dimensions du Canal marketing.

## Conditions préalables

* Les données de la suite de rapports doivent déjà être importées dans Adobe Experience Platform à l’aide du [connecteur de données Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html).
* Les règles de traitement du canal marketing doivent déjà être configurées. Voir [Règles de traitement pour les Canaux marketing](https://docs.adobe.com/content/help/fr-FR/analytics/components/marketing-channels/c-rules.html) dans le guide des composants Analytics traditionnels.

## Éléments du schéma du Canal marketing

Une fois que vous utilisez le connecteur de données Analytics sur une suite de rapports de votre choix, un schéma XDM est créé pour vous. Ce schéma contient toutes les dimensions et mesures d’Analytics en tant que données brutes. Ces données brutes ne contiennent ni attribution ni persistance. En revanche, chaque accès s’exécute par le biais des règles de traitement du canal marketing et enregistre la première règle correspondante. Vous spécifiez l’attribution et la persistance lors de la création d’une vue de données dans CJA.

1. [Créez une ](/help/connections/create-connection.md) connexion qui inclut un jeu de données basé sur le connecteur de données Analytics.
2. [Créez une ](/help/data-views/create-dataview.md) vue de données qui comprend les dimensions suivantes :
   * **`channel.typeAtSource`**: Équivalent à la dimension de  [canal ](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) marketing.
   * **`channel._id`**: Équivalent au détail du canal  [marketing](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. Attribuez à chaque dimension le modèle d’attribution et la persistance désirés. Si vous souhaitez des dimensions Première touche et Dernière touche, faites glisser plusieurs fois chaque dimension de canal marketing vers la zone de composants. Attribuez à chaque dimension le modèle d’attribution et la persistance désirés. L’Adobe recommande également de donner un nom d’affichage à chaque dimension afin de la rendre plus facile à utiliser dans Workspace.
4. Créez la vue de données.

Vos dimensions de canal marketing sont désormais disponibles dans Analysis Workspace.

## Différences de traitement et d’architecture

>[!IMPORTANT]
>
>Il existe plusieurs différences fondamentales entre les données de la suite de rapports et les données de la plateforme. L’Adobe recommande vivement d’ajuster les règles de traitement du canal marketing de votre suite de rapports afin de faciliter la collecte des données dans la plate-forme.


Comme les dimensions de canal Première touche et Dernière touche sont essentiellement les mêmes avec différents modèles d’attribution, vous pouvez recréer des dimensions similaires lorsque [vous créez une vue de données](/help/data-views/create-dataview.md). Vous pouvez créer plusieurs dimensions basées sur le même élément de schéma, en leur donnant différents modèles d’attribution et de persistance.

## Différences entre les

