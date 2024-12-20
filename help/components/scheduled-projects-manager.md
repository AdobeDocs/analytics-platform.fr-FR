---
description: Dans Analysis Workspace, vous pouvez utiliser les mesures de deux façons.
title: Mesures
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: 8676497c9341e3ff74d1b82ca79bc1e73caf514f
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 15%

---

# Projets planifiés

Les projets Analysis Workspace planifiés peuvent être gérés dans Customer Journey Analytics à l’aide de **[!UICONTROL Composants]** > **[!UICONTROL Projets planifiés]**.

Dans **[!UICONTROL Projets planifiés]**, vous pouvez modifier et supprimer des planifications de projet récurrentes.  La [liste de projets planifiés](#scheduled-project-list) affiche les éléments créés par un utilisateur spécifique. Si le compte utilisateur est désactivé dans l’application, toutes les diffusions planifiées s’arrêteront.

![Interface de projets planifiés](assets/scheduled-projects.png)

## Liste des projets planifiés

La liste des projets planifiés contient des colonnes pour les opérations suivantes :

| Colonne | Description |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Lorsqu’un ou plusieurs projets planifiés sont sélectionnés, une barre d’actions bleue s’affiche au bas de l’interface Projets planifiés. Voir [Actions](#actions) pour plus d’informations. |
| ![Star](/help/assets/icons/Star.svg) | Sélectionnez pour favoriser ![Star](/help/assets/icons/Star.svg) ou annuler ![StarOutline](/help/assets/icons/StarOutline.svg) pour un projet planifié. |
| **[!UICONTROL Identifiant de planning]** | Identifiant principalement utilisé à des fins de débogage. |
| **[!UICONTROL Nom]** | Nom de ce projet.<br/> Sélectionnez ![InfoOutline](/help/assets/icons/InfoOutline.svg) pour afficher plus de détails sur le projet planifié.<br/>Sélectionnez ![Plus](/help/assets/icons/More.svg) pour ouvrir un menu contextuel. Dans ce menu, vous pouvez effectuer les opérations suivantes :<ul><li>![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]** un projet planifié.</li><li>![Étiquettes](/help/assets/icons/Labels.svg) **[!UICONTROL Baliser]** un projet planifié.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approuver]** un projet planifié.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exporter CSV]** : exportez un projet planifié dans un fichier CSV.</li></ul> |
| **[!UICONTROL Propriétaire]** | Personne qui a créé le projet et qui en est propriétaire. |
| **[!UICONTROL Balises]** | (facultatif) Le balisage est un moyen efficace d’organiser les projets. Tous les utilisateurs peuvent créer des balises et en appliquer une ou plusieurs à un projet. Néanmoins, vous ne pouvez afficher les balises que pour les projets que vous possédez ou qui ont été partagés avec vous. |
| **[!UICONTROL Distribué à]** | Les destinataires de ce projet planifié. |
| **[!UICONTROL Date d’expiration]** | Vous pouvez définir la date d’expiration sur un an au maximum, quelle que soit la fréquence de planification. |
| **[!UICONTROL Fréquence]** | À quelle fréquence ce projet de planification doit être envoyé à un ou plusieurs destinataires. |
| **[!UICONTROL Heure d’exécution]** | Heure à laquelle ce projet planifié est envoyé. |
| **[!UICONTROL Nombre de requêtes]** | Nombre de requêtes concernant ce projet. |
| **[!UICONTROL Période la plus longue]** | La période la plus longue définie pour le projet planifié. Cette valeur peut s’avérer utile pour examiner les problèmes de performances. Voir [Gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity-overview.md) pour plus d’informations. |
| **[!UICONTROL Nombre de requêtes]** | Nombre de requêtes exécutées pour le projet planifié. Cette valeur peut s’avérer utile pour examiner les problèmes de performances. Voir [Gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity-overview.md) pour plus d’informations. |


Vous pouvez utiliser ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour configurer les colonnes à afficher.

Recherchez un projet planifié à l’aide de ![Recherche](/help/assets/icons/Search.svg). Vous pouvez également voir si des filtres sont appliqués à partir du panneau Filtres . Pour supprimer un filtre, sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour un filtre. Pour supprimer tous les filtres, sélectionnez **[!UICONTROL Effacer tout]**.

Pour modifier un projet planifié, sélectionnez le titre du projet planifié. Utilisez la boîte de dialogue **[!UICONTROL Modifier le projet planifié]** pour mettre à jour les détails du planning.

![Modifier le projet planifié](assets/edit-scheduled-project.png)

Sélectionnez **[!UICONTROL Mettre à jour]** pour mettre à jour le planning.




## Actions

Vous trouverez ci-dessous des actions courantes dans le Gestionnaire de projets planifiés. Vous pouvez sélectionner des actions dans le menu contextuel ou dans la barre d’actions bleue lors de la sélection d’un ou de plusieurs projets planifiés.

| Icône | Action | Description |
|:---:|---|---|
| ![Fermer](/help/assets/icons/Close.svg) | **[!UICONTROL *x *sélectionné]** | Sélectionnez cette option pour désélectionner les projets planifiés sélectionnés. |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimez les projets planifiés sélectionnés pour le projet ; les projets ne sont pas supprimés. |
| ![Étiquettes](/help/assets/icons/Labels.svg) | **[!UICONTROL Balise]** | Balisez les projets planifiés sélectionnés. Dans le fichier **[!UICONTROL Tag Scheduled projects]**, sélectionnez tags et **[!UICONTROL Save]** to save (Enregistrer). |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approuver]** | Approuvez les projets planifiés sélectionnés. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exporter dans un fichier CSV]** | Exportez les projets planifiés sélectionnés vers un fichier nommé `Export Scheduled Projects List.csv`. |


## Filtre

Vous pouvez filtrer les projets planifiés [Liste de projets planifiés](#scheduled-project-list) à l’aide du panneau de filtrage. Pour afficher ou masquer le panneau de filtrage, utilisez ![Filter](/help/assets/icons/Filter.svg).

Le panneau Filtre se compose des sections suivantes.

### Balises

| Balises | Description |
|---|---|
| ![Balises](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | La section **[!UICONTROL Balises]** vous permet de filtrer par balises. <ul><li>Vous utilisez ![Rechercher](/help/assets/icons/Search.svg) **[!UICONTROL Rechercher des balises]** pour rechercher des balises que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs balises. Les balises disponibles dépendent des sélections effectuées dans d’autres sections du panneau de filtrage.</li><li>Les chiffres indiquent :<ul><li>7︎⃣ : nombre de projets planifiés associés à la balise spécifique.</li></ul></li></ul> |


### Propriétaires

| Propriétaire | Description |
|---|---|
| ![Propriétaires](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | La section **[!UICONTROL Propriétaire]** vous permet de filtrer les propriétaires. <ul><li>Vous utilisez ![Search](/help/assets/icons/Search.svg) *Search Owners* pour rechercher les propriétaires que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs propriétaires. Les propriétaires disponibles dépendent des sélections effectuées dans d’autres sections du panneau de filtrage.</li><li>Les chiffres indiquent :<ul><li>4︎⃣ : nombre de projets planifiés associés au propriétaire spécifique.</li></ul></li></ul> |


### Autres filtres

| Autres filtres | Description |
|---|---|
| ![Autres filtres](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | La section **[!UICONTROL Autres filtres]** vous permet de filtrer selon d’autres filtres prédéfinis.<ul><li>Vous pouvez sélectionner une ou plusieurs des options suivantes :<ul><li> **[!UICONTROL Expiré]** : filtrez les projets planifiés expirés.</li><li>**[!UICONTROL Échec]** : filtrez les projets planifiés pour lesquels la planification a échoué.</li></ul>Ce que vous pouvez sélectionner dépend de votre rôle et de vos autorisations.</li><li>Vous pouvez sélectionner plusieurs autres filtres. Les autres filtres disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtres.</li><li>Les chiffres indiquent :<ul><li>4︎⃣ : nombre de projets planifiés associés à l’autre filtre spécifique.</li></ul></li></ul> |
