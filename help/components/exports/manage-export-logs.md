---
description: Gestion des journaux des exportations existantes
keywords: Analysis Workspace
title: Gérer les journaux d’export
feature: Components
exl-id: 6d676a0a-b117-421e-9a90-8c550f08d474
role: User
source-git-commit: ad43b199d4174894f0e428bcaf1748ca80bddb45
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 5%

---

# Gérer les journaux d’export

Les journaux d’exportation fournissent des détails sur chaque exportation et sont générés chaque fois que des données Analysis Workspace sont exportées vers le cloud. (Pour plus d’informations sur la manière dont les données peuvent être exportées vers le cloud, voir [Export des rapports de Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md).)

Pour les exportations planifiées, les journaux reflètent les paramètres d’exportation tels qu’ils étaient lors de l’envoi du journal. Les journaux ne peuvent pas être supprimés.

## Afficher les journaux d’exportation

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Logs**] .

   ![Fenêtre d’exportation affichant l’onglet Journaux](assets/export-logs-tab.png)

   Les détails de chaque journal sont affichés dans les colonnes disponibles.

1. Effectuez l’une des opérations suivantes :

   * [Personnalisez les colonnes affichées](#configure-columns).

   * Sélectionnez l’ **icône d’informations** ![ icône d’informations](assets/information-icon.png) en regard du nom du journal pour afficher l’exportation associée au journal.

   * Sélectionnez l’ **icône Modifier l’exportation** ![icône d’information](assets/edit-export-icon.png) en regard du nom du journal pour modifier l’exportation associée au journal.

     Pour plus d’informations sur la modification d’une exportation, voir [Export des rapports de Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md).

## Filtrage et recherche de journaux

Pour trouver les informations dont vous avez besoin, vous pouvez filtrer la liste des logs ou rechercher un log.

### Filtrage de la liste des logs

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Logs**] .

1. Sélectionnez l&#39;icône **Filtre** .

   ![Fenêtre Exportations présentant la liste Filtrer par type de compte](assets/export-log-filters.png)

   Vous pouvez filtrer selon les critères suivants :

   | Filtre | Description |
   |---------|----------|
   | [!UICONTROL **Export ID**] | Indiquez l’ID d’exportation du journal d’exportation que vous souhaitez afficher. |
   | [!UICONTROL **Type de compte**] | Type de compte auquel le journal est associé. Les types de compte suivants sont disponibles : <ul><li>[!UICONTROL **Zone d’entrée de données AEP**]</li><li>[!UICONTROL **{Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Plateforme cloud Google**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Statut**] | État de l’exportation. Les statuts suivants sont disponibles : <ul><li>[!UICONTROL **En attente**] : une instance spécifique d&#39;un export a été démarrée mais n&#39;est pas encore terminée.<p>La réexécution d’une exportation dont l’état est En attente retarde le processus d’exportation.</p></li><li>[!UICONTROL **Completed**] : une instance spécifique d’un export est en cours de traitement et est disponible dans le compte d’export.</li><li>[!UICONTROL **Échec**]<p>Différentes situations peuvent entraîner l’échec de l’exportation. Passez la souris sur l’état Échec pour afficher les détails sur l’échec.<p>Pour plus d’informations sur les raisons possibles d’un échec, voir [Dépannage des exports ayant échoué](/help/components/exports/troubleshoot-exports.md).</p> |

   {style="table-layout:auto"}

### Recherche de journaux

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Logs**] .

1. Dans le champ de recherche, commencez à saisir les informations associées au journal que vous recherchez. Vous pouvez rechercher des données dans n’importe quelle colonne du tableau.

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->

## Modification d’un export

Vous pouvez éditer l&#39;export associé à un journal spécifique.

Cette option n’est pas disponible lors de la sélection de plusieurs journaux.

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Logs**] .

1. Localisez le journal associé à l’exportation que vous souhaitez modifier.

1. Sélectionnez l&#39;icône **Modifier l&#39;export** ![icône exporter le journal](assets/export-icon.png) en regard du nom du journal.

   Ou

   Cochez la case en regard du journal, puis sélectionnez [!UICONTROL **Modifier l’exportation**].

## Configuration des colonnes

Vous pouvez ajouter ou supprimer des colonnes dans l’onglet [!UICONTROL Journaux] pour configurer les informations affichées.

Sélectionnez un en-tête de colonne pour trier les journaux en fonction de cette colonne. Par défaut, les logs sont triés par date et heure de début de l&#39;export.

Pour configurer des colonnes sur l’onglet [!UICONTROL Logs] :

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Logs**] .

1. Sélectionnez l&#39;icône **Personnaliser la table** ![ ](assets/customize-table-icon.png) dans le coin supérieur droit de la page [!UICONTROL Journaux].

   Les colonnes suivantes sont disponibles :

   | Colonne disponible | Description |
   |---------|----------|
   | Nom de l’export | Nom de l’exportation. Les utilisateurs donnent un nom aux exportations lorsqu’ils les créent, comme décrit dans la section [Exporter les rapports des Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md). |
   | ID d’exportation | L’identifiant automatiquement attribué à l’exportation lors de sa création. <!-- True? --> |
   | ID d’instance | L’identifiant de l’instance du Customer Journey Analytics. <!-- True? --> |
   | Nom de la vue de données | Nom de la vue de données associée à l’exportation. Les utilisateurs peuvent sélectionner la vue de données lors de la création de l’exportation, comme décrit dans la section [Exporter les rapports du Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md). |
   | Nombre de fichiers | Le nombre de fichiers inclus dans l’exportation. |
   | Taille | Taille de l’exportation.<p>La taille du fichier est calculée avec une base de 1 024, qui est parfois représentée sous la forme de KIB et MIB. Si votre fournisseur de cloud calcule la taille avec une base de 1 000, il se peut que la taille affichée dans votre fournisseur de cloud soit légèrement différente de celle affichée ici.</p> |
   | Emplacement | Emplacement sur le compte où les données ont été exportées. |
   | Compte | Le compte sur lequel les données ont été exportées. |
   | État | État de l’exportation. Les états disponibles sont [!UICONTROL En attente], [!UICONTROL Délivrés] et [!UICONTROL Échec]. |
   | Date de diffusion | Date à laquelle l’exportation a eu lieu. |
   | Type de compte | Type de compte cloud sur lequel les données ont été exportées. Les types de compte disponibles sont [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake] et [!UICONTROL Adobe Experience Platform]. |
   | Nombre de lignes | Nombre de lignes incluses dans le tableau exporté. |

   {style="table-layout:auto"}

1. Assurez-vous que toutes les colonnes à afficher sont sélectionnées. Les colonnes sélectionnées apparaissent sur la page [!UICONTROL Journaux] et affichent les informations pertinentes.

## Afficher les journaux d’audit

Les exportations de tables complètes sont également suivies dans les [journaux d’audit de Customer Journey Analytics](/help/privacy/audit-log.md). <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->
