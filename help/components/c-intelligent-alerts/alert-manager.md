---
description: Création, modification ou suppression des alertes.
title: Gérer les alertes
feature: Workspace Basics
role: User, Admin
source-git-commit: 6a279ac39e6b94200ff93ac1a3796d202e6349c7
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 7%

---

# Gérer les alertes


Vous pouvez filtrer, baliser, supprimer, renommer, copier, activer, désactiver le renouvellement et exporter des alertes à partir d’une interface de gestion centralisée des [!UICONTROL alertes]. Pour gérer des alertes :

* Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis **[!UICONTROL Alertes]**.

La structure du gestionnaire d’alertes ressemble à celle du [gestionnaire de filtres](/help/components/filters/manage-filters.md) et du [gestionnaire de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-manager.md).


## Gestionnaire d’alertes

Le gestionnaire d’alertes comprend les éléments suivants :

![Interface des filtres](assets/alerts-manager.png)

### Liste des alertes

La liste d’alertes affiche toutes les alertes que vous possédez, les alertes qui ont été incluses dans tous vos projets et les alertes qui ont été partagées avec vous. La liste contient les colonnes suivantes :

| Colonne | Description |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Sélectionnez pour favoriser ![Star](/help/assets/icons/Star.svg) ou pour annuler ![StarOutline](/help/assets/icons/StarOutline.svg) avec une alerte. |
| **[!UICONTROL Titre et description]** | Pour modifier l’alerte, sélectionnez le lien de titre qui ouvre le [créateur d’alertes](alert-builder.md#alert-builder). |
| **[!UICONTROL Type]** | Indique si l’alerte est une alerte de données de Customer Journey Analytics ou une alerte d’utilisation de l’appel au serveur. |
| **[!UICONTROL Activé]** | Indique si l’alerte est activée ou désactivée. |
| **[!UICONTROL Vue de données]** | Les vues de données auxquelles cette alerte s’applique. |
| **[!UICONTROL Propriétaire]** | Propriétaire de l’alerte. En tant que non administrateur, vous ne voyez que les alertes que vous possédez ou celles qui sont partagées avec vous. |
| **[!UICONTROL Balises]** | Les balises de cette alerte. |
| **[!UICONTROL Date d’expiration]** | Date et heure d’expiration de l’alerte. |
| **[!UICONTROL Date de modification]** | Date et heure de la dernière modification de l’alerte. |

<!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour spécifier les colonnes à afficher.

### Barre d’actions

Vous pouvez agir sur les alertes à l’aide de la barre d’actions. La barre d’actions contient les actions suivantes :

| Icône | Action | Description |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Ajouter]** | Ajoutez une autre alerte à l’aide du [Générateur d’alertes](alert-builder.md#alert-builder). |
| ![Recherche](/help/assets/icons/Search.svg) | [!UICONTROL *Recherche par titre*] | Lorsqu’aucune alerte n’est sélectionnée dans la liste, recherchez des alertes dans ce champ de recherche. |
| ![Maison de disques](/help/assets/icons/Label.svg) | **[!UICONTROL Balise]** | Marquez les alertes sélectionnées. Dans la boîte de dialogue **[!UICONTROL Tag Alert]**, sélectionnez ou désélectionnez les balises des alertes sélectionnées. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les balises des alertes sélectionnées. |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimer les alertes sélectionnées. Vous êtes invité à faire une confirmation. |
| ![Modifier](/help/assets/icons/Edit.svg) | **[!UICONTROL Renommer]** | Renommez une alerte sélectionnée. Lorsque cette option est sélectionnée, vous pouvez renommer l’alerte intégrée. |
| ![Copier](/help/assets/icons/Copy.svg) | **[!UICONTROL Copier]** | Copiez l’alerte sélectionnée. De nouvelles alertes sont créées avec le même nom et le même suffixe `(Copy)`. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Activer]** ou **[!UICONTROL Désactiver]** | Activez ou désactivez les alertes sélectionnées. |
| ![Actualiser](/help/assets/icons/Refresh.svg) | **[!UICONTROL Renouveler]** | Renouvelle la date d’expiration de l’alerte. La date d’expiration s’étend sur 1 an à partir du jour où vous sélectionnez cette option, quelle que soit la date d’expiration d’origine. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exporter dans un fichier CSV]** | Exportez les alertes dans un fichier `Alerts List.csv`. |


### Barre de filtres active

La barre de filtrage affiche les filtres actifs appliqués du panneau des alertes à la liste des alertes (le cas échéant). Vous pouvez supprimer rapidement un filtre à l’aide de ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si plusieurs filtres sont spécifiés, vous pouvez les supprimer à l’aide de **[!UICONTROL Tout supprimer]**.


### Panneau Filtrer

Vous pouvez filtrer la liste des alertes à l’aide du panneau de gauche ![Filtre](/help/assets/icons/Filter.svg) **[!UICONTROL 3}.]** Le panneau Filtre affiche le type de filtre et le nombre d’alertes correspondant au filtre spécifique.

{{filterspanel}}


#### Section de filtrage des balises

{{tagfiltersection}}


#### Section Filtre de vue de données

{{dataviewfiltersection}}


#### Section Filtre des propriétaires

{{ownerfiltersection}}


#### Section Filtre d’état activé

{{enabledstatusfiltersection}}


#### Section Filtre de type

{{typefiltersection}}


#### Section Autres filtres

{{otherfiltersfiltersection}}



## Modifier des alertes

Vous pouvez modifier une alerte

* Dans la liste [[!UICONTROL Alerte]](#alerts-list), sélectionnez le titre de l’alerte.

Vous utilisez le [Générateur d’alertes](alert-builder.md#alert-builder) pour modifier l’alerte.

## Dépannage d’une alerte

Lors de la résolution des problèmes liés à une alerte, indiquez le numéro JID (ID d’instance de tâche) pour Adobe l’assistance. Le numéro JID se trouve au bas de la notification par e-mail de l’alerte que vous recevez.

![Email d’alerte](assets/alerts-email.PNG)
