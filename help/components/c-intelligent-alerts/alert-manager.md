---
description: Découvrez comment gérer les alertes.
title: Gérer les alertes
feature: Workspace Basics
role: User, Admin
exl-id: 174c3ebd-a77b-4403-ae9a-bb0cff4bcca6
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 22%

---

# Gérer les alertes


Vous pouvez filtrer, baliser, supprimer, renommer, copier, activer, désactiver, renouveler et exporter des alertes à partir d’une interface de gestion centrale [!UICONTROL Alertes]. Pour gérer des alertes :

* Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis sélectionnez **[!UICONTROL Alertes]**.

La structure du gestionnaire d’alertes est similaire à celle du [gestionnaire de segments](/help/components/segments/seg-manage.md) et du [gestionnaire de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-manager.md).


## Gestionnaire d’alertes

Le gestionnaire d’alertes comporte les éléments d’interface suivants :

![Interface des filtres](assets/alerts-manager.png)

### Liste des alertes

La liste des alertes affiche ➊ toutes les alertes que vous possédez, celles qui ont été incluses dans tous vos projets et celles qui ont été partagées avec vous. La liste comporte les colonnes suivantes :

| Colonne | Description |
|---|---|
| ![Contour en forme d’étoile](/help/assets/icons/StarOutline.svg) | Sélectionnez pour favoriser ![Étoile](/help/assets/icons/Star.svg) ou ne pas favoriser ![ÉtoileContour](/help/assets/icons/StarOutline.svg) une alerte. |
| **[!UICONTROL Titre et description]** | Pour modifier l’alerte, cliquez sur le lien du titre, qui ouvre le [créateur d’alertes](alert-builder.md#alert-builder). |
| **[!UICONTROL Type]** | Indique si l’alerte est une alerte de données Customer Journey Analytics ou une alerte d’utilisation de l’appel au serveur. |
| **[!UICONTROL Activé]** | Indique si l’alerte est activée ou désactivée. |
| **[!UICONTROL Vue de données]** | Vues de données auxquelles cette alerte s’applique. |
| **[!UICONTROL Propriétaire]** | Propriétaire de l’alerte. En tant que non-administrateur, vous ne voyez que les alertes que vous possédez ou celles qui sont partagées avec vous. |
| **[!UICONTROL Balises]** | Balises pour cette alerte. |
| **[!UICONTROL Date d’expiration]** | Date et heure d’expiration de l’alerte. |
| **[!UICONTROL Date de modification]** | Date et heure de la dernière modification de l’alerte. |

<!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

Utilisez ![Paramètres de colonne](/help/assets/icons/ColumnSetting.svg) pour spécifier les colonnes à afficher.

### Barre d’actions

Vous pouvez agir sur les alertes à l’aide de la barre d’actions ➋. La barre d’actions contient les actions suivantes :

| Icône | Action | Description |
|:---:|---|---|
| ![Cercle d’ajout](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Ajouter]** | Ajoutez une autre alerte à l’aide du [créateur d’alertes](alert-builder.md#alert-builder). |
| ![Recherche](/help/assets/icons/Search.svg) | [!UICONTROL *Rechercher par titre*] | Lorsqu’aucune alerte n’est sélectionnée dans la liste, recherchez des alertes à l’aide de ce champ de recherche. |
| ![Libellé](/help/assets/icons/Label.svg) | **[!UICONTROL Étiquette]** | Balisez les alertes sélectionnées. Dans la boîte de dialogue **[!UICONTROL Alerte de balise]**, sélectionnez ou désélectionnez les balises pour les alertes sélectionnées. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les balises des alertes sélectionnées. |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimez les alertes sélectionnées. Il vous est demandé de confirmer. |
| ![Modifier](/help/assets/icons/Edit.svg) | **[!UICONTROL Renommer]** | Renommez une alerte sélectionnée. Lorsque cette option est sélectionnée, vous pouvez renommer l’alerte en ligne. |
| ![Copier](/help/assets/icons/Copy.svg) | **[!UICONTROL Copier]** | Copiez l’alerte sélectionnée. De nouvelles alertes sont créées avec le même nom et le même suffixe `(Copy)`. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL activer]** ou **[!UICONTROL désactiver]** | Activer ou désactiver les alertes sélectionnées. |
| ![Actualiser](/help/assets/icons/Refresh.svg) | **[!UICONTROL Renouveler]** | Renouvelle la date d’expiration d’une alerte. La date d’expiration s’étend sur 1 an à compter du jour où vous sélectionnez cette option, quelle que soit la date d’expiration d’origine. |
| ![Fichier CSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exporter dans un fichier CSV]** | Exportez les alertes dans un fichier `Alerts List.csv`. |


### Barre de filtres actifs

La barre de filtrage affiche ➌ les filtres actifs appliqués à partir du panneau de filtrage à la liste des alertes (le cas échéant). Vous pouvez supprimer rapidement un filtre à l’aide de ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si plusieurs filtres sont spécifiés, vous pouvez tous les supprimer à l’aide de **[!UICONTROL Tout supprimer]**.


### Panneau Filtrer

Vous pouvez filtrer la liste des alertes à l’aide du ![ du panneau de gauche ](/help/assets/icons/Filter.svg)Filtrer **** Filtrer➍. Le panneau de filtrage affiche le type de filtre et le nombre d’alertes qui respectent le filtre spécifique.


1. Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) pour ouvrir le panneau Filtres. Si vous avez besoin de plus d’espace pour la liste des alertes, vous pouvez sélectionner ![Filtrer](/help/assets/icons/Filter.svg) une fois de plus pour fermer le panneau.
1. Sélectionnez des filtres dans l’une des sections de filtres disponibles.


#### Section de filtrage des balises

{{tagfiltersection}}


#### Section Filtre de la vue de données

{{dataviewfiltersection}}


#### Section de filtre des propriétaires

{{ownerfiltersection}}


#### Section Filtre de statut activé

{{enabledstatusfiltersection}}


#### Section de filtre de type

{{typefiltersection}}


#### Section des autres filtres

{{otherfiltersfiltersection}}



## Modifier les alertes

Vous pouvez modifier une alerte.

* Dans la liste [[!UICONTROL Alerte]](#alerts-list), sélectionnez le titre de l’alerte.

Vous utilisez le [créateur d’alertes](alert-builder.md#alert-builder) pour modifier l’alerte.

## Résolution des problèmes liés à une alerte

Lors de la résolution d’un problème avec une alerte, indiquez le numéro JID (Job Instance ID) à l’assistance Adobe. Le numéro de JID se trouve au bas de l’e-mail de notification d’alerte que vous recevez.

![E-mail d’alerte](assets/alerts-email.PNG)
