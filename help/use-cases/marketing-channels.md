---
title: Utilisation des dimensions du canal marketing dans Adobe Experience Platform
description: Utilisez le connecteur de données Analytics pour importer les règles de traitement de Marketing Canal dans Adobe Experience Platform.
translation-type: tm+mt
source-git-commit: b5ed4c65877fa8e2de83810a3c4bd1a4048f5b31
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 3%

---


# Utilisation des dimensions du canal marketing dans Adobe Experience Platform

Si votre entreprise utilise [Analytics Data Connector](https://docs.adobe.com/content/help/fr-FR/experience-platform/sources/connectors/adobe-applications/analytics.html) pour importer les données de la suite de rapports dans CJA, vous pouvez configurer une connexion dans CJA pour créer des rapports sur les dimensions du Canal marketing.

## Conditions préalables

* Les données de la suite de rapports doivent déjà être importées dans Adobe Experience Platform à l’aide du [connecteur de données Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html). D’autres sources de données ne sont pas prises en charge, car les canaux marketing reposent sur des règles de traitement dans une suite de rapports Analytics.
* Les règles de traitement du canal marketing doivent déjà être configurées. Voir [Règles de traitement pour les Canaux marketing](https://docs.adobe.com/content/help/fr-FR/analytics/components/marketing-channels/c-rules.html) dans le guide des composants Analytics traditionnels.

## Éléments du schéma du Canal marketing

Une fois que vous avez établi le connecteur de données Analytics sur une suite de rapports de votre choix, un schéma XDM est créé pour vous. Ce schéma contient toutes les dimensions et mesures d’Analytics en tant que données brutes. Ces données brutes ne contiennent ni attribution ni persistance. Au lieu de cela, chaque événement s’exécute via les règles de traitement du canal marketing et enregistre la première règle correspondante. Vous spécifiez l’attribution et la persistance lors de la création d’une vue de données dans CJA.

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

Les paramètres du canal marketing fonctionnent différemment entre les données de la plateforme et les données de la suite de rapports. Tenez compte des différences suivantes lors de la configuration des canaux marketing pour la CJA :

* **Est la première page de la visite** : Ce critère de règle est commun à plusieurs définitions de canal marketing par défaut. Toute règle de traitement contenant ce critère est ignorée dans la plate-forme (d’autres critères de la même règle s’appliquent toujours). Les sessions sont déterminées au moment de la requête des données plutôt qu’au moment de la collecte des données, ce qui empêche la plateforme d’utiliser ces critères de règle spécifiques. L’Adobe recommande de supprimer le critère &quot;Est la première page de la visite&quot; de chaque règle de traitement du canal marketing.

   ![Première page de la visite](assets/first-page-of-visit.png)

* **Remplacer le Canal** Dernière touche : Ce paramètre dans le Gestionnaire de Canaux marketing empêche normalement certains canaux d’obtenir le crédit du canal Dernière touche. La plate-forme ignore ce paramètre, ce qui permet à des canaux larges tels que &quot;Direct&quot; ou &quot;Internal&quot; d’attribuer des attributs à des mesures de manière potentiellement indésirable. Adobe recommande de supprimer les canaux pour lesquels l&#39;option &quot;Remplacer le Canal Dernière touche&quot; n&#39;est pas cochée.
   * Vous pouvez supprimer le canal marketing &quot;Direct&quot; dans le Gestionnaire de Canaux marketing, puis vous reposer sur l’élément de dimension &quot;Aucune valeur&quot; de la CJA pour ce canal. Vous pouvez également renommer cet élément de dimension en &quot;Direct&quot; ou exclure entièrement l’élément de dimension lors de la configuration d’une vue de données.
   * Vous pouvez également créer une classification de canal marketing, en se classant chaque valeur à elle-même, à l’exception des canaux que vous souhaitez exclure dans la CJA. Vous pouvez ensuite utiliser cette dimension de classification lors de la création d’une vue de données au lieu de `channel.typeAtSource`.

   ![Remplacer le canal Dernière touche](assets/override-last-touch-channel.png)

* **Expiration** du Canal marketing : Ce paramètre de période d’engagement détermine la période d’inactivité avant qu’un visiteur puisse obtenir un nouveau canal Première touche dans les données de la suite de rapports. Platform utilise ses propres paramètres d’attribution. Par conséquent, ce paramètre est totalement ignoré dans CJA.

   ![Expiration du canal marketing](assets/marketing-channel-expiration.png)

## Comparaison des données entre la CJA et les analyses traditionnelles

L’architecture de Adobe Experience Platform étant différente d’une suite de rapports Analytics traditionnelle, les résultats ne sont pas nécessairement identiques. Cependant, vous pouvez utiliser les conseils suivants pour faciliter cette comparaison :

* Vérifiez que les différences architecturales répertoriées ci-dessus n’affectent pas votre comparaison. Cela inclut la suppression des canaux qui ne remplacent pas le canal Dernière touche et les critères de règle qui sont le premier accès d’une visite (session).
* Vérifiez par doublon que votre connexion utilise la même suite de rapports qu’Analytics classique. Si votre connexion CJA contient plusieurs suites de rapports avec leurs propres règles de traitement du canal marketing, il n’est pas facile de la comparer à Analytics traditionnel. Vous souhaitez créer une connexion distincte pour chaque suite de rapports afin de comparer les données.
* Veillez à comparer les mêmes plages de dates et à ce que le paramètre de fuseau horaire défini dans votre vue de données soit le même que celui de la suite de rapports.
* Utilisez un modèle d’attribution personnalisé lors de l’affichage des données d’une suite de rapports. Par exemple, utilisez la dimension [canal marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html) avec des mesures qui utilisent un modèle d’attribution autre que celui par défaut. L’Adobe recommande de ne pas comparer les dimensions par défaut [canal Première touche](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html) ou [canal Dernière touche](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html), car elles reposent sur l’attribution collectée dans la suite de rapports. CJA ne repose pas sur les données d’attribution d’une suite de rapports ; en revanche, il est calculé lorsqu’un rapport CJA est exécuté.
* Certaines mesures ne présentent pas de comparaison raisonnable en raison de différences architecturales entre les données de la suite de rapports et les données de la plateforme. Par exemple, les visites/sessions, les visiteurs/les personnes et les occurrences/événements.
