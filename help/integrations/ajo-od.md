---
title: Intégrer la gestion des décisions Adobe Journey Optimizer à Customer Journey Analytics
description: Incluez les données générées par la gestion des décisions Adobe Journey Optimizer et analysez-les à l’aide d’Analysis Workspace dans Customer Journey Analytics.
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Experience Platform Integration
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 99%

---

# Intégrer la gestion des décisions à Adobe Customer Journey Analytics


La [gestion des décisions](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=fr) Adobe Journey Optimizer facilite la personnalisation avec une bibliothèque centrale d’offres marketing et un moteur de décision qui applique des règles et des contraintes aux profils en temps réel riches créés par Adobe Experience Platform afin de vous aider à envoyer à vos clientes et clients la bonne offre au bon moment.

La gestion des décisions fait partie d’Adobe Journey Optimizer et est intégrée à celui-ci. Elle peut également être utilisée indépendamment des campagnes et parcours définis dans Adobe Journey Optimizer, en utilisant la prise en charge de l’[API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html) riche.

Vous pouvez importer les données générées par la gestion des décisions afin d’effectuer une analyse avancée dans Customer Journey Analytics en procédant comme suit :

## Envoyer des données de la gestion des décisions vers Adobe Experience Platform

Adobe Experience Platform sert de source de données centrale et de lien entre la gestion des décisions et Customer Journey Analytics. Les données de la gestion des décisions sont collectées dans Experience Platform **automatiquement** ou dans le cadre d’**événements d’expérience envoyés explicitement** (par exemple, impressions ou clics). Pour plus d’informations, voir [Prise en main avec les collectes de données](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html).

## Créer une connexion

Une fois que les données de gestion des décisions sont dans Adobe Experience Platform, vous pouvez créer une [connexion](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr) en fonction de votre jeu de données de gestion des décisions. Vous pouvez également ajouter des jeux de données de gestion des décisions à une connexion existante.

Sélectionnez et configurez les jeux de données suivants :

| Jeu de données | Type de jeu de données | Paramètres de connexion | Description |
| --- | --- | --- | --- |
| ODE DecisonEvents - Décisions de _sandbox_ | Événement | ID de personne : `IdentityMap` | Contient des données générées automatiquement pour les événements de décision de la gestion des décisions. _Sandbox_ fait référence au nom du sandbox spécifique. |
| Jeu de données d’événements de messages de feedback Adobe Journey Optimizer | Événement | ID de personne : `IdentityMap` | Contient les événements de diffusion des messages. |
| Jeu de données d’événements d’expérience de suivi d’e-mails Adobe Journey Optimizer | Événement | ID de personne : `IdentityMap` | Contient les événements de suivi des e-mails. |
| Jeu de données d’événements d’expérience de suivi de notifications push Adobe Journey Optimizer | Événement | ID de personne : `IdentityMap` | Contient les événements de suivi des notifications push. |
| Jeu de données d’entités Adobe Journey Optimizer | Recherche | Clé : `_id`<br>clé correspondante : `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contient des classifications qui associent des métadonnées de parcours et de campagne à toutes les données d’événement Adobe Journey Optimizer. |

{style="table-layout:auto"}

## Créer une vue de données

Une fois la connexion créée, vous pouvez créer une ou plusieurs [vues des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=fr) pour configurer les dimensions et mesures souhaitées disponibles dans Customer Journey Analytics.

>[!NOTE]
>
>Les écarts de données entre Adobe Journey Optimizer et Customer Journey Analytics sont généralement inférieurs à 1-2 %. Des écarts plus importants sont possibles pour les données collectées au cours des deux dernières heures. Utilisez des périodes excluant aujourd’hui pour atténuer les écarts entre les temps de traitement.

### Configurer des dimensions

Vous pouvez créer les dimensions suivantes dans une vue de données pour obtenir une parité approximative avec des dimensions similaires dans Gestion des décisions. Voir [Paramètres des composants](/help/data-views/component-settings/overview.md) dans le Gestionnaire de vues de données pour en savoir plus sur les options de personnalisation des dimensions.

| Dimension | Élément de schéma | Paramètres de composant |
| --- | --- | --- |
| Nom de l’activité | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Type de composant : dimension |
| Identifiant de conteneur | `_experience.decisioning.containerID` | Type de composant : dimension |
| Identifiant de corrélation | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Type de composant : dimension |
| Nom de l’option de décision | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Type de composant : dimension |
| Nom de l’option de décision de secours | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Type de composant : dimension |
| Nom de l’emplacement | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Type de composant : dimension |

{style="table-layout:auto"}


### Configurer des mesures

Vous pouvez créer les mesures suivantes dans une vue de données pour obtenir une parité approximative avec des mesures similaires dans Gestion des décisions. Voir [Paramètres des composants](/help/data-views/component-settings/overview.md) dans le Gestionnaire de vues de données pour en savoir plus sur les options de personnalisation des mesures.

| Mesure | Description | Élément de schéma | Paramètres de composant |
| --- | --- | --- | --- |
| Type d’événement (renommer pour faire référence à un événement spécifique, par exemple `Feedback` pour `message.feedback`) [1] | Quantité d’un type d’événement spécifique | `eventType` | Type de composant : Mesure <br/>**[!UICONTROL Définir les valeurs d’inclusion/exclusion ]** : Activé <br/>**[!UICONTROL Correspondance]** : [!UICONTROL Si tous les critères sont satisfaits ]<br/>**[!UICONTROL Critères ]** :**[!UICONTROL  est égal à&#x200B;]**`message.feedback` |
| Score de l’option de décision | Valeur calculée pour une option de décision dans le contexte d’une portée unique. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Type de composant : mesure |
| Score de l’option de décision de secours | Valeur calculée pour une option de décision de secours dans le contexte d’une portée unique. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Type de composant : mesure |
| Renvois d’offres | Nombre d’offres renvoyées ou refusées sans aucune autre interaction directe. | `_experience.decisioning.`<br/>`propositionEventType.display` | Type de composant : mesure |
| Affichage des offres | Nombre d’offres affichées sur le profil. | `_experience.decisioning.`<br/>`propositionEventType.display` | Type de composant : mesure |
| Interaction avec des offres | Nombre d’offres affichées sur le profil. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Type de composant : mesure |
| Envois d’offres | Nombre d’offres envoyées au profil. | `_experience.decisioning.`<br/>`propositionEventType.send` | Type de composant : mesure |
| Déclencheur d’offres | Nombre d’offres sélectionnées pour être affichées par le SDK client. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Type de composant : mesure |
| Désabonnement d’offres | Nombre d’offres demandées par le profil qui ne doit pas être affichées à l’avenir. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Type de composant : mesure |

{style="table-layout:auto"}

[1] Vous pouvez définir plusieurs mesures pour les différents types d’événement disponibles. Voir [Paramètres de composant des valeurs d’inclusion/d’exclusion](/help/data-views/component-settings/include-exclude-values.md) pour plus d’informations.
