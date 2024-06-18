---
title: Intégrer Adobe Journey Optimizer à Customer Journey Analytics
description: Importez les données générées par Adobe Journey Optimizer et analysez-les à l’aide d’Analysis Workspace dans Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 6e1db2351aa9fcc4682b892334430c1896cee914
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 83%

---

# Intégrer Adobe Journey Optimizer à Adobe Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=fr) vous aide à offrir des expériences connectées, contextuelles et personnalisées. Cela permet d’exposer vos clients à l’étape suivante de leur parcours client.

Vous pouvez importer les données générées par Journey Optimizer pour effectuer une analyse avancée dans Customer Journey Analytics. Vous pouvez le faire automatiquement. Si nécessaire, vous pouvez personnaliser manuellement des jeux de données, des dimensions ou des mesures supplémentaires disponibles dans les vues de données que vous utilisez pour Adobe Journey Optimizer et Customer Journey Analytics.

## Configurer automatiquement une vue de données de Customer Journey Analytics à utiliser avec Journey Optimizer

Une option de configuration dans Customer Journey Analytics vous permet de désigner une vue de données de Customer Journey Analytics à utiliser avec Journey Optimizer, sans avoir besoin d’une configuration manuelle. <p>Pour plus d’informations sur l’activation de cette option de configuration, voir [Compatibilité](/help/data-views/create-dataview.md#compatibility) dans [Création ou modification d’une vue de données](/help/data-views/create-dataview.md).

## Configuration manuelle d’une vue de données de Customer Journey Analytics à utiliser avec Journey Optimizer

Les sections suivantes décrivent comment importer manuellement les données générées par Journey Optimizer afin d’effectuer une analyse avancée dans Customer Journey Analytics. Cela n’est nécessaire que si la variable [option de configuration automatique](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) est insuffisante pour répondre à vos besoins.

### Envoi de données de Journey Optimizer vers Adobe Experience Platform

Adobe Experience Platform sert de source de données centrale et de lien entre Journey Optimizer et Customer Journey Analytics. Consultez [Prise en main des jeux de données](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=fr) dans le guide de l’utilisateur de Journey Optimizer pour savoir comment envoyer des données Journey Optimizer à Platform en tant que jeu de données.

### Créer une connexion dans Customer Journey Analytics

Une fois que les données Journey Optimizer sont dans Adobe Experience Platform, vous pouvez [créer une connexion](/help/connections/create-connection.md) en fonction de votre jeu de données Journey Optimizer. Vous pouvez également ajouter des jeux de données Journey Optimizer à une connexion existante.

Sélectionnez et configurez les jeux de données suivants :

| Jeu de données | Type de jeu de données | Paramètres de connexion | Description |
| --- | --- | --- | --- |
| Jeu de données d’événement de commentaires sur les messages AJO | Événement | ID de personne : `IdentityMap` | Contient les événements de diffusion de message, tels que « [!UICONTROL Envois] » et « [!UICONTROL Rebonds] ». |
| Jeu de données d’événement d’expérience de tracking d’e-mail AJO | Événement | ID de personne : `IdentityMap` | Contient des événements de suivi d’e-mails tels que « [!UICONTROL Ouvertures] », « [!UICONTROL Clics] », et « [!UICONTROL Désabonnements] ». |
| Jeu de données d’événement d’expérience de tracking de notifications push AJO | Événement | ID de personne : `IdentityMap` | Contient des événements de suivi de notifications push tels que « [!UICONTROL Lancements d’application] ». |
| Événements d’étape de parcours | Événement | ID de personne : `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Contient des événements indiquant les profils ayant participé à chaque nœud du parcours. |
| Jeu de données d’entité AJO | Recherche | Clé : `_id`<br>clé correspondante : `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contient des classifications qui associent des métadonnées de parcours et de campagne à toutes les données d’événement Adobe Journey Optimizer. |

{style="table-layout:auto"}


### Configurez la vue de données pour qu’elle s’adapte aux dimensions et aux mesures Journey Optimizer.

Une fois la connexion créée, vous pouvez créer une ou plusieurs [vues des données](/help/data-views/create-dataview.md) pour configurer les dimensions et mesures souhaitées disponibles dans Customer Journey Analytics.

>[!NOTE]
>
>Les écarts de données entre Adobe Journey Optimizer et Customer Journey Analytics sont généralement inférieurs à 1-2 %. Des écarts plus importants sont possibles pour les données collectées au cours des deux dernières heures. Utilisez des périodes excluant aujourd’hui pour atténuer les écarts entre les temps de traitement.


#### Configurer des dimensions dans la vue de données

Vous pouvez créer les dimensions suivantes dans une vue de données pour obtenir une parité approximative avec des dimensions similaires dans Journey Optimizer. Voir [Paramètres des composants](/help/data-views/component-settings/overview.md) dans le Gestionnaire de vues de données pour en savoir plus sur les options de personnalisation des dimensions.

| Dimension | Élément de schéma | Paramètres de composant |
| --- | --- | --- |
| Nom du parcours | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Type de composant : dimension |
| Nom et version du parcours | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Type de composant : dimension |
| Nom du nœud de parcours | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeName` | Type de composant : dimension |
| Type de nœud de parcours | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | Type de composant : dimension |
| Nom de la campagne | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | Type de composant : dimension |
| Canal | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | Type de composant : dimension |
| Titre de notification push | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | Type de composant : dimension |
| Objet de l’e-mail | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | Type de composant : dimension |
| Libellé du lien | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | Type de composant : dimension |
| Nom de l’expérience | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | Type de composant : Dimension<br>Libellés contextuels : Expérience d’expérimentation |
| Nom du traitement | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | Type de composant : Dimension<br>LIbellés contextuels : Variante d’expérience |
| Raison de l’échec de diffusion des e-mails | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | Type de composant : dimension |
| Raison d’exclusion de diffusion des e-mails | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | Type de composant : dimension |
| Libellé de l’élément | `_experience.decisioning.propositionAction.label` | Type de composant : dimension |

{style="table-layout:auto"}

#### Configurer les mesures dans la vue de données

Vous pouvez créer les mesures suivantes dans une vue de données pour obtenir une parité approximative avec des mesures similaires dans Journey Optimizer. Voir [Paramètres des composants](/help/data-views/component-settings/overview.md) dans le Gestionnaire de vues de données pour en savoir plus sur les options de personnalisation des mesures.

| Mesure | Description | Élément de schéma | Paramètres de composant |
| --- | --- | --- | --- |
| Rebonds | Nombre de messages qui ont fait l’objet d’un rebond, y compris les rebonds immédiats et les rebonds post-diffusion. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Si l’un des critères est satisfait<br>Est égal à : `bounce`, Est égal à : `denylist` |
| Rebonds après diffusion | Certains services de messagerie signalent les e-mail envoyés, puis les font rebondir ultérieurement. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `async` |
| Clics par e-mail | Nombre de clics dans les messages. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `click` |
| Ouvertures d’e-mails | Nombre de messages ouverts. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `open` |
| Erreurs | Nombre de messages avec erreur. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `error` |
| Exclut | Nombre de messages exclus. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `exclude` |
| Envois | Nombre de messages acceptés par les fournisseurs de messagerie. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `sent` |
| Plaintes pour spam | Nombre de plaintes pour spam. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Type de composant : Mesure<br>Inclure les valeurs d’exclusion : Est égal à `spam_complaint` |
| Désabonnements | Nombre de désabonnements. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Type de composant : mesure <br>Inclure les valeurs d’exclusion : est égal à `unsubscribe` |
| Envois Edge | Nombre de fois où le réseau Edge envoie un message au SDK Web ou Mobile. | Utiliser l’élément de chaîne de schéma `_experience.decisioning.propositionEventType.send` | |
| Affichages entrants | Nombre d’affichages d’un message web ou in-app à l’utilisateur ou l’utilisatrice. | Utiliser l’élément de chaîne de schéma `_experience.decisioning.propositionEventType.display` | |
| Clics entrants | Nombre de clics de messages web ou in-app. | Utiliser l’élément de chaîne de schéma `_experience.decisioning.propositionEventType.interact` | |
| Déclencheurs (triggers) in-app | Nombre de fois où le moteur de prise de décision a suggéré que le message s’affiche. Le SDK Mobile peut remplacer la décision de réduction du nombre d’affichages réels. | Utiliser l’élément de chaîne de schéma `_experience.decisioning.propositionEventType.trigger` | |
| Rejets in-app | Nombre de fois où un message in-app est supprimé de l’interface utilisateur par le SDK. | Utiliser l’élément de chaîne de schéma `_experience.decisioning.propositionEventType.dismiss` | |

{style="table-layout:auto"}

#### Configurer les mesures calculées dans Analysis Workspace

Une fois que vous avez configuré les dimensions et mesures souhaitées pour le jeu de données Journey Optimizer, vous pouvez également configurer des [mesures calculées](/help/components/calc-metrics/calc-metr-overview.md) pour obtenir des informations supplémentaires sur ces données. Ces mesures calculées sont basées sur les mesures créées ci-dessus dans le Gestionnaire de vues de données.

| Mesure calculée | Description | Formule |
| --- | --- | --- |
| Nombre de messages envoyés | Le nombre total de messages envoyés. Inclut les messages réussis ou en échec. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Messages diffusés | Le nombre d’e-mails envoyés aux clients ou aux clientes. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
