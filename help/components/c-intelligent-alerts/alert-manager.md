---
description: Création, modification ou suppression des alertes.
title: Gestionnaire d’alertes (Analysis Workspace)
feature: Workspace Basics
role: User, Admin
source-git-commit: 640624ab017d8fc0e7b942c2f00c71cf255c4296
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 7%

---

# Gérer les alertes

Vous pouvez gérer les alertes existantes dans le gestionnaire d’alertes. Vous pouvez effectuer diverses tâches de gestion sur les alertes, telles que le balisage, le changement de nom, la suppression, etc.

La structure du gestionnaire d’alertes ressemble à celle du [gestionnaire de filtres](/help/components/filters/manage-filters.md) et du [ gestionnaire de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-manager.md).

## Créer des alertes

Pour créer des alertes à partir du gestionnaire d’alertes :

1. Sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Alertes]** pour accéder au gestionnaire d’alertes en Customer Journey Analytics.

   ![](assets/alert-manager.png)

1. Sélectionnez [!UICONTROL **Ajouter**] (ou [!UICONTROL **Créer une alerte**] si vous n’avez aucune alerte existante).

1. Passez à la section [Créer des alertes](/help/components/c-intelligent-alerts/alert-builder.md) pour plus d’informations sur la création d’alertes.

## Gérer les alertes existantes

Pour gérer les alertes existantes dans le gestionnaire d’alertes :

1. Sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Alertes]** pour accéder au gestionnaire d’alertes en Customer Journey Analytics.

   ![](assets/alert-manager.png)

1. Sélectionnez une ou plusieurs alertes à gérer.

   ![](assets/alert-manager-tasks.png)

1. Dans la barre d’actions, sélectionnez l’une des options suivantes :

   | Action | Fonction |
   |---------|----------|
   | [!UICONTROL **Balise**] | Appliquez une balise à une alerte. Vous pouvez ainsi organiser les alertes pour en faciliter l’utilisation. |
   | [!UICONTROL **Supprimer**] | Supprime l’alerte. |
   | [!UICONTROL **Renommer**] | Renomme l’alerte. |
   | [!UICONTROL **Approuver**] | Marquez l’alerte comme Approuvé. |
   | [!UICONTROL **Copier**] | Crée une copie (en double) de l’alerte. |
   | [!UICONTROL **Désactiver**] | Désactive une alerte actuellement activée. |
   | [!UICONTROL **Activer**] | Active une alerte actuellement désactivée. |
   | [!UICONTROL **Renouveler**] | Renouvelle la date d’expiration de l’alerte. Cela prolonge la date d’expiration d’un an à partir du jour où vous avez sélectionné cette option, quelle que soit la date d’expiration d’origine. |
   | [!UICONTROL **Exporter dans un fichier CSV**] | Exporte l’alerte dans un fichier .CSV. |

## Modification d’une alerte

Pour modifier une alerte existante :

1. Sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Alertes]** pour accéder au gestionnaire d’alertes dans Adobe Analytics.

   ![](assets/alert-manager.png)

1. Sélectionnez le nom de l&#39;alerte dans la colonne [!UICONTROL **Titre et description**].

1. Modifiez l’alerte selon vos besoins.

   Voici quelques-unes des actions que vous pouvez effectuer lors de la modification d’une alerte :

   * Ajouter des alertes à d’autres suites de rapports
   * Modifier le propriétaire
   * Mise à jour des filtres
   * Mettre à jour la date d’expiration

1. Modifiez l’alerte, puis sélectionnez [!UICONTROL **Enregistrer**].

## Configuration des colonnes

Vous pouvez paramétrer les informations affichées pour chaque alerte dans le Gestionnaire d&#39;alertes en configurant les colonnes qui s&#39;affichent.

Pour configurer les colonnes visibles dans le gestionnaire d’alertes :

1. Dans Adobe Analytics, sélectionnez l’onglet **[!UICONTROL Composants]**, puis sélectionnez **[!UICONTROL Alertes]**.

1. Dans le gestionnaire d’alertes, sélectionnez l’icône **Personnaliser les colonnes** ![ icône ](assets/customize-columns-icon.png), puis sélectionnez les colonnes à afficher dans le gestionnaire d’alertes.

   Les colonnes suivantes sont disponibles :

   | Titre de la colonne | Description |
   |---|---|
   | Titre et description | Ces valeurs sont fournies dans le Générateur d’alertes. Pour modifier le titre et la description, sélectionnez le lien du titre pour ouvrir le Générateur d’alertes. |
   | Favoris | Affiche des icônes d’étoile en regard de chaque alerte, ce qui vous permet de marquer les alertes comme favorites. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Type | Indique si l’alerte est une alerte de données Analytics ou une alerte d’utilisation de l’appel au serveur. |
   | Activé | Indique si l’alerte est actuellement activée ou désactivée. |
   | Suite de rapports | Indique dans quelle suite de rapports l’alerte a été enregistrée en dernier. |
   | Propriétaire | Indique qui possède l’alerte. En tant que non administrateur, vous ne pouvez afficher que les alertes que vous possédez ou celles qui ont été partagées avec vous. |
   | Balises | Affiche les balises qui ont été appliquées à l’alerte, soit par vous, soit par des personnes qui ont partagé l’alerte avec vous. |
   | Date d’expiration | Affiche la date et l’heure d’expiration de l’alerte. |
   | Date de modification | Indique la date de la dernière modification de l’alerte. |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

## Dépannage d’une alerte

Lors de la résolution des problèmes liés à une alerte, indiquez le numéro JID (ID d’instance de tâche) pour Adobe l’assistance. Le numéro JID se trouve au bas de la notification électronique d’alerte que vous avez reçue.

![Email d’alerte](assets/alerts-email.PNG)