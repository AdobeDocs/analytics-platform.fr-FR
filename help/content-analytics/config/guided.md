---
title: Configuration guidée par Content Analytics
description: Découvrez comment configurer Content Analytics à l’aide d’une configuration guidée d’intégration.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
autotag-review: '2026-05-19T08:54:42.845Z'
TQID: 'https://experienceleague.adobe.com/kEqjocKd5pNypjQlF70HeF1bKuoG9Qi-AT6nJiIwuV0'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c18d9e03-ac7d-4811-9c92-3e92ddc70ade
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 6af3e9063dc192814c888e786ca61ff1703aedf5
workflow-type: tm+mt
source-wordcount: 4177
ht-degree: 63%

---


# Configuration guidée de Content Analytics

La configuration guidée vous permet de configurer rapidement et facilement Content Analytics. La configuration guidée utilise un assistant pour définir les exigences afin de configurer Content Analytics automatiquement pour votre organisation. Dans l’écran **[!UICONTROL Configuration]**, vous pouvez créer une configuration ou modifier une configuration existante.

>[!IMPORTANT]
>
>Votre organisation ne peut avoir qu’une seule configuration Content Analytics par sandbox.

>[!NOTE]
>
>L’assistant de configuration prend en charge plusieurs vues de données et canaux. Il est différent de la version précédente qui ne prenait en charge qu’une seule vue de données et que le canal web. Vous devez sélectionner un sandbox et une connexion avant de pouvoir sélectionner une ou plusieurs vues de données dans la section [Vues de données](#data-views). Les configurations des **[!UICONTROL capture d’expérience]**, **[!UICONTROL collecte de données]** et **[!UICONTROL remplacements d’en-tête]** dépendent du canal et font partie de chacun des canaux que vous configurez dans la section [Canaux](#channels).

Pour accéder à la configuration de Content Analytics :

* Sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Configuration de Content Analytics]** dans le menu principal de Customer Journey Analytics.

Dans l’écran **[!UICONTROL Configurations de Content Analytics]**, un tableau des configurations existantes de Content Analytics s’affiche.

![Configurations Content Analytics](../assets/aca-configuration-table.png)
Pour chaque configuration, les détails suivants sont disponibles :

| Colonne | Description |
|---|---|
| **[!UICONTROL Nom]** | Nom de la configuration. |
| **[!UICONTROL Créé par]** | Compte technique ayant créé la configuration. |
| **[!UICONTROL Date de création]** | Date et heure de création de la configuration. |
| **[!UICONTROL Date de modification]** | Date et heure de la dernière modification de la configuration. |
| **[!UICONTROL Sandbox]** | Sandbox au sein de l’organisation dans lequel Content Analytics est configuré et implémenté (ou le sera à l’avenir). |
| **[!UICONTROL Statut]** | Statut de la configuration. Le statut indique le nombre de canaux activés pour lesquels la configuration est terminée. Utilisez ![InfoOutline](/help/assets/icons/InfoOutline.svg) pour ouvrir une fenêtre contextuelle contenant plus de détails. |

Vous pouvez utiliser ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour personnaliser le tableau. Sélectionnez les colonnes à afficher dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]** et sélectionnez **[!UICONTROL Appliquer]** pour appliquer les modifications.

À partir de l’écran **[!UICONTROL Configuration]** de Content Analytics, vous pouvez créer une configuration ou modifier une configuration existante.

Pour créer une configuration, procédez comme suit :

* Sélectionnez **[!UICONTROL Créer une configuration]**. Cette action ouvre l’[assistant de configuration guidé](#guided-configuration-wizard).

Pour modifier une configuration existante, procédez comme suit :

* Sélectionnez ![Plus](/help/assets/icons/More.svg), puis ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** pour une configuration Content Analytics existante. Cette action ouvre l’[assistant de configuration guidé](#guided-configuration-wizard).

## Assistant de configuration guidé

L’assistant de configuration guidé se compose de quatre sections ([Détails](#details), [Connexion](#connection), [Vue de données](#data-view) et [Canaux](#channels)), chacune vous invitant à fournir les informations requises pour configurer correctement Content Analytics. Renseignez chaque section avant de passer à la section suivante, car certains paramètres d’une section peuvent dépendre des valeurs de configuration des sections précédentes.

### Détails {#onboarding-details}

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Détails"
>abstract="Fournissez le nom de la connexion. Les sections **[!UICONTROL Vue de données]**, **[!UICONTROL Capture et définition d’expérience]** et **[!UICONTROL Collecte de données]** permettent de fournir plus de détails pour configurer correctement Content Analytics."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Détails"
>abstract="Ce guide définit les exigences nécessaires à la configuration de l’analyse du contenu. Attribuez un nom à cette configuration."

>[!CONTEXTUALHELP]
>id="aca_onboarding_connection_boldheader"
>title="Connexion"
>abstract="**Connexion**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_connection_header"
>title="Connexion"
>abstract="Dans Customer Journey Analytics, sélectionnez une connexion existante avec laquelle fusionner vos données Content Analytics."

Chaque configuration nécessite un nom unique. Par exemple : `Example Content Analytics configuration`. Le nom est requis pour enregistrer ou implémenter une configuration.

Pour chaque configuration, vous devez également sélectionner le sandbox pour lequel vous souhaitez configurer Content Analytics.

![Détails de la configuration de Content Analytics](../assets/aca-configuration-details.png)

* **[!UICONTROL Name]** : chaque configuration nécessite un nom unique. Par exemple : `Example Content Analytics configuration`. Le nom est requis pour enregistrer ou implémenter une configuration.

* **[!UICONTROL Sandbox]** : la configuration nécessite un sandbox. Sélectionnez un sandbox dans la liste des sandbox auxquels vous avez accès et sur lesquels sont collectées les données que vous souhaitez utiliser pour Content Analytics.

  Si vous modifiez un sandbox configuré pour lequel vous avez défini une connexion et éventuellement des vues de données, vous êtes averti que la connexion et les vues de données doivent être reconfigurées.

### Connexion

Vous devez sélectionner une connexion à laquelle vous souhaitez ajouter la collecte de données Content Analytics.

Si vous n’avez pas sélectionné de connexion pour votre configuration :

1. Utilisez ![Données](/help/assets/icons/Data.svg) **[!UICONTROL Sélectionner une connexion]** pour ouvrir la boîte de dialogue **[!UICONTROL Sélectionner une connexion]** qui répertorie toutes les connexions disponibles sur le sandbox.
1. Dans la boîte de dialogue **[!UICONTROL Sélectionner une connexion]**, sélectionnez ![SelectBox](/help/assets/icons/SelectBox.svg) une connexion que vous souhaitez utiliser. Vous ne pouvez sélectionner qu’une seule connexion.
1. Sélectionnez **[!UICONTROL Utiliser la connexion]**.

Si vous avez déjà sélectionné une connexion, mais que vous souhaitez la modifier :

1. Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]**.
1. Dans la boîte de dialogue **[!UICONTROL Sélectionner une connexion]**, modifiez la connexion que vous souhaitez utiliser.
1. Sélectionnez **[!UICONTROL Utiliser la connexion]**.


### Vues des données {#onboarding-data-view}

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Vue de données"
>abstract="Pour la configuration de Content Analytics, vous devez sélectionner une vue de données existante. Vous pouvez ainsi fusionner vos données d’analyse de contenu avec d’autres données."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Vue de données"
>abstract="Dans Customer Journey Analytics, sélectionnez une vue de données existante avec laquelle fusionner vos données d’analyse de contenu."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Vue de données"
>abstract="Dans Customer Journey Analytics, sélectionnez une vue de données existante avec laquelle fusionner vos données d’analyse de contenu.<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="Nouvelle vue de données"
>abstract="Vous avez sélectionné une nouvelle vue de données pour cette configuration. La nouvelle vue de données sera mise à jour afin d’inclure les mesures et dimensions de Content Analytics. Ces mesures et dimensions seront supprimées de la vue de données sélectionnée à l’origine.<br/><br/>Si une autre connexion est associée à la nouvelle vue de données, la connexion est mise à jour pour inclure les jeux de données Content Analytics. Les jeux de données de l’analyse du contenu ne sont pas supprimés de la connexion sélectionnée à l’origine."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="Nettoyer la vue de données sélectionnée"
>abstract="La vue de données que vous avez sélectionnée est déjà configurée pour Content Analytics. Cette configuration Content Analytics existante est supprimée et votre nouvelle configuration s’applique à la vue de données."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Nettoyer la vue de données précédente"
>abstract="Vous avez sélectionné une nouvelle vue de données. La configuration Content Analytics de la vue de données sélectionnée précédente est supprimée."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_new_dialog"
>title="Nouvelle vue de données"
>abstract="Vous avez sélectionné une nouvelle vue de données pour cette configuration. La nouvelle vue de données sera mise à jour afin d’inclure les mesures et dimensions de Content Analytics. Les mesures et dimensions similaires seront supprimées de la vue de données existante.<br/>Si une autre connexion est associée à la nouvelle vue de données, la connexion est mise à jour pour inclure les jeux de données Content Analytics. Notez que les jeux de données Content Analytics ne sont pas supprimés de la configuration existante."


>[!CONTEXTUALHELP]
>id="ac_onboarding_dataviews_button"
>title="Vue de données"
>abstract="Pour la configuration de Content Analytics, vous devez sélectionner une ou plusieurs vues de données. Vous pouvez ainsi fusionner vos données d’analyse de contenu avec d’autres données."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_header"
>title="Vues des données"
>abstract="Dans Customer Journey Analytics, sélectionnez une ou plusieurs vues de données existantes avec lesquelles fusionner vos données Content Analytics."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_header_alt"
>title="Vues des données"
>abstract="Dans Customer Journey Analytics, sélectionnez une ou plusieurs vues de données existantes avec lesquelles fusionner vos données Content Analytics.<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_new_dialog"
>title="Vues de données sélectionnées"
>abstract="Vous avez modifié les vues de données sélectionnées pour cette configuration. Les vues de données sélectionnées seront mises à jour afin d’inclure les mesures et dimensions de Content Analytics. Ces mesures et dimensions seront supprimées des vues de données précédemment sélectionnées qui ne sont plus sélectionnées.<br/><br/>Si une autre connexion est associée aux vues de données sélectionnées, la connexion est mise à jour pour inclure les jeux de données Content Analytics. Les jeux de données de l’analyse du contenu ne sont pas supprimés de la connexion sélectionnée à l’origine.<br/><br/>Toutes les vues de données sélectionnées héritent des canaux qui font partie de cette configuration."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_change_dialog"
>title="Vues de données sélectionnées"
>abstract="Vous avez modifié les vues de données sélectionnées pour cette configuration. Les vues de données sélectionnées seront mises à jour afin d’inclure les mesures et dimensions de Content Analytics. Ces mesures et dimensions seront supprimées des vues de données précédemment sélectionnées qui ne sont plus sélectionnées.<br/><br/>Si une autre connexion est associée aux vues de données sélectionnées, la connexion est mise à jour pour inclure les jeux de données Content Analytics. Les jeux de données de l’analyse du contenu ne sont pas supprimés de la connexion sélectionnée à l’origine.<br/><br/>Toutes les vues de données sélectionnées héritent des canaux qui font partie de cette configuration."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_current_cleanup_labels_dialog"
>title="Vues de données sélectionnées"
>abstract="Vous avez modifié les vues de données sélectionnées pour cette configuration. Les vues de données sélectionnées seront mises à jour afin d’inclure les mesures et dimensions de Content Analytics. Ces mesures et dimensions seront supprimées des vues de données précédemment sélectionnées qui ne sont plus sélectionnées.<br/><br/>Si une autre connexion est associée aux vues de données sélectionnées, la connexion est mise à jour pour inclure les jeux de données Content Analytics. Les jeux de données de l’analyse du contenu ne sont pas supprimés de la connexion sélectionnée à l’origine.<br/><br/>Toutes les vues de données sélectionnées héritent des canaux qui font partie de cette configuration."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_prev_cleanup_labels_dialog"
>title="Vues de données sélectionnées"
>abstract="Vous avez modifié les vues de données sélectionnées pour cette configuration. Les vues de données sélectionnées seront mises à jour afin d’inclure les mesures et dimensions de Content Analytics. Ces mesures et dimensions seront supprimées des vues de données précédemment sélectionnées qui ne sont plus sélectionnées.<br/><br/>Si une autre connexion est associée aux vues de données sélectionnées, la connexion est mise à jour pour inclure les jeux de données Content Analytics. Les jeux de données de l’analyse du contenu ne sont pas supprimés de la connexion sélectionnée à l’origine.<br/><br/>Toutes les vues de données sélectionnées héritent des canaux qui font partie de cette configuration."

>[!CONTEXTUALHELP]
>id="aca_onboarding_channels_button"
>title="Canaux"
>abstract="Activez et configurez un ou plusieurs canaux pour la configuration."

>[!CONTEXTUALHELP]
>id="aca_onboarding_channels_header"
>title="Canaux"
>abstract="Activez et configurez un ou plusieurs canaux pour la configuration. Toutes les vues de données faisant partie de la configuration héritent des canaux activés."


Votre configuration nécessite la sélection d’une ou de plusieurs [vues de données](/help/data-views/data-views.md).

Si vous n’avez pas sélectionné de vues de données pour votre configuration :

1. Utilisez ![Données](/help/assets/icons/Data.svg) **[!UICONTROL Sélectionner la vue de données]** pour ouvrir la boîte de dialogue **[!UICONTROL Vue de données]** qui répertorie toutes les vues de données disponibles pour la connexion que vous avez configurée pour Content Analytics.
1. Dans la boîte de dialogue **[!UICONTROL Vue de données]**, sélectionnez ![SelectBox](/help/assets/icons/SelectBox.svg) une ou plusieurs vues de données à utiliser.
1. Sélectionnez **[!UICONTROL Enregistrer]**.

Si vous avez déjà sélectionné une ou plusieurs vues de données, mais que vous souhaitez modifier cette sélection :

1. Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier la sélection de la vue de données]**.
1. Dans la boîte de dialogue **[!UICONTROL Vue de données]**, modifiez la sélection ![SelectBox](/help/assets/icons/SelectBox.svg) des vues de données que vous souhaitez utiliser.
1. Sélectionnez **[!UICONTROL Enregistrer]**.

Une fois que vous avez sélectionné **[!UICONTROL Enregistrer]**, une boîte de dialogue **[!UICONTROL Vues de données sélectionnées]** s’affiche et vous informe des implications de l’inclusion de Content Analytics pour les vues de données sélectionnées. Sélectionnez **[!UICONTROL Continuer]** pour continuer ou **[!UICONTROL Annuler]** pour annuler.

Les actions suivantes sont disponibles dans la boîte de dialogue **[!UICONTROL Vue de données]** :

* Pour rechercher une vue de données spécifique, utilisez le champ ![Recherche](/help/assets/icons/Search.svg).
* Pour filtrer la liste des vues de données disponibles, sélectionnez ![Afficher le filtre](/help/assets/icons/Filter.svg). Vous pouvez filtrer la liste sur [!UICONTROL Propriétaire].<br/>Utilisez ![Masquer](/help/assets/icons/Filter.svg) **[!UICONTROL Masquer les filtres]** pour masquer le volet des segments.
* Pour définir les colonnes à afficher dans le tableau, sélectionnez ![Paramètres des colonnes](/help/assets/icons/ColumnSetting.svg). Sélectionnez les colonnes à afficher dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]** et sélectionnez **[!UICONTROL Appliquer]** pour appliquer les modifications.

### Canaux

Dans la section **[!UICONTROL Canaux]**, sélectionnez les canaux que vous souhaitez activer pour Content Analytics. Vous pouvez choisir entre **[!UICONTROL Mobile]** et **[!UICONTROL Web]**.

* Pour sélectionner un canal que vous n’avez pas encore configuré, sélectionnez **[!UICONTROL Activer]**.
* Pour sélectionner un canal déjà configuré, mais pour lequel vous souhaitez modifier la configuration, sélectionnez **[!UICONTROL Modifier la configuration]**.

Vous pouvez ensuite configurer le canal de manière plus détaillée. Cette configuration est différente selon que vous activez et configurez ou modifiez une configuration pour le canal [mobile](#mobile) ou [web](#web).

#### Mobile {#mobile}

<!-- For updated ACA -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_experience_locations_boldheader"
>title="Collecte de données d’emplacements d’expériences mobiles"
>abstract="**Emplacements d’expérience à exclure**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_experience_locations_header"
>title="Collecte de données d’emplacements d’expériences mobiles"
>abstract="Indiquez les emplacements d’expériences à **exclure** lors de la collecte de données pour Content Analytics. Veillez à exclure les emplacements d’expérience personnellement identifiables."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_locations_boldheader"
>title="Collecte de données d’emplacements de ressources mobiles"
>abstract="**Emplacements de ressources à exclure**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_locations_header"
>title="Collecte de données d’emplacements de ressources mobiles"
>abstract="Indiquez les emplacements de ressources à **exclure** lors de la collecte de données pour Content Analytics. Veillez à exclure les emplacements de ressources personnellement identifiables."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_urls_boldheader"
>title="Collecte de données d’URL de ressources mobiles"
>abstract="**URL de ressources à exclure**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_urls_header"
>title="Collecte de données d’URL de ressources mobiles"
>abstract="Indiquez les URL de ressources à **exclure** lors de la collecte de données pour Content Analytics. Veillez à exclure les URL de ressources personnellement identifiables."

Pour le canal mobile, vous pouvez configurer les options [capture et définition d’expérience](#experience-capture-and-definition), [collecte de données](#data-collection) et [remplacements d’en-tête](#header-overrides).

##### Capture et définition de l’expérience {#mobile-experience-capture-and-definition}

Dans cette section, vous pouvez choisir d’inclure des expériences dans les données mobiles que vous collectez avec Content Analytics.  Pour le canal mobile, une expérience correspond à ce que vous avez enregistré comme expérience à l’aide de Adobe Experience Platform SDK for Content Analytics.

Par défaut, l’option **[!UICONTROL Inclure les expériences]** est désactivée.

N’envisagez d’inclure des expériences que lorsque vous avez instrumenté votre application mobile pour enregistrer des expériences et effectuer le suivi des vues d’expérience et des clics d’expérience.

##### Collecte de données {#mobile-data-collection}

Les paramètres de collecte de données vous permettent de définir les données (emplacements d’expérience, emplacements des ressources, URL des ressources) que vous souhaitez collecter pour Content Analytics. Assurez-vous de ne pas collecter d’informations d’identification personnelle dans le cadre de cette collecte de données.

Pour configurer la collecte de données :

* Utilisez une propriété de balises mobiles existante ou créez une propriété de balises mobiles.

   * Pour utiliser une propriété de balises mobiles existante, procédez comme suit :

      1. Sélectionnez **[!UICONTROL Choisir existant]**.
      2. Sélectionnez une propriété existante dans le menu déroulant **[!UICONTROL Propriété Balises]**. Vous pouvez commencer à saisir pour rechercher et limiter les options disponibles. Vous ne pouvez pas sélectionner une propriété Balises qu’une autre configuration Content Analytics implémentée utilise déjà.


   * Pour créer une propriété de balises mobile, procédez comme suit :

      1. Sélectionnez **[!UICONTROL Créer]**.
      1. Spécifiez un **[!UICONTROL Nom de balise]**, par exemple `ACA Test for Documentation`.
      1. Spécifiez des **[!UICONTROL Domaines]**, par exemple `example.com`.

* Indiquez quels emplacements d’expérience doivent être exclus lors de la collecte de données pour Content Analytics. Veillez à exclure les emplacements d’expérience personnellement identifiables.

  Spécifiez une **[!UICONTROL chaîne d’expression régulière]** pour les **[!UICONTROL emplacements d’expérience à exclure]**. <br/>Par exemple : `^(?!.*documentation).*` d’exclure tous les emplacements d’expérience de documentation de Content Analytics.

* Indiquez quels emplacements de ressources doivent être exclus lors de la collecte de données pour Content Analytics. Veillez à exclure les emplacements de ressources personnellement identifiables.

  Spécifiez une **[!UICONTROL chaîne d’expression régulière]** pour les **[!UICONTROL emplacements de ressources à exclure]**. <br/>Par exemple : `^(?!.*(logo\.jpg)).*$` d’exclure tous les emplacements de ressources avec le logo JPEG images de Content Analytics.

* Indiquez quelles URL de ressources doivent être exclues lors de la collecte de données pour Content Analytics. Veillez à exclure les URL de ressources personnellement identifiables.

  Spécifiez une **[!UICONTROL chaîne d’expression régulière]** pour **[!UICONTROL URL de ressource à exclure]**. <br/>Par exemple : `^(?!.*(logo\.jpg)).*$` d’exclure toutes les URL de ressources faisant référence aux images JPEG de logo de Content Analytics.


##### Remplacements d’en-têtes {#mobile-header-overrides}

<!-- needs modification for mobile channel -->

Vous pouvez éventuellement spécifier dans la section **[!UICONTROL Remplacements d’en-tête]** un nom d’en-tête et une valeur d’en-tête secrète.  Cette configuration de remplacement de l’en-tête garantit que Content Analytics envoie un en-tête HTTP personnalisé pour récupérer les ressources des applications mobiles, en contournant les technologies de détection des robots ou de point de contrôle du trafic.

![Section remplacements de l’en-tête](/help/content-analytics/assets/aca-configuration-header-overrides.png)

1. Activez **[!UICONTROL Configurer les remplacements d’en-tête]**.
1. Saisissez le **[!UICONTROL Nom de l’en-tête]**. Par exemple : `x-asset-service`.
1. Saisissez la **[!UICONTROL valeur d’en-tête]**. Tout ce que vous spécifiez est secret et non visible dans l’interface utilisateur (sauf si vous choisissez explicitement de divulguer ![Visibilité](/help/assets/icons/Visibility.svg) la valeur lors de la saisie).

##### Enregistrer {#mobile-save}

Une fois que vous avez configuré le canal mobile, sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer la configuration. Sélectionnez **[!UICONTROL Annuler]** pour annuler la configuration.


#### Web {#web}

Pour le canal web, vous pouvez configurer [la capture et la définition d’expérience](#experience-capture-and-definition-1), [la collecte de données](#data-collection-1) et [les remplacements d’en-tête](#header-overrides-1).

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Capture et définition de l’expérience"
>abstract="Vous pouvez inclure des expériences dans les données que vous collectez avec Content Analytics. Lorsque cette option est sélectionnée, vous devez définir une ou plusieurs combinaisons d’expression régulière et de paramètres de requête pour définir les URL pour lesquelles inclure des expériences."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Capture et définition de l’expérience"
>abstract="Collecter des expériences dans Content Analytics"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="Capture et définition de l’expérience"
>abstract="Spécifiez les paramètres qui déterminent le rendu du contenu sur votre site web."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_new_include_experiences"
>title="Capture et définition de l’expérience"
>abstract="Lorsque cette option est activée, les données d’expérience sont collectées, les attributs d’expérience sont générés et les rapports d’expérience sont disponibles."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_include_experiences"
>title="Capture et définition de l’expérience"
>abstract="Lorsque cette option est activée, les données d’expérience sont collectées, les attributs d’expérience sont générés et les rapports d’expérience sont disponibles. <br><br/>Utilisez ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier]** pour modifier la configuration de la collecte de données pour les expériences dans la propriété Balises associée à la configuration actuelle."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Capture et définition de l’expérience"
>abstract="Vous devez modifier les paramètres de la collecte de données d’expérience dans l’extension Adobe Content Analytics."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Collecte de données"
>abstract="Définissez la propriété de balise à utiliser ou créez-en une. Définissez également les pages et les ressources à inclure ou à exclure à l’aide d’expressions régulières.<br/>Pour une mise en œuvre indépendante des balises, sélectionnez **[!UICONTROL Créer]**.  Une propriété Balises est créée, mais vous n’avez pas l’obligation de l’utiliser."
>additional-url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/content-analytics/configuration/tags-agnostic" text="Bibliothèque JavaScript Content Analytics"


>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Collecte de données"
>abstract="**Fournir une propriété de balise**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="Collecte de données"
>abstract="**Pages à inclure/exclure**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="Collecte de données"
>abstract="Indiquez les pages à **inclure** ou **exclure** lors de la collecte de données pour Content Analytics. Veillez à exclure les pages personnellement identifiables."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="Collecte de données"
>abstract="**Actifs à inclure/exclure**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="Collecte de données"
>abstract="Indiquez les ressources à **inclure** ou **exclure** lors de la collecte de données pour Content Analytics. Veillez à exclure les ressources personnellement identifiables."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="Collecte de données"
>abstract="Vous pouvez modifier les paramètres des pages de l’extension Adobe Content Analytics dans la propriété Balise, associée à la configuration sélectionnée."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Collecte de données"
>abstract="Vous pouvez modifier les paramètres des ressources de l’extension Adobe Content Analytics dans la propriété Balise, associée à la configuration sélectionnée."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tags_disabled_description "
>title="Propriété des balises désactivée"
>abstract="L’extension Content Analytics est déjà active."


<!-- For updated ACA -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_pages_boldheader"
>title="Collecte de données de pages web"
>abstract="**Pages à inclure/exclure**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_pages_header"
>title="Collecte de données de pages web"
>abstract="Indiquez les pages à **inclure** ou **exclure** lors de la collecte de données pour Content Analytics."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_assets_boldheader"
>title="Collecte de données de ressources web"
>abstract="**Actifs à inclure/exclure**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_assets_header"
>title="Collecte de données de ressources web"
>abstract="Indiquez les ressources à **inclure** ou **exclure** lors de la collecte de données pour Content Analytics. Veillez à exclure les ressources personnellement identifiables."


##### Capture et définition de l’expérience {#web-experience-capture-and-definition}

Dans cette section, vous pouvez choisir d’inclure des expériences dans les données web que vous collectez avec Content Analytics.  Une expérience se compose de tout le texte d’une page web qui est reproductible à l’aide de l’URL de la visite initiale de l’utilisateur.

Par défaut, l’option **[!UICONTROL Inclure les expériences]** est désactivée. Lorsque cette option est sélectionnée, définissez les URL pour lesquelles vous souhaitez inclure des expériences.

Vous ne devriez envisager d’inclure des expériences que si les conditions suivantes s’appliquent :

* Les pages du site doivent être reproductibles à l’aide de l’URL de la page.
* Le contenu textuel affiché par une personne donnée peut être reproduit à l’aide de l’URL de la page et ne dépend pas de cookies ou d’autres mécanismes de personnalisation.

>[!IMPORTANT]
>
>Implémentez le [contrôle de version Content Analytics](manual.md#versioning) pour collecter les modifications que vous apportez aux expériences (pages) dans le cadre de Content Analytics.



###### Nouvelle configuration {#new-experiences-configuration}

Pour inclure des expériences dans une configuration nouvelle ou non implémentée, procédez comme suit :

![Configuration de Content Analytics pour la capture et la définition de l’expérience](../assets/aca-configuration-experience.png)

1. Activez **[!UICONTROL Inclure des expériences]**. Le bouton (bascule) pour activer les expériences a un impact sur les éléments suivants :

   * La collecte de données dans l’extension Content Analytics
   * Le processus générant des attributs d’expérience à partir des données d’événement Content Analytics
   * Modèle de rapport dans Customer Journey Analytics.

1. Sélectionnez **[!UICONTROL Ajouter une expression régulière]** pour ajouter une combinaison d’expression régulière de domaine et de paramètres de requête.
1. Indiquez comment le contenu est rendu sur votre site web en définissant des combinaisons d’une **[!UICONTROL Expression régulière du domaine]** et de **[!UICONTROL Paramètres de requête]** qui affectent le contenu de la page.
   1. Saisissez une **[!UICONTROL Expression régulière de domaine]**, par exemple `/^(?!.*\b(store|help|admin)\b)/`. Veillez à ajouter une séquence d’échappement aux expressions régulières à l’aide de `/`. L’expression régulière de domaine indique à quelles URL ces paramètres s’appliquent. Par exemple, vous pouvez avoir plusieurs sites et différents paramètres qui pilotent le contenu de chacun des sites. Si les paramètres de requête s’appliquent à toutes vos pages, vous pouvez utiliser `.*` pour inclure toutes les pages.
   1. Spécifiez une liste de **[!UICONTROL paramètres de requête]** séparés par des virgules, par exemple `outdoors, patio, kitchen`.
1. Sélectionnez **[!UICONTROL Supprimer]** si vous souhaitez supprimer une combinaison d’une expression régulière de domaine et de paramètres de requête.
1. Sélectionnez **[!UICONTROL Ajouter une expression régulière]** si vous souhaitez ajouter une autre combinaison d’une expression régulière et de paramètres de requête.


###### Configuration implémentée {#implemented-experiences-configuration}

Pour modifier des expériences existantes ou nouvelles dans une configuration implémentée, procédez comme suit :

![Configuration de Content Analytics pour la capture et la définition de l’expérience](../assets/aca-configuration-experience-edit.png)

* Sélectionnez le bouton (bascule) **[!UICONTROL Inclure des expériences]** pour activer ou désactiver les éléments suivants :

   * Le processus générant des attributs d’expérience à partir des données d’événement Content Analytics
   * Modèle de rapport dans Customer Journey Analytics.

* Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** pour modifier davantage la configuration de la collecte de données pour les expériences dans Content Analytics. Vous pouvez modifier les paramètres de l’[extension Adobe Content Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) dans la propriété Balise, associée à la configuration sélectionnée.

##### Collecte de données {#web-data-collection}

Les paramètres de collecte de données vous permettent de définir les données (pages, ressources) à collecter pour Content Analytics. Ne collectez aucune information d’identification personnelle dans le cadre de cette collecte de données.

Pour configurer la collecte de données :

* Utilisez une propriété de balises web existante ou créez une propriété de balises web.

   * Pour utiliser une propriété de balises web existante, procédez comme suit :

      1. Sélectionnez **[!UICONTROL Choisir existant]**.
      2. Sélectionnez une propriété existante dans le menu déroulant **[!UICONTROL Propriété Balises]**. Vous pouvez commencer à saisir pour rechercher et limiter les options disponibles. Vous ne pouvez pas sélectionner une propriété Balises qu’une autre configuration Content Analytics implémentée utilise déjà.


   * Pour créer une propriété Balises web, procédez comme suit :

      1. Sélectionnez **[!UICONTROL Créer]**.
      1. Spécifiez un **[!UICONTROL Nom de balise]**, par exemple `ACA Test for Documentation`.
      1. Spécifiez des **[!UICONTROL Domaines]**, par exemple `example.com`.

     Utilisez une nouvelle propriété Tags si vous souhaitez créer une implémentation indépendante des balises pour le canal web à l’aide de la bibliothèque JavaScript Content Analytics [&#128279;](/help/content-analytics/config/tags-agnostic.md). La propriété Tags est créée, mais vous n’utiliserez pas la propriété dans l’implémentation agnostique. Toutefois, l’implémentation agnostique nécessite que vous ayez exécuté l’assistant de configuration guidée au moins une fois.

* Indiquez les pages à inclure ou exclure lors de la collecte de données pour Content Analytics. Veillez à exclure les pages personnellement identifiables.

  Spécifiez une **[!UICONTROL Chaîne d’expression régulière]** pour **[!UICONTROL Pages à inclure/exclure]**. <br/>Par exemple, `^(?!.*documentation).*` pour exclure toutes les pages de documentation de Content Analytics.

* Indiquer les ressources à inclure ou exclure lors de la collecte de données pour Content Analytics. Veillez à exclure les ressources personnellement identifiables.

  Spécifiez une **[!UICONTROL Chaîne d’expression régulière]** pour **[!UICONTROL Ressource à inclure/exclure]**. <br/>Par exemple, `^(?!.*(logo\.jpg)).*$` pour exclure toutes les images JPEG des logos de Content Analytics.


##### Remplacements d’en-têtes {#web-header-overrides}

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_header_overrides_boldheader"
>title="Remplacements d’en-têtes"
>abstract="**Remplacements d’en-têtes**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_header_overrides_header"
>title="Remplacements d’en-têtes"
>abstract="Fonctionnalité avancée permettant de contourner la détection des robots ou de filtrer le trafic. Content Analytics inclut vos en-têtes HTTP personnalisés lors de l’appel de vos points d’entrée."

<!-- needs modification for mobile channel -->

Vous pouvez éventuellement spécifier dans la section **[!UICONTROL Remplacements d’en-tête]** un nom d’en-tête et une valeur d’en-tête secrète.  Cette configuration de remplacement d’en-tête garantit que Content Analytics envoie des en-têtes HTTP personnalisés pour contourner les technologies de détection de robots ou de point de contrôle de trafic que vous avez implémentées.

![Section remplacements de l’en-tête](/help/content-analytics/assets/aca-configuration-header-overrides.png)

1. Activez **[!UICONTROL Configurer les remplacements d’en-tête]**.
1. Saisissez le **[!UICONTROL Nom de l’en-tête]**. Par exemple : `x-asset-service`.
1. Saisissez la **[!UICONTROL valeur d’en-tête]**. Tout ce que vous spécifiez est secret et non visible dans l’interface utilisateur (sauf si vous choisissez explicitement de divulguer ![Visibilité](/help/assets/icons/Visibility.svg) la valeur lors de la saisie).


>[!CONTEXTUALHELP]
>id="aca_onboarding_paidmedia_adplatforms_nosourceconnectors"
>title="Aucun connecteur source"
>abstract="Paid Media nécessite des connecteurs source Experience Platform pour vos éditeurs d’annonces publicitaires. Aucun connecteur Google Ads ou Meta Ads n’est disponible dans ce sandbox. Configurez un ou plusieurs de ces connecteurs dans l’interface **&#x200B;**&#x200B;> **[!UICONTROL Sources]** et revenez à cette étape pour continuer la configuration des médias achetés Content Analytics."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/ads" text="Source Google Ads"

##### Enregistrer {#web-save}

Après avoir spécifié les détails du canal web, sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer la configuration. Sélectionnez **[!UICONTROL Annuler]** pour annuler la configuration.


### Résumé {#summary}

Une fois que vous avez fourni tous les détails nécessaires, un résumé fournit des détails sur les artefacts créés ou modifiés.

* Un résumé **[!UICONTROL Vous êtes presque en mesure d’implémenter _nom de configuration_ pour Content Analytics]** s’affiche lorsque vous implémentez une nouvelle configuration.

* Pour les configurations existantes implémentées, un résumé **[!UICONTROL Vous avez implémenté _nom de configuration_ pour Content Analytics]** s’affiche.

![Résumé de configuration Content Analytics](../assets/aca-configuration-summary.png)

### Actions {#actions}

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Confirmation d’implémentation"
>abstract="Si vous sélectionnez **[!UICONTROL Implémenter]**, vous configurerez Content Analytics en fonction des entrées que vous avez fournies dans ce workflow. Plusieurs paramètres sont choisis par défaut en fonction de ce qui est généralement utile pour l’analyse du contenu, mais vous (en tant que responsable du contrôle de données) devez examiner les paramètres de chaque artefact pour confirmer que les paramètres sont implémentés conformément à votre politique de confidentialité, à vos droits et obligations contractuels et aux exigences de consentement en vertu de la loi applicable.<br/><br/>Notez qu’aucune donnée ne sera collectée tant que la bibliothèque de balises associée à cette configuration ne sera pas publiée manuellement.<br/><br/>Afin de dériver les attributs des images et du texte, Adobe récupère les attributs à l’aide de :<ol><li>l’URL de la page, capturée au moment de la visite du site par l’utilisateur ou l’utilisatrice, en fonction des paramètres de collecte de données que vous avez configurés ; et</li><li>URI où l’image est hébergée.</li></ol>Vous ne devez pas baliser les images hébergées sur des sites tiers."

Lorsque vous créez ou modifiez une configuration, vous disposez des options suivantes :

* **[!UICONTROL Ignorer]** : toutes les modifications apportées dans le cadre de la configuration sont ignorées.
* **[!UICONTROL Enregistrer pour plus tard]** : les modifications apportées à la configuration sont enregistrées. Vous pouvez revoir la configuration ultérieurement pour apporter d’autres modifications ou implémenter la configuration. L’unique condition pour enregistrer une configuration est de saisir une valeur pour [!UICONTROL Nom].
* **[!UICONTROL Implémenter]** : les paramètres de la configuration ou les modifications qui y sont apportées sont enregistrés et implémentés. Tous les champs marqués comme ![Obligatoires](/help/assets/icons/Required.svg) doivent avoir les valeurs appropriées. L’implémentation comprend les éléments suivants :

   * Configuration **[!UICONTROL Customer Journey Analytics]** :
      * La vue de données sélectionnée est mise à jour pour inclure les dimensions et mesures Content Analytics.
      * La connexion liée à la vue de données sélectionnée est modifiée de manière à inclure les jeux de données d’événements et d’attributs Content Analytics.
      * Un modèle de rapport Content Analytics est ajouté à Workspace.


   * Configuration **[!UICONTROL Adobe Experience Platform]** :
      * Création de schémas pour modéliser les événements Content Analytics, les attributs de ressource et les attributs d’expérience (s’ils sont configurés).
      * Création de jeux de données pour collecter les événements Content Analytics, les attributs de ressource et les attributs d’expérience (s’ils sont configurés).
      * Création d’un flux de données qui utilise le service de fonctionnalité pour générer et mettre à jour des attributs de contenu à partir d’événements Content Analytics.


   * Configuration de la **[!UICONTROL collecte de données]** :
      * La propriété Balises existante ou nouvelle est configurée pour prendre en charge la collecte de données Content Analytics. Cette configuration implique l’inclusion de l’extension Adobe Content Analytics pour les balises.
      * Un train de données est créé pour les événements Content Analytics.
      * L’extension Adobe Content Analytics est configurée pour s’assurer que les événements Content Analytics sont envoyés au train de données pour Content Analytics.
      * Si Web SDK ou Mobile SDK n’est pas configuré pour la propriété Tags, une nouvelle configuration de Web SDK ou Mobile SDK est créée pour envoyer uniquement les événements Content Analytics.
      * Si Web SDK ou Mobile SDK est configuré pour la propriété Tags, aucune modification n’est apportée à la configuration existante de Web SDK ou Mobile SDK.


* **[!UICONTROL Enregistrer]** : les modifications apportées à une configuration implémentée sont enregistrées et l’implémentation est mise à jour.
* **[!UICONTROL Sortie]**. Quitte la configuration guidée. Toutes les modifications apportées à une configuration implémentée sont ignorées.


## Publier {#publish}

Pour commencer à collecter des données pour votre configuration Content Analytics, vous devez [manuellement](manual.md) publier les propriétés de balises créées pour les canaux que vous avez activés.


>[!MORELIKETHIS]
>
>[Configuration manuelle](manual.md)
>

