---
title: Utiliser les dimensions de canal marketing dans Adobe Experience Platform
description: Utilisez le connecteur source Analytics pour importer les règles de traitement des canaux marketing dans Adobe Experience Platform.
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 63%

---

# Utiliser les dimensions de canal marketing dans Adobe Experience Platform

Si votre entreprise utilise la variable [Connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr) pour importer les données de la suite de rapports dans Customer Journey Analytics, vous pouvez configurer une connexion dans Customer Journey Analytics afin de créer des rapports sur les dimensions du canal marketing.

## Conditions préalables

* Les données de la suite de rapports doivent déjà être importées dans Adobe Experience Platform à l’aide de la variable [Connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). Les autres sources de données ne sont pas prises en charge, car les canaux marketing dépendent des règles de traitement d’une suite de rapports Analytics.
* Les règles de traitement de canal marketing doivent déjà être configurées. Voir [Règles de traitement des canaux marketing](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=fr) dans le guide Composants Adobe Analytics .

## Éléments de schéma de canal marketing

Une fois que vous avez établi le connecteur source Analytics sur une suite de rapports souhaitée, un schéma XDM est créé pour vous. Ce schéma contient toutes les dimensions et mesures Analytics sous forme de données brutes. Ces données brutes ne contiennent ni attribution ni persistance. Au lieu de cela, chaque événement s’exécute à travers les règles de traitement de canal marketing et enregistre la première règle correspondante. Vous spécifiez l’attribution et la persistance lors de la création d’une vue de données dans Customer Journey Analytics.

1. [Création d’une connexion](/help/connections/create-connection.md) qui inclut un jeu de données basé sur le connecteur source Analytics.
2. [Créez une vue de données](/help/data-views/create-dataview.md) qui inclut les dimensions suivantes :
   * **`channel.typeAtSource`** : équivalente à la dimension [Canal marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=fr).
   * **`channel._id`** : équivalente à la dimension [Détails du canal marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-detail.html?lang=fr).
3. Attribuez à chaque dimension le modèle d’attribution et la persistance souhaités. Pour obtenir des dimensions First Touch et Last Touch, faites glisser plusieurs fois chaque dimension de canal marketing vers la zone de composants. Attribuez à chaque dimension le modèle d’attribution et la persistance souhaités. Adobe recommande également d’attribuer un nom d’affichage à chaque dimension afin d’en faciliter l’utilisation dans Espace de travail.
4. Créez la vue de données.

Vos dimensions de canal marketing sont désormais disponibles dans Analysis Workspace.

>[!NOTE]
>
> Le connecteur source Analytics requiert que les deux `channel.typeAtSource` (Canal marketing) et `channel._id` (Détails du canal marketing) est renseigné ; dans le cas contraire, aucun n’est transféré vers XDM ExperienceEvent. Si le détail du canal marketing est vide dans la suite de rapports source, un champ vierge s’affiche. `channel._id` et le connecteur source Analytics est vide. `channel.typeAtSource` ainsi que . Cela peut se traduire par des différences de rapports entre Adobe Analytics et Customer Journey Analytics.

## Différences de traitement et d’architecture

>[!IMPORTANT]
>
>Il existe plusieurs différences fondamentales entre les données des suites de rapports et les données de Platform. Adobe recommande vivement d’adapter les règles de traitement de canal marketing de votre suite de rapports afin de faciliter la collecte de données dans Platform.

>[!NOTE]
>
>Afin d’optimiser l’efficacité des canaux marketing pour Attribution IQ et Customer Journey Analytics, nous avons publié quelques [bonnes pratiques révisées](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=fr).

Les paramètres de canal marketing fonctionnent de façon différente sur les données de Platform et les données des suites de rapports. Tenez compte des différences suivantes lors de la configuration des canaux marketing pour Customer Journey Analytics :

* **Est la première page de la visite** : ce critère de règle est commun à plusieurs définitions de canal marketing par défaut. Toute règle de traitement qui contient ce critère est ignorée dans Platform (les autres critères de ladite règle s’appliquent toujours). La détermination des sessions s’effectue au moment de la requête des données plutôt qu’au moment de leur collecte, ce qui empêche Platform d’utiliser ces critères de règle spécifiques. Adobe recommande de réévaluer toute règle de traitement des canaux marketing contenant les critères ‘Est la première page de la visite’, en optant pour d’autres approches qui atteignent vos objectifs.

  ![Première page de la visite](../assets/first-page-of-visit.png)

* **Remplacer le canal Last Touch** : ce paramètre du gestionnaire de canaux marketing empêche normalement certains canaux d’obtenir le crédit de canal Last Touch. Platform ignore ce paramètre, ce qui permet à de larges canaux comme « Direct » ou « Interne » d’attribuer des attributs à des mesures de manière potentiellement indésirable. Adobe recommande de supprimer les canaux pour lesquels l’option « Remplacer le canal Last Touch » est décochée.
   * Vous pouvez supprimer le canal marketing &quot;Direct&quot; dans le Gestionnaire de canaux marketing, puis dépendre de l’élément de dimension &quot;Aucune valeur&quot; de Customer Journey Analytics pour ce canal. Vous pouvez également renommer cet élément de dimension en « Direct » ou l’exclure entièrement lors de la configuration d’une vue de données.
   * Vous pouvez également créer une classification de canal marketing, en classant chaque valeur à elle-même, à l’exception des canaux que vous souhaitez exclure dans Customer Journey Analytics. Vous pouvez ensuite utiliser cette dimension de classification à la place de `channel.typeAtSource` lors de la création d’une vue de données.

  ![Remplacer le canal Last Touch](../assets/override-last-touch-channel.png)

* **Expiration du canal marketing**: Ce paramètre de période d’engagement détermine la période d’inactivité pendant laquelle une personne peut obtenir un nouveau canal Première touche dans les données de la suite de rapports. Platform utilise ses propres paramètres d’attribution. Par conséquent, ce paramètre est entièrement ignoré dans Customer Journey Analytics.

  ![Expiration du canal marketing](../assets/marketing-channel-expiration.png)

## Comparaison des données entre Customer Journey Analytics et Adobe Analytics

L’architecture de Adobe Experience Platform étant différente d’une suite de rapports Adobe Analytics, il n’est pas garanti que les résultats correspondent. Toutefois, vous pouvez suivre les conseils ci-dessous pour faciliter cette comparaison :

* Vérifiez que les différences architecturales répertoriées ci-dessus n’affectent pas votre comparaison. Cette opération inclut la suppression des canaux qui ne chevauchent pas le canal Last Touch ainsi que celle des critères de règle qui sont le premier accès d’une visite (session).
* Vérifiez deux fois que votre connexion utilise la même suite de rapports qu’Adobe Analytics. Si votre connexion de Customer Journey Analytics contient plusieurs suites de rapports avec leurs propres règles de traitement des canaux marketing, il n’existe pas de moyen facile de les comparer à Adobe Analytics. Créez une connexion distincte pour chaque suite de rapports afin de comparer les données.
* Assurez-vous de comparer les mêmes périodes et que le paramètre de fuseau horaire défini dans votre vue de données est identique à celui de la suite de rapports.
* Utilisez un modèle d’attribution personnalisé lors de l’affichage des données d’une suite de rapports. Par exemple, utilisez la dimension [Canal marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=fr) avec des mesures qui utilisent un modèle d’attribution autre que celui par défaut. Adobe déconseille de comparer le [canal First Touch](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html?lang=fr) ou le [canal Last Touch](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html?lang=fr) aux dimensions par défaut, car ils dépendent de l’attribution collectée dans la suite de rapports. Customer Journey Analytics ne dépend pas des données d’attribution d’une suite de rapports ; au lieu de cela, il est calculé lorsqu’un rapport de Customer Journey Analytics est exécuté.
* Certaines mesures ne présentent pas de comparaison raisonnable en raison des différences architecturales entre les données de la suite de rapports et celles de Platform. Par exemple, les visites/sessions, les personnes/personnes et les occurrences/événements.
