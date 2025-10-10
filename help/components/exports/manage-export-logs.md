---
description: Gérer les journaux pour les exportations existantes
keywords: Analysis Workspace
title: Gérer les journaux d’export
feature: Components
exl-id: 6d676a0a-b117-421e-9a90-8c550f08d474
role: User
source-git-commit: ad43b199d4174894f0e428bcaf1748ca80bddb45
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 8%

---

# Gérer les journaux d’export

Les journaux d’exportation fournissent des détails sur chaque exportation et sont générés chaque fois que des données Analysis Workspace sont exportées vers le cloud. (Pour plus d’informations sur la manière dont les données peuvent être exportées vers le cloud, voir [ Exporter des rapports Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md).)

Pour les exportations planifiées, les journaux reflètent les paramètres d’exportation tels qu’ils étaient lorsque le journal a été envoyé. Les journaux ne peuvent pas être supprimés.

## Afficher les journaux d’exportation

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Journaux**].

   ![Fenêtre Exporter affichant l’onglet Logs](assets/export-logs-tab.png)

   Les détails de chaque journal s’affichent dans les colonnes disponibles.

1. Effectuez l’une des opérations suivantes :

   * [Personnaliser les colonnes](#configure-columns) affichées.

   * Sélectionnez l’icône **Informations** ![Informations](assets/information-icon.png) en regard du nom du journal pour afficher l’exportation associée au journal.

   * Sélectionnez l’icône **Modifier l’icône d’exportation** ![Icône d’information](assets/edit-export-icon.png) en regard du nom du journal pour modifier l’exportation associée au journal.

     Pour plus d’informations sur la modification d’une exportation, voir [Exporter des rapports Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md).

## Filtrer et rechercher des journaux

Pour trouver les informations dont vous avez besoin, vous pouvez filtrer la liste des journaux ou rechercher un journal.

### Filtrer la liste des logs

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Journaux**].

1. Sélectionnez l’icône **Filtrer**.

   ![Fenêtre Exports affichant la liste Filtrer par type de compte](assets/export-log-filters.png)

   Vous pouvez filtrer selon les critères suivants :

   | Filtre | Description |
   |---------|----------|
   | [!UICONTROL **ID d’exportation**] | Indiquez l’ID d’exportation du journal d’exportation à afficher. |
   | [!UICONTROL **Type de compte**] | Type de compte auquel le journal est associé. Les types de compte disponibles sont les suivants : <ul><li>[!UICONTROL **Zone de destination des données AEP**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **RBAC Azure**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Statut**] | Statut de l’exportation. Les statuts suivants sont disponibles : <ul><li>[!UICONTROL **En attente**] : une instance spécifique d’une exportation a été démarrée, mais n’est pas encore terminée.<p>La réexécution d’une exportation dont le statut est En attente retarde le processus d’exportation.</p></li><li>[!UICONTROL **Terminé**] : le traitement d’une instance spécifique d’une exportation est terminé et elle est disponible dans le compte d’exportation.</li><li>[!UICONTROL **Échec**]<p>Plusieurs situations peuvent entraîner l’échec d’une exportation. Passez la souris sur le statut En échec pour afficher les détails de l’échec.<p>Pour plus d’informations sur les raisons possibles d’un échec, voir [Dépannage des exportations ayant échoué](/help/components/exports/troubleshoot-exports.md).</p> |

   {style="table-layout:auto"}

### Rechercher des journaux

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Journaux**].

1. Dans le champ de recherche, commencez à saisir toutes les informations associées au journal que vous recherchez. Vous pouvez rechercher des données à partir de n’importe quelle colonne disponible dans le tableau.

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->

## Modification d’un export

Vous pouvez modifier l’exportation associée à un journal spécifique.

Cette option n’est pas disponible lors de la sélection de plusieurs journaux.

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Journaux**].

1. Recherchez le journal associé à l’exportation que vous souhaitez modifier.

1. Sélectionnez l’icône **Modifier l’exportation** ![icône du journal d’exportation](assets/export-icon.png) en regard du nom du journal.

   Ou

   Cochez la case en regard du journal, puis sélectionnez [!UICONTROL **Modifier l’exportation**].

## Configurer les colonnes

Vous pouvez ajouter ou supprimer des colonnes sur l’onglet [!UICONTROL Journaux] pour configurer les informations affichées.

Sélectionnez un en-tête de colonne pour trier les journaux en fonction de cette colonne. Par défaut, les journaux sont triés par date et heure de début de l’exportation.

Pour configurer les colonnes de l’onglet [!UICONTROL Journaux] :

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Journaux**].

1. Sélectionnez l’icône **Personnaliser le tableau** ![Personnaliser le tableau](assets/customize-table-icon.png) dans le coin supérieur droit de la page [!UICONTROL Journaux].

   Les colonnes suivantes sont disponibles :

   | Colonne disponible | Description |
   |---------|----------|
   | Nom de l’export | Nom de l’exportation. Les utilisateurs nomment les exports au moment de leur création, comme décrit dans la section [Exporter des rapports Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md). |
   | ID d’exportation | ID automatiquement attribué à l’exportation lors de sa création. <!-- True? --> |
   | ID d’instance | Identifiant de l’instance Customer Journey Analytics. <!-- True? --> |
   | Nom de la vue de données | Nom de la vue de données associée à l’exportation. Les utilisateurs peuvent sélectionner la vue de données lors de la création de l’exportation, comme décrit dans la section [Exporter des rapports Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md). |
   | Nombre de fichiers | Nombre de fichiers inclus dans l’exportation. |
   | Taille | Taille de l’exportation.<p>La taille de fichier est calculée avec une base de 1 024, qui est parfois représentée par KIB et MIB. Si votre fournisseur de cloud calcule la taille avec une base de 1 000, il se peut que la taille affichée dans votre fournisseur de cloud soit légèrement différente de celle affichée ici.</p> |
   | Emplacement | Emplacement sur le compte où les données ont été exportées. |
   | Compte | Compte sur lequel les données ont été exportées. |
   | État | Statut de l’exportation. Les statuts disponibles sont [!UICONTROL En attente], [!UICONTROL Diffusé] et [!UICONTROL Échec]. |
   | Date de diffusion | Date à laquelle l’exportation a eu lieu. |
   | Type de compte | Type de compte cloud sur lequel les données ont été exportées. Les types de compte disponibles sont les suivants : [!UICONTROL ARN du rôle Amazon S3] [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake] et [!UICONTROL Adobe Experience Platform]. |
   | Nombre de lignes | Nombre de lignes incluses dans le tableau exporté. |

   {style="table-layout:auto"}

1. Assurez-vous que toutes les colonnes que vous souhaitez afficher sont sélectionnées. Les colonnes sélectionnées s’affichent sur la page [!UICONTROL Journaux] et affichent les informations pertinentes.

## Afficher les journaux d’audit

Les exportations de table complète sont également suivies dans les journaux d’audit [Customer Journey Analytics](/help/privacy/audit-log.md). <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->
