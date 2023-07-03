---
title: Journaux d’audit
description: Découvrez comment afficher et gérer les journaux d’audit des Customer Journey Analytics.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 67%

---

# Journaux d’audit

Pour accroître la transparence et la visibilité des activités exécutées dans le système, Adobe Customer Journey Analytics vous permet de contrôler l’activité des utilisateurs pour divers services et fonctionnalités sous la forme de &quot;journaux d’audit&quot;. Ces logs constituent un journal d’audit qui peut vous aider à résoudre les problèmes et à vous conformer efficacement aux politiques de gestion des données d’entreprise et aux exigences réglementaires, telles que la Health Insurance Portability and Accountability Act (HIPAA).

Pour faire simple, un journal d’audit indique **qui** a effectué **quelle** action et **quand**. Chaque action enregistrée dans un journal contient des métadonnées qui indiquent le type d’action, la date et l’heure, l’ID d’e-mail de l’utilisateur qui a exécuté l’action et des attributs supplémentaires liés au type d’action.

Cette rubrique aborde les journaux d’audit en Customer Journey Analytics, notamment la manière de les afficher et de les gérer dans l’interface utilisateur.

## Accéder aux journaux d’audit

Lorsque la fonction est activée pour votre organisation, les journaux d’audit sont automatiquement collectés au fur et à mesure de l’activité. Vous n’avez pas besoin d’activer manuellement la collecte des journaux.

Pour afficher et exporter les journaux d’audit, l’autorisation de contrôle d’accès **[!UICONTROL Accès aux journaux d’audit]** doit avoir été accordée dans Adobe Console. Pour savoir comment gérer les autorisations individuelles pour les fonctionnalités de Customer Journey Analytics, reportez-vous à la section [documentation sur le contrôle d’accès](../admin/cja-access-control.md).

## Afficher le journal d’audit dans l’interface utilisateur

Dans Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Journaux d’audit]**.

Le journal d’audit pour aujourd’hui et hier s’affiche par défaut.

![journal d’audit](assets/audit_ui.png)

Vous pouvez sélectionner les colonnes visibles en accédant au sélecteur de colonnes en haut à droite.

## Afficher des informations sur les entrées de journal individuelles

Double-cliquez sur le bouton info (i) en regard d’une description.

![journal d’audit](assets/info-button-audit.png)

Les éléments suivants s’affichent :

* **[!UICONTROL Nom de l’action]**: L’action effectuée. Valeurs possibles :
   * API_REQUEST
   * APPROUVER
   * CREATE
   * DELETE
   * MODIFIER
   * EXPORTER
   * ORG_CHANGE
   * ACTUALISER
   * PARTAGER
   * TRANSFERT
   * UNAPPROBATION
   * UNSHARE
* **[!UICONTROL Date de création]**: Date et heure auxquelles l’action a été effectuée.
* **[!UICONTROL Description]**: Résumé de l’action.
* **[!UICONTROL Nom d’utilisateur]**: L’utilisateur qui a effectué l’action.
* **[!UICONTROL Email]**: Adresse électronique de l’utilisateur qui a effectué l’action.
* **[!UICONTROL Nom du composant]**: Composant sur lequel l’utilisateur a effectué une action.
* **[!UICONTROL Type de composant]**: Type de composant. Valeurs possibles :
   * ANNOTATION
   * AUDIENCE
   * CALCULATED_METRIC
   * CONNEXION
   * DATA_GROUP
   * DATA_VIEW
   * DATASET_STITCHING
   * DATE_RANGE
   * FEATURE_ACCESS
   * FILTRER
   * IMS_ORG
   * MOBILE
   * PROJET
   * RAPPORT
   * SCHEDULED_PROJECT
   * UTILISATEUR
   * USER_GROUP
* **[!UICONTROL Identifiant du composant]**: Identifiant du composant sur lequel l’utilisateur a effectué une action.
* **[!UICONTROL Identifiant de l’organisation IMS]**: L’identifiant IMS de l’organisation, au format `ABC123@AdobeOrg`.
* **[!UICONTROL Identifiant de journal]**: Identifiant unique identifiant cette entrée de journal.
* **[!UICONTROL Identifiant utilisateur]**: Identifiant unique identifiant l’utilisateur qui a effectué l’action.
* **[!UICONTROL Type d’utilisateur]**: Type d’authentification utilisé. Les valeurs valides sont les suivantes :
   * IMS
   * OKTA

### Filtrer des journaux d’audit

Sélectionnez l’icône en forme d’entonnoir (![filtre](assets/filter-icon.png)) pour afficher une liste de contrôles de filtre afin de limiter les résultats. Seuls les 1 000 derniers enregistrements sont affichés, quels que soient les différents filtres sélectionnés.

![filtres](assets/filters.png)

Les filtres suivants sont disponibles pour les événements d’audit dans l’interface utilisateur :

| Filtre | Description |
| --- | --- |
| [!UICONTROL Période] | Filtrez une autre période en sélectionnant une autre date ou une autre période en faisant glisser le curseur sur plusieurs dates. Par défaut, les dates d’aujourd’hui et d’hier sont sélectionnées. |
| [!UICONTROL Action] | Filtrez sur tout nom d’action répertorié ci-dessus. |
| [!UICONTROL Identifiant utilisateur] | Filtrez un utilisateur spécifique selon son identifiant utilisateur. L’identifiant utilisateur est accessible en sélectionnant le bouton info (i) en regard d’un nom d’utilisateur. |
| [!UICONTROL Adresse électronique] | Filtrez l’adresse électronique d’un utilisateur spécifique. Pour trouver l’adresse électronique, cliquez sur le bouton d’informations (i) en regard d’un nom d’utilisateur. |
| [!UICONTROL ID du composant] | Filtrez un identifiant de composant spécifique. L’ID du composant est accessible en sélectionnant le bouton d’informations (i) pour un composant désiré. |
| [!UICONTROL Type de composant] | Filtrez sur tout type de composant répertorié ci-dessus. |

{style="table-layout:auto"}

## Types d’événements capturés par les journaux d’audit

Le tableau ci-dessous présente les actions sur lesquelles les types de composant sont enregistrées par les journaux d’audit :

| Type de composant | Actions |
| --- | --- |
| [!UICONTROL Annotation] | <ul><li>Créer</li><li>Supprimer</li><li>Modifier</li></ul> |
| [!UICONTROL Audience] | <ul><li>API_Request</li><li>Créer</li><li>Supprimer</li><li>Modifier</li><li>Exporter</li><li>Actualiser</li></ul> |
| [!UICONTROL Mesure calculée] | <ul><li>API_Request</li><li>Créer</li><li>Supprimer</li><li>Modifier</li></ul> |
| [!UICONTROL Connexion] | <ul><li>API_Request</li><li>Créer</li><li>Supprimer</li><li>Modifier</li></ul> |
| [!UICONTROL Vue de données] | <ul><li>API_Request</li><li>Créer</li><li>Supprimer</li><li>Modifier</li></ul> |
| [!UICONTROL Période] | <ul><li>API_Request</li><li>Créer</li><li>Supprimer</li><li>Modifier</li></ul> |
| [!UICONTROL Filtrer] | <ul><li>API_Request</li><li>Créer</li><li>Supprimer</li><li>Modifier</li></ul> |
| [!UICONTROL Organisation IMS] | <ul><li>API_Request</li><li>Créer</li><li>Supprimer</li><li>Modifier</li></ul> |
| [!UICONTROL Projet] | <ul><li>API_Request</li><li>Créer</li><li>Supprimer</li><li>Modifier</li></ul> |
| [!UICONTROL Rapport] | <ul><li>API_Request</li></ul> |
| [!UICONTROL Projet planifié] | <ul><li>API_Request</li><li>Créer</li><li>Supprimer</li><li>Modifier</li></ul> |
| [!UICONTROL Utilisateur] | <ul><li>API_Request</li><li>Créer</li><li>Supprimer</li><li>Modifier</li></ul> |
| [!UICONTROL Groupe d’utilisateurs] | <ul><li>API_Request</li><li>Créer</li><li>Supprimer</li><li>Modifier</li></ul> |

{style="table-layout:auto"}

## Télécharger des journaux d’audit

Vous pouvez télécharger les journaux d’audit au format CSV ou JSON. Les filtres appliqués ou les colonnes sélectionnées sont répercutés dans les fichiers téléchargés.

1. Cliquez sur **[!UICONTROL Télécharger]** en haut à droite de l’écran.
1. Spécifiez le format.
1. Cliquez à nouveau sur **[!UICONTROL Télécharger]**.

## Gérer les journaux d’audit dans l’API

Toutes les actions que vous pouvez effectuer dans l’interface utilisateur peuvent également être effectuées à l’aide d’appels API. Voir [Document de référence de l’API Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) pour plus d’informations.
