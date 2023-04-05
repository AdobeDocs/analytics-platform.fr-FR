---
title: Intégration de la gestion des décisions Adobe Journey Optimizer à Customer Journey Analytics (CJA)
description: Incluez les données générées par Adobe Journey Optimizer Decision Management et analysez-les à l’aide d’Analysis Workspace dans Customer Journey Analytics.
source-git-commit: f9ee0db464c49339bc36b144e18ef4aea4f4f033
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 19%

---

# Intégration de la gestion des décisions à Customer Journey Analytics


Adobe Journey Optimizer [Gestion des décisions](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) facilite la personnalisation grâce à une bibliothèque centrale d’offres marketing et à un moteur de décision qui applique des règles et des contraintes aux profils riches en temps réel créés par Adobe Experience Platform pour vous aider à envoyer à vos clients la bonne offre au bon moment.

La gestion des décisions fait partie de Adobe Journey Optimizer et est intégrée à ce dernier (AJO). Il peut également être utilisé indépendamment des parcours et des campagnes définis dans AJO, en utilisant son [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) prise en charge.

Vous pouvez importer les données générées par la gestion des décisions pour effectuer une analyse avancée dans Customer Journey Analytics (CJA) en procédant comme suit :

## Envoi de données depuis la gestion de la décision vers Adobe Experience Platform

Adobe Experience Platform sert de source de données centrale et de lien entre la gestion de la décision et le Customer Journey Analytics. Les données de la gestion de la décision sont collectées dans Experience Platform **automatiquement** ou dans le cadre d’ **événements d’expérience envoyés explicitement** (par exemple, impressions ou clics). Voir [Prise en main de la collecte de données](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) pour plus d’informations.

## Création d’une connexion

Une fois que les données de la gestion de la décision sont dans Adobe Experience Platform, vous pouvez créer une [Connexion](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr) en fonction de vos jeux de données de gestion de la décision. Vous pouvez également ajouter des jeux de données de gestion de la décision à une connexion existante.

Sélectionnez et configurez les jeux de données suivants :

| Jeu de données  | Type de jeu de données | Paramètres de connexion | Description |
| --- | --- | --- | --- |
| ODE DecisonEvents - _sandbox_ prise de décision | Événement | ID de personne: `IdentityMap` | Contient des données générées automatiquement pour les événements de décision de la gestion de la décision. _Sandbox_ fait référence au nom de l’environnement de test spécifique. |
| Jeu de données d’événement de retour de message AJO | Événement | ID de personne: `IdentityMap` | Contient les événements de diffusion de message. |
| Jeu de données d’événement de suivi d’email AJO | Événement | ID de personne: `IdentityMap` | Contient les événements de suivi de courrier électronique. |
| Jeu de données d’événement de suivi push AJO | Événement | ID de personne: `IdentityMap` | Contient les événements de suivi push. |
| Jeu de données d’entité AJO | Recherche | Clé : `_id`<br>Clé correspondante : `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contient des classifications qui associent des métadonnées de Parcours et de campagne à toutes les données d’événement AJO. |

{style="table-layout:auto"}

## Création d’une vue de données

Une fois la connexion créée, vous pouvez en créer une ou plusieurs. [Vues des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=fr) pour configurer les dimensions et mesures souhaitées disponibles dans CJA.

>[!NOTE]
>
>Les écarts de données entre AJO et CJA sont généralement inférieures à 1-2 %. Des écarts plus importants sont possibles pour les données collectées au cours des deux dernières heures. Utilisez des périodes excluant aujourd’hui pour atténuer les écarts entre les temps de traitement.

### Configuration des dimensions

Vous pouvez créer les dimensions suivantes dans une vue de données afin d’obtenir une parité approximative avec des dimensions similaires dans la gestion de la décision. Voir [Paramètres des composants](/help/data-views/component-settings/overview.md) dans le Gestionnaire de vues de données pour en savoir plus sur les options de personnalisation des dimensions.

| Dimension | Élément de schéma | Paramètres de composant |
| --- | --- | --- |
| Nom de l’activité | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Type de composant : Dimension |
| Identifiant du conteneur | `_experience.decisioning.containerID` | Type de composant : Dimension |
| Identifiant de corrélation | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Type de composant : Dimension |
| Nom de l’option de décision | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Type de composant : Dimension |
| Nom de l’option de décision de secours | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Type de composant : Dimension |
| Nom de l’emplacement | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Type de composant : Dimension |

{style="table-layout:auto"}


### Configuration des mesures

Vous pouvez créer les mesures suivantes dans une vue de données afin d’obtenir une parité approximative avec des mesures similaires dans la gestion des décisions. Voir [Paramètres des composants](/help/data-views/component-settings/overview.md) dans le Gestionnaire de vues de données pour en savoir plus sur les options de personnalisation des mesures.

| Mesure | Description | Élément de schéma | Paramètres de composant |
| --- | --- | --- | --- |
| Type d’événement (renommer pour faire référence à un événement spécifique, par exemple `Feedback` pour `message.feedback`) [1] | Quantité d’un type d’événement spécifique | `eventType` | Type de composant : Mesure<br/>**[!UICONTROL Définition des valeurs d’exclusion d’inclusion ]**: Activé<br/>**[!UICONTROL Correspondance]**: [!UICONTROL Si tous les critères sont satisfaits]<br/>**[!UICONTROL Critères ]**:**[!UICONTROL  Est égal à&#x200B;]**`message.feedback` |
| Score de l’option de décision | Valeur calculée pour une option de décision dans le contexte d’une portée unique. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Type de composant : Mesure |
| Score de l’option de décision de secours | Valeur calculée pour une option de décision de secours dans le contexte d’une portée unique. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Type de composant : Mesure |
| Offres ignorées | Nombre d’offres ignorées ou rejetées sans autre interaction directe. | `_experience.decisioning.`<br/>`propositionEventType.display` | Type de composant : Mesure |
| Affichage des offres | Nombre d’offres affichées sur le profil. | `_experience.decisioning.`<br/>`propositionEventType.display` | Type de composant : Mesure |
| Interaction Offres | Nombre d’offres affichées sur le profil. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Type de composant : Mesure |
| Offres envoyées | Nombre d’offres envoyées au profil. | `_experience.decisioning.`<br/>`propositionEventType.send` | Type de composant : Mesure |
| Déclencheur d’offres | Nombre d’offres sélectionnées pour être affichées par le SDK client. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Type de composant : Mesure |
| Offres - Désabonner | Nombre d’offres demandées par le profil qui ne s’afficheront pas à l’avenir. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Type de composant : Mesure |

{style="table-layout:auto"}
[1] Vous pouvez définir plusieurs mesures pour les différents types d’événement disponibles. Voir [Inclure les paramètres du composant Exclure les valeurs](/help/data-views/component-settings/include-exclude-values.md) pour plus d’informations.
