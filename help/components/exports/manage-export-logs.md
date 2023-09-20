---
description: Gestion des journaux des exportations existantes
keywords: Analysis Workspace
title: Gestion des logs d’exportation
feature: Components
hide: true
hidefromtoc: true
source-git-commit: f070f998758cead3709f6c48412b22b29de00164
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 7%

---

# Gestion des logs d’exportation

{{select-package}}

Les journaux d’exportation fournissent des détails sur chaque exportation et sont générés chaque fois que des données Analysis Workspace sont exportées vers le cloud. (Pour plus d’informations sur la manière dont les données peuvent être exportées dans le cloud, voir [Exportation des données de Customer Journey Analytics dans le cloud](/help/analysis-workspace/export/export-cloud.md).)

Pour les exportations planifiées, les journaux reflètent les paramètres d’exportation tels qu’ils étaient lors de l’envoi du journal. Les journaux ne peuvent pas être supprimés.

## Filtrage et recherche de journaux

Pour trouver les informations dont vous avez besoin, vous pouvez filtrer la liste des logs ou rechercher un log.

### Filtrage de la liste des logs

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Journal**] .

1. Sélectionnez la variable **Filtrer** Icône

   ![Filtrer les informations](assets/export-log-filters.png)

   Vous pouvez filtrer selon les critères suivants :

   | Filtre | Description |
   |---------|----------|
   | [!UICONTROL **Type de compte**] | Type de compte auquel le journal est associé. Les types de compte suivants sont disponibles : <ul><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **SAS Azure**]</li><li>[!UICONTROL **RBAC Azure**]</li><li>[!UICONTROL **Snowflake**]</li><li>[!UICONTROL **Adobe Experience Manager**]</li></ul>. |
   | [!UICONTROL **Statut**] | État de l’exportation. Les statuts suivants sont disponibles : <ul><li>[!UICONTROL **En attente**]: une instance spécifique d&#39;un export a été démarrée mais n&#39;est pas encore terminée.<p>La réexécution d’une exportation dont l’état est En attente retarde le processus d’exportation.</p></li><li>[!UICONTROL **Terminé**]: une instance spécifique d’un export est en cours de traitement et est disponible dans le compte d’export.</li><li>[!UICONTROL **Échec**]<p>Les situations suivantes peuvent entraîner l’échec de l’exportation. Passez la souris sur l’état Échec pour afficher les détails sur l’échec. <ul><li>Expiration planifiée de l’exportation</li><li>Limite de ligne atteinte pour l’exportation planifiée </li></ul> </p></li></ul> |

   {style="table-layout:auto"}

### Recherche de journaux

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Journal**] .

1. Dans l’onglet de recherche, commencez à saisir les informations associées au journal que vous recherchez. Vous pouvez rechercher des données dans n’importe quelle colonne du tableau.

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->

## Modification d’un export

Vous pouvez éditer l&#39;export associé à un journal spécifique.

Cette option n’est pas disponible lors de la sélection de plusieurs journaux.

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Journaux**] , puis sélectionnez un journal.

   <!-- add screenshot? -->

1. Sélectionnez [!UICONTROL **Modifier**].

## Configuration des colonnes

Vous pouvez ajouter ou supprimer des colonnes sur le [!UICONTROL Journal] pour configurer les informations qui s’affichent.

Sélectionnez un en-tête de colonne pour trier les journaux en fonction de cette colonne. Par défaut, les logs sont triés par date et heure de début de l&#39;export.

Pour configurer les colonnes du [!UICONTROL Journal] tab :

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exportations**].

1. Sélectionnez la variable [!UICONTROL **Journal**] .

1. Sélectionnez la variable **Personnalisation du tableau** icon ![personnaliser le tableau](assets/customize-table-icon.png) dans le coin supérieur droit du [!UICONTROL Journal] page.

   Les colonnes suivantes sont disponibles :

   | Colonne disponible | Description |
   |---------|----------|
   | Nom de l’export | Nom de l’exportation. Les utilisateurs donnent un nom aux exportations lorsqu’ils les créent, comme décrit dans la section [Exportation des données de Customer Journey Analytics dans le cloud](/help/analysis-workspace/export/export-cloud.md). |
   | ID d’exportation | L’identifiant automatiquement attribué à l’exportation lors de sa création. <!-- True? --> |
   | ID d’instance | L’identifiant de l’instance du Customer Journey Analytics. <!-- True? --> |
   | Nom de la vue de données | Nom de la vue de données associée à l’exportation. Les utilisateurs peuvent sélectionner la vue de données lors de la création de l’exportation, comme décrit dans la section [Exportation des données de Customer Journey Analytics dans le cloud](/help/analysis-workspace/export/export-cloud.md). |
   | Nombre de fichiers | Le nombre de fichiers inclus dans l’exportation. |
   | Taille | Taille de l’exportation.<p>La taille du fichier est calculée avec une base de 1 024, qui est parfois représentée sous la forme de KIB et MIB. Si votre fournisseur de cloud calcule la taille avec une base de 1 000, il se peut que la taille affichée dans votre fournisseur de cloud soit légèrement différente de celle affichée ici.</p> |
   | Emplacement | Emplacement sur le compte où les données ont été exportées. |
   | Compte | Le compte sur lequel les données ont été exportées. |
   | État | État de l’exportation. Les états disponibles sont les suivants : [!UICONTROL En attente], [!UICONTROL Délivrés], et [!UICONTROL En échec]. |
   | Date de diffusion | Date à laquelle l’exportation a eu lieu. |
   | Type de compte | Type de compte cloud sur lequel les données ont été exportées. Les types de compte disponibles sont [!UICONTROL APERÇU du rôle Amazon S3], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake], et [!UICONTROL Adobe Experience Platform]. |
   | Nombre de lignes | Nombre de lignes incluses dans le tableau exporté. |

   {style="table-layout:auto"}

1. Assurez-vous que toutes les colonnes à afficher sont sélectionnées. Les colonnes sélectionnées s’affichent sur la [!UICONTROL Journal] et afficher les informations pertinentes.

## Afficher les journaux d’audit

Les exportations en tableau complet sont également suivies dans la variable [Journaux d’audit des Customer Journey Analytics](/help/privacy/audit-log.md). <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->