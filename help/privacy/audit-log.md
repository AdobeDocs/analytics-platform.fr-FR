---
title: Journaux d’audit
description: Découvrez comment afficher et gérer les journaux d’audit CJA.
source-git-commit: a866dec61df93bf730529a2d7513b4d76bab6694
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 18%

---


# Journaux d’audit

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de [tests limités](/help/release-notes/releases.md).

Pour accroître la transparence et la visibilité des activités exécutées dans le système, Customer Journey Analytics (CJA) vous permet de contrôler l’activité des utilisateurs pour divers services et fonctionnalités sous la forme de &quot;journaux d’audit&quot;. Ces journaux constituent un journal de vérification qui peut vous aider à résoudre les problèmes et à vous conformer efficacement aux politiques de gestion des données d’entreprise et aux exigences réglementaires, telles que la Loi sur la transférabilité et la responsabilité de l’assurance-santé (HIPAA).

En un sens simple, un journal d’audit indique : **who** performance **what** et **when**. Chaque action enregistrée dans un journal contient des métadonnées qui indiquent le type d’action, la date et l’heure, l’e-mail de l’utilisateur qui a exécuté l’action et des attributs supplémentaires liés au type d’action.

Cette rubrique traite des journaux d’audit dans CJA, notamment de la manière de les afficher et de les gérer dans l’interface utilisateur.

## Accès aux journaux d’audit

Lorsque la fonction est activée pour votre organisation, les journaux d’audit sont automatiquement collectés au fur et à mesure de l’activité. Vous n’avez pas besoin d’activer manuellement la collecte des journaux.

Pour afficher et exporter les journaux d’audit, le **[!UICONTROL Accès aux journaux d’audit]** autorisation de contrôle d’accès dans Adobe Console. Pour savoir comment gérer les autorisations individuelles pour les fonctionnalités CJA, reportez-vous à la section [documentation sur le contrôle d’accès](/help/getting-started/cja-access-control.md).

## Affichage des journaux d’audit dans l’interface utilisateur

Dans CJA, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Journaux d’audit]**.

Le journal d’audit pour aujourd’hui et hier s’affiche par défaut.

![journal d’audit](assets/audit_ui.png)

Vous pouvez sélectionner les colonnes visibles en accédant au sélecteur de colonnes en haut à droite.

## Affichage des informations sur les entrées de journal individuelles

Double-cliquez sur le bouton info (i) en regard d’une description.

![journal d’audit](assets/info-button-audit.png)

Les éléments suivants s’affichent :

| Élément | Description |
| --- | --- |
| Nom de l’action | Voici la liste des actions possibles : <ul><li>API_Request</li><li>Approuver</li><li>Créez</li><li>Modifier  </li><li>Exporter</li><li>Login_failed</li><li>Login_success</li><li>Déconnexion</li><li>Org_change</li><li>Actualiser</li><li>Partager</li><li>Transférer</li><li>Ne pas approuver</li><li>Annuler le partage</li></ul> |
| Description | Résumé de l’action, type de composant (avec ID) et autres valeurs. |
| Nom d’utilisateur | L’utilisateur qui effectue l’action. |
| Type de composant | Les types de composants possibles sont les suivants : <ul><li>Annotation</li><li>Audience</li><li>Mesure calculée</li><li>Connexion</li><li>Data_Group</li><li>Data_View</li><li>Feature_Access</li><li>Filtre</li><li>IMS_Org</li><li>Mobile</li><li>Projet  </li><li>Rapport</li><li>Scheduled_Project</li><li>Utilisateur</li><li>User_Group</li></ul> |
| Identifiant de l’organisation IMS | Identifiant unique attribué à votre instance lorsque vous vous connectez pour la première fois à Adobe Experience Cloud. Il doit être au format suivant : xxx@AdobeOrg. |
| Identifiant utilisateur | Identifiant unique identifiant l’utilisateur qui a effectué cette action. |
| Date de création  | Quand cette action a été entreprise. |
| Courriel  | Adresse électronique de l’utilisateur qui effectue l’action. |
| ID du composant | Identifiant unique qui identifie le composant sur lequel l’action est effectuée. |
| ID du journal | Identifiant unique identifiant cette entrée de journal. |
| Type d’utilisateur | Les types possibles sont les suivants : IMS, OKTA |

### Filtrage des journaux d’audit

Sélectionnez l’icône d’entonnoir (![filter](assets/filter-icon.png)) pour afficher une liste de contrôles de filtre afin de limiter les résultats. Seuls les 1000 derniers enregistrements sont affichés, quels que soient les différents filtres sélectionnés.

![filtres](assets/filters.png)

Les filtres suivants sont disponibles pour les événements de contrôle dans l’interface utilisateur :

| Filtre | Description |
| --- | --- |
| [!UICONTROL Période] | Filtrez sur une autre période en sélectionnant une autre date ou une autre période en faisant glisser le curseur sur plusieurs dates. Par défaut, les dates d’aujourd’hui et d’hier sont sélectionnées. |
| [!UICONTROL Action] | Filtrez sur une ou plusieurs des actions suivantes : <ul><li>API_Request</li><li>Approuver</li><li>Créez</li><li>Modifier  </li><li>Exporter</li><li>Login_failed</li><li>Login_success</li><li>Déconnexion</li><li>Org_change</li><li>Actualiser</li><li>Partager</li><li>Transférer</li><li>Ne pas approuver</li><li>Annuler le partage</li></ul> |
| [!UICONTROL Identifiant utilisateur] | Filtrez sur un utilisateur spécifique selon son identifiant utilisateur. L’ID utilisateur est accessible en sélectionnant le bouton info (i) en regard d’un nom d’utilisateur. |
| [!UICONTROL Courriel ] | Filtrer sur l’adresse électronique d’un utilisateur spécifique. Pour trouver l’email, cliquez sur le bouton d’informations (i) en regard d’un nom d’utilisateur. |
| [!UICONTROL ID du composant] | Filtrez sur un identifiant de composant spécifique. L’identifiant utilisateur est accessible en sélectionnant le bouton d’informations (i) pour un composant. |
| [!UICONTROL Type de composant] | Filtrer sur un ou plusieurs types de composant : <ul><li>Annotation</li><li>Audience</li><li>Mesure calculée</li><li>Connexion</li><li>Data_Group</li><li>Data_View</li><li>Feature_Access</li><li>Filtre</li><li>IMS_Org</li><li>Mobile</li><li>Projet  </li><li>Rapport</li><li>Scheduled_Project</li><li>Utilisateur</li><li>User_Group</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Types d’événements capturés par les journaux d’audit

Le tableau suivant décrit les actions sur lesquelles les types de composants sont enregistrés par les journaux d’audit :

| Type de composant | Actions |
| --- | --- |
| [!UICONTROL Annotation] | <ul><li>Créez</li><li>Supprimer</li><li>Modifier  </li></ul> |
| [!UICONTROL Audience] | <ul><li>API_Request</li><li>Créez</li><li>Supprimer</li><li>Modifier  </li><li>Exporter</li><li>Actualiser</li></ul> |
| [!UICONTROL Mesure calculée] | <ul><li>API_Request</li><li>Créez</li><li>Supprimer</li><li>Modifier  </li></ul> |
| [!UICONTROL Connexion] | <ul><li>API_Request</li><li>Créez</li><li>Supprimer</li><li>Modifier  </li></ul> |
| [!UICONTROL Vue de données] | <ul><li>API_Request</li><li>Créez</li><li>Supprimer</li><li>Modifier  </li></ul> |
| [!UICONTROL Période] | <ul><li>API_Request</li><li>Créez</li><li>Supprimer</li><li>Modifier  </li></ul> |
| [!UICONTROL Filtrer] | <ul><li>API_Request</li><li>Créez</li><li>Supprimer</li><li>Modifier  </li></ul> |
| [!UICONTROL Organisation IMS] | <ul><li>API_Request</li><li>Créez</li><li>Supprimer</li><li>Modifier  </li></ul> |
| [!UICONTROL Projet  ] | <ul><li>API_Request</li><li>Créez</li><li>Supprimer</li><li>Modifier  </li></ul> |
| [!UICONTROL Rapport] | <ul><li>API_Request</li></ul> |
| [!UICONTROL Projet planifié] | <ul><li>API_Request</li><li>Créez</li><li>Supprimer</li><li>Modifier  </li></ul> |
| [!UICONTROL Utilisateur] | <ul><li>API_Request</li><li>Créez</li><li>Supprimer</li><li>Modifier  </li></ul> |
| [!UICONTROL Groupe d’utilisateurs] | <ul><li>API_Request</li><li>Créez</li><li>Supprimer</li><li>Modifier  </li></ul> |

{style=&quot;table-layout:auto&quot;}

## Téléchargement des journaux d’audit

Vous pouvez télécharger les journaux d’audit au format CSV ou JSON. Les filtres appliqués ou les colonnes sélectionnées sont répercutés dans les fichiers téléchargés.

1. Cliquez sur **[!UICONTROL Télécharger]** en haut à droite de l’écran.
1. Spécifiez le format.
1. Cliquez sur **[!UICONTROL Télécharger]** encore une fois.

## Gestion des journaux d’audit dans l’API

Toutes les actions que vous pouvez effectuer dans l’interface utilisateur peuvent également être effectuées à l’aide d’appels API. Voir [Document de référence de l’API CJA](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) pour plus d’informations.