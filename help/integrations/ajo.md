---
title: Intégrer Adobe Journey Optimizer à Customer Journey Analytics
description: Importez les données générées par AJO et analysez-les à l’aide d’Analysis Workspace dans CJA.
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: ht
source-wordcount: '664'
ht-degree: 100%

---


# Intégrer Adobe Journey Optimizer à Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=fr) vous aide à offrir des expériences connectées, contextuelles et personnalisées. Cela permet d’exposer vos clients à l’étape suivante de leur parcours client.

Vous pouvez importer les données générées par Journey Optimizer afin d’effectuer une analyse avancée dans Customer Journey Analytics en procédant comme suit :

## Envoi de données de Journey Optimizer vers Adobe Experience Platform

Adobe Experience Platform sert de source de données centrale et de lien entre Journey Optimizer et Customer Journey Analytics. Consultez [Prise en main des jeux de données](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=fr) dans le guide de l’utilisateur de Journey Optimizer pour savoir comment envoyer des données Journey Optimizer à Platform en tant que jeu de données.

## Créer une connexion dans Customer Journey Analytics

Une fois que les données Journey Optimizer sont dans Adobe Experience Platform, vous pouvez [créer une connexion](/help/connections/create-connection.md) en fonction de votre jeu de données Journey Optimizer. Sélectionnez le jeu de données que vous avez envoyé à Platform.

## Configurez la vue de données pour qu’elle s’adapte aux dimensions et aux mesures Journey Optimizer.

Une fois la connexion créée, vous pouvez créer une ou plusieurs [vues des données](/help/data-views/create-dataview.md) pour configurer les dimensions et mesures souhaitées disponibles dans Customer Journey Analytics.

Vous pouvez créer les mesures suivantes dans une vue de données pour obtenir une parité approximative avec des mesures similaires dans Journey Optimizer. Consultez [Paramètres des composants](/help/data-views/component-settings/overview.md) dans le Gestionnaire de vues de données pour plus d’informations sur la personnalisation des dimensions et des mesures.

| Mesure | Description | Paramètres des vues de données |
| --- | --- | --- |
| Rebonds | Nombre de messages qui ont fait l’objet d’un rebond | Utilisez l’élément de chaîne de schéma `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` avec les paramètres suivants : <br>Type de composant : mesure<br>Incluez les valeurs d’exclusion : si l’un des critères est satisfait<br>Est égal à : `bounce`<br>Est égal à : `denylist` |
| Erreurs | Nombre de messages avec erreur | Utilisez l’élément de chaîne de schéma `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` avec les paramètres suivants :<br>Type de composant : mesure<br>Incluez les valeurs d’exclusion : est égal à `error` |
| Exclut | Nombre de messages exclus | Utilisez l’élément de chaîne de schéma `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` avec les paramètres suivants : <br>Type de composant : mesure<br>Incluez les valeurs d’exclusion : est égal à `exclude` |
| Désabonnements | Nombre de désabonnements | Utilisez l’élément de chaîne de schéma `_experience.customerJourneyManagement.messageInteraction.interactionType` avec les paramètres suivants : <br>Type de composant : mesure<br>Incluez les valeurs d’exclusion : est égal à `unsubscribe` |
| Clics | Nombre de clics dans les messages | Utilisez l’élément de chaîne de schéma `_experience.customerJourneyManagement.messageInteraction.interactionType` avec les paramètres suivants : <br>Type de composant : mesure<br>Incluez les valeurs d’exclusion : est égal à `click` |
| Ouvertures | Nombre de messages ouverts | Utilisez l’élément de chaîne de schéma `_experience.customerJourneyManagement.messageInteraction.interactionType` avec les paramètres suivants : <br>Type de composant : mesure<br>Incluez les valeurs d’exclusion : est égal à `open` |
| Plaintes contre le spam | Nombre de plaintes pour spam | Utilisez l’élément de chaîne de schéma `_experience.customerJourneyManagement.messageInteraction.interactionType` avec les paramètres suivants : <br>Type de composant : mesure<br>Incluez les valeurs d’exclusion : est égal à `spam_complaint` |
| Messages envoyés avec succès | Nombre de messages envoyés avec succès | Utilisez l’élément de chaîne de schéma `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` avec les paramètres suivants : <br>Type de composant : mesure<br>Incluez les valeurs d’exclusion : est égal à `sent` |
| Échecs de synchronisation | Nombre total de messages qui n’ont pas pu être synchronisés | Utilisez l’élément de chaîne de schéma `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` avec les paramètres suivants : <br>Type de composant : mesure<br>Incluez les valeurs d’exclusion : est égal à `sync` |

{style=&quot;table-layout:auto&quot;}

## Configurer des mesures calculées à l’aide de mesures Journey Optimizer

Une fois que vous avez configuré les dimensions et mesures souhaitées pour le jeu de données Journey Optimizer, vous pouvez également configurer des [mesures calculées](/help/components/calc-metrics/calc-metr-overview.md) pour obtenir des informations supplémentaires sur ces données. Ces mesures calculées sont basées sur les mesures créées ci-dessus dans le Gestionnaire de vues de données.

| Mesure calculée | Description | Formule |
| --- | --- | --- |
| Nombre total de messages envoyés | Nombre total de messages envoyés, réussis ou en échec | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Différences entre les rapports Journey Optimizer et Customer Journey Analytics

Les écarts de données entre les produits sont généralement compris entre 1 et 2 %. Des écarts plus importants entre les produits peuvent potentiellement être attribués à ce qui suit :

* Le temps de traitement des données entrantes peut être légèrement différent entre les produits, en particulier pour les données collectées au cours des deux dernières heures. Utilisez des périodes à l’exception d’aujourd’hui pour atténuer les écarts entre les temps de traitement.
* La mesure calculée « Nombre total de messages envoyés » n’inclut pas la mesure « Reprises ». Les données de la mesure « Reprises » ne sont pas incluses dans le jeu de données, indiquant des nombres potentiellement plus faibles dans les rapports CJA que dans les rapports AJO. Toutefois, les données de reprise sont converties dans la mesure « Messages envoyés avec succès » ou « Rebonds ». Utilisez des périodes d’une semaine ou plus pour atténuer les écarts avec la mesure « Nombre total de messages envoyés » entre les produits.
