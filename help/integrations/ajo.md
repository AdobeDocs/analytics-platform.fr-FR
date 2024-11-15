---
title: Intégrer Adobe Journey Optimizer
description: Importez les données générées par Adobe Journey Optimizer et analysez-les à l’aide d’Analysis Workspace dans Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: d5e8c75f1e3a207b625421a13219674f8da6c3f5
workflow-type: ht
source-wordcount: '3020'
ht-degree: 100%

---

# Intégrer Journey Optimizer

[Adobe Journey Optimizer](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/get-started/get-started) vous aide à offrir des expériences connectées, contextuelles et personnalisées. Cela permet d’exposer vos clients à l’étape suivante de leur parcours client.

Vous pouvez configurer les données générées par Journey Optimizer afin d’effectuer une analyse avancée dans Customer Journey Analytics. Vous pouvez configurer cette intégration automatiquement. Si nécessaire, vous pouvez personnaliser manuellement des jeux de données, des dimensions ou des mesures supplémentaires disponibles dans votre connexion ou vos vues de données.

## Configurer automatiquement l’intégration Journey Optimizer

Journey Optimizer prend en charge l’utilisation de Customer Journey Analytics comme moteur de création de rapports. Voir [Commencer avec la nouvelle interface de création de rapports](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) dans la documentation de Journey Optimizer.

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

Les sections suivantes décrivent comment utiliser manuellement les données générées par Journey Optimizer pour effectuer des analyses avancées dans Customer Journey Analytics. Cette configuration manuelle n’est nécessaire que si l’[option de configuration automatique](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) est insuffisante pour répondre à vos besoins.

### Envoyer des données de Journey Optimizer vers Experience Platform

Adobe Experience Platform sert de source de données centrale et de lien entre Journey Optimizer et Customer Journey Analytics. Consultez [Commencer avec les jeux de données](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) dans le guide d’utilisation de Journey Optimizer pour savoir comment envoyer des données Journey Optimizer à Experience Platform en tant que jeu de données.

### Créer une connexion

Une fois que les données Journey Optimizer sont dans Adobe Experience Platform, vous pouvez [créer une connexion](/help/connections/create-connection.md) en fonction de votre jeu de données Journey Optimizer. Vous pouvez également ajouter des jeux de données Journey Optimizer à une connexion existante.

Sélectionnez et configurez les jeux de données suivants :

| Jeu de données | Type de jeu de données | Paramètres de connexion | Description |
| --- | --- | --- | --- |
| Jeu de données d’événement de feedback de message AJO | Événement | ID de personne : `IdentityMap` | Contient les événements de diffusion de message, tels que « [!UICONTROL Envois] » et « [!UICONTROL Rebonds] ». |
| Jeu de données d’événement d’expérience de suivi d’e-mail AJO | Événement | ID de personne : `IdentityMap` | Contient des événements de suivi d’e-mails tels que « [!UICONTROL Ouvertures] », « [!UICONTROL Clics] », et « [!UICONTROL Désabonnements] ». |
| Jeu de données d’événement d’expérience de suivi de notification push AJO | Événement | ID de personne : `IdentityMap` | Contient des événements de suivi de notifications push tels que « [!UICONTROL Lancements d’application] ». |
| Événements d’étape de parcours | Événement | ID de personne : `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Contient des événements indiquant les profils ayant participé à chaque nœud du parcours. |
| Jeu de données d’entité AJO | Recherche | Clé : `_id`<br>clé correspondante : `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contient des classifications qui associent des métadonnées de parcours et de campagne à toutes les données d’événement Journey Optimizer. |

{style="table-layout:auto"}


### Configurer la vue de données

Une fois la connexion créée, vous pouvez créer une ou plusieurs [vues des données](/help/data-views/create-dataview.md) pour configurer les dimensions et mesures souhaitées disponibles dans Customer Journey Analytics.

>[!NOTE]
>
>Les écarts de données entre Journey Optimizer et Customer Journey Analytics sont généralement inférieurs à 1-2 %. Des écarts plus importants sont possibles pour les données collectées au cours des deux dernières heures. Utilisez des périodes excluant aujourd’hui pour atténuer les écarts entre les temps de traitement.


#### Configurer des dimensions

Vous pouvez créer les dimensions suivantes dans une vue de données pour obtenir une parité approximative avec des dimensions similaires dans Journey Optimizer. Voir [Paramètres des composants](/help/data-views/component-settings/overview.md) dans le Gestionnaire de vues de données pour en savoir plus sur les options de personnalisation des dimensions.

| Dimension | Description | Jeu(x) de données | Élément de schéma | Paramètres de composant |
| --- | --- | --- | --- | --- |
| Erreur d’exécution d’action (AJO) | Condition d’erreur qui empêchait l’exécution du parcours d’exécuter l’action. | Événements d’étape de parcours | `_experience.journeyOrchestration.`<br/>`stepEvents.actionExecutionError ` | Type de composant : dimension |
| Libellé d’action (AJO) | Le client ou la cliente a généré le nom d’affichage de l’élément avec lequel la personne finale a interagi. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.decisioning.`<br/>`propositionAction.label` | Type de composant : dimension |
| Identifiant de lot (AJO) | GUID créé à l’appel de chaque nouvelle instance de lot pour une action de parcours ou de campagne planifiée. Par exemple, si une action de parcours ou de campagne planifiée s’exécute à 8 h et 10 h, il existe deux batchInstanceID?s distincts. | Jeu de données d’événement d’expérience de suivi de notification push AJO, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | ` _experience.customerJourneyManagement.`<br/>`messageExecution.batchInstanceID` | Type de composant : dimension |
| Date et heure des instances de lot (AJO) | Date et heure de l’instance de lot. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | Champs dérivés | Type de composant : dimension (champ dérivé) |
| Identifiant de campagne (AJO) | Identifiant de la campagne. | Jeu de données d’entité AJO | `_experience.customerJourneyManagement.entities.`<br/>`campaign.campaignID` | Type de composant : dimension |
| Nom de campagne (AJO) | Nom de la campagne. | Jeu de données d’entité AJO | `_experience.customerJourneyManagement.entities.`<br/>`campaign.name` | Type de composant : dimension |
| Identifiant de version de la campagne (AJO) | Identifiant de version de la campagne. | Jeu de données d’entité AJO | `_experience.customerJourneyManagement.`<br/>`entities.campaign.campaignVersionID` | Type de composant : dimension |
| Canal (AJO) | Canal avec lequel ces données doivent être corrélées. | Jeu de données d’entité AJO | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.channel._id` | Type de composant : dimension |
| Identifiant de corrélation (AJO) | Identifiant de corrélation. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.decisioning.propositions.`<br/>`scopeDetails.correlationID` | Type de composant : dimension |
| Identifiant de politique de décision (AJO) | Identifiant de la politique de décision utilisée lors de la décision des éléments à inclure dans cette proposition. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | Champs dérivés | Type de composant : dimension (champ dérivé) |
| Domaine de la personne destinataire de l’e-mail (AJO) | Domaine de l’adresse e-mail | Jeu de données d’événement d’expérience de suivi de notification push AJO, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`emailChannelContext.address` | Type de composant : dimension |
| Objet de l’e-mail (AJO) | Objet de l’e-mail, non personnalisé | Jeu de données d’entité AJO | `_experience.customerJourneyManagement.entities.`<br/>`channelDetails.email.subject` | Type de composant : dimension |
| Identifiant d’événement (AJO) | Identifiant unique de l’événement de série temporelle. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_id` | Type de composant : dimension (champ dérivé) |
| ID de critères de sortie (AJO) | ID des critères de sortie utilisés pour déterminer si le parcours doit être fermé. | Événements d’étape de parcours | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaID` | Type de composant : dimension |
| Nom de critères de sortie (AJO) | Nom des critères de sortie. | Événements d’étape de parcours | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaName` | Type de composant : dimension |
| Identifiant de l’expérience (AJO) | Identifiant de l’expérience. | Jeu de données d’entité AJO | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | Type de composant : dimension |
| Nom de l’expérience (AJO) | Nom de l’expérience. | Jeu de données d’entité AJO | `_experience.customerJourneyManagement.entities.`<br/>`experiment.experimentName` | Type de composant : libellés contextuels de dimension : expérience d’expérimentation |
| Erreur de récupération (AJO) | Condition d’erreur qui empêchait l’exécution du parcours d’exécuter la récupération. | Événements d’étape de parcours | `_experience.journeyOrchestration.`<br/>`stepEvents.fetchError` | Type de composant : dimension |
| Optimisé pour l’heure d’envoi (AJO) | Exécution du message SendTimeOptimized | Jeu de données d’événement d’expérience de suivi de notification push AJO, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageProfile.isSendTimeOptimized` | Type de composant : dimension |
| Parcours de test (AJO) | L’événement fait-il partie d’une exécution de parcours de test ? | Événements d’étape de parcours | `_experience.journeyOrchestration.`<br/>`stepEvents.inTest` | Type de composant : dimension |
| Message de test (AJO) | Message envoyé en tant qu’exécution de test | Jeu de données d’événement d’expérience de suivi de notification push AJO, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageProfile.isTestExecution` | Type de composant : dimension |
| Identifiant de l’élément (AJO) | Identifiant de l’élément. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.decisioning.`<br/>`propositions.items.id` | Type de composant : dimension |
| Nom de l’élément (AJO) | Nom de l’élément | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.decisioning.`<br/>`propositions.items.name` | Type de composant : dimension |
| ID d’action de parcours | ID d’action de parcours, pour lequel MessageExecution est déclenché. | Jeu de données d’événement d’expérience de suivi de notification push AJO, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageExecution.journeyActionID` | Type de composant : dimension |
| Nom du nœud d’action du parcours (AJO) | Nom du nœud d’action du parcours. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires pour les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO, jeu de données d’entité AJO | Champs dérivés | Type de composant : dimension (champ dérivé) |
| Nom du nœud d’événement de parcours (AJO) | Cette valeur est définie chaque fois qu’un segment ou un événement externe se produit dans un parcours. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires pour les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO, jeu de données d’entité AJO | Champs dérivés | Type de composant : dimension (champ dérivé) |
| Identifiant du parcours (AJO) | Identifiant du parcours. | Jeu de données d’entité AJO | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyID` | Type de composant : dimension |
| Nom du parcours (AJO) | Nom du parcours. | Jeu de données d’entité AJO | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyName` | Type de composant : dimension |
| Nom et version du parcours (AJO) | Nom et version du parcours. | Jeu de données d’entité AJO | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNameAndVersion` | Type de composant : dimension |
| Identifiant de version du parcours (AJO) | Identifiant de version du parcours. | Jeu de données d’entité AJO | `_experience.customerJourneyManagement.entities.`<br/>`journey.journeyVersionID` | Type de composant : dimension |
| Identifiant de page de destination (AJO) | Identifiant unique de la page de destination. | Jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.landingpage.landingPageID` | Type de composant : dimension |
| Source de la page de destination (AJO) | Source de la page de destination. | Jeu de données d’événement d’expérience de suivi d’e-mail AJO | Champs dérivés | Type de composant : dimension (champ dérivé) |
| URL de lien (AJO) | URL sur laquelle l’utilisateur ou l’utilisatrice a cliqué. | Jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.urlID` | Type de composant : dimension |

{style="table-layout:auto"}

#### Configurer des mesures

Vous pouvez créer les mesures suivantes dans une vue de données pour obtenir une parité approximative avec des mesures similaires dans Journey Optimizer. Voir [Paramètres des composants](/help/data-views/component-settings/overview.md) dans le Gestionnaire de vues de données pour en savoir plus sur les options de personnalisation des mesures.

| Mesure | Description | Jeu(x) de données | Élément de schéma | Paramètres de composant |
| --- | --- | --- | --- | --- |
| Installations d’applications (AJO) | Nombre d’installations d’application | Jeu de données d’événement d’expérience de suivi de notification push AJO | `application.installs.value` | Type de composant : mesure |
| Lancements d’application (AJO) | Nombre de lancements de l’application mobile | Jeu de données d’événement d’expérience de suivi de notification push AJO | `application.launches.value` | Type de composant : mesure |
| Rebonds pour les canaux sortants (AJO) | Nombre total de messages ayant fait l’objet d’un rebond sur les canaux sortants | Jeu de données d’événement de feedback de message AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Type de composant : mesure |
| Clics (AJO) | Nombre total de clics sur tous les canaux | Jeu de données d’événement de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement d’expérience de suivi d’e-mail AJO, jeu de données d’événement de commentaires pour les messages AJO | Champs dérivés | Type de composant : mesure (champ dérivé) |
| Nombre d’offres de secours (AJO) | Nombre d’offres de secours. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.decisioning.propositions.items.`<br/>`itemSelection.selectionDetail.selectionType` | Type de composant : mesure |
| Nombre d’offres (AJO) | Nombre dʼoffres. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | ` _experience.decisioning.`<br/>`propositions.items.id` | Type de composant : mesure |
| Mesure de déduplication (AJO) | Mesure de déduplication | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_id` | Type de composant : mesure |
| Diffusé (AJO) | Nombre total de messages diffusés. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | Champs dérivés | Type de composant : mesure (champ dérivé) |
| Refusé (AJO) | Compte chaque fois que le message in-app est fermé par le SDK Adobe, quelle que soit l’action choisie par la personne finale pour le fermer. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Type de composant : mesure |
| Affichages (AJO) | Ce nombre indique les affichages des messages AJO. Cela inclut les ouvertures d’e-mail, les affichages web et les affichages in-app. Les plateformes mobiles ne signalent pas les SMS et les affichages de messages push. Elles ne sont donc pas comptabilisées. | Jeu de données d’événement de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement d’expérience de suivi d’e-mail AJO, jeu de données d’événement de commentaires pour les messages AJO | Champs dérivés | Type de composant : mesure (champ dérivé) |
| Ouvertures d’e-mail (AJO) | Nombre total d’ouvertures d’e-mail | Jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Type de composant : mesure |
| Clics entrants (AJO) | Nombre total de clics sur les canaux entrants | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.decisioning.`<br/>`propositionEventType.interact` | Type de composant : mesure |
| Rejets entrants (AJO) | Nombre total de rejets sur les canaux entrants | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Type de composant : mesure |
| Impressions entrantes (AJO) | Nombre total d’impressions sur les canaux entrants | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.decisioning.`<br/>`propositionEventType.display` | Type de composant : mesure |
| Fin du parcours (AJO) | True si l’étape actuelle entraînait la fin d’une instance du parcours. Il s’agit de la dernière étape d’un parcours pour un profil donné qui a été exécutée avec succès. | Événements d’étape de parcours | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | Type de composant : mesure |
| Entrées du parcours (AJO) | True si l’événement d’étape était un événement d’entrée de parcours pour un profil. | Événements d’étape de parcours | Champs dérivés | Type de composant : mesure (champ dérivé) |
| Sorties du parcours (AJO) | True si l’étape actuelle entraînait la fin d’une instance du parcours. Il s’agit de la dernière étape d’un parcours pour un profil donné qui a été exécutée avec succès. | Événements d’étape de parcours | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | Type de composant : mesure |
| Échecs du parcours (AJO) | Indique l’état actuel de l’étape dont l’exécution est terminée. Valeurs possibles : `Transitions` (l’étape suivante se produit sur une transition d’événement), `EndStep` (la dernière étape de cette instance de parcours a été exécutée), `Error` (cette étape a rencontré une condition d’erreur, mettant fin à l’instance de parcours actuelle), `TimedOut` (l’étape actuelle s’est terminée en raison d’un délai d’attente lors d’une récupération ou d’une action). | Événements d’étape de parcours | `_experience.journeyOrchestration.`<br/>`stepEvents.stepStatus` | Type de composant : mesure |
| Clics sur la page de destination (AJO) | Nombre total de clics sur la page de destination. | Jeu de données d’événement d’expérience de suivi d’e-mail AJO | Champs dérivés | Type de composant : mesure (champ dérivé) |
| Conversions de pages de destination (AJO) | Nombre total de conversions sur la page de destination. | Jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Type de composant : mesure |
| Vues de la page de destination (AJO) | Nombre total de vues sur la page de destination. | Jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Type de composant : mesure |
| Entrées du nœud (AJO) | True si l’événement d’étape était un événement d’entrée de nœud pour un profil. | Événements d’étape de parcours | Champs dérivés | Type de composant : mesure (champ dérivé) |
| Clics sortants (AJO) | Nombre total de clics sur les canaux sortants | Jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Type de composant : mesure |
| Erreurs sortantes (AJO) | Nombre total de messages contenant des erreurs sur les canaux sortants | Jeu de données d’événement de feedback de message AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Type de composant : mesure |
| Exclusions sortantes (AJO) | Nombre total d’événements d’exclusion sur les canaux sortants | Jeu de données d’événement de feedback de message AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Type de composant : mesure |
| Envois sortants (AJO) | Nombre total de messages envoyés sur les canaux sortants | Jeu de données d’événement de feedback de message AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Type de composant : mesure |
| Actions personnalisées de notification push (AJO) | Nombre total d’actions personnalisées dans l’interaction avec des notifications push. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `eventType` | Type de composant : mesure |
| Interactions des notifications push (AJO) | Nombre de lancements d’une application mobile en raison d’une interaction directe avec un message push | Jeu de données d’événement d’expérience de suivi de notification push AJO | `application.launches.value` | Type de composant : mesure |
| Envois (AJO) | Nombre total de messages envoyés sur tous les canaux | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | Champs dérivés | Type de composant : mesure (champ dérivé) |
| Messages SMS entrants (AJO) | Réponse entrante par SMS. Par exemple, arrêter, commencer, s’abonner, etc. | Jeu de données d’événement d’expérience de suivi de notification push AJO, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.inboundMessage` | Type de composant : mesure |
| Taux de plaintes relatives au spam (AJO) | Nombre total de plaintes relatives au spam | Jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Type de composant : mesure |
| Ajouts à la liste d’abonnements (AJO) | Nombre total d’ajouts à la liste d’abonnements. | Jeu de données d’événement d’expérience de suivi d’e-mail AJO | Champs dérivés | Type de composant : mesure (champ dérivé) |
| Suppressions de la liste d’abonnements (AJO) | Nombre total de suppressions de la liste d’abonnements. | Jeu de données d’événement d’expérience de suivi d’e-mail AJO | Champs dérivés | Type de composant : mesure (champ dérivé) |
| Ciblé (AJO) | Nombre de fois où une proposition a été ciblée sur une personne. Il s’agit du nombre de fois où une proposition a été envisagée d’être affichée pour une personne. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | Champs dérivés | Type de composant : mesure (champ dérivé) |
| Déclenché (AJO) | La proposition a été choisie pour être affichée par le SDK Adobe. D’autres facteurs peuvent empêcher son affichage réel. | Jeu de données d’événement d’expérience de suivi de notification push AJO, événements d’étape de parcours, jeu de données d’événement de commentaires sur les messages AJO, jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Type de composant : mesure |
| Visiteurs et visiteuses uniques dans l’expérience (AJO) | Visiteurs et visiteuses uniques dans l’expérience | Jeu de données d’entité AJO | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | Type de composant : mesure |
| Désabonnements (AJO) | Nombre total de désabonnements | Jeu de données d’événement d’expérience de suivi d’e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Type de composant : mesure |

{style="table-layout:auto"}
