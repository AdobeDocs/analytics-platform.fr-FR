---
title: Configuration guidée de Content Analytics
description: Comment configurer Content Analytics à l’aide d’une configuration guidée d’intégration
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 1c4342d91e0c939d596c9660ffc510c4698f8680
workflow-type: tm+mt
source-wordcount: '2696'
ht-degree: 98%

---

# Configuration guidée de Content Analytics

La configuration guidée vous permet de configurer rapidement et facilement Content Analytics. La configuration guidée utilise un assistant pour définir les exigences afin de configurer Content Analytics automatiquement pour votre organisation. Dans l’écran **[!UICONTROL Configuration]**, vous pouvez créer une configuration ou modifier une configuration existante.

>[!IMPORTANT]
>
>Votre organisation ne peut avoir qu’une seule configuration Content Analytics par sandbox.

Pour accéder à la configuration de Content Analytics :

* Sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Configuration de Content Analytics]** dans le menu principal de Customer Journey Analytics.

Dans l’écran **[!UICONTROL Configurations de Content Analytics]**, un tableau des configurations existantes de Content Analytics s’affiche.

![Configurations de Content Analytics](../assets/aca-configuration-table.png)
Pour chaque configuration, les détails suivants sont disponibles :

| Colonne | Description |
|---|---|
| **[!UICONTROL Nom]** | Nom de la configuration. |
| **[!UICONTROL Créé par]** | Compte technique ayant créé la configuration. |
| **[!UICONTROL Date de création]** | Date et heure de création de la configuration. |
| **[!UICONTROL Date de modification]** | Date et heure de la dernière modification de la configuration. |
| **[!UICONTROL Sandbox]** | Sandbox au sein de l’organisation dans lequel Content Analytics est configuré et implémenté (ou le sera à l’avenir). |
| **[!UICONTROL Statut]** | Statut de la configuration. Le statut peut être <br/>![Statut Gris](/help/assets/icons/StatusGray.svg) **[!UICONTROL Brouillon]** : la configuration est enregistrée pour une utilisation ultérieure et n’est pas déployée.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Échec]** : la configuration a échoué. Vous pouvez sélectionner **[!UICONTROL Modifier]** pour obtenir des informations sur l’échec. Adobe gère de manière proactive toute mise en œuvre ayant échoué. Vous pouvez contacter l’assistance clientèle pour plus d’informations.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Terminée]** : la configuration est terminée et a été implémentée avec succès. |

Vous pouvez utiliser ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour personnaliser le tableau. Sélectionnez les colonnes à afficher dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]** et sélectionnez **[!UICONTROL Appliquer]** pour appliquer les modifications.

À partir de l’écran **[!UICONTROL Configuration]** de Content Analytics, vous pouvez créer une configuration ou modifier une configuration existante.

Pour créer une configuration, procédez comme suit :

* Sélectionnez **[!UICONTROL Créer une configuration]**. Cette action ouvre l’[assistant de configuration guidé](#guided-configuration-wizard).

Pour modifier une configuration existante, procédez comme suit :

* Sélectionnez ![Plus](/help/assets/icons/More.svg), puis ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** pour une configuration Content Analytics existante. Cette action ouvre l’[assistant de configuration guidé](#guided-configuration-wizard).

## Assistant de configuration guidé

L’assistant de configuration guidé se compose de quatre sections ([Détails](#details), [Vue de données](#data-view), [Capture et définition d’expérience](#experience-capture-and-definition) et [Collecte de données](#data-collection)), chacune vous invitant à fournir les détails requis pour configurer correctement Content Analytics. Renseignez chaque section avant de passer à la section suivante, car certains paramètres d’une section peuvent dépendre des valeurs de configuration des sections précédentes.

### Détails {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Détails"
>abstract="Fournissez le nom de la connexion. Les sections **[!UICONTROL Vue de données]**, **[!UICONTROL Capture et définition d’expérience]** et **[!UICONTROL Collecte de données]** permettent de fournir plus de détails pour configurer correctement Content Analytics."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Détails"
>abstract="Ce guide définit les exigences nécessaires à la configuration de l’analyse du contenu. Attribuez un nom à cette configuration."

<!-- markdownlint-enable MD034 -->

Chaque configuration nécessite un nom unique. Par exemple : `Example Content Analytics configuration`. Le nom est requis pour enregistrer ou implémenter une configuration.

![Détails de la configuration de Content Analytics](../assets/aca-configuration-details.png)


### Vue de données {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Vue de données"
>abstract="Pour la configuration de Content Analytics, vous devez sélectionner une vue de données existante. Vous pouvez donc fusionner vos données Content Analytics avec d’autres données."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Vue de données"
>abstract="Dans Customer Journey Analytics, sélectionnez une vue de données existante avec laquelle fusionner vos données Content Analytics."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Vue de données"
>abstract="Dans Customer Journey Analytics, sélectionnez une vue de données existante avec laquelle fusionner vos données Content Analytics.<br/>"

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

<!-- markdownlint-enable MD034 -->

Votre configuration nécessite la sélection d’une [Vue de données](/help/data-views/data-views.md).

1. Sélectionner une vue de données

   * Pour sélectionner une nouvelle vue de données pour une confguration, utilisez ![Données](/help/assets/icons/Data.svg) **[!UICONTROL Sélectionner la vue de données]**.

     ![Configuration Content Analytics d’une vue de données](../assets/aca-configuration-dataview.png)

   * Pour modifier une vue de données pour une configuration, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]**.

     ![Configuration Content Analytics d’une vue de données](../assets/aca-configuration-dataview-edit.png)


   Dans les deux scénarios, une boîte de dialogue **[!UICONTROL Vue de données]** s’affiche, dans laquelle vous pouvez sélectionner une vue de données pour votre configuration.

   ![Configuration Content Analytics d’une vue de données - Tableau des vues de données](../assets/aca-configuration-dataview-dialog.png)

   Si vous créez une configuration, la liste affiche uniquement les vues de données associées aux sandbox qui n’ont pas de configuration active. En outre, vous ne voyez que les vues de données associées aux sandbox auxquels vous avez accès et les connexions que vous avez le droit de modifier.

   Si vous modifiez une configuration existante, la liste affiche uniquement les vues de données disponibles dans le sandbox déjà associé à la configuration existante.

   Vous pouvez effectuer les actions suivantes :

   * Pour rechercher une vue de données spécifique, utilisez le champ ![Recherche](/help/assets/icons/Search.svg).
   * Pour filtrer la liste des vues de données disponibles, sélectionnez ![ Afficher le filtre ](/help/assets/icons/Filter.svg). Vous pouvez filtrer la liste par [!UICONTROL Connexion], [!UICONTROL Propriétaire] et [!UICONTROL Sandbox].<br/>Utilisez ![Masquer](/help/assets/icons/Filter.svg) **[!UICONTROL Masquer les segments]** pour masquer le volet de segments.
   * Pour définir les colonnes à afficher dans le tableau, sélectionnez ![Paramètres des colonnes](/help/assets/icons/ColumnSetting.svg). Sélectionnez les colonnes à afficher dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]** et sélectionnez **[!UICONTROL Appliquer]** pour appliquer les modifications.

1. Sélectionnez ![SelectBox](/help/assets/icons/SelectBox.svg) la vue de données que vous souhaitez utiliser.
1. Sélectionnez **[!UICONTROL Enregistrer]** pour confirmer la vue de données sélectionnée. Sélectionnez **[!UICONTROL Annuler]** pour annuler.


Dans Customer Journey Analytics, une [vue de données](/help/data-views/data-views.md) est liée à une [connexion](/help/connections/overview.md) Customer Journey Analytics. Et une connexion est basée sur un sandbox au sein de votre organisation. Une fois la configuration enregistrée, le champ **[!UICONTROL Sandbox]** est automatiquement renseigné avec le nom correct du sandbox, en fonction de la vue de données sélectionnée.


### Capture et définition de l’expérience {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

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

<!-- markdownlint-enable MD034 -->

Dans cette section, vous pouvez inclure des expériences dans les données que vous collectez avec Content Analytics.  Une expérience correspond à tout le texte d’une page web qui est reproductible à l’aide de l’URL utilisée par la première personne qui visite cette page web.

Par défaut, l’option **[!UICONTROL Inclure les expériences]** est désactivée. Lorsque cette option est sélectionnée, vous devez définir les URL pour lesquelles vous souhaitez inclure des expériences.

Vous ne devriez envisager d’inclure des expériences que si les conditions suivantes s’appliquent :

* Les pages du site doivent être reproductibles à l’aide de l’URL de la page.
* Le contenu textuel affiché par une personne donnée peut être reproduit à l’aide de l’URL de la page et ne dépend pas de cookies ou d’autres mécanismes de personnalisation.

>[!IMPORTANT]
>
>Implémentez le [contrôle de version Content Analytics](manual.md#versioning) pour collecter les modifications que vous apportez aux expériences (pages) dans le cadre de Content Analytics.



#### Nouvelle configuration {#new-experiences-configuration}

Pour inclure des expériences dans une configuration nouvelle ou non implémentée, procédez comme suit :

![Configuration de Content Analytics pour la capture et la définition de l’expérience](../assets/aca-configuration-experience.png)

1. Activez **[!UICONTROL Inclure des expériences]**. Le bouton (bascule) pour activer les expériences a un impact sur les éléments suivants :

   * La collecte de données dans l’extension Content Analytics
   * Le processus générant des attributs d’expérience à partir des données d’événement Content Analytics
   * Modèle de rapport dans Customer Journey Analytics.

1. Spécifiez les paramètres qui déterminent le mode de rendu du contenu sur votre site web. Les paramètres consistent en zéro, une ou plusieurs combinaisons d’une **[!UICONTROL Expression régulière du domaine]** et de **[!UICONTROL Paramètres de requête]**. Les paramètres de requête indiquent les paramètres qui affectent le contenu de votre page. Cette entrée permet à Content Analytics d’ignorer les paramètres qui n’affectent pas le contenu de la page, lors de la définition d’une expérience unique.
   1. Saisissez une **[!UICONTROL Expression régulière de domaine]**, par exemple `/^(?!.*\b(store|help|admin)\b)/`. Veillez à ajouter une séquence d’échappement aux expressions régulières à l’aide de `/`. L’expression régulière de domaine indique à quelles URL ces paramètres s’appliquent. Par exemple, vous pouvez avoir plusieurs sites et différents paramètres qui pilotent le contenu de chacun des sites. Si les paramètres de requête s’appliquent à toutes vos pages, vous pouvez utiliser `.*` pour inclure toutes les pages.
   1. Spécifiez une liste de **[!UICONTROL paramètres de requête]** séparés par des virgules, par exemple `outdoors, patio, kitchen`.
1. Sélectionnez **[!UICONTROL Supprimer]** si vous souhaitez supprimer une combinaison d’une expression régulière de domaine et de paramètres de requête.
1. Sélectionnez **[!UICONTROL Ajouter une expression régulière]** si vous souhaitez ajouter une autre combinaison d’une expression régulière et de paramètres de requête.


#### Configuration implémentée {#implemented-experiences-configuration}

Pour modifier des expériences existantes ou nouvelles dans une configuration implémentée, procédez comme suit :

![Configuration de Content Analytics pour la capture et la définition de l’expérience](../assets/aca-configuration-experience-edit.png)

* Sélectionnez le bouton (bascule) **[!UICONTROL Inclure des expériences]** pour activer ou désactiver les éléments suivants :

   * Le processus générant des attributs d’expérience à partir des données d’événement Content Analytics
   * Modèle de rapport dans Customer Journey Analytics.

* Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** pour modifier plus en détail la configuration de la collecte de données pour les expériences dans Content Analytics. Vous pouvez modifier les paramètres de l’[extension Adobe Content Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) dans la propriété Balise, associée à la configuration sélectionnée.


### Collecte de données {#onboarding-data-collection}

Dans cette section, vous allez configurer comment collecter vos données d’analyse de contenu.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Collecte de données"
>abstract="Définissez la propriété de balise à utiliser ou créez-en une. Définissez également les pages et les ressources à inclure ou à exclure à l’aide d’expressions régulières."

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
>abstract="Indiquer les pages à **inclure** ou **exclure** lors de la collecte de données pour l’analyse du contenu"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="Collecte de données"
>abstract="**Actifs à inclure/exclure**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="Collecte de données"
>abstract="Indiquer les ressources à **inclure** ou **exclure** lors de la collecte de données pour l’analyse du contenu"

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

<!-- markdownlint-enable MD034 -->

#### Nouvelle configuration {#new-configuration}

Dans une nouvelle configuration, vous devez définir si vous souhaitez utiliser une propriété de balise existante ou en créer une. Définissez également les pages et les ressources à inclure ou à exclure à l’aide d’expressions régulières.

* Pour utiliser une propriété de balise existante, procédez comme suit :

  ![Balise existante de la collecte de données Content Analytics](../assets/aca-configuration-datacollection-existingtag.png)

   1. Sélectionnez **[!UICONTROL Choisir existant]**.
   2. Sélectionnez une propriété existante dans le menu déroulant **[!UICONTROL Propriété des balises]**. Vous pouvez commencer à saisir pour rechercher et limiter les options disponibles. Vous ne pouvez pas sélectionner de propriété de balise déjà utilisée par une autre configuration Content Analytics mise en œuvre.


* Pour créer une propriété de balise, procédez comme suit :

  ![Nouvelle balise de collecte de données Content Analytics](../assets/aca-configuration-datacollection-newtag.png)

   1. Sélectionnez **[!UICONTROL Créer]**.
   1. Spécifiez un **[!UICONTROL Nom de balise]**, par exemple `ACA Test for Documentation`.
   1. Spécifiez des **[!UICONTROL Domaines]**, par exemple `example.com`.

* Indiquez les pages à inclure ou exclure lors de la collecte de données pour l’analyse du contenu.

  Spécifiez une chaîne d’expression régulière pour **[!UICONTROL Pages à inclure/exclure]**. <br/>Par exemple, `^(?!.*documentation).*` pour exclure toutes les pages de documentation de Content Analytics.

* Indiquer les ressources à inclure ou exclure lors de la collecte de données pour Content Analytics.

  Spécifiez une chaîne d’expression régulière pour **[!UICONTROL Ressources à inclure ou à exclure]**. <br/>Par exemple, `^(?!.*(logo\.jpg|\.svg)).*$` pour exclure toutes les images JPEG et SVG des logos de Content Analytics.

>[!IMPORTANT]
>
>Supprimez manuellement l’extension automatique du SDK web incluse de la propriété Balises qui vient d’être créée si vous disposez déjà d’une implémentation de SDK web qui utilise la [bibliothèque JavaScript](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/install/library) au lieu de l’[extension Balises](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration).
>



#### Configuration existante {#existing-configuration}

Vous ne pouvez pas modifier la propriété Balises d’une configuration existante. Pour mettre à jour une propriété Tags associée à une configuration existante, utilisez la configuration de l’extension Content Analytics Tag [&#128279;](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview).

Vous pouvez toutefois modifier les pages et les ressources à inclure ou à exclure.

* Pour modifier les pages à inclure ou à exclure lors de la collecte de données pour Content Analytics, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** sous **[!UICONTROL Expérience]**. Vous accédez à l’[extension Adobe Content Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) associée à la propriété Balises pour la configuration Content Analytics actuelle. Vous pouvez modifier l’expression régulière pour inclure ou exclure des pages. Veillez à [publier](#publish) vos modifications.

* Pour modifier les ressources à inclure ou à exclure lors de la collecte de données pour Content Analytics, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** sous **[!UICONTROL Ressource]**. Ceci vous redirige vers l’[extension Adobe Content Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) associée à la propriété Balises pour la configuration Content Analytics actuelle. Vous pouvez modifier l’expression régulière pour inclure ou exclure des ressources. Veillez à [publier](#publish) vos modifications.

### Résumé {#summary}

Une fois que vous avez fourni tous les détails nécessaires, un résumé fournit des détails sur les artefacts créés ou modifiés.

* Un résumé **[!UICONTROL Vous êtes presque en mesure d’implémenter _nom de configuration_ pour Content Analytics]** s’affiche lorsque vous implémentez une nouvelle configuration.

* Pour les configurations existantes implémentées, un résumé **[!UICONTROL Vous avez implémenté _nom de configuration_ pour Content Analytics]** s’affiche.

![Résumé de configuration Content Analytics](../assets/aca-configuration-summary.png)

### Actions {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Confirmation d’implémentation"
>abstract="Si vous sélectionnez **[!UICONTROL Implémenter]**, vous configurerez Content Analytics en fonction des entrées que vous avez fournies dans ce workflow. Plusieurs paramètres sont choisis par défaut en fonction de ce qui est généralement utile pour l’analyse du contenu, mais vous (en tant que responsable du contrôle de données) devez examiner les paramètres de chaque artefact pour confirmer que les paramètres sont implémentés conformément à votre politique de confidentialité, à vos droits et obligations contractuels et aux exigences de consentement en vertu de la loi applicable.<br/><br/>Notez qu’aucune donnée ne sera collectée tant que la bibliothèque de balises associée à cette configuration ne sera pas publiée manuellement.<br/><br/>Afin de dériver les attributs des images et du texte, Adobe récupère les attributs à l’aide de :<ol><li>l’URL de la page, capturée au moment de la visite du site par l’utilisateur ou l’utilisatrice, en fonction des paramètres de collecte de données que vous avez configurés ; et</li><li>URI où l’image est hébergée.</li></ol>Vous ne devez pas baliser les images hébergées sur des sites tiers."

<!-- markdownlint-enable MD034 -->

Lorsque vous créez ou modifiez une configuration, vous disposez des options suivantes :

* **[!UICONTROL Ignorer]** : toutes les modifications apportées dans le cadre de la configuration sont ignorées.
* **[!UICONTROL Enregistrer pour plus tard]** : les modifications apportées à la configuration sont enregistrées. Vous pouvez revoir la configuration ultérieurement pour apporter d’autres modifications ou implémenter la configuration. L’unique condition pour enregistrer une configuration est de saisir une valeur pour [!UICONTROL Nom].
* **[!UICONTROL Implémenter]** : les paramètres de la configuration ou les modifications qui y sont apportées sont enregistrés et implémentés. Tous les champs marqués comme ![Obligatoires](/help/assets/icons/Required.svg) doivent avoir des valeurs appropriées. L’implémentation comprend les éléments suivants :

   * Configuration **[!UICONTROL Customer Journey Analytics]** :
      * La vue de données sélectionnée est mise à jour pour inclure la dimension et les mesures Content Analytics.
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
      * Si le SDK web n’est pas configuré pour la propriété de balises, une nouvelle configuration de SDK web est créée pour envoyer uniquement les événements Content Analytics.
      * Si le SDK web est configuré pour cette propriété Balises, aucune modification n’est apportée à la configuration existante du SDK web.


* **[!UICONTROL Enregistrer]** : les modifications apportées à une configuration implémentée sont enregistrées et l’implémentation est mise à jour.
* **[!UICONTROL Sortie]**. Quitte la configuration guidée. Toutes les modifications apportées à une configuration implémentée sont ignorées.


## Publier {#publish}

Pour commencer à collecter des données pour votre configuration Content Analytics, vous devez publier [manuellement](manual.md) la propriété Balises créée lorsque vous sélectionnez **[!UICONTROL Implémenter]**.


>[!MORELIKETHIS]
>
>[Configuration manuelle](manual.md)
>
