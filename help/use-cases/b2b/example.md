---
title: Exemple de projet B2B
description: Découvrez comment configurer et générer des rapports sur les données B2B
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: 980afb6d8344c04b431c596d39a8f0003b7201ba
workflow-type: tm+mt
source-wordcount: '1822'
ht-degree: 21%

---

# Exemple de projet B2B

Cet article explique, à travers des exemples, comment configurer et générer des rapports sur les données B2B en Customer Journey Analytics.

## Connexion

Définissez votre connexion pour inclure tous les jeux de données B2B pertinents provenant d’Experience Platform. Cela inclut les jeux de données de recherche importants requis dans une configuration B2B standard dans Experience Platform. Voir [Ajout de données au niveau du compte en tant que jeu de données de recherche](b2b.md) pour plus d’informations.

Jeux de données que vous pouvez envisager d’ajouter à votre connexion :

| Jeu de données  | Schéma | Type de schéma | Classe de base | Description |
|---|---|---|---|---|
| Jeu de données d’activité B2B | Schéma d’activité B2B | Événement | XDM ExperienceEvent | Un ExperienceEvent est un enregistrement factuel de ce qui s’est produit, y compris le moment et l’identité de la personne impliquée. Les événements d’expérience peuvent être explicites (actions humaines directement observables) ou implicites (obtenus sans action humaine directe), et sont enregistrés sans agrégation ni interprétation. Ils sont essentiels à l’analyse du domaine temporel, car ils permettent l’observation et l’analyse des changements qui surviennent dans une période donnée, et la comparaison entre plusieurs périodes pour suivre les tendances. |
| Jeu de données de personne B2B | Schéma de personne B2B | Profil | XDM Individual Profile | Un profil XDM individuel forme une représentation singulière des attributs et des intérêts des individus identifiés et partiellement identifiés. Les profils moins identifiés peuvent contenir uniquement des signaux comportementaux anonymes, tels que des cookies de navigateur, tandis que les profils hautement identifiés peuvent contenir des informations personnelles détaillées telles que le nom, la date de naissance, l’emplacement et l’adresse électronique. À mesure qu’un profil se développe, il devient un solide référentiel d’informations personnelles, d’informations d’identification, de coordonnées et de préférences de communication pour une personne. |
| Jeu de données des membres de campagne B2B | Schéma de membre de campagne B2B | Recherche | Membres de XDM Business Campaign | XDM Business Campaign Members est une classe de modèle de données d’expérience (XDM) standard qui décrit un contact ou un prospect associé à une campagne commerciale. |
| Jeu de données de compte B2B | Schéma du compte B2B | Recherche | Compte d’entreprise XDM | XDM Business Account est une classe XDM standard qui capture les propriétés minimales requises d’un compte d’entreprise. |
| Jeu de données sur la relation de personne de compte B2B | Schéma de relation de personne de compte B2B | Recherche | Relation avec la personne du compte d’entreprise XDM | XDM Business Account Person Relation est une classe XDM (modèle de données d’expérience) standard qui capture les propriétés minimales requises d’une personne associée à un compte d’entreprise. |
| Jeu de données d’opportunité B2B | Schéma d’opportunité B2B | Recherche | XDM Business Opportunity | XDM Business Opportunity est une classe XDM standard qui capture les propriétés minimales requises d’une opportunité commerciale. |
| Jeu de données de relation d’opportunité B2B | Schéma de relation de personne d’opportunité B2B | Recherche | Relation avec la personne de XDM Business Opportunity | XDM Business Opportunity Person Relation est une classe de modèle de données d’expérience (XDM) standard qui capture les propriétés minimales requises d’une personne associée à une opportunité commerciale. |
| Jeu de données de campagne B2B | Schéma de campagne B2B | Recherche | XDM Business Campaign | XDM Business Campaign est une classe XDM (Experience Data Model) standard qui capture les propriétés minimales requises d’une campagne commerciale. |
| Jeu de données de liste marketing B2B | Schéma de liste marketing B2B | Recherche | Liste marketing XDM | XDM Business Marketing List est une classe XDM standard qui capture les propriétés minimales requises d’une liste marketing. Les listes marketing vous permettent de classer par priorité les clients prospects les plus susceptibles d’acheter votre produit. |
| Jeu de données des membres de liste marketing B2B | Schéma des membres de liste marketing B2B | Recherche | Membres de la liste XDM  Marketing | XDM Business Marketing List Members est une classe XDM standard qui décrit les membres, les personnes ou les contacts associés à une liste marketing. |

La relation entre les schémas de recherche, le schéma de profil et le schéma d’événement est définie dans la configuration B2B d’Experience Platform. Voir Schémas dans [Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html?lang=en) et [Définition d’une relation multiple-à-un entre deux schémas dans Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html?lang=en) pour plus d’informations.

![Relation entre les schémas B2B](assets/classes.png)

Pour chaque jeu de données de recherche que vous ajoutez à votre connexion, vous devez définir explicitement la relation avec un jeu de données d’événement à l’aide de Clé et Clé correspondante dans la boîte de dialogue Modifier le jeu de données. Par exemple :

![Clé - Clé correspondante](assets/key-matchingkey.png)


Le tableau ci-dessous présente un exemple de présentation de la variable [!UICONTROL ID de personne], [!UICONTROL Clé], et [!UICONTROL Clé correspondante] pour chacun des jeux de données.


| Jeu de données  | ID de personne | Clé | Clé correspondante (dans le jeu de données d’événement) |
|---|---|---|---|
| Jeu de données d’activité B2B | `personKey.sourceKey` | | |
| Jeu de données de personne B2B | `b2b.personKey.sourceKey` | | |
| Jeu de données de compte B2B | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| Jeu de données d’opportunité B2B | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| Jeu de données de campagne B2B | | `campaignKey.sourceKey` | *_organizationID*`.interactions.campaignKey.sourceKey` |
| Jeu de données de liste marketing B2B | | `listKey.sourceKey` | `listOperations.listKey.sourceKey` |

{style="table-layout:auto"}


Dans le tableau *_organizationID*`.interaction.*`, fait référence au groupe de champs personnalisé que vous avez ajouté au schéma d’activité B2B pour définir la relation avec le compte B2B et le schéma d’opportunité B2B. La variable `listOperations.listKey.sourceKey` fait référence au groupe de champs Ajouter à la liste ajouté au schéma d’activité B2B pour effectuer le suivi lorsqu’une personne est ajoutée à une liste spécifique.

Voir [Ajout et configuration de jeux de données](../../connections/create-connection.md) pour plus d’informations sur la configuration des paramètres d’un jeu de données.


## Vues des données

Pour avoir accès aux dimensions et mesures B2B appropriées lors de la création de votre projet Workspace, vous devez définir votre vue de données en conséquence.

Cette section fournit des recommandations et des suggestions sur les dimensions et les mesures à inclure lors de la définition de la variable [components](../../data-views/create-dataview.md#components) pour les jeux de données B2B dans votre vue de données.

Pour chaque composant, le nom, le type de schéma, le chemin d’accès au schéma et (le cas échéant) des détails sur la configuration sont fournis.

+++ Jeu de données d’activité B2B

### Mesures

| Nom du composant | Type de données de schéma | Chemin du schéma | Configuration |
|---|---|---|---|
| Ajouter à Campaign | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `leadOperation.addToCampaign` |
| Ajouter à l’opportunité | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `opportunityEvent.addToOpportunity` |
| Application fermée | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `application.close` |
| Lancement d’application | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `application.launch` |
| Flux de campagne | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** ` leadOperation.changeCampaignStream` |
| Passage en caisse | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `commerce.checkouts` |
| Convertir le prospect | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `leadOperation.convertLead` |
| Courrier électronique cliqué | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `directMarketing.emailClicked` |
| Courrier électronique diffusé | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `directMarketing.emailDelivered` |
| Email ouvert | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `directMarketing.emailOpened` |
| E-mails envoyés | Chaîne | eventType | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `directMarketing.emailSent` |
| Désabonnement du courrier électronique | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `directMarketing.emailUnsubscribed` |
| Formulaire rempli | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `web.formFilledOut` |
| Formulaire commencé | Chaîne | `web.fillOutForm.webFormName` | |
| Prospects | Chaîne | eventType | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `leadOperation.newLead` |
| Opportunité mise à jour | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `opportunityEvent.opportunityUpdated` |
| Prix | Double | *_organizationID*`.interactions.products.price` |  |
| Priorité | Nombre entier | `leadOperation.changeScore.priority` |  |
| Ajouter une liste de produits | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `commerce.productListAdds.value` |
| Ouverture de la liste de produits | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `commerce.productListOpens.value` |
| Mode Prod | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `commerce.productViews.value` |
| Achats | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `commerce.purchases.value` |
| Supprimer de l’opportunité | Chaîne | `eventType` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `opportunityEvent.removeFromOpportunity` |
| Enregistrer pour plus tard | Chaîne | eventType | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `commerce.productViews.value` |

{style="table-layout:auto"}


### Dimensions

| Nom du composant | Type de données de schéma | Chemin du schéma | Configuration |
|---|---|---|---|
| Clé de compte (clé source) | Chaîne | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| État converti | Chaîne | `leadOperation.convertLead.convertedStatus` | |
| Type d’événement | Chaîne | `eventType` | |
| Nom du formulaire | Chaîne | `leadOperation.newLead.formName` | |
| Identifiant | Chaîne | `_id` | |
| Notification envoyée | Booléen | `leadOperation.convertLead.isSentNotificationEmail` | |
| Mots-clés | Chaîne | `search.keywords` | |
| ID de liste | Chaîne | `listOperations.listID` | |
| Nom de la liste | Chaîne | `leadOperation.newLead.listName` | |
| Nom de la page | Chaîne | `web.webPageDetails.name` | |
| Clé de personne (clé source) | Chaîne | `personKey.sourceKey` | |
| Produit par | Chaîne | produitsBy | |
| Nom du produit | Chaîne | *_organizationID*`.Interactions.products.name` | |
| Rôle | Chaîne | `opportunityEvent.role` | |
| Horodatage | Date-time | `timestamp` | Format de date et d’heure : **[!UICONTROL Jour]** |
| URL | Chaîne | `web.webPageDetails.URL` | |
| Nom du formulaire web | Chaîne | `web.fillOutForm.webFormName` | |
| URL du produit | Chaîne | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


+++ Jeu de données de personne B2B


### Mesures

Aucun composant de mesure n’est défini dans le cadre de ce jeu de données.


### Dimensions

| Nom du composant | Type de données de schéma | Chemin du schéma | Configuration |
|---|---|---|---|
| Date de la dernière activité | Date-time | `extSourceSystemAudit.lastActivityDate` | Format de date et d’heure : **[!UICONTROL Jour]** |
| ID de personne | Chaîne | `personID` | |

{style="table-layout:auto"}

+++


+++  Jeu de données d’opportunité B2B

### Mesures

| Nom du composant | Type de données de schéma | Chemin du schéma | Configuration |
|---|---|---|---|
| Recettes attendues | Double | `expectedRevenue.amount` | Comportement : **[!UICONTROL Nombre de valeurs]** |
| Montant de l’opportunité | Double | `opportunityAmount.amount` | Comportement : **[!UICONTROL Nombre de valeurs]** |
| Étape d’opportunité - Livre fermé | Chaîne | `opportunityStage` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `Closed - Booked` |
| Étape d’opportunité - Perspective | Chaîne | `opportunityStage` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `Prospect` |
| Étape d’opportunité - Qualification | Chaîne | `opportunityStage` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `Opportunity Qualification` |
| Étape d’opportunité - Définition de la solution | Chaîne | `opportunityStage` | **[!UICONTROL Définition des valeurs d’inclusion/exclusion]**<br/>**[!UICONTROL Respect de la casse]**<br/>Correspondance :**[!UICONTROL  Si tous les critères sont satisfaits]**<br/>Critères : **[!UICONTROL Est égal à]** `Solution Definition and Validation` |

{style="table-layout:auto"}


### Dimensions

| Nom du composant | Type de données de schéma | Chemin du schéma | Configuration |
|---|---|---|---|
| Indicateur fermé | Booléen | `isClosed` | |
| Identifiant de société | Chaîne | `opportunityID` | |
| Catégorie de prévisions | Chaîne | `forecastCategoryName` | |
| Date de la dernière activité | Date-time | `lastActivityDate` | Format de date et d’heure : **[!UICONTROL Jour]** |
| Source de piste | Chaîne | `leadSource` | |
| Nom de l’opportunité | Chaîne | `opportunityName` | |
| État de l’opportunité | Chaîne | `opportunityStage` | |
| Won Flag | Booléen | `isWon` | |

{style="table-layout:auto"}

+++


+++ Jeu de données Campaign B2B

### Mesures

| Nom du composant | Type de données de schéma | Chemin du schéma | Configuration |
|---|---|---|---|
| Coût de la campagne | Double | `actualCost.amount` | |

{style="table-layout:auto"}


### Dimensions

| Nom du composant | Type de données de schéma | Chemin du schéma | Configuration |
|---|---|---|---|
| ID de campagne | Chaîne | `campaignID` | |
| Nom de la campagne | Chaîne | `campaignName` | |
| Date de début de la campagne | Date-time | `campaignStartDate` | Format de date et d’heure : **[!UICONTROL Jour]** |
| Nom du canal | Chaîne | `channelName` | |
| Identifiant de campagne parent | Chaîne | `parentCampaignID` | |

{style="table-layout:auto"}

+++



+++ Jeu de données de compte B2B

### Mesures

| Nom du composant | Type de données de schéma | Chemin du schéma | Configuration |
|---|---|---|---|
| Recettes annuelles | Double | `accountOrganization.annualRevenue.amount` | |
| Nombre d&#39;employés | Nombre entier | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


### Dimensions

| Nom du composant | Type de données de schéma | Chemin du schéma | Configuration |
|---|---|---|---|
| Identifiant de compte | Chaîne | `accountID` | |
| Type de compte | Chaîne | `accountType` | |
| Ville | Chaîne | `accountBillingAddress.city` | |
| Pays | Chaîne | `accountBillingAddress.country` | |
| Secteur industriel | Chaîne | `accountOrganization.industry` | |
| Région | Chaîne | `accountBillingAddress.region` | |
| ID Source | Chaîne | `accountKey.sourceID` | |
| ID d’instance source | Chaîne | `accountKey.sourceInstanceID` | |
| Clé source | Chaîne | `accountKey.sourceKey` | |
| Type de source | Chaîne | `accountKey.sourceType` | |

{style="table-layout:auto"}

+++


+++ Jeu de données de membres de campagne B2B

### Mesures

| Nom du composant | Type de données de schéma | Chemin du schéma | Configuration |
|---|---|---|---|
| Ont rebondi | Long | *_organizationID*`.campaignBounced` | Comportement : **[!UICONTROL Nombre de valeurs]** |
| Cliqué | Long | *_organizationID*`.campaignClicked` | Comportement : **[!UICONTROL Nombre de valeurs]** |
| Ouvert | Long | *_organizationID*`.CampaignOpened` | Comportement : **[!UICONTROL Nombre de valeurs]** |
| Envoyé | Long | *_organizationID*`.campaignSent` | Comportement : **[!UICONTROL Nombre de valeurs]** |
| Abonné | Long | *_organizationID*`.campaignSubscribed` | Comportement : **[!UICONTROL Nombre de valeurs]** |
| Inscriptions au webinaire | Long | *_organizationID*`.Registrations` | Comportement : **[!UICONTROL Nombre de valeurs]** |

{style="table-layout:auto"}

### Dimensions

| Nom du composant | Type de données de schéma | Chemin du schéma | Configuration |
|---|---|---|---|
| ID de campagne | Chaîne | `campaignID` | |
| Identifiant du membre de campagne | Chaîne | `campaignMemberID` | |
| État du membre de campagne | Chaîne | `memberStatus` | |
| Raison de l’état des membres de campagne | Chaîne | `memberStatusReason` | |
| Date de création | Date-time | `extSourceSystemAudit.createdDate` | Format de date et d’heure : **[!UICONTROL Jour]** |
| Date de première réponse | Chaîne | `firstRespondedDate` | Format de date et d’heure : **[!UICONTROL Jour]** |
| Réussite atteinte | Booléen | `hasReachedSuccess` | |
| A répondu | Booléen | `hasResponded` | |
| Dernier état | Chaîne | `lastStatus` | |
| Date de dernière mise à jour | Date-time | `extSourceSystemAudit.lastUpdatedDate` | Format de date et d’heure : **[!UICONTROL Jour]** |
| Date d’abonnement | Date-time | `membershipDate` | Format de date et d’heure : **[!UICONTROL Jour]** |
| Cadence des infirmières | Chaîne | `nurtureCadence` | |
| Nom du suivi de la formation | Chaîne | `nurtureTrackName` | |
| ID de personne | Chaîne | `personID` | |
| Date de succès atteinte | Date-time | `reachedSuccessDate` | Format de date et d’heure : **[!UICONTROL Jour]** |
| ID d’enregistrement du webinaire | Chaîne | `webinarRegistrationID` | |
| URL d’enregistrement du webinaire | Chaîne | `webinarConfirmationUrl` | |
| isExhausted | Booléen | isExhausted | |

{style="table-layout:auto"}

+++

<!--
### B2B Marketing List Member dataset

The B2B Marketing List Member dataset contains member of marketing lists.

-->

## Workspace

Une fois vos composants correctement définis, vous pouvez désormais créer des visualisations B2B spécifiques dans votre projet Workspace.

Vous trouverez ci-dessous un exemple de projet Workspace qui repose sur la connexion et la vue de données décrites ci-dessus. Pour plus d’informations, voir les descriptions de chaque visualisation.

+++ Détails

![Visualisations](assets/visualizations.png)

+++

