---
title: Comment gérer les connexions dans Customer Journey Analytics
description: Décrit comment gérer des connexions à des jeux de données Experience Platform dans Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: a377c9bc4b58623e0b04da7f9ff1010572f7a610
workflow-type: tm+mt
source-wordcount: '2535'
ht-degree: 25%

---

# Gestion des connexions

Une fois que vous avez [création ou modification d’une ou de plusieurs connexions](/help/connections/create-connection.md), vous pouvez les gérer dans **[!UICONTROL Connexions]**. Les connexions permettent :

* Affichez toutes vos connexions en un coup d’oeil, y compris le propriétaire, l’environnement de test et le moment où les connexions ont été créées et modifiées.
* Modification d’une connexion.
* Supprimer une connexion.
* Créer une vue de données à partir d’une connexion.
* Affichage de tous les jeux de données dans une connexion.
* Vérifiez l’état des jeux de données de votre connexion et l’état du processus d’ingestion. Par exemple, quand vos données sont disponibles afin que vous puissiez commencer à créer des rapports et des analyses dans Analysis Workspace.
* Identifiez les incohérences de données dues à une mauvaise configuration. Vous manque-t-il des lignes ? Si tel est le cas, quelles lignes sont manquantes et pourquoi ? Avez-vous mal configuré les connexions et généré des données manquantes en Customer Journey Analytics ?


Un tableau affiche toutes les connexions disponibles. Vous pouvez rechercher rapidement une connexion à l’aide de la fonction de recherche ![Rechercher](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) de la boîte.

Les colonnes/icônes suivantes sont disponibles dans le tableau.

| Colonne / Icône | Description |
| --- | --- |
| [!UICONTROL Nom] | Nom convivial de la connexion. Pour afficher les détails de la connexion, sélectionnez le nom de l’hyperlien. Voir [Détails de la connexion](#connection-details). |
| ![Informations](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Pour afficher des informations sur [!UICONTROL Jeux de données inclus], [!UICONTROL Sandbox], [!UICONTROL Propriétaire], etc., sélectionnez ![Informations](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) en regard du nom de la connexion.<p>Une fenêtre contextuelle affiche les détails. <p><img src="./assets/conn-info.png" alt="Affichage des informations de connexion" width="50%" /> |
| ![Vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | À [créer une vue de données](#create-a-data-view) pour la connexion, sélectionnez ![Vue des données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) . Cette icône s’affiche uniquement lorsqu’aucune vue de données n’est déjà associée à la connexion. |
| ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Sélectionner ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) à : <p>![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Modifier](#edit-a-connection) une connexion.<p>![Supprimer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Supprimer](#delete-a-connection) une connexion.<p>![Vue des données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Créer une vue de données](#create-a-data-view). Utilisez cette option pour créer des vues de données supplémentaires pour la connexion. |
| [!UICONTROL Jeux de données] | Affiche un ou plusieurs liens vers les jeux de données qui font partie de la connexion. Vous pouvez sélectionner l’hyperlien du jeu de données pour afficher le jeu de données dans la connexion. Si d’autres jeux de données font partie de la connexion sélectionnée, sélectionnez **[!UICONTROL +*x* more]** pour afficher un **[!UICONTROL Jeux de données inclus]** du panneau. Ce panneau affiche des liens vers tous les jeux de données et une option permettant de rechercher un jeu de données spécifique qui fait partie de la connexion.<p><img src="./assets/datasets-included.png" alt="Ressources de données incluses" width="50%" /><p>La sélection d’un nom de jeu de données ouvre le jeu de données dans l’interface utilisateur de l’Experience Platform dans un nouvel onglet. |
| [!UICONTROL Sandbox] | Affiche la variable [Environnement de test Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=fr) à partir de laquelle cette connexion dessine ses jeux de données. Ce sandbox a été sélectionné lorsque vous avez créé la connexion pour la première fois. Il ne peut pas être modifié. |
| [!UICONTROL Propriétaire] | Personne qui a créé la connexion. |
| [!UICONTROL Importer de nouvelles données] | Affiche l’état de l’importation de nouvelles données pour les jeux de données : <p><span style="color:green">●</span>   **[!UICONTROL _x _Activé]**pour connaître le nombre de jeux de données configurés pour importer de nouvelles données, et&lt;/<p><span style="color:gray">●</span>   **[!UICONTROL _x Désactivé_]** pour connaître le nombre de jeux de données désactivés pour la nouvelle importation de données. |
| [!UICONTROL Date de création] | Horodatage de création de la connexion. |
| [!UICONTROL Dernière modification] | Horodatage de la dernière mise à jour de la connexion. |
| [!UICONTROL Renvoyer les données] | Affiche l’état des données de renvoi dans les jeux de données.<p><span style="color:red">●</span>   **[!UICONTROL _x _renvoi en échec]**pour le nombre de renvois échoués entre les jeux de données,<p><span style="color:orange">●</span>   **[!UICONTROL _x _traitement des renvois]**pour le nombre de renvois de traitement entre les jeux de données,<p><span style="color:green">●</span>   **[!UICONTROL _x _renvoi terminé]**pour le nombre de renvois terminés pour les jeux de données, et<p><span style="color:grey">●</span>   **[!UICONTROL _Off_]** si aucun renvoi n’est défini pour les jeux de données dans la connexion. |

Vous pouvez configurer les colonnes à afficher à l’aide de ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Cela affiche la variable **Personnalisation du tableau** pour activer/désactiver les colonnes du tableau.

## Modifier une connexion

Permet aux administrateurs de modifier la connexion.

1. Sélectionner ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) en regard du nom de la connexion
1. Sélectionner ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier]** dans le menu contextuel.

Vous pouvez également :

1. Sélectionnez la ligne de connexion.

1. Sélectionner ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier]** de la barre bleue.

Lors de l’édition d’une connexion, vous pouvez :

* Démarrez et arrêtez d’importer de nouvelles données.
* Renommer une connexion.
* Actualisez le ou les jeux de données.
* Supprimez le ou les jeux de données des connexions.

Voir [Créer ou modifier une connexion](create-connection.md) pour plus d’informations.


## Supprimer une connexion {#connections-delete}

Permet aux administrateurs de supprimer la connexion.

1. Sélectionner ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) en regard du nom de la connexion.
1. Sélectionner ![Supprimer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Supprimer]**.

Vous pouvez également :

1. Sélectionnez la ligne de connexion.

1. Sélectionner ![Supprimer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Supprimer]** de la barre bleue.

Lorsque vous supprimez une connexion, une **[!UICONTROL Supprimer la connexion]** indique quelles vues de données sont supprimées et quels projets workspace sont affectés.

<img src="./assets/delete-connection.png" alt="Supprimer la connexion" width="50%" />

Sélectionner **[!UICONTROL Continuer]** pour supprimer la connexion.

Voir [Supprimer les implications](/help/admin/cja-deletion.md) pour plus d’informations sur les implications de la suppression d’une connexion.


## Création d’une vue de données

Permet aux administrateurs de créer une vue de données pour la connexion.

* Si aucune vue de données n’est associée à la connexion :

   1. Sélectionner ![Ajouter une vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) en regard du nom de la connexion.

* Si une ou plusieurs vues de données sont déjà créées pour la connexion :

   1. Sélectionner ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) en regard du nom de la connexion.
   1. Sélectionner ![Ajouter une vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Créer une vue de données]**.

Vous pouvez également :

1. Sélectionnez la ligne de connexion.

1. Sélectionner ![Ajouter une vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Créer une vue de données]** dans la barre de boutons bleue.

Consultez [Créer ou modifier une vue de données](/help/data-views/create-dataview.md) pour plus d’informations.

## Détails de la connexion {#connection-detail}

Pour accéder aux détails d&#39;une connexion, sélectionnez un nom de connexion dans la table des connexions.

![Fenêtre de tous les jeux de données présentant les widgets et les paramètres](assets/conn-details.png)

L’interface de détails des connexions fournit une vue détaillée de l’état d’une connexion. Vous pouvez :

* Vérifier le statut des jeux de données de votre connexion et du processus dʼingestion.
* Identifiez les problèmes de configuration qui peuvent entraîner la suppression ou la suppression d’enregistrements.
* Voir quand les données sont disponibles pour le compte rendu des performances.

| Interface utilisateur | Description |
| --- | --- |
| ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Modifier la connexion] | Pour modifier les détails d’une connexion, sélectionnez ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier la connexion]** . Voir [Créer ou modifier une connexion](create-connection.md) pour plus d’informations. |
| Sélecteur de jeux de données | Permet de sélectionner un ou tous les jeux de données de la connexion. Vous ne pouvez pas sélectionner plusieurs jeux de données. La valeur par défaut est [!UICONTROL Tous les jeux de données]. |
| Sélecteur de période | Modifier la date de début ou de fin ou sélectionner ![Calendrier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) pour ouvrir le sélecteur de plage de données. Dans le sélecteur de période, sélectionnez une période à l’aide de l’une des périodes prédéfinies (par exemple **[!UICONTROL 6 derniers mois]**) ou utilisez le calendrier pour sélectionner les dates de début et de fin. Sélectionner **[!UICONTROL Appliquer]** pour appliquer la nouvelle plage de données. |
| [!UICONTROL Enregistrements de données d’événement disponibles] | Affiche le nombre total de lignes de jeux de données dʼévénement disponibles pour le compte rendu des performances, **sur lʼensemble de la connexion**. Ce nombre est indépendant des paramètres du calendrier. Le nombre change si vous sélectionnez un jeu de données à partir du sélecteur de jeux de données ou en sélectionnant un jeu de données dans le tableau. Une fois les données ajoutées, une latence de 1 à 2 heures s’affiche pour que les données apparaissent dans les rapports. |
| [!UICONTROL Mesures] | Affiche les enregistrements dʼévénements ajoutés, ignorés et supprimés ainsi que le nombre de lots ajoutés, **pour le jeu de données et la période sélectionnés**.<p>Sélectionner **[!UICONTROL Vérifier le détail]** pour afficher la variable **[!UICONTROL Vérifier les détails ignorés]** , répertoriant pour tous les jeux de données d’événement ou le jeu de données sélectionné le nombre d’enregistrements ignorés et la raison.<p><img src="./assets/skipped-records.png" width="70%"/><p>Sélectionner ![Infos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) avec plus d’informations. Pour certaines raisons ignorées, comme [!UICONTROL Identifiant visiteur vide], la fenêtre contextuelle affiche Exemple de PSQL pour EQS (Experience Platform pour Query Service) que vous pouvez utiliser dans [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=fr) pour rechercher les enregistrements ignorés dans le jeu de données. Sélectionner ![Copier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copie d’exemple PSQL pour EQS]** pour copier le SQL. |
| [!UICONTROL Enregistrements ajoutés] | Indique le nombre de lignes ajoutées au cours de la période sélectionnée, **pour le jeu de données et la période sélectionnés**. Mis à jour toutes les 10 minutes. <p>**Remarque**: données pour **[!UICONTROL Enregistrements ajoutés]** inclut uniquement les données d’événement à ce stade, et non les données de profil ou de recherche. |
| [!UICONTROL Enregistrements ignorés] | Indique le nombre de lignes ignorées au cours de la période sélectionnée, **pour le jeu de données et la période sélectionnés**. Les raisons pour ignorer les enregistrements sont les suivantes : horodatages manquants, ID de personne manquant ou non valide, etc. Mis à jour toutes les 10 minutes. <p>Un ID de personne non valide (par exemple, « non défini » ou « 00000000 » ou toute combinaison de nombres et de lettres dans un [!UICONTROL ID de personne] qui apparaît dans un événement plus d’un million de fois au cours d’un mois donné) ne peut pas être attribué à un utilisateur ou à une personne spécifique. Ils ne peuvent pas être ingérés dans le système et entraînent une ingestion et un reporting sujets aux erreurs. Pour corriger les ID de personne non valides, vous disposez de 3 options :<ul><li>Utilisation [Assemblage](/help/stitching/overview.md) pour renseigner les identifiants utilisateur non définis ou entièrement nuls avec des identifiants utilisateur valides.</li><li>Videz l’ID utilisateur, qui sera ensuite ignoré lors de l’ingestion (préférable à des ID utilisateur non valides ou totalement nuls).</li><li>Corrigez tout ID utilisateur non valide dans votre système avant d’ingérer les données.</li></ul> <p>**Remarque**: données pour **[!UICONTROL Enregistrements ignorés]** inclut uniquement les données d’événement à ce stade, et non les données de profil ou de recherche. |
| [!UICONTROL Enregistrements] supprimé | Indique le nombre de lignes supprimées au cours de la période sélectionnée, **pour le jeu de données et la période sélectionnés**. Quelquʼun peut avoir supprimé un jeu de données dans Experience Platform, par exemple. Mis à jour toutes les 10 minutes.<p>**Remarque**: données pour **[!UICONTROL Enregistrements supprimés]** inclut uniquement les données d’événement à ce stade, et non les données de profil ou de recherche. |
| ![Rechercher](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Rechercher le nom ou l’identifiant du jeu de données_ | Champ de recherche de jeux de données. Vous pouvez rechercher le tableau des jeux de données par nom de jeu de données ou [!UICONTROL Identifiant du jeu de données]. |
| [!UICONTROL Tableau des jeux de données] | Affiche les jeux de données qui font partie de la connexion. |
| [!UICONTROL Jeux de données] | Affiche le nom du jeu de données qui fait partie de la connexion. Vous pouvez sélectionner l’hyperlien pour ouvrir le jeu de données dans l’interface utilisateur de l’Experience Platform dans un nouvel onglet. Vous pouvez sélectionner la ligne ou la case à cocher pour afficher uniquement les détails du jeu de données sélectionné. |
| [!UICONTROL Identifiant du jeu de données] | Généré automatiquement par l’Experience Platform. |
| [!UICONTROL Enregistrements ajoutés] | Nombre d’enregistrements/de lignes de jeu de données ajoutés à une connexion au cours de l’intervalle de temps sélectionné. |
| [!UICONTROL Enregistrements ignorés] | Nombre d’enregistrements/de lignes de jeu de données ignorés lors du transfert de données pour une connexion au cours de l’intervalle de temps sélectionné. |
| [!UICONTROL Enregistrements supprimés] | Nombre d’enregistrements/de lignes de jeu de données supprimés d’une connexion au cours de l’intervalle de temps sélectionné. |
| [!UICONTROL Lots ajoutés] | Nombre de lots de jeux de données ont été ajoutés à une connexion. |
| [!UICONTROL Dernier ajout] | Horodatage du dernier lot du jeu de données ajouté à une connexion. |
| [!UICONTROL Type de source de données] | Type source du jeu de données. Vous définissez le type de source lors de la création d&#39;une connexion. |
| [!UICONTROL Type de jeu de données] | Type de jeu de données pour ce jeu de données. Le type peut être [!UICONTROL Événement], [!UICONTROL Recherche], ou [!UICONTROL Profil]. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr#configure-dataset) |
| Schéma | Schéma Experience Platform sur lequel le jeu de données est basé. |
| [!UICONTROL Importer de nouvelles données] | Affiche l’état de l’importation de nouvelles données pour le jeu de données : <p><span style="color:green">●</span>   **[!UICONTROL _x _Activé]**si le jeu de données est configuré pour importer de nouvelles données, et<p><span style="color:gray">●</span>   **[!UICONTROL _x Désactivé_]** si le jeu de données est configuré pour ne pas importer de nouvelles données d’importation. |
| [!UICONTROL Renvoyer les données] | Affiche l’état des données de renvoi pour le jeu de données.<p><span style="color:red">●</span>   **[!UICONTROL _x _renvoi en échec]**pour le nombre de renvois ayant échoué,<p><span style="color:orange">●</span>   **[!UICONTROL _x _traitement des renvois]**pour le nombre de renvois traités,<p><span style="color:green">●</span>   **[!UICONTROL _x _renvoi terminé]**pour le nombre de renvois terminés, et<p><span style="color:grey">●</span>   **[!UICONTROL _Off_]** si aucun renvoi n’est configuré. |

>[!IMPORTANT]
>
>Les données ingérées avant le 13 août 2021 ne sont pas reflétées dans la variable [!UICONTROL Connexions] .

### Panneau de connexion

Lorsqu’aucun jeu de données n’est sélectionné dans le tableau des jeux de données, un panneau situé sur le côté droit de l’interface Connexions affiche les options et les détails de connexion.

| Options / Détails | Description |
| --- | --- |
| ![Actualiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Actualiser] | Pour actualiser la connexion et permettre la prise en compte des enregistrements récemment ajoutés, sélectionnez ![Actualiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Actualiser]**. |
| ![Supprimer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Supprimer]** | [Supprimer](#delete-a-connection) cette connexion. |
| ![Ajouter une vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Créer une vue de données]** | [Création d’une vue de données](#create-a-data-view) selon cette connexion. Voir [Vues des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=fr) pour plus d’informations. |
| [!UICONTROL Nom de la connexion] | Affiche le nom convivial de la connexion. |
| [!UICONTROL Description de la connexion] | Affiche une description plus détaillée de l’objectif de cette connexion. |
| [!UICONTROL Sandbox] | La variable [Environnement de test Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=fr) à partir de laquelle cette connexion dessine son ou ses jeux de données. Cet environnement de test a été sélectionné lors de la première création de la connexion. Il ne peut pas être modifié. |
| [!UICONTROL ID de connexion] | Cet identifiant est généré dans Experience Platform. Vous pouvez utiliser ![Copier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) pour copier l’identifiant. |
| [!UICONTROL Vues de données utilisant la connexion] | Répertorie toutes les vues de données qui utilisent cette connexion. |
| [!UICONTROL Importer de nouvelles données] | Affiche l’état de l’importation de nouvelles données pour les jeux de données : <p><span style="color:green">●</span>   **[!UICONTROL _x _Activé]**pour connaître le nombre de jeux de données configurés pour importer de nouvelles données, et<p><span style="color:gray">●</span>   **[!UICONTROL _x Désactivé_]** pour connaître le nombre de jeux de données désactivés pour la nouvelle importation de données. |
| [!UICONTROL Renvoyer les données] | Affiche l’état des données de renvoi pour les jeux de données.<p><span style="color:red">●</span>   **[!UICONTROL _x _renvoi en échec]**pour le nombre de renvois échoués entre les jeux de données,<p><span style="color:orange">●</span>   **[!UICONTROL _x _traitement des renvois]**pour le nombre de renvois de traitement entre les jeux de données,<p><span style="color:green">●</span>   **[!UICONTROL _x _renvoi terminé]**pour le nombre de renvois terminés pour les jeux de données, et<p><span style="color:grey">●</span>   **[!UICONTROL _Off_]** si aucun renvoi n’est défini pour les jeux de données dans la connexion. |
| [!UICONTROL Créé par] | Affiche le nom de la personne qui a créé la connexion. |
| [!UICONTROL Dernière modification] | Affiche l’horodatage de la dernière modification apportée à la connexion. |
| [!UICONTROL Dernière modification par] | Affiche la personne qui a modifié la connexion pour la dernière fois. |

### Panneau Jeu de données

Lorsqu’un jeu de données est sélectionné dans le tableau des jeux de données, un panneau situé sur le côté droit de l’interface Connexions affiche les détails du jeu de données sélectionné.

| Détails | Description |
| --- | --- |
| [!UICONTROL ID de personne] | Affiche une identité qui a été définie dans le schéma du jeu de données dans Experience Platform. Il s’agit de l’ID de personne que vous avez sélectionné lors de la création de la connexion. Si vous créez une connexion qui inclut des jeux de données avec des identifiants différents, les rapports le reflètent. Pour fusionner des jeux de données, vous devez utiliser le même ID de personne dans les jeux de données. |
| [!UICONTROL Clé] | Affiche la clé que vous avez spécifiée pour un jeu de données de recherche. |
| [!UICONTROL Clé correspondante] | Affiche la clé correspondante que vous avez spécifiée pour un jeu de données de recherche. |
| [!UICONTROL Date et heure] | Afficher l’horodatage défini pour un jeu de données d’événement. |
| [!UICONTROL Enregistrements disponibles] | Représente le nombre total de lignes ingérées pour ce jeu de données, au cours de la période sélectionnée dans le calendrier. Une fois ajoutées, les données apparaissent dans le compte rendu des performances sans aucune latence. Cependant, lorsque vous créez une nouvelle connexion, il y a [latence](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=fr#3.-getting-data-into-customer-journey-analytics). |
| [!UICONTROL Enregistrements ajoutés] | Indique le nombre de lignes ajoutées au cours de la période sélectionnée. |
| [!UICONTROL Enregistrements supprimés] | Indique le nombre d’enregistrements supprimés au cours de la période sélectionnée. |
| [!UICONTROL Lots ajoutés] | Indique le nombre de lots de données ajoutés à ce jeu de données. |
| [!UICONTROL Enregistrements ignorés] | Indique le nombre de lignes ignorées lors de lʼingestion au cours de la période sélectionnée.<p>Les raisons pour ignorer les enregistrements sont les suivantes : horodatages manquants, ID de personne manquant ou non valide, etc. Mis à jour toutes les 10 minutes.<p>Un ID de personne non valide (par exemple, « non défini » ou « 00000000 » ou toute combinaison de nombres et de lettres dans un [!UICONTROL ID de personne] qui apparaît dans un événement plus d’un million de fois au cours d’un mois donné) ne peut pas être attribué à un utilisateur ou à une personne spécifique. Ils ne peuvent pas être ingérés dans le système et entraînent une ingestion et un reporting sujets aux erreurs. Pour corriger les ID de personne non valides, vous disposez de 3 options :<ul><li>Utilisation [Assemblage](/help/stitching/overview.md) pour renseigner les identifiants utilisateur non définis ou entièrement nuls avec des identifiants utilisateur valides.</li><li>Videz l’ID utilisateur, qui est ensuite ignoré lors de l’ingestion (préférable à des ID utilisateur non valides ou tous nuls).</li><li>Corrigez tout ID utilisateur non valide dans votre système avant d’ingérer les données.</li></ul> |
| [!UICONTROL Dernier ajout] | Indique la date à laquelle le dernier lot a été ajouté. |
| [!UICONTROL Importer de nouvelles données] | Affiche l’état de l’importation de nouvelles données pour le jeu de données : <p><span style="color:green">●</span>   **[!UICONTROL _x _Activé]**si le jeu de données est configuré pour importer de nouvelles données, et<p><span style="color:gray">●</span>   **[!UICONTROL _x Désactivé_]** si le jeu de données est configuré pour ne pas importer de nouvelles données d’importation. |
| [!UICONTROL Renvoyer les données] | Affiche l’état des données de renvoi pour le jeu de données.<p><span style="color:red">●</span>   **[!UICONTROL _x _renvoi en échec]**pour le nombre de renvois ayant échoué,<p><span style="color:orange">●</span>   **[!UICONTROL _x _traitement des renvois]**pour le nombre de renvois traités,<p><span style="color:green">●</span>   **[!UICONTROL _x _renvoi terminé]**pour le nombre de renvois terminés, et<p><span style="color:grey">●</span>   **[!UICONTROL _Off_]** si aucun renvoi n’est configuré.<p>Pour afficher une boîte de dialogue avec un aperçu des renvois précédents du jeu de données, sélectionnez <img src="./assets/pastbackfill.svg" alt="Renvois précédents" width="2%" /> **[!UICONTROL Renvois passés]**. |
| [!UICONTROL Type de source de données] | Type de source de données tel que défini lors de l’ajout d’un jeu de données à la connexion. |
| [!UICONTROL Type de jeu de données] | Soit [!UICONTROL Événement], [!UICONTROL Recherche] ou [!UICONTROL Profil]. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr#configure-dataset) |
| [!UICONTROL Schéma] | Affiche le schéma Experience Platform sur lequel ce jeu de données est basé. |
| [!UICONTROL Identifiant du jeu de données] | Cet identifiant de jeu de données est généré dans Experience Platform. |


>[!MORELIKETHIS]
>
>[Affichage, dépannage et modification des paramètres de connexion](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html?lang=en) tutoriel .
