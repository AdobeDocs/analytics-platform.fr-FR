---
title: Configuration guidée de Content Analytics
description: Configuration de Content Analytics à l’aide d’une configuration guidée d’intégration
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 69e2f358398fd8d2646e5a3c1cb6dfd1b5b5efbb
workflow-type: tm+mt
source-wordcount: '1651'
ht-degree: 11%

---

# Configuration guidée de Content Analytics

>[!WARNING]
>
>Cet article est un avant-projet non officiel d’une version finale à venir et fait partie de la documentation de Content Analytics. Tout le contenu est sujet à modification et aucune obligation légale quelle qu&#39;elle soit ne peut être dérivée de la version actuelle de cet article.
>

{#release-limited-testing}

La configuration guidée vous permet de configurer rapidement et facilement des analyses de contenu. La configuration guidée utilise un assistant pour définir les exigences afin de configurer Content Analytics automatiquement pour votre organisation. Dans l’écran **[!UICONTROL Configuration]**, vous pouvez créer une configuration ou modifier une configuration existante.

Pour accéder à la configuration de Content Analytics

* Sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Analyse de contenu]** dans le menu principal de Customer Journey Analytics.

Dans l’écran Configuration de Content Analytics, un tableau des configurations d’analyse de contenu existantes s’affiche.

![Configurations de Content Analytics](../assets/aca-configuration-table.png)
Pour chaque configuration, les détails suivants sont disponibles :

| Colonne | Description |
|---|---|
| **[!UICONTROL Nom]** | Nom de la configuration. |
| **[!UICONTROL Créé par]** | Compte technique ayant créé la configuration. |
| **[!UICONTROL Créé le]** | Date et heure de création de la configuration. |
| **[!UICONTROL Modifié le]** | Date et heure de la dernière modification de la configuration. |
| **[!UICONTROL Sandbox]** | Sandbox au sein de l’organisation dans lequel Content Analytics est configuré et implémenté (prévu). |
| **[!UICONTROL Statut]** | Statut de la configuration. Le statut peut être <br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Draft]** : la configuration est enregistrée pour une utilisation ultérieure et n’est pas déployée.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Failed]** : la configuration a échoué. Vous devez modifier la configuration et apporter les modifications nécessaires.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]** : la configuration est terminée et a été implémentée avec succès. |

Vous pouvez utiliser ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour personnaliser le tableau. Sélectionnez les colonnes à afficher dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]** et sélectionnez **[!UICONTROL Appliquer]** pour appliquer les modifications.

À partir de l’écran Content Analytics **[!UICONTROL Configuration]**, vous pouvez créer une configuration ou modifier une configuration existante.

Pour créer une configuration :

* Sélectionnez **[!UICONTROL Créer une configuration]**. Cette action ouvre l’assistant de configuration guidé.

Pour modifier une configuration existante :

* Sélectionnez ![Plus](/help/assets/icons/More.svg) puis ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** pour une configuration Content Analytics existante. Cette action ouvre l’assistant de configuration guidé.

## Assistant de configuration guidé

L’assistant de configuration guidé se compose de quatre sections ([Détails](#details), [Vue de données](#data-view), [Capture et définition d’expérience](#experience-capture-and-definition) et [Collecte de données](#data-collection)), chacune vous invitant à fournir les détails requis pour configurer correctement Content Analytics. Renseignez chaque section avant de passer à la section suivante, car certains paramètres d’une section peuvent dépendre des valeurs de configuration des sections précédentes.

### Détails {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Détails"
>abstract="Fournissez le nom de la connexion. Dans les sections **[!UICONTROL Vue des données]**, **[!UICONTROL Capture et définition d’expérience]** et **[!UICONTROL Collecte de données]** vous fournissez plus de détails pour vous assurer que Content Analytics peut être configuré correctement."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Détails"
>abstract="Ce guide définit les exigences nécessaires à la configuration de l’analyse du contenu. Attribuez un nom à cette configuration."

<!-- markdownlint-enable MD034 -->

Chaque configuration nécessite un nom unique. Par exemple : `Example Content Analytics configuration`.

![Détails de la configuration de Content Analytics](../assets/aca-configuration-details.png)


### Vue de données {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Vue de données"
>abstract="Pour la configuration de Content Analytics, vous devez sélectionner une vue de données existante. Vous pouvez donc fusionner vos données d’analyse de contenu avec d’autres données."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Vue de données"
>abstract="Sélectionnez dans Customer Journey Analytics une vue de données existante avec laquelle vous souhaitez fusionner vos données d’analyse de contenu.<br/>[En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/data-views){target=\"_blank\"}"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Vue de données"
>abstract="Sélectionnez dans Customer Journey Analytics une vue de données existante avec laquelle vous souhaitez fusionner vos données d’analyse de contenu.<br/>"

<!-- markdownlint-enable MD034 -->

Votre configuration nécessite la sélection d’une [Vue de données](/help/data-views/data-views.md).

![Configuration Content Analytics d’une vue de données](../assets/aca-configuration-dataview.png)

Pour sélectionner une vue de données :

1. Utilisez ![Data](/help/assets/icons/Data.svg) **[!UICONTROL Select Data view]**. Une boîte de dialogue **[!UICONTROL Vue de données]** s’affiche, dans laquelle vous pouvez sélectionner une vue de données pour votre configuration.

   Si vous créez une configuration, la liste affiche uniquement les vues de données associées aux sandbox qui n’ont pas de configuration active.
Si vous modifiez une configuration existante, la liste affiche uniquement les vues de données disponibles dans le sandbox déjà associé à la configuration existante.

   * Pour filtrer la liste des vues de données disponibles, sélectionnez ![ Afficher les filtres ](/help/assets/icons/Filter.svg). Vous pouvez filtrer la liste par Connexion, Propriétaire et Sandbox.<br/>Utilisez ![Masquer](/help/assets/icons/Filter.svg) **[!UICONTROL Masquer les filtres]** pour masquer le volet de filtrage.
   * Pour définir les colonnes à afficher dans le tableau, sélectionnez ![Paramètres des colonnes](/help/assets/icons/ColumnSetting.svg). Sélectionnez les colonnes à afficher dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]** et sélectionnez **[!UICONTROL Appliquer]** pour appliquer les modifications.
1. Sélectionnez **[!UICONTROL Enregistrer]** pour confirmer la vue de données sélectionnée. Sélectionnez **[!UICONTROL Annuler]** pour annuler.

Une vue de données est liée à un Customer Journey Analytics [Connexion](/help/connections/overview.md). Et une connexion est basée sur un sandbox au sein de votre organisation. Une fois la configuration enregistrée, la **[!UICONTROL Sandbox]** est automatiquement renseignée avec le nom correct du sandbox, en fonction de la vue de données sélectionnée.


### Capture et définition de l’expérience

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Capture et définition de l’expérience"
>abstract="Vous pouvez choisir d’inclure des expériences dans les données que vous collectez avec l’analyse du contenu. Lorsque cette option est sélectionnée, vous devez définir une ou plusieurs combinaisons d’expression régulière et de paramètres de requête pour définir les URL pour lesquelles inclure des expériences."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Capture et définition de l’expérience"
>abstract="Collecter des expériences dans l’analyse du contenu"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_url_header"
>title="Capture et définition de l’expérience"
>abstract="Spécifier les URL auxquelles s’appliquent les paramètres ci-dessous"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_edit_button"
>title="Capture et définition de l’expérience"
>abstract="Vous pouvez modifier les paramètres de l’extension Adobe Content Analytics dans la propriété Balise , associée à la configuration sélectionnée."



<!-- markdownlint-enable MD034 -->

Dans cette section, vous pouvez choisir d’inclure des expériences dans les données que vous collectez avec Content Analytics. Une expérience correspond à tout le texte d’une page web qui est reproductible à l’aide de l’URL utilisée par l’utilisateur initial qui visite cette page web. Lorsque cette option est sélectionnée, vous devez définir les URL pour lesquelles vous souhaitez inclure des expériences.

Pour inclure des expériences dans une configuration nouvelle ou non implémentée :

![Configuration de Content Analytics Capture et définition de l’expérience](../assets/aca-configuration-experience.png)

1. Activez **[!UICONTROL Inclure des expériences]**.
1. Spécifiez les paramètres qui déterminent le rendu du contenu sur votre site web. Les paramètres consistent en zéro ou plusieurs combinaisons d’une **[!UICONTROL Expression régulière du domaine]** et **[!UICONTROL Paramètres de requête]**.
   1. Saisissez une **[!UICONTROL Expression régulière du domaine]** par exemple `(?!.*\b(store|help|admin)\b)`.
   1. Spécifiez une liste de paramètres de requête séparés par des virgules **[!UICONTROL par exemple]** `outdoors, patio, kitchen`.
   1. Sélectionnez **[!UICONTROL Supprimer]** si vous souhaitez supprimer une combinaison.
   1. Sélectionnez **[!UICONTROL Ajouter autre]** si vous souhaitez ajouter une autre combinaison.

Pour modifier des expériences existantes ou en inclure de nouvelles dans une configuration implémentée :

![Configuration de Content Analytics Capture et définition de l’expérience](../assets/aca-configuration-experience-edit.png)

* Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) Modifier pour modifier les paramètres de l’extension Adobe Content Analytics dans la propriété Balise , associée à la configuration sélectionnée.


### Collecte de données {#onboarding-data-collection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Collecte de données"
>abstract="Définissez la propriété de balise à utiliser ou créez-en une. Définissez également les pages et les ressources à inclure ou à exclure à l’aide d’expressions régulières."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Collecte de données"
>abstract="Créer une propriété de balise"

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

<!-- markdownlint-enable MD034 -->

#### Nouvelle configuration

Dans une nouvelle configuration, vous devez définir la propriété de balise à utiliser ou créer une propriété de balise. Vous devez également définir les pages et les ressources à inclure ou à exclure à l’aide d’expressions régulières.

* Pour utiliser une propriété Tag existante, procédez comme suit :

  ![Balise Existante De La Collecte De Données Content Analytics](../assets/aca-configuration-datacollection-existingtag.png)

   * Sélectionnez **[!UICONTROL Existant]**.
   * Sélectionnez une propriété existante dans le menu déroulant **[!UICONTROL Propriété de balise]**.

* Pour créer une propriété Tag, procédez comme suit :

  ![Nouvelle Balise De Collecte De Données Content Analytics](../assets/aca-configuration-datacollection-newtag.png)

   1. Sélectionnez **[!UICONTROL Créer]**.
   2. Spécifiez un **[!UICONTROL Nom de balise]** par exemple `ACA Test`.
   3. Spécifiez un ou plusieurs **[!UICONTROL domaines]** par exemple, `example.com`.

   * Pour ajouter d’autres domaines, sélectionnez **[!UICONTROL Ajouter un autre domaine]**.
   * Pour supprimer un domaine, sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg).

* Si vous avez choisi d’inclure des expériences, indiquez quelles pages doivent être incluses ou exclues lors de la collecte de données pour Content Analytics.

   * Spécifiez une expression régulière pour **[!UICONTROL Experience]**. Par exemple : `(?!.*\b(store|help|admin)\b)`.

* Indiquez quelles ressources doivent être incluses ou exclues lors de la collecte de données pour Content Analytics.

   * Spécifiez une expression régulière pour **[!UICONTROL Ressource]**. Par exemple : `(?!.*\b(store|help|admin)\b)`.


#### Configuration existante

Pour une configuration existante, vous ne pouvez pas modifier la propriété de balise. Vous pouvez toutefois modifier les pages et les ressources à inclure ou à exclure.

* Pour modifier les pages à inclure ou à exclure lors de la collecte de données pour Content Analytics, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** sous **[!UICONTROL Experience]**.

* Pour modifier les ressources à inclure ou à exclure lors de la collecte de données pour Content Analytics, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier]** sous **[!UICONTROL Ressource]**.

### Résumé

Une fois que vous avez fourni tous les détails nécessaires, un résumé **[!UICONTROL Vous êtes presque prêt à implémenter _nom de configuration_ pour Content Analytics]** s’affiche.

Pour les configurations existantes implémentées, un résumé **[!UICONTROL Vous avez implémenté _nom de configuration_ s’affiche pour Content Analytics]**.

![Résumé de la configuration de Content Analytics](../assets/aca-configuration-summary.png)

### Actions

Lorsque vous avez créé ou modifié une configuration, les actions suivantes sont disponibles.

* **[!UICONTROL Ignorer]** : toutes les modifications apportées dans le cadre de la création d’une configuration ou de la modification d’une configuration existante sont ignorées.
* **[!UICONTROL Enregistrer pour plus tard]** : les modifications apportées à une nouvelle configuration ou à une configuration existante non encore implémentée sont enregistrées. Vous pouvez revoir la configuration ultérieurement pour apporter d’autres modifications ou implémenter la configuration.
* **[!UICONTROL Implémentation]** : les modifications apportées à une nouvelle configuration ou à une configuration existante non encore implémentée sont enregistrées et implémentées. La mise en œuvre comprend les éléments suivants :
   * Configuration de **[!UICONTROL Adobe Experience Platform]** :
      1. Création de schémas pour modéliser les événements Content Analytics, les attributs de ressource et les attributs d’expérience (s’ils sont configurés).
      1. Création de jeux de données pour collecter les événements Content Analytics, les attributs de ressource et les attributs d’expérience (s’ils sont configurés).
   * Configuration de **[!UICONTROL Content Analytics]** :
      * Configuration d&#39;un processus d&#39;assemblage de fonctionnalités basé sur la configuration.
   * Configuration de **[!UICONTROL Customer Journey Analytics]** :
      1. La vue de données sélectionnée est mise à jour pour inclure la dimension et les mesures Content Analytics.
      1. La connexion liée à la vue de données sélectionnée est modifiée pour inclure les jeux de données d’événements et d’attributs Content Analytics.
      1. Les modèles de création de rapports Content Analytics sont ajoutés à Workspace.
   * Configuration **[!UICONTROL collecte de données]** :
      1. La nouvelle propriété de balise ou la propriété existante est configurée pour prendre en charge la collecte de données Content Analytics. Cette configuration implique l’inclusion de l’extension Adobe Content Analytics pour les balises.
      1. Un flux de données est créé pour les événements Content Analytics.
      1. L’extension Adobe Content Analytics est configurée pour s’assurer que les événements Content Analytics sont envoyés au flux de données pour Content Analytics.
      1. Si le SDK Web n’est pas configuré pour la propriété Tags, une nouvelle configuration de SDK Web est créée pour envoyer uniquement les événements Content Analytics.
      1. Si Web SDK est configuré pour cette propriété de balise, aucune modification n’est apportée à la configuration Web SDK existante.
* **[!UICONTROL Enregistrer]** : les modifications apportées à une configuration implémentée sont enregistrées et l’implémentation est mise à jour.


