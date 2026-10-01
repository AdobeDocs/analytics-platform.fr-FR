---
title: Créer Ou Modifier Une Configuration D’Informations De Conversation
description: Découvrez comment configurer les configurations de Conversation Insights.
solution: Customer Journey Analytics
feature: AI Tools
role: Admin, User
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 58ed911b3d2c719dd05082c463fe66403e207ef9
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 16%
---
# Création ou modification de configurations

Conversation Insights vous permet d’analyser les conversations à partir des expériences d’agent que vous proposez à vos clients. Ces expériences d’agent peuvent être basées sur des modèles de langage étendus (LLM) ou sur des conversations humaines. Par exemple, un bot conversationnel interagissant avec les transcriptions d’un client ou d’un centre d’appel.
Grâce à Conversation Insights, vous pouvez comprendre l’impact des agents sur les résultats réels des utilisateurs et utilisatrices.

Grâce à l’interface de configuration des informations de conversation, vous pouvez rapidement créer ou modifier une configuration et les artefacts associés (connexion, vues de données, etc.).

Lorsque vous créez ou modifiez une configuration Insights de conversation, vous spécifiez le sandbox et les jeux de données d’événement qui contiennent des invites, des réponses et des données de commentaires. Vous sélectionnez également la connexion Customer Journey Analytics à laquelle vous souhaitez ajouter ces jeux de données. Ainsi que la vue de données à laquelle vous souhaitez ajouter les mesures et dimensions Insights de conversation.

Seuls les administrateurs système peuvent créer ou modifier des configurations de Conversation Insights.

Vous pouvez créer ou modifier des configurations à partir de l’interface [ Configurations de Conversation Insights ](./conversation-insights-manage.md).

## Restaurer le jeu de données fusionné manquant

Si vous modifiez une configuration et que le jeu de données fusionné qui a été généré pour la configuration n’existe plus, sélectionnez **[!UICONTROL Restaurer]** pour régénérer le jeu de données fusionné.


## Étapes de configuration

Pour chaque configuration :

1. Dans la section **[!UICONTROL Détails]**, spécifiez les informations suivantes :

   ![Détails des informations de conversation](assets/conversation-insights-configuration-details.png)

   | Champ | Description |
   |---------|----------|
   | **[!UICONTROL Nom]** | Attribuez un nom à la configuration. |
   | **[!UICONTROL Sandbox]** | Sélectionnez la sandbox Experience Platform qui contient les jeux de données d’événements d’invites, de réponses et de commentaires que vous souhaitez ajouter à votre connexion. |

1. Dans la section **[!UICONTROL Jeux de données]**, spécifiez les informations suivantes :

   ![Jeux de données d’informations sur les conversations](assets/conversation-insights-configuration-datasets.png)

   | Champ | Description |
   |---------|----------|
   | **[!UICONTROL Invite le jeu de données d’événement]** | Sélectionnez le jeu de données qui contient les données d’événement d’invite. |
   | **[!UICONTROL Jeu de données d’événement de réponses]** | Sélectionnez le jeu de données contenant les données d’événement de réponse. |
   | **[!UICONTROL Jeu de données d’événement de retour]** | Sélectionnez le jeu de données contenant les données d’événement de retour. |

1. Dans la section **[!UICONTROL Connexion]**, si aucune connexion n’est déjà configurée, utilisez **[!UICONTROL Sélectionner une connexion]** pour sélectionner une connexion.

   ![Connexion Insights de conversation](assets/conversation-insights-configuration-connection.png)

   Si une connexion est déjà configurée, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** pour sélectionner une autre connexion.

   ![Conversation Insights Edit Connection](assets/conversation-insights-configuration-edit-connection.png)

   Dans la boîte de dialogue **[!UICONTROL Sélectionner une connexion]** :

   ![Les informations de conversation sélectionnent la connexion](assets/conversation-insights-configuration-select-connection.png)

   1. Cochez la case en regard de la connexion à laquelle vous souhaitez ajouter les jeux de données d’événements d’invites, de réponses et de commentaires.
   1. Sélectionnez **[!UICONTROL Utiliser la connexion]**.

   * Pour effectuer une recherche dans la liste des connexions à sélectionner, utilisez le champ ![Rechercher](/help/assets/icons/Search.svg).
   * Pour configurer les colonnes à afficher dans le tableau, sélectionnez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). Dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]**, sélectionnez les colonnes à afficher. Sélectionnez ensuite **[!UICONTROL Appliquer]**.

1. Dans la section **[!UICONTROL Vues de données]** , si aucune vue de données n’est déjà configurée, sélectionnez **[!UICONTROL Sélectionner les vues de données]** pour sélectionner les vues de données.

   Si les vues de données sont déjà configurées, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier la sélection des vues de données]** pour reconfigurer la sélection des vues de données.

   Dans la boîte de dialogue **[!UICONTROL Sélectionner plusieurs vues de données]** :

   ![Conversation Insights : sélectionnez les vues de données](assets/conversation-insights-configuration-select-data-views.png)

   1. Sélectionnez une ou plusieurs vues de données à utiliser pour la configuration des informations sur la conversation.

   1. Sélectionnez **[!UICONTROL Utiliser les vues de données]** pour utiliser les vues de données. Sélectionner Annuler pour annuler.

   * Pour effectuer une recherche dans la liste des vues de données à sélectionner, utilisez le champ ![Rechercher](/help/assets/icons/Search.svg).
   * Pour configurer les colonnes à afficher dans le tableau, sélectionnez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). Dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]**, sélectionnez les colonnes à afficher. Sélectionnez ensuite **[!UICONTROL Appliquer]**.

1. Pour terminer la configuration :

   * Sélectionnez **[!UICONTROL Ignorer]** pour une nouvelle configuration qui n’est pas créée.

   * Sélectionnez **[!UICONTROL Enregistrer pour plus tard]** pour une nouvelle configuration que vous souhaitez enregistrer, mais pour laquelle vous ne souhaitez pas créer l’artefact (mises à jour des vues de données par exemple). Vous pouvez revoir la configuration ultérieurement et terminer la création réelle de la configuration.

   * Sélectionnez **[!UICONTROL Créer]** pour créer la configuration.

   * Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer la configuration modifiée.

   * Sélectionnez **[!UICONTROL Restaurer]** pour restaurer la configuration afin de régénérer un nouveau jeu de données fusionné pour la configuration.

   * Sélectionnez **[!UICONTROL Quitter]** pour ignorer toute modification de la configuration.


## Vérification de la vue de données

Les vues de données que vous avez configurées dans [Étapes de configuration](#configuration-steps) ont **[!UICONTROL Informations sur la conversation]** comme valeur pour **[!UICONTROL Intégrations]** dans [Vues de données](/help/data-views/manage-dataviews.md).

Pour chacune des vues de données configurées :

* **Conteneurs** : l’onglet [Conteneurs](/help/data-views/create-dataview.md#containers) contient un nouveau **[!UICONTROL Nom du conteneur]** : **[!UICONTROL conversation]** avec **[!UICONTROL Nom d’affichage]**: **[!UICONTROL Container]** comme **[!UICONTROL Système]** Type de conteneur **** supplémentaire.
* **Composants** : d’autres dossiers de champs de schéma s’affichent. Par exemple : agentExperience et conversation. En outre, les composants suivants sont automatiquement ajoutés :

  | Mesures | Type de données de schéma | Chemin du schéma |
  |---|---|---|
  | Commentaires clientèle | Chaîne | eventType |
  | Sentiments positifs | Chaîne | Champs dérivés |
  | Recommandations | Chaîne | eventType |
  | Tours | Chaîne | eventType |

  | Dimensions | Type de données de schéma | Chemin du schéma |
  |---|---|---|
  | ID d’agent ou d’agente | Chaîne | `agenticExperience.agents.agentID` |
  | Nom d’agent ou d’agente | Chaîne | `agenticExperience.agents.name` |
  | Nom de concierge | Chaîne | `agenticExperience.name` |
  | Version de concierge | Chaîne | `agenticExperience.version` |
  | ID de conversation | Chaîne | `conversation.conversationID` |
  | Nom de la conversation | Chaîne | `conversation.conversationName` |
  | Nom du signal de la conversation | Chaîne | `conversation.signals.name` |
  | Valeur booléenne de la synthèse de conversation | Booléen | `conversation.signals.values.booleanValue` |
  | Degré de confiance de la synthèse de conversation | Double | `conversation.signals.values.confidence` |
  | Clé de métadonnées de la synthèse de conversation | Chaîne | `conversation.signals.values.metadata.key` |
  | Valeur de nombre de la synthèse de conversation | Double | `conversation.signals.values.numberValue` |
  | Qualificatifs de synthèse de conversation | Chaîne | `conversation.signals.values.qualifiers` |
  | Signaux de ton de conversation | Chaîne | `conversation.signals.attributes.tones.values` |
  | Environnement | Chaîne | `agenticExperience.environment` |
  | Classification du feedback | Chaîne | Champs dérivés |
  | Commentaires – Classification des évaluations | Chaîne | `conversation.feedback.rating.classification` |
  | Objectif de la section Commentaires | Chaîne | `conversation.feedback.raw.purpose` |
  | Source des commentaires | Chaîne | `conversation.feedback.source` |
  | Expression | Chaîne | `conversation.signals.attributes.subjects.values.phrase` |
  | Texte brut de réponse | Chaîne | `conversation.response.raw.text` |
  | Source de réponse | Chaîne | `conversation.response.source` |
  | Classification de sentiment | Chaîne | Champs dérivés |
  | Nom de compétence | Chaîne | `agenticExperience.agents.skills.name` |
  | Version de compétence | Chaîne | `agenticExperience.agents.skills.version` |
  | Valeur | Chaîne | `agenticExperience.agents.skills.parameters.value` |


<!--

1. In the Data views dialog, select the checkbox next to one or more data views that you want to use when analyzing Experience Platform audience data within Analysis Workspace. These data views are automatically configured with Experience Platform audience data for reporting.

1. Select **[!UICONTROL Use data views]**.

1. Select **[!UICONTROL Create]** to create the configuration.

   >[!IMPORTANT]
   >
   >Because the profile dataset is updated once per day, audiences are available in Customer Journey Analytics data views on the day after you create the audience analysis configuration.


1. After 24 hours, [view audience dimensions in the data view](#view-audience-dimensions-in-the-data-view) to verify that the audience dimensions are available in the data views that you selected. 


 
## View audience dimensions in the data view

After you [create an audience analysis configuration](#create-an-audience-analysis-configuration), you can verify that audience dimensions were added to the data views that you selected during the configuration.

To view audience dimensions in the data view, you must be a product profile administrator for the product profile that the data view is assigned to. For more information, see [Access control](/help/technotes/access-control.md).

To view the audience analysis dimensions in the data view:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. In the **[!UICONTROL Dimensions]** section, the following dimensions should now be available:

   * **[!UICONTROL Audience Name]**

   * **[!UICONTROL Audience Origin]**

   * **[!UICONTROL Exited Audience Origin]**

   * **[!UICONTROL Exited Audience Name]**

   Note that each of these dimensions was added to the profile dataset that is associated with the merge policy that you selected during the audience analysis configuration, and each was added to the new lookup dataset that was created.

   ![Audience dimensions available in the data view](assets/audience-analysis-dataview-dataset.png)

1. Use the audience analysis dimensions in Analysis Workspace. 

   Users who have access to use the data view in Analysis Workspace can now see the new dimensions and use them in their analyses. For information about how to use the audience analysis dimensions in Analysis Workspace, see [Analyze Experience Platform audiences in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

-->