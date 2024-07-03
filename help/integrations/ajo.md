---
title: Intégrer Adobe Journey Optimizer à Customer Journey Analytics
description: Importez les données générées par Adobe Journey Optimizer et analysez-les à l’aide d’Analysis Workspace dans Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 13c3f99dba7725553c775df4492803f759ebead5
workflow-type: ht
source-wordcount: '1541'
ht-degree: 100%

---

# Intégrer Journey Optimizer à Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/get-started/get-started) vous aide à offrir des expériences connectées, contextuelles et personnalisées. Cela permet d’exposer vos clients à l’étape suivante de leur parcours client.

Vous pouvez configurer les données générées par Journey Optimizer afin d’effectuer une analyse avancée dans Customer Journey Analytics. Vous pouvez configurer cette intégration automatiquement. Si nécessaire, vous pouvez personnaliser manuellement des jeux de données, des dimensions ou des mesures supplémentaires disponibles dans votre connexion ou vos vues de données.

## Configurer automatiquement l’intégration Journey Optimizer

{{release-limited-testing-section}}

Journey Optimizer prend en charge l’utilisation de Customer Journey Analytics comme moteur de création de rapports. Voir [Commencer avec la nouvelle interface de création de rapports](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/channel-report/report-gs-cja) dans la documentation de Journey Optimizer.

Lorsque vous avez activé la création de rapports de Customer Journey Analytics pour Journey Optimizer, une [connexion](/help/connections/overview.md) et une [vue des données](/help/data-views/data-views.md) sont créées automatiquement pour le sandbox spécifique.

### Connexion

La connexion porte le nom **[!UICONTROL Connexion AJO activée (*nom du sandbox*)]** et contient les valeurs prêtes à l’emploi suivantes pour la configuration et les jeux de données :

| **Paramètres de connexion** | Valeur |
|---|---| 
| [!UICONTROL Nom de la connexion] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL Description de la connexion] | [!UICONTROL *Décrivez votre connexion ici.*] |
| [!UICONTROL Balises] | [!UICONTROL *Sélectionner les balises*] |


| **Paramètres des données** | Valeur |
|---|---| 
| [!UICONTROL Activer la fenêtre dynamique de données] | Activé. [!UICONTROL Nombre de mois sélectionnés] `13`. |
| [!UICONTROL Sandbox] | [!UICONTROL *Nom du sandbox*] (désactivé ; vous ne pouvez pas modifier ce paramètre). |
| [!UICONTROL Nombre moyen d’événements quotidiens] | Moins de 1 million (désactivé, vous ne pouvez pas modifier ce paramètre). |


| Nom du jeu de données | Schéma | Type de jeu de données | Type de source de données | ID de personne | Clé | Clé correspondante | Importer de nouvelles données | Renvoyer les données |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL Jeu de données d’entité AJO] | [!UICONTROL Schéma d’enregistrement d’entité AJO] | [!UICONTROL Rechercher] | [!UICONTROL Autre] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![Status Green](assets/../../connections/assets/status-green.svg) Activé | ![Status Gray](assets/../../connections/assets/status-gray.svg) Désactivé |
| [!UICONTROL Événements d’étape de parcours] | [!UICONTROL Schéma d’événement d’étape de parcours pour Journey Orchestration] | [!UICONTROL Événement] | [!UICONTROL Autre] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | - | - | ![Status Green](assets/../../connections/assets/status-green.svg) Activé | ![Status Gray](assets/../../connections/assets/status-gray.svg) Désactivé |
| [!UICONTROL Jeu de données d’événement d’expérience de tracking d’e-mail AJO] | [!UICONTROL Schéma d’événement d’expérience de tracking d’e-mail AJO] | [!UICONTROL Événement] | [!UICONTROL Autre] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Status Green](assets/../../connections/assets/status-green.svg) Activé | ![Status Gray](assets/../../connections/assets/status-gray.svg) Désactivé |
| [!UICONTROL Jeu de données d’événement d’expérience de tracking d’e-mail AJO] | [!UICONTROL Schéma d’événement d’expérience de tracking d’e-mail AJO] | [!UICONTROL Événement] | [!UICONTROL Autre] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Status Green](assets/../../connections/assets/status-green.svg) Activé | ![Status Gray](assets/../../connections/assets/status-gray.svg) Désactivé |
| [!UICONTROL Jeu de données d’événement de message de feedback AJO] | [!UICONTROL Jeu de données d’événement de message de feedback AJO] | [!UICONTROL Événement] | [!UICONTROL Autre] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Status Green](assets/../../connections/assets/status-green.svg) Activé | ![Status Gray](assets/../../connections/assets/status-gray.svg) Désactivé |
| [!UICONTROL Jeu de données d’événement d’expérience de tracking de notifications push AJO] | [!UICONTROL Schéma d’événement d’expérience de tracking de notifications push AJO] | [!UICONTROL Événement] | [!UICONTROL Autre] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Status Green](assets/../../connections/assets/status-green.svg) Activé | ![Status Gray](assets/../../connections/assets/status-gray.svg) Désactivé |


### Vue de données

La vue de données porte le nom **Vue de données AJO activée (*nom du sandbox*)**.

- Dans l’onglet **[!UICONTROL Configurer]**, les valeurs suivantes sont prêtes à l’emploi.

  | Paramètres | Valeur |
  |---|---|
  | [!UICONTROL Connexion] | Connexion AJO activée (*nom de l’environnement de test*) |
  | [!UICONTROL Nom] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL ID externe] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` (dérivé du nom) |
  | [!UICONTROL Description] | `undefined` |

  {style="table-layout:fixed"}

  | Compatibilité | Valeur |
  |---|---|
  | [!UICONTROL Définir la vue des données par défaut dans Adobe Journey Optimizer] | Activé (par défaut).<br/><br/>Cette option de configuration vous permet de désigner une vue de données à utiliser avec Journey Optimizer, sans avoir à effectuer de configuration manuelle. Pour plus d’informations sur l’activation de cette option de configuration (si elle n’est pas déjà activée par défaut), voir la section [Compatibilité](/help/data-views/create-dataview.md#compatibility) dans [Créer ou modifier une vue de données](/help/data-views/create-dataview.md). <br/><br/>Lorsque vous désactivez cette option, une boîte de dialogue vous demande si vous souhaitez continuer à modifier la vue de données par défaut. Lorsque vous sélectionnez **[!UICONTROL Continuer]**, vous devez sélectionner une autre vue de données comme vue de données par défaut. Sélectionnez **[!UICONTROL Confirmer]** pour confirmer votre sélection. Sélectionnez **[!UICONTROL Annuler]** pour annuler la modification de la vue de données par défaut. |

  | Conteneurs | Valeur |
  |---|---|
  | [!UICONTROL Nom du conteneur de personnes] | `Person` |
  | [!UICONTROL Nom du conteneur de sessions] | `Session` |
  | [!UICONTROL Nom du conteneur d’événements] | `Event` |

  | Calendrier | Valeur |
  |---|---|
  | [!UICONTROL Fuseau horaire] | Fuseau horaire conforme à votre emplacement |
  | [!UICONTROL Type de calendrier] | Grégorien |
  | [!UICONTROL Premier mois de l’année] | Janvier |
  | [!UICONTROL Premier jour de la semaine] | Dimanche |


- Dans l’onglet **Composants** :
   - Toutes les mesures et dimensions qui comportent [!UICONTROL (AJO)] sont ajoutées automatiquement à leur nom dans le cadre de cette configuration automatique.
   - Certaines mesures ou dimensions, qui ont été ajoutées automatiquement, sont basées sur des champs dérivés. Ces champs dérivés sont spécifiquement créés pour cette intégration. Par exemple, la mesure [!UICONTROL Clics sur la page de destination (AJO)] est basée sur le champ dérivé [!UICONTROL Clics sur la page de destination].
   - Certaines mesures ou dimensions possèdent une configuration supplémentaire. Par exemple, les paramètres [!UICONTROL Format] et [!UICONTROL Valeurs d’inclusion et d’exclusion] sont appliqués pour le [!UICONTROL Taux de plaintes relatives au spam (AJO)].
   - Toutes les mesures et dimensions automatiquement ajoutées possèdent un libellé de contexte nommé `:`*`name_of_metric_or_dimension`*. Par exemple, la mesure [!UICONTROL Clics sur la page de destination (AJO)] possède le libellé de contexte `:Landing page clicks (AJO)`.

- Dans l’onglet **[!UICONTROL Paramètres]**, aucune valeur de configuration spécifique n’est appliquée.

>[!IMPORTANT]
>
>La modification de l’une des valeurs configurées automatiquement pour la connexion et la vue de données a des conséquences sur les rapports Journey Optimizer qui dépendent et utilisent l’intégration de Customer Journey Analytics configurée automatiquement.


## Configurer manuellement une vue de données à utiliser avec Journey Optimizer

Les sections suivantes décrivent comment utiliser manuellement les données générées par Journey Optimizer pour effectuer des analyses avancées dans Customer Journey Analytics. Cela n’est nécessaire que si l’[option de configuration automatique](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) est insuffisante pour répondre à vos besoins.

### Envoyer des données de Journey Optimizer vers Experience Platform

Adobe Experience Platform sert de source de données centrale et de lien entre Journey Optimizer et Customer Journey Analytics. Consultez [Commencer avec les jeux de données](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) dans le guide d’utilisation de Journey Optimizer pour savoir comment envoyer des données Journey Optimizer à Experience Platform en tant que jeu de données.

### Créer une connexion dans Customer Journey Analytics

Une fois que les données Journey Optimizer sont dans Adobe Experience Platform, vous pouvez [créer une connexion](/help/connections/create-connection.md) en fonction de votre jeu de données Journey Optimizer. Vous pouvez également ajouter des jeux de données Journey Optimizer à une connexion existante.

Sélectionnez et configurez les jeux de données suivants :

| Jeu de données | Type de jeu de données | Paramètres de connexion | Description |
| --- | --- | --- | --- |
| Jeu de données d’événement de commentaires sur les messages AJO | Événement | ID de personne : `IdentityMap` | Contient les événements de diffusion de message, tels que « [!UICONTROL Envois] » et « [!UICONTROL Rebonds] ». |
| Jeu de données d’événement d’expérience de tracking d’e-mail AJO | Événement | ID de personne : `IdentityMap` | Contient des événements de suivi d’e-mails tels que « [!UICONTROL Ouvertures] », « [!UICONTROL Clics] », et « [!UICONTROL Désabonnements] ». |
| Jeu de données d’événement d’expérience de tracking de notifications push AJO | Événement | ID de personne : `IdentityMap` | Contient des événements de suivi de notifications push tels que « [!UICONTROL Lancements d’application] ». |
| Événements d’étape de parcours | Événement | ID de personne : `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Contient des événements indiquant les profils ayant participé à chaque nœud du parcours. |
| Jeu de données d’entité AJO | Recherche | Clé : `_id`<br>clé correspondante : `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contient des classifications qui associent des métadonnées de parcours et de campagne à toutes les données d’événement Journey Optimizer. |

{style="table-layout:auto"}


### Configurez la vue de données pour qu’elle s’adapte aux dimensions et aux mesures Journey Optimizer.

Une fois la connexion créée, vous pouvez créer une ou plusieurs [vues des données](/help/data-views/create-dataview.md) pour configurer les dimensions et mesures souhaitées disponibles dans Customer Journey Analytics.

>[!NOTE]
>
>Les écarts de données entre Journey Optimizer et Customer Journey Analytics sont généralement inférieurs à 1-2 %. Des écarts plus importants sont possibles pour les données collectées au cours des deux dernières heures. Utilisez des périodes excluant aujourd’hui pour atténuer les écarts entre les temps de traitement.


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
