---
title: Exemple de projet B2B
description: Découvrez comment configurer et générer des rapports sur les données B2B
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: 9c60c00818e82a6ca891ab9d90260922437c6cca
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 19%

---

# Exemple de projet B2B

Cet article explique comment configurer, configurer et générer des rapports au niveau du profil (personne) sur la base de données B2B en Customer Journey Analytics.

## Connexion

Définissez votre connexion pour inclure tous les jeux de données B2B pertinents provenant d’Experience Platform. Veillez à inclure et à transformer tous les jeux de données de recherche pertinents requis pour un scénario de rapport basé sur les personnes B2B type. Voir [Transformation des jeux de données de recherche B2B](/help/connections/transform-datasets-b2b-lookups.md) pour plus d’informations.

Jeux de données que vous pouvez envisager d’ajouter à votre connexion :

| Jeu de données | Schéma | Type de schéma | Classe de base | Description |
|---|---|---|---|---|
| Jeu de données d’activité B2B | Schéma d’activité B2B | Événement | XDM ExperienceEvent | Un ExperienceEvent est un enregistrement factuel de ce qui s’est produit, y compris le moment et l’identité de la personne impliquée. Les événements d’expérience peuvent être explicites (actions humaines directement observables) ou implicites (obtenus sans action humaine directe), et sont enregistrés sans agrégation ni interprétation. Ils sont essentiels à l’analyse du domaine temporel, car ils permettent l’observation et l’analyse des changements qui surviennent dans une période donnée, et la comparaison entre plusieurs périodes pour suivre les tendances. |
| Jeu de données de personne B2B | Schéma de personne B2B | Profile | XDM Individual Profile | Un profil XDM individuel forme une représentation singulière des attributs et des intérêts des individus identifiés et partiellement identifiés. Les profils moins identifiés peuvent contenir uniquement des signaux comportementaux anonymes, tels que des cookies de navigateur, tandis que les profils hautement identifiés peuvent contenir des informations personnelles détaillées telles que le nom, la date de naissance, l’emplacement et l’adresse électronique. À mesure qu’un profil se développe, il devient un solide référentiel d’informations personnelles, d’informations d’identification, de coordonnées et de préférences de communication pour une personne. |
| Jeu de données sur la relation de personne de compte B2B | Schéma de relation de personne de compte B2B | Recherche | Relation Personne/Compte d’entreprise XDM | XDM Business Account Person Relation est une classe XDM (modèle de données d’expérience) standard qui capture les propriétés minimales requises d’une personne associée à un compte d’entreprise. |
| Jeu de données de relation d’opportunité B2B | Schéma de relation de personne d’opportunité B2B | Recherche | Relation Personne/XDM Business Opportunity | XDM Business Opportunity Person Relation est une classe de modèle de données d’expérience (XDM) standard qui capture les propriétés minimales requises d’une personne associée à une opportunité commerciale. |
| Jeu de données des membres de liste marketing B2B | Schéma des membres de liste marketing B2B | Recherche | Membres de la liste marketing XDM | XDM Business Marketing List Members est une classe XDM standard qui décrit les membres, les personnes ou les contacts associés à une liste marketing. |
| Jeu de données des membres de campagne B2B | Schéma de membre de campagne B2B | Recherche | Membres de XDM Business Campaign | XDM Business Campaign Members est une classe de modèle de données d’expérience (XDM) standard qui décrit un contact ou un prospect associé à une campagne commerciale. |
<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


La relation entre les schémas de recherche, le schéma de profil et le schéma d’événement est définie dans la configuration B2B d’Experience Platform. Voir Schémas dans [Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html) et [Définition d’une relation multiple-à-un entre deux schémas dans Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html) pour plus d’informations.

![Relation entre les schémas B2B](assets/classes.png)

Pour chaque jeu de données de recherche que vous ajoutez à votre connexion, vous devez définir explicitement la relation avec un jeu de données d’événement à l’aide de **[!UICONTROL Clé]** et **[!UICONTROL Clé correspondante]** dans le **[!UICONTROL Modifier le jeu de données]** boîte de dialogue. Par exemple :

![Clé - Clé correspondante](assets/key-matchingkey.png)

Quatre schémas sont explicitement utilisés pour connecter le schéma Personne à d’autres schémas pertinents : Compte, Opportunité, Campagne et Liste Marketing. Ces schémas sont basés sur les classes de schémas suivantes :

* Relation Personne/Compte d’entreprise XDM
* Relation Personne/XDM Business Opportunity
* Membres de la liste XDM Business Marketing
* Membres de XDM Business Campaign

Pour chaque jeu de données de recherche, pour un schéma basé sur une telle classe de schéma, vous activez également **[!UICONTROL Transformer un jeu de données]** pour s’assurer que les données sont transformées pour les recherches basées sur les personnes. Voir [Transformer des jeux de données pour les recherches B2B](/help/connections/transform-datasets-b2b-lookups.md) pour plus d’informations.

Le tableau ci-dessous présente un exemple de présentation de la variable [!UICONTROL ID de personne], [!UICONTROL Clé], et [!UICONTROL Clé correspondante] pour chacun des jeux de données.


| Jeu de données | ID de personne | Clé | Clé correspondante (dans le jeu de données d’événement) |
|---|---|---|---|
| Jeu de données d’activité B2B | `personKey.sourceKey` | | |
| Jeu de données de personne B2B | `b2b.personKey.sourceKey` | | |
| Jeu de données de personne de compte B2B | | `personKey.sourceKey` | `personKey.sourceKey` |
| Jeu de données d’opportunité B2B | | `personKey.sourceKey` | `personKey.sourceKey` |
| Jeu de données des membres de campagne B2B | | `personKey.sourceKey` | `personKey.sourceKey` |
| Jeu de données de liste marketing B2B | | `personKey.sourceKey` | `personKey.sourceKey` |

{style="table-layout:auto"}

Voir [Ajout et configuration de jeux de données](../../connections/create-connection.md) pour plus d’informations sur la configuration des paramètres d’un jeu de données.


## Vue de données

Pour avoir accès aux dimensions et mesures B2B appropriées lors de la création de votre projet Workspace, vous devez définir votre vue de données en conséquence.

Vous pouvez ajouter les composants suivants en tant que dimensions à votre vue de données pour vous assurer que vous pouvez créer des rapports sur le niveau basé sur la personne sur vos données B2B. Les noms des composants sont modifiés pour plus de clarté.

| Nom du composant | Jeu de données | Type de données de schéma | Chemin du schéma |
|---|---|---|---|
| Personne | Activité B2B | Chaîne | `personID` |
| Compte | Personne du compte B2B | Chaîne | `accountKey.sourceID` |
| Campagne | Membre de campagne B2B | Chaîne | `campaignKey.sourceKey` |
| Nom de la liste marketing | Liste marketing B2B | Chaîne | `marketingListID` |
| Opportunité | Personne d’opportunité B2B | Chaîne | `opportunityKey.sourceID` |


<!--
This section provides recommendations and suggestions on what dimensions and metrics to include when defining the [components](../../data-views/create-dataview.md#components) for B2B datasets in your data view.

For each component, the name, schema type, schema path, and (when applicable) details about the configuration are provided.


+++ B2B Activity dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Add To Campaign | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.addToCampaign` |
| Add To Opportunity | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.addToOpportunity` |
| Application Closed | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `application.close` |
| Application Launch | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `application.launch` |
| Campaign Stream | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** ` leadOperation.changeCampaignStream` |
| Checkout | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.checkouts` |
| Convert Lead | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.convertLead` |
| Email Clicked | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailClicked` |
| Email Delivered | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailDelivered` |
| Email Opened | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailOpened` |
| Email Sent | String | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailSent` |
| Email Unsubscribed | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailUnsubscribed` |
| Form Filled Out | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `web.formFilledOut` |
| Form Started | String | `web.fillOutForm.webFormName` | |
| Leads | String | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.newLead` |
| Opportunity Updated | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.opportunityUpdated` |
| Price | Double | *_organizationID*`.interactions.products.price` |  |
| Priority | Integer | `leadOperation.changeScore.priority` |  |
| Prod List Add | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productListAdds.value` |
| Prod List Open | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productListOpens.value` |
| Prod View | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productViews.value` |
| Purchases | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.purchases.value` |
| Remove From Opportunity | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.removeFromOpportunity` |
| Save for Laters | String | eventType |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productViews.value` |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Account Key (Source Key) | String | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| Converted Status | String | `leadOperation.convertLead.convertedStatus` | |
| Event Type | String | `eventType` | |
| Form Name | String | `leadOperation.newLead.formName` | |
| Identifier | String | `_id` | |
| Is Sent Notification | Boolean | `leadOperation.convertLead.isSentNotificationEmail` | |
| Keywords | String | `search.keywords` | |
| List ID | String | `listOperations.listID` | |
| List Name | String | `leadOperation.newLead.listName` | |
| Page Name | String | `web.webPageDetails.name` | |
| Person Key (Source Key) | String | `personKey.sourceKey` | |
| Produced By | String | producedBy | |
| Product Name | String | *_organizationID*`.Interactions.products.name` | |
| Role | String | `opportunityEvent.role` | | 
| Timestamp | Date-time | `timestamp` | Date-Time format: **[!UICONTROL Day]** |
| URL | String | `web.webPageDetails.URL` | |
| Web Form Name | String | `web.fillOutForm.webFormName` | |
| Product URL | String | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


+++ B2B Person dataset


### Metrics

No metric components are defined as part of this dataset.


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Last Activity Date | Date-time | `extSourceSystemAudit.lastActivityDate` | Date-Time format: **[!UICONTROL Day]** |
| Person ID | String | `personID` | |

{style="table-layout:auto"}

+++

+++ B2B Account Person dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Annual Revenue | Double | `accountOrganization.annualRevenue.amount` | |
| Number of employees | Integer | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Acount | String | `accountKey.sourceID` | 

{style="table-layout:auto"}

| Account Identifier | String | `accountID` | |
| Account Type | String | `accountType` | |
| City | String | `accountBillingAddress.city` | |
| Country | String | `accountBillingAddress.country` | |
| Industry | String | `accountOrganization.industry` | |
| Region | String | `accountBillingAddress.region` | |
| Source ID | String | `accountKey.sourceID` | |
| Source Instance ID | String | `accountKey.sourceInstanceID` | |
| Source Key | String | `accountKey.sourceKey` | |
| Source Type | String | `accountKey.sourceType` | |


+++

+++  B2B Opportunity Person dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Expected Revenue | Double | `expectedRevenue.amount` | Behavior: **[!UICONTROL Count values]** |
| Opportunity Amount | Double | `opportunityAmount.amount` | Behavior: **[!UICONTROL Count values]** |
| Opportunity Stage - Closed Book | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Closed - Booked` |
| Opportunity Stage - Prospect | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Prospect` |
| Opportunity Stage - Qualification | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Opportunity Qualification` |
| Opportunity Stage - Solution Definition | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Solution Definition and Validation` |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Closed Flag | Boolean | `isClosed` | |
| Company ID | String | `opportunityID` | |
| Forecast Category | String | `forecastCategoryName` | |
| Last Activity Date | Date-time | `lastActivityDate` | Date-time format: **[!UICONTROL Day]** |
| Lead Source | String | `leadSource` | |
| Opportunity Name | String | `opportunityName` | | 
| Opportunity Status | String | `opportunityStage` | |
| Won Flag | Boolean | `isWon` | |

{style="table-layout:auto"}

+++


+++ B2B Campaign Member dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Bounced | Long | *_organizationID*`.campaignBounced` | Behavior: **[!UICONTROL Count values]** |
| Clicked | Long | *_organizationID*`.campaignClicked` | Behavior: **[!UICONTROL Count values]** |
| Opened | Long | *_organizationID*`.CampaignOpened` | Behavior: **[!UICONTROL Count values]** |
| Sent | Long | *_organizationID*`.campaignSent` | Behavior: **[!UICONTROL Count values]** |
| Subscribed | Long | *_organizationID*`.campaignSubscribed` | Behavior: **[!UICONTROL Count values]** |
| Webinar Registrations | Long | *_organizationID*`.Registrations` | Behavior: **[!UICONTROL Count values]** |

{style="table-layout:auto"}

### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Campaign ID | String | `campaignID` | |
| Campaign Member ID | String | `campaignMemberID` | |
| Campaign Member Status | String | `memberStatus` | |
| Campaign Member Status Reason | String | `memberStatusReason` | |
| Created Date | Date-time | `extSourceSystemAudit.createdDate` | Date-time format: **[!UICONTROL Day]** |
| First Responded Date | String | `firstRespondedDate` | Date-time format: **[!UICONTROL Day]** |
| Has Reached Success | Boolean | `hasReachedSuccess` | |
| Has Responded | Boolean | `hasResponded` | |
| Last Status | String | `lastStatus` | |
| Last Updated Date | Date-time | `extSourceSystemAudit.lastUpdatedDate` | Date-time format: **[!UICONTROL Day]** |
| Membership Date | Date-time | `membershipDate` | Date-time format: **[!UICONTROL Day]** |
| Nurture Cadence | String | `nurtureCadence` | |
| Nurture Track Name | String | `nurtureTrackName` | |
| Person ID | String | `personID` | |
| Reached Success Date | Date-time | `reachedSuccessDate` | Date-time format: **[!UICONTROL Day]** |
| Webinar Registration ID | String | `webinarRegistrationID` | |
| Webinar Registration URL | String | `webinarConfirmationUrl` | |
| isExhausted | Boolean | isExhausted | |

{style="table-layout:auto"}

+++

+++ B2B Marketing List Member dataset

### Metrics

### Dimensions

+++

-->

## Workspace

Lorsque vos composants sont correctement définis dans la vue de données, vous pouvez désormais créer des rapports B2B et des visualisations spécifiques dans votre projet Workspace.

Vous trouverez ci-dessous un exemple de projet qui repose sur la connexion et la vue de données décrites ci-dessus.

![Exemple de projet](assets/sample-project.png)

<!-- See the descriptions for each visualization for more details.

+++ Example project

![Visualizations](assets/visualizations.png)

+++
-->
