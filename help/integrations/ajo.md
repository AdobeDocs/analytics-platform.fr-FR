---
title: Intégrer Adobe Journey Optimizer à Customer Journey Analytics
description: importer les données générées par Adobe Journey Optimizer et les analyser à l’aide d’Analysis Workspace dans Customer Journey Analytics ;
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 64%

---

# Intégration de Adobe Journey Optimizer à Adobe Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=fr) vous aide à offrir des expériences connectées, contextuelles et personnalisées. Cela permet d’exposer vos clients à l’étape suivante de leur parcours client.

Vous pouvez importer les données générées par Journey Optimizer afin d’effectuer une analyse avancée dans Customer Journey Analytics en procédant comme suit :

## Envoi de données de Journey Optimizer vers Adobe Experience Platform

Adobe Experience Platform sert de source de données centrale et de lien entre Journey Optimizer et Customer Journey Analytics. Consultez [Prise en main des jeux de données](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=fr) dans le guide de l’utilisateur de Journey Optimizer pour savoir comment envoyer des données Journey Optimizer à Platform en tant que jeu de données.

## Créer une connexion dans Customer Journey Analytics

Une fois les données Journey Optimizer dans Adobe Experience Platform, vous pouvez [Création d’une connexion](/help/connections/create-connection.md) en fonction de vos jeux de données Journey Optimizer. Vous pouvez également ajouter des jeux de données Journey Optimizer à une connexion existante.

Sélectionnez et configurez les jeux de données suivants :

| Jeu de données  | Type de jeu de données | Paramètres de connexion | Description |
| --- | --- | --- | --- |
| Jeu de données d’événement de retour de message AJO | Événement | ID de personne : `IdentityMap` | Contient les événements de diffusion de message, tels que &quot;[!UICONTROL Envois]&#39; et &#39;[!UICONTROL Rebonds]&#39;. |
| Jeu de données d’événement de suivi d’email AJO | Événement | ID de personne : `IdentityMap` | Contient des événements de suivi de courrier électronique tels que &quot;[!UICONTROL Ouvertures]&#39;, &#39;[!UICONTROL Clics]&#39;, et &#39;[!UICONTROL Désabonne]&#39;. |
| Jeu de données d’événement de suivi push AJO | Événement | ID de personne : `IdentityMap` | Contient des événements de suivi push tels que &quot;[!UICONTROL Lancements d’application]&#39;. |
| Événements d’étape de parcours | Événement | ID de personne : `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Contient des événements indiquant les profils ayant participé à chaque noeud du parcours. |
| Jeu de données d’entité AJO | Recherche | Clé : `_id`<br>Clé correspondante : `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contient des classifications qui associent des métadonnées de Parcours et de campagne à toutes les données d’événement Adobe Journey Optimizer. |

{style="table-layout:auto"}


## Configurez la vue de données pour qu’elle s’adapte aux dimensions et aux mesures Journey Optimizer.

Une fois la connexion créée, vous pouvez créer une ou plusieurs [vues des données](/help/data-views/create-dataview.md) pour configurer les dimensions et mesures souhaitées disponibles dans Customer Journey Analytics.

>[!NOTE]
>
>Les incohérences de données entre Adobe Journey Optimizer et Customer Journey Analytics sont généralement inférieures à 1-2 %. Des écarts plus importants sont possibles pour les données collectées au cours des deux dernières heures. Utilisez des périodes excluant aujourd’hui pour atténuer les écarts entre les temps de traitement.


### Configurer des dimensions dans la vue de données

Vous pouvez créer les dimensions suivantes dans une vue de données pour obtenir une parité approximative avec des dimensions similaires dans Journey Optimizer. Voir [Paramètres des composants](/help/data-views/component-settings/overview.md) dans le Gestionnaire de vues de données pour en savoir plus sur les options de personnalisation des dimensions.

| Dimension | Élément de schéma | Paramètres de composant |
| --- | --- | --- |
| Nom du parcours | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Type de composant : Dimension |
| Nom et version du parcours | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Type de composant : Dimension |
| Nom du nœud de parcours | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Type de composant : Dimension |
| Type de nœud de parcours | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | Type de composant : Dimension |
| Nom de la campagne | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | Type de composant : Dimension |
| Canal | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | Type de composant : Dimension |
| Titre de notification push | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | Type de composant : Dimension |
| Objet de l’e-mail | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | Type de composant : Dimension |
| Libellé du lien | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | Type de composant : Dimension |
| Nom de l’expérience | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | Type de composant : Dimension<br>Libellés contextuels : Expérience d’expérimentation |
| Nom du traitement | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | Type de composant : Dimension<br>LIbellés contextuels : Variante d’expérience |
| Raison de l’échec de diffusion des e-mails | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | Type de composant : Dimension |
| Raison d’exclusion de diffusion des e-mails | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | Type de composant : Dimension |
| Libellé d’élément | `_experience.decisioning.propositionAction.label` | Type de composant : Dimension |

{style="table-layout:auto"}

### Configurer les mesures dans la vue de données

Vous pouvez créer les mesures suivantes dans une vue de données pour obtenir une parité approximative avec des mesures similaires dans Journey Optimizer. Voir [Paramètres des composants](/help/data-views/component-settings/overview.md) dans le Gestionnaire de vues de données pour en savoir plus sur les options de personnalisation des mesures.

| Mesure | Description | Élément de schéma | Paramètres de composant |
| --- | --- | --- | --- |
| Rebonds | Le nombre de messages qui ont fait l’objet d’un bounce, y compris les bounces immédiats et les bounces après l’envoi. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Si l’un des critères est satisfait<br>Est égal à : `bounce`, Est égal à : `denylist` |
| Rebonds après diffusion | Certains services de messagerie signalent les e-mail envoyés, puis les font rebondir ultérieurement. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `async` |
| Clics par e-mail | Nombre de clics dans les messages. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `click` |
| Ouvertures d’e-mails | Nombre de messages ouverts. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `open` |
| Erreurs | Nombre de messages qui ont été erronés. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `error` |
| Exclut | Nombre de messages exclus. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `exclude` |
| Envois | Nombre de messages acceptés par les fournisseurs de messagerie. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `sent` |
| Plaintes pour spam | Nombre de plaintes pour spam. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `spam_complaint` |
| Désabonnements | Nombre de désabonnements. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `unsubscribe` |
| Envois Edge | Nombre de fois où le réseau Edge envoie un message au SDK Web ou Mobile | Utilisation de l’élément de chaîne de schéma `_experience.decisioning.propositionEventType.send` |
| Affichages entrants | Nombre d&#39;affichages d&#39;un message Web ou In-App à l&#39;utilisateur | Utilisation de l’élément de chaîne de schéma `_experience.decisioning.propositionEventType.display` |
| Clics entrants | Nombre de clics de messages Web ou In-App | Utilisation de l’élément de chaîne de schéma `_experience.decisioning.propositionEventType.interact` |
| Déclencheurs In-App | Nombre de fois où le moteur de prise de décision a suggéré que le message s’affiche. Le SDK Mobile peut remplacer la décision de réduction du nombre d’affichages réels. | Utilisation de l’élément de chaîne de schéma `_experience.decisioning.propositionEventType.trigger` |
| Rejets In-App | Nombre de fois où un message In-App est supprimé de l’interface utilisateur par le SDK | Utilisation de l’élément de chaîne de schéma `_experience.decisioning.propositionEventType.dismiss` |

{style="table-layout:auto"}

### Configurer les mesures calculées dans Analysis Workspace

Une fois que vous avez configuré les dimensions et mesures souhaitées pour le jeu de données Journey Optimizer, vous pouvez également configurer des [mesures calculées](/help/components/calc-metrics/calc-metr-overview.md) pour obtenir des informations supplémentaires sur ces données. Ces mesures calculées sont basées sur les mesures créées ci-dessus dans le Gestionnaire de vues de données.

| Mesure calculée | Description | Formule |
| --- | --- | --- |
| Nombre de messages envoyés | Le nombre total de messages envoyés. Inclut les messages réussis ou en échec. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Messages diffusés | Le nombre d’e-mails envoyés aux clients ou aux clientes. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
