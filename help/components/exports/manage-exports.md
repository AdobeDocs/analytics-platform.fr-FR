---
description: Gestion des exportations existantes
keywords: Analysis Workspace
title: Gérer des exports
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
role: User
source-git-commit: 6f8a43acfba23d6faeff078873742315f1506699
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 4%

---

# Gérer des exports

Après avoir exporté une table complète comme décrit dans [Export Customer Journey Analytics reports to the cloud](/help/analysis-workspace/export/export-cloud.md), les exportations sont disponibles sur l’onglet [!UICONTROL Exports] de la page [!UICONTROL Exports].

Vous ne pouvez afficher que les exportations que vous créez.

## Filtrer et rechercher des exportations

Pour trouver les informations dont vous avez besoin, vous pouvez filtrer la liste des exports ou rechercher une exportation.

### Filtrer la liste des exports

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l&#39;onglet [!UICONTROL **Exports**] .

1. Sélectionnez l&#39;icône **Filtre** .

   <!--add screenshot -->

   Vous pouvez filtrer selon les critères suivants :

   | Filtre | Description |
   |---------|----------|
   | [!UICONTROL **Type de compte**] | Type de compte auquel l’exportation est associée. Les types de compte suivants sont disponibles : <ul><li>[!UICONTROL **Zone d’entrée de données AEP**]</li><li>[!UICONTROL **&lbrace;Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Plateforme cloud Google**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Statut**] | État de l’exportation. Les statuts suivants sont disponibles : <ul><li>[!UICONTROL **Actif**] : indique qu’une exportation planifiée n’a pas encore expiré ou qu’une exportation ponctuelle n’est pas encore terminée. </li><li>[!UICONTROL **Completed**] : indique qu’une exportation a réussi. Pour les exports planifiés, cela indique que le planning a expiré.</li><li>[!UICONTROL **Échec**]<p>Les situations suivantes peuvent entraîner l’échec de l’exportation. Passez la souris sur l’état [!UICONTROL **Failed**] pour afficher des informations détaillées sur l’échec. <ul><li>Expiration planifiée de l’exportation</li><li>Limite de ligne atteinte pour l’exportation planifiée </li></ul> </p></li></ul> |
   | [!UICONTROL **Fréquence**] | Fréquence de l’exportation. Les fréquences disponibles sont les suivantes : <ul><li>[!UICONTROL **Une fois**]</li><li>[!UICONTROL **Quotidien**]</li><li>[!UICONTROL **Hebdomadaire**]</li><li>[!UICONTROL **Mensuel**]</li><li>[!UICONTROL **Annuel**]</li></ul> |

   {style="table-layout:auto"}

### Recherche d’exportations

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l&#39;onglet [!UICONTROL **Exports**] .

1. Dans le champ de recherche, commencez à saisir les informations associées à l’exportation que vous recherchez. Vous pouvez rechercher des données dans n’importe quelle colonne du tableau.

## Modification d’un export

Vous pouvez modifier les propriétés, le format, la planification et les informations d’emplacement d’une exportation.

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Dans l’onglet [!UICONTROL **Exports**], cochez la case en regard de l’exportation que vous souhaitez modifier.

   Cette option n’est pas disponible lors de la sélection de plusieurs exports.

1. Sélectionnez [!UICONTROL **Modifier**].

   La boîte de dialogue [!UICONTROL **Exporter la table complète**] s’affiche.

1. Mettez à jour l’une des options disponibles. Pour plus d’informations sur chaque option, voir [Exporter des tables complètes à partir d’Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) dans [Exporter des rapports de Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md).

## Duplication d&#39;un export

Vous pouvez dupliquer une exportation existante.

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Dans l’onglet [!UICONTROL **Exports**], cochez la case en regard de l’exportation que vous souhaitez dupliquer.

   Cette option n’est pas disponible lors de la sélection de plusieurs exports.

1. Sélectionnez [!UICONTROL **Dupliquer**].

   Un doublon de l&#39;export est alors créé. Le nom de la nouvelle exportation correspond au nom de l’exportation d’origine, _[!UICONTROL - Copie]_ ajouté au nom du fichier.

1. (Facultatif) [Modifiez la nouvelle exportation](#edit-an-export), y compris le nom de fichier et toute autre propriété que vous souhaitez modifier.

## Lancement manuel d’une exportation

Vous pouvez lancer manuellement une exportation, soit pour une exportation planifiée, soit pour une exportation ponctuelle précédemment terminée.

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Dans l’onglet [!UICONTROL **Exports**], cochez la case en regard de l’exportation que vous souhaitez exécuter.

   Cette option n’est pas disponible lors de la sélection de plusieurs exports.

1. Sélectionnez [!UICONTROL **Exporter maintenant**].

## Balisage d’un export

Lorsque vous appliquez des balises à une exportation, vous pouvez les afficher dans la colonne [!UICONTROL Balises] de la page [!UICONTROL Exports]. Pour plus d’informations, voir [Configuration des colonnes](#configure-columns) .

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Dans l’onglet [!UICONTROL **Exports**], cochez la case en regard d’un ou plusieurs exports que vous souhaitez baliser.

1. Sélectionnez [!UICONTROL **Modifier les balises**].

1. Dans la boîte de dialogue [!UICONTROL **Tag export**], saisissez le nom d’une balise pour créer une balise ou choisissez une balise existante dans le menu déroulant.

   Toutes les balises courantes entre les exportations sélectionnées s’affichent dans la boîte de dialogue des balises. <!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. Sélectionnez [!UICONTROL **Appliquer les balises**].

## Suppression d’un export

Vous pouvez supprimer des exportations de la page Exports . Les exports planifiés supprimés ne seront plus envoyés.

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Dans l’onglet [!UICONTROL **Exports**], cochez la case en regard d’un ou plusieurs exports que vous souhaitez supprimer.

1. Sélectionnez [!UICONTROL **Supprimer**], puis [!UICONTROL **Supprimer**] lorsque le message de confirmation s’affiche.

## Configurer des colonnes sur la page [!UICONTROL Exports]

Vous pouvez ajouter ou supprimer des colonnes dans l&#39;onglet [!UICONTROL Exports] pour configurer les informations affichées.

Sélectionnez un en-tête de colonne pour trier les exports selon cette colonne. Par défaut, les exports sont triés par date et heure de la dernière modification de l’exportation.

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Dans l&#39;onglet [!UICONTROL **Exports**], sélectionnez l&#39;icône **Personnaliser la table** ![Personnaliser la table](assets/customize-table-icon.png) dans le coin supérieur droit de la page [!UICONTROL Exports].

   Les colonnes suivantes sont disponibles :

   | Colonne disponible | Description |
   |---------|----------|
   | Nom | Nom de l’exportation. Les utilisateurs donnent un nom aux exportations lorsqu’ils les créent, comme décrit dans la section [Exporter les rapports des Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md). |
   | ID | L’identifiant automatiquement attribué à l’exportation lors de sa création. <!-- True? --> |
   | Nom de la vue de données | Nom de la vue de données associée à l’exportation. Les utilisateurs peuvent sélectionner la vue de données lors de la création de l’exportation, comme décrit dans la section [Exporter les rapports du Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md). |
   | État | État de l’exportation. Les états disponibles sont [!UICONTROL Actif], [!UICONTROL Terminé] et [!UICONTROL Échec].<p> **Remarque :** Pour plus d’informations sur la résolution des problèmes d’exportation ayant échoué, voir [ Résolution des problèmes d’exportation ayant échoué ](/help/components/exports/troubleshoot-exports.md).</p> |
   | Balises | Affiche toutes les balises appliquées à l’exportation. Pour plus d’informations sur l’application de balises à un export, voir [Balisage d’un export](#tag-an-export). |
   | Taille du tableau (dernier envoi) | Taille de l’exportation la dernière fois qu’elle a été envoyée. |
   | Créé par | L’utilisateur qui a créé l’exportation. |
   | Créé | Date et heure de création de l’exportation. <!-- true? --> |
   | Emplacement | Emplacement sur le compte où les données ont été exportées. |
   | Compte | Le compte sur lequel les données ont été exportées. |
   | Fréquence | Fréquence d&#39;envoi de l&#39;export. Les options disponibles sont [!UICONTROL Une fois], [!UICONTROL Quotidien], [!UICONTROL Hebdomadaire], [!UICONTROL Mensuellement par jour de la semaine], [!UICONTROL Mensuellement par jour du mois], [!UICONTROL Annuellement par jour du mois] et [!UICONTROL Annuellement par date spécifique]. |
   | Heure d’envoi | Heure à laquelle l’exportation a été envoyée. |
   | Dernier envoi | Dernière fois que l’exportation a été envoyée. |
   | Dernière modification | Dernière modification de l’exportation. Les éléments de la page Exports sont triés par défaut par cette colonne. |
   | Type de compte | Type de compte cloud sur lequel les données ont été exportées. Les types de compte disponibles sont [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake] et [!UICONTROL Adobe Experience Platform]. |

   {style="table-layout:auto"}

1. Assurez-vous que toutes les colonnes à afficher sont sélectionnées. Les colonnes sélectionnées apparaissent sur la page Exports et affichent les informations pertinentes.
