---
title: Créer Ou Modifier Une Configuration D’Informations De Conversation
description: Découvrez comment configurer les configurations de Conversation Insights.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: b29ee2f04a1775dca6a8fd93c3ac3050b67f0ceb
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 8%
---
# Création ou modification de configurations


Conversation Insights vous permet d’analyser les conversations (à partir de modèles de langage volumineux (LLM) ou d’êtres humains) à grande échelle et de donner à ces conversations un contexte dans le parcours client complet. Grâce à Conversation Insights, vous pouvez comprendre l’impact des représentants sur les résultats réels des utilisateurs.

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
   * Pour configurer les colonnes à afficher dans le tableau, sélectionnez ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]**, sélectionnez les colonnes à afficher. Sélectionnez ensuite **[!UICONTROL Appliquer]**.

1. Dans la section **[!UICONTROL Vues de données]** , si aucune vue de données n’est déjà configurée, sélectionnez **[!UICONTROL Sélectionner les vues de données]** pour sélectionner les vues de données.

   Si les vues de données sont déjà configurées, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier la sélection des vues de données]** pour reconfigurer la sélection des vues de données.

   Dans la boîte de dialogue **[!UICONTROL Sélectionner plusieurs vues de données]** :

   ![Conversation Insights : sélectionnez les vues de données](assets/conversation-insights-configuration-select-data-views.png)

   1. Sélectionnez une ou plusieurs vues de données à utiliser pour la configuration des informations sur la conversation.

   1. Sélectionnez **[!UICONTROL Utiliser les vues de données]** pour utiliser les vues de données. Sélectionner Annuler pour annuler.

   * Pour effectuer une recherche dans la liste des vues de données à sélectionner, utilisez le champ ![Rechercher](/help/assets/icons/Search.svg).
   * Pour configurer les colonnes à afficher dans le tableau, sélectionnez ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]**, sélectionnez les colonnes à afficher. Sélectionnez ensuite **[!UICONTROL Appliquer]**.

1. Pour terminer la configuration :

   * Sélectionnez **[!UICONTROL Ignorer]** pour une nouvelle configuration qui n’est pas créée.

   * Sélectionnez **[!UICONTROL Enregistrer pour plus tard]** pour une nouvelle configuration que vous souhaitez enregistrer, mais pour laquelle vous ne souhaitez pas créer l’artefact (mises à jour des vues de données par exemple). Vous pouvez donc revoir la configuration ultérieurement et terminer la création réelle de la configuration.

   * Sélectionnez **[!UICONTROL Créer]** pour créer la configuration.

   * Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer la configuration modifiée.

   * Sélectionnez **[!UICONTROL Restaurer]** pour restaurer la configuration afin de régénérer un nouveau jeu de données fusionné pour la configuration.

   * Sélectionnez **[!UICONTROL Quitter]** pour ignorer toute modification de la configuration.


## Vérification de la vue de données

(Expliquez les mesures et dimensions affichées à partir des jeux de données pertinents)


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