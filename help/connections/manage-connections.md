---
title: Comment gérer les connexions dans Customer Journey Analytics
description: Décrit la manière de gérer des connexions aux jeux de données Experience Platform dans Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 5311106f486a30dbc7f06b3ef60dc7e666d2fe03
workflow-type: tm+mt
source-wordcount: '4288'
ht-degree: 90%

---

# Gérer des connexions

Une fois que vous avez [créé ou modifié une ou plusieurs connexions](/help/connections/create-connection.md), vous pouvez les gérer dans **[!UICONTROL Connexions]**. Les connexions vous permettent d’effectuer les actions suivantes :

* Affichez de manière récapitulative les principales caractéristiques de vos connexions, y compris la personne propriétaire, le sandbox ainsi que la date à laquelle elles ont été créées et modifiées.
* Modifiez une connexion.
* Supprimer une connexion.
* Créer une vue de données à partir d’une connexion.
* Affichage de tous les jeux de données dans une connexion.
* Vérifiez le statut des jeux de données de votre connexion et du processus dʼingestion. Par exemple, quand vos données sont-elles disponibles pour que vous puissiez commencer à créer des rapports et des analyses dans Analysis Workspace ?
* Identifiez les incohérences de données dues à une mauvaise configuration. Vous manque-t-il des lignes ? Si c’est le cas, quelles lignes sont manquantes, et pourquoi ? Avez-vous mal configuré les connexions et généré des données manquantes dans Customer Journey Analytics ?
* Obtenez des informations sur l’utilisation des lignes ingérées et pouvant faire l’objet d’un rapport sur toutes vos connexions.

L’affichage [!UICONTROL Connexions] a deux interfaces : [[!UICONTROL Liste]](#list) et [[!UICONTROL Utilisation]](#usage).


## Liste

L’interface [!UICONTROL Liste] est l’interface par défaut pour Connexions. Si cette option n’est pas sélectionnée, sélectionnez l’onglet **[!UICONTROL Liste]** pour accéder à l’interface.

![Vue en liste](assets/list-view.png)

L’interface [!UICONTROL Liste] affiche un tableau de toutes les connexions disponibles. Vous pouvez rechercher rapidement une connexion à l’aide de la zone Rechercher ![Rechercher](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

Les colonnes ou icônes suivantes sont disponibles dans le tableau.

| Colonne ou icône | Description |
| --- | --- |
| [!UICONTROL Nom] | Nom convivial de la connexion. Pour afficher les détails de la connexion, sélectionnez le nom avec un lien hypertexte. Consultez [Détails de le connexion](#connection-details). |
| ![Informations](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Pour afficher des informations sur [!UICONTROL Jeux de données inclus], [!UICONTROL Sandbox], [!UICONTROL Propriétaire], etc., sélectionnez ![Informations](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) en regard du nom de la connexion.<p>Une fenêtre contextuelle affiche des détails. <p><img src="./assets/conn-info.png" alt="Afficher les informations de la connexion" width="400"/> |
| ![Vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Pour [créer une vue de données](#create-a-data-view) pour la connexion, sélectionnez ![Vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). Cette icône s’affiche uniquement lorsqu’aucune vue de données n’est déjà associée à la connexion. |
| ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Sélectionnez ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) pour effectuer ce qui suit : <p>![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Modifiez](#edit-a-connection) une connexion.<p>![Supprimer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Supprimez](#delete-a-connection) une connexion.<p>![Vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Créez une vue de données](#create-a-data-view). Pour créer des vues de données supplémentaires pour la connexion.<p>Carte de connexion ![GraphPathing](/help/assets/icons/GraphPathing.svg). Pour afficher un mappage de connexion pour la connexion. |
| **[!UICONTROL Jeux de données]** | Un ou plusieurs liens vers les jeux de données qui font partie de la connexion. Vous pouvez sélectionner le lien hypertexte du jeu de données pour afficher le jeu de données dans la connexion. Si d’autres jeux de données font partie de la connexion sélectionnée, sélectionnez **[!UICONTROL +*x* plus]** pour afficher un panneau **[!UICONTROL Jeux de données inclus]**. Ce panneau affiche des liens vers tous les jeux de données et une option permettant de rechercher un jeu de données spécifique faisant partie de la connexion.<p><img src="./assets/datasets-included.png" alt="Jeux de données inclus" width="400"/><p>La sélection d’un nom de jeu de données ouvre le jeu de données dans l’interface d’utilisation d’Experience Platform dans un nouvel onglet. |
| **[!UICONTROL Sandbox]** | [Sandbox Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/sandbox/home) dʼoù cette connexion tire ses jeux de données. Ce sandbox a été sélectionné lorsque vous avez créé la connexion pour la première fois. Il ne peut pas être modifié. |
| **[!UICONTROL Propriétaire]** | Personne qui a créé la connexion. |
| **[!UICONTROL Importer de nouvelles données]** | Statut de l’import de nouvelles données pour les jeux de données : <p>![Statut vert](assets/status-green.svg)    **[!UICONTROL _x _On]**pour les jeux de données configurés afin d’importer de nouvelles données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _x désactivés_]** pour les jeux de données non configurés pour importer de nouvelles données. |
| **[!UICONTROL Date de création]** | Date et heure auxquelles la connexion a été créée. |
| **[!UICONTROL Dernière modification]** | Date et heure de la dernière mise à jour de la connexion. |
| **[!UICONTROL Renvoyer les données]** | Statut des données de renvoi dans les jeux de données.<p>![Statut rouge](assets/status-red.svg) **[!UICONTROL _x _renvois ont échoué]**pour le nombre de renvois ayant échoué dans les jeux de données,<p>![Statut orange](assets/status-orange.svg) **[!UICONTROL _x _ renvois en cours de traitement]**pour le nombre de renvois en cours de traitement dans les jeux de données,<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _ renvois terminés]**pour le nombre de renvois terminés pour les jeux de données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _Désactivé_]** au cas où aucun renvoi n’est défini pour les jeux de données dans la connexion. |

Pour configurer les colonnes à afficher, sélectionnez ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg), qui affichent la boîte de dialogue **Personnaliser le tableau** vous permettant d’activer ou de désactiver les colonnes du tableau.

### Modifier une connexion

Pour modifier une connexion :

1. Sélectionnez ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) en regard du nom de la connexion.
1. Sélectionnez ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier]** dans le menu contextuel.

Vous pouvez également effectuer les opérations suivantes :

1. Sélectionnez la ligne de connexion.

1. Sélectionnez ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier]** dans la barre bleue.

Lorsque vous modifiez une connexion, vous pouvez :

* Démarrer et cesser dʼimporter de nouvelles données.
* Renommer une connexion.
* Actualisez le ou les jeux de données.
* Supprimez le ou les jeux de données des connexions.

Consultez [Créer ou modifier une connexion](create-connection.md) pour plus d’informations.


### Supprimer une connexion {#connections-delete}

Pour supprimer une connexion :

1. Sélectionnez ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) en regard du nom de la connexion.
1. Sélectionnez ![Supprimer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Supprimer]**.

Vous pouvez également effectuer les opérations suivantes :

1. Sélectionnez la ligne de connexion.

1. Sélectionnez ![Supprimer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Supprimer]** dans la barre bleue.

Lorsque vous supprimez une connexion, un panneau **[!UICONTROL Supprimer la connexion]** indique quelles vues de données sont supprimées et quels projets d’espace de travail sont affectés.

![Supprimer la connexion](assets/delete-connection.png)

Sélectionnez **[!UICONTROL Continuer]** pour supprimer la connexion.

Pour plus d’informations sur la suppression d’une connexion, consultez [Conséquences de la suppression](/help/technotes/deletion.md).


### Créer une vue de données à partir d’une connexion

Pour créer une vue de données pour une connexion

* Si aucune vue de données n’est associée à la connexion, procédez comme suit :

   1. Sélectionnez ![Ajouter une vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) en regard du nom de la connexion.

* Si une ou plusieurs vues de données sont déjà créées pour la connexion, procédez comme suit :

   1. Sélectionnez ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) en regard du nom de la connexion.
   1. Sélectionnez ![Ajouter une vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Créer une vue de données]**.

Vous pouvez également effectuer les opérations suivantes :

1. Sélectionnez la ligne de connexion.

1. Sélectionnez ![Ajouter une vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Créer une vue de données]** dans la barre de boutons bleue.

Consultez [Créer ou modifier une vue de données](/help/data-views/create-dataview.md) pour plus d’informations.


### Mapper une connexion

Pour afficher un mappage [connexion](/help/connections/create-connection.md#connection-map) qui détaille les relations entre les jeux de données qui font partie d’une connexion :

1. Sélectionnez ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) en regard du nom de la connexion.
1. Sélectionnez ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Connection map]**.

### Détails de la connexion {#connection-detail}

Pour accéder aux détails d’une connexion, sélectionnez un nom de connexion dans le tableau des connexions.

![Fenêtre Tous les jeux de données présentant les widgets et les paramètres](assets/conn-details.png)

L’interface Détails des connexions vous offre une vue très détaillée du statut dʼune connexion. Vous pouvez :

* Vérifier le statut des jeux de données de votre connexion et du processus dʼingestion.
* Identifiez les problèmes de configuration qui provoquent des enregistrements ignorés ou supprimés.
* Voir quand les données sont disponibles pour le compte rendu des performances.

| Interface utilisateur | Description |
| --- | --- |
| ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier la connexion]** | Pour modifier les détails d’une connexion, sélectionnez ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier la connexion]**. Consultez [Créer ou modifier une connexion](create-connection.md) pour plus d’informations. |
| **[!UICONTROL *Sélecteur de jeu de données *]** | Permet de sélectionner un ou tous les jeux de données de la connexion. Vous ne pouvez pas sélectionner plusieurs jeux de données. La valeur par défaut est **[!UICONTROL Tous les jeux de données]**. |
| **[!UICONTROL *Sélecteur de période *]** | Modifiez la date de début ou de fin, ou sélectionnez ![Calendrier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) pour ouvrir le sélecteur de période. Dans le sélecteur de période, sélectionnez une période à l’aide de l’une des périodes prédéfinies (par exemple, **[!UICONTROL 6 derniers mois]**) ou utilisez le calendrier pour sélectionner les dates de début et de fin. Sélectionnez **[!UICONTROL Appliquer]** pour appliquer la nouvelle période. |
| **[!UICONTROL Enregistrements de données d’événement disponibles]** | Affiche le nombre total de lignes de jeux de données dʼévénement disponibles pour la création de rapports, **sur lʼensemble de la connexion**. Ce nombre est indépendant des paramètres du calendrier. Le nombre varie si vous sélectionnez un jeu de données à partir du sélecteur de jeux de données ou en sélectionnant un jeu de données dans le tableau. Il existe une latence d’1 à 2 heures avant que les données nʼapparaissent dans la création de rapports. |
| [!UICONTROL **[!UICONTROL Mesures]**] | Résumez les enregistrements de jeux de données d’événement, de recherche, de profil et de synthèse qui sont ajoutés, ignorés et supprimés, ainsi que le nombre de lots ajoutés. Ces mesures sont basées sur **le jeu de données et la période que vous avez sélectionnés**.<p>Sélectionnez **[!UICONTROL Vérifier les détails]** pour afficher la fenêtre contextuelle **[!UICONTROL Vérifier les détails ignorés]**. La fenêtre contextuelle répertorie le nombre d’enregistrements ignorés et la raison pour tous les jeux de données d’événement ou du jeu de données sélectionné.<p><img src="./assets/skipped-records.png" width="500"/><p>Sélectionnez la fenêtre contextuelle ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) avec plus d’informations. Pour certaines raisons ignorées, telles que [!UICONTROL ID de visiteur ou visiteuse vide], la fenêtre contextuelle affiche Exemple de PSQL pour EQS (Experience Platform pour Query Service) que vous pouvez utiliser dans [Query Service](https://experienceleague.adobe.com/fr/docs/experience-platform/query/home) pour rechercher les enregistrements ignorés dans le jeu de données. Sélectionnez ![Copier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copier l’exemple de PSQL pour EQS]** pour copier le code SQL. |
| **[!UICONTROL Enregistrements ajoutés]** | Indique le nombre de lignes ajoutées au cours de la période sélectionnée, **pour le jeu de données et la période sélectionnés**. Mise à jour toutes les 10 minutes. |
| **[!UICONTROL Enregistrements ignorés]** | Indique le nombre de lignes ignorées au cours de la période sélectionnée, **pour le jeu de données et la période sélectionnés**. Les raisons pour lesquelles des enregistrements sont ignorés sont les suivantes : dates et heures manquantes, manquant ou non valide ou ID de compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, etc. Mise à jour toutes les 10 minutes. <p>Les identifiants non valides (tels que `undefined` ou `00000000`, ou toute combinaison de chiffres et de lettres dans un [!UICONTROL ID de personne] qui apparaît dans un événement plus d’un million de fois au cours d’un mois donné) sont des identifiants qui ne peuvent pas être attribués à un utilisateur ou à une personne spécifique. Ces enregistrements ne peuvent pas être ingérés dans le système et entraînent une ingestion et un compte rendu des performances sujets aux erreurs. Pour corriger les ID de personne ou de compte non valides [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, vous disposez de 3 options :<ul><li>Utilisez le [Groupement](/help/stitching/overview.md) pour renseigner les ID d’utilisateur ou d’utilisatrice non définis ou composés entièrement de zéros avec des ID d’utilisateur ou d’utilisatrice valides.</li><li>Effacez l’ID d’utilisateur ou d’utilisatrice, qui sera également ignoré lors de l’ingestion (préférable aux ID d’utilisateur ou d’utilisatrice non valides ou entièrement composés de zéros).</li><li>Corrigez tout ID d’utilisateur ou d’utilisatrice non valide dans votre système avant d’ingérer les données.</li></ul> |
| **[!UICONTROL Enregistrements supprimés]** | Indique le nombre de lignes supprimées au cours de la période sélectionnée, **pour le jeu de données et la période sélectionnés**. Une personne peut avoir supprimé un jeu de données dans [!DNL Experience Platform], par exemple. Mise à jour toutes les 10 minutes.<p>Dans certains scénarios, cette valeur peut également inclure des enregistrements remplacés, comme avec le groupement ou certaines mises à jour des jeux de données de recherche. Prenons cet exemple :</p><ul><li>Vous chargez un enregistrement dans un jeu de données de profil individuel XDM, que Customer Journey Analytics est configuré pour ingérer en tant que données de recherche de profil. Dans les détails de la connexion, ce jeu de données affiche 1 enregistrement ajouté.</li><li>Vous chargez un doublon de l’enregistrement d’origine dans le même jeu de données AEP, qui contient désormais deux enregistrements. Customer Journey Analytics ingère l’enregistrement supplémentaire à partir du jeu de données de recherche [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} du profil ou du compte. Puisqu’un enregistrement de profil ou de compte est déjà ingéré dans la connexion pour cet ID de personne ou de compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, Customer Journey Analytics supprime sa version antérieure et ajoute les nouvelles données de profil. Dans les détails de la connexion, cette action représenterait 1 enregistrement ajouté et 1 enregistrement supprimé, car Customer Journey Analytics ne conserve que les données de recherche de profil les plus récentes pour tout ID de personne ou ID de compte ingéré [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}.</li><li>Au total, le jeu de données AEP contient deux enregistrements qui se trouvent être identiques. Séparément, les détails de la connexion Customer Journey Analytics affichent le statut de ses données ingérées : 2 enregistrements ajoutés et 1 enregistrement supprimé pour ce jeu de données de profil. </li></ul> |
| ![Recherche](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Champ de recherche de jeux de données. Vous pouvez rechercher dans le tableau de jeus de données par nom de jeu de données ou par [!UICONTROL identifiant de jeu de données]. |
| [!UICONTROL Tableau des jeux de données] | Affiche les jeux de données qui font partie de la connexion. Voir le tableau ci-dessous pour plus d’explications. |

Le tableau des jeux de données affiche les colonnes suivantes :

| Colonne | Description |
| --- | --- |
| **[!UICONTROL Jeux de données]** | Identifiant du jeu de données faisant partie de la connexion. Vous pouvez sélectionner le lien hypertexte pour ouvrir le jeu de données dans l’interface d’utilisation d’Experience Platform dans un nouvel onglet. Vous pouvez sélectionner la ligne ou la case à cocher pour afficher les détails du jeu de données sélectionné uniquement. |
| **[!UICONTROL Identifiant du jeu de données]** | Généré automatiquement par Experience Platform. |
| **[!UICONTROL Enregistrements ajoutés]** | Nombre d’enregistrements de jeux de données (lignes) ajoutés à une connexion au cours de la période sélectionnée. |
| **[!UICONTROL Enregistrements ignorés]** | Nombre d’enregistrements de jeux de données (lignes) ignorés pendant le transfert de données pour une connexion au cours de la période sélectionnée. |
| **[!UICONTROL Enregistrements supprimés]** | Nombre d’enregistrements de jeux de données (lignes) supprimés d’une connexion au cours de la période sélectionnée. |
| **[!UICONTROL Lots ajoutés]** | Nombre de lots de jeux de données ayant été ajoutés à une connexion. |
| **[!UICONTROL Dernier ajout]** | Date et heure du dernier lot à partir de tout jeu de données ajouté une connexion. |
| **[!UICONTROL Type de source de données]** | Type de source du jeu de données. Vous définissez le type de source lors de la création d’une connexion. |
| **[!UICONTROL Type de jeu de données]** | Type de jeu de données pour ce jeu de données. Le type peut être [!UICONTROL Événement], [!UICONTROL Profil], [!UICONTROL Recherche] ou [!UICONTROL Synthèse]. [En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-connections/create-connection) |
| **[!UICONTROL Schéma]** | Schéma Experience Platform sur lequel est basé ce jeu de données. |
| **[!UICONTROL Importer de nouvelles données]** | Statut de l’import des nouvelles données pour le jeu de données : <p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _ activés]**si le jeu de données est configuré pour importer de nouvelles données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _x désactivés_]** si le jeu de données est configuré pour ne pas importer de nouvelles données. |
| **[!UICONTROL Transformer les données]** | Statut de transformation des jeux de données de recherche B2B applicables. Voir [Transformer des jeux de données pour les recherches B2B](transform-datasets-b2b-lookups.md) pour plus d’informations.<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _activés]**pour les jeux de données applicables activés pour la transformation, <p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _x désactivés_]** pour les jeux de données applicables non activés pour la transformation, et<p>**[!UICONTROL N/A]** pour tous les autres jeux de données, non applicables pour la transformation. |
| **[!UICONTROL Renvoyer les données]** | Statut des données de renvoi pour le jeu de données.<p>![Statut rouge](assets/status-red.svg) **[!UICONTROL _x _renvois ayant échoué]**pour le nombre de renvois ayant échoué,<p>![Statut rouge](assets/status-orange.svg) **[!UICONTROL _x _renvois en cours de traitement]**pour le nombre de renvois en cours de traitement,<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _renvois terminés]**pour le nombre de renvois terminés, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _Désactivé_]** au cas où les renvois ne sont pas configurés. |
| **[!UICONTROL Importer de nouvelles données]** | Statut de l’import des nouvelles données pour le jeu de données : <p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _ activés]**si le jeu de données est configuré pour importer de nouvelles données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _x désactivés_]** si le jeu de données est configuré pour ne pas importer de nouvelles données. |
| **[!UICONTROL Renvoyer les données]** | Statut des données de renvoi pour le jeu de données.<p>![Statut rouge](assets/status-red.svg) **[!UICONTROL _x _renvois ayant échoué]**pour le nombre de renvois ayant échoué,<p>![Statut rouge](assets/status-orange.svg) **[!UICONTROL _x _renvois en cours de traitement]**pour le nombre de renvois en cours de traitement,<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _renvois terminés]**pour le nombre de renvois terminés, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _Désactivé_]** au cas où aucun renvoi n’est configuré. |

>[!IMPORTANT]
>
>Les données ingérées avant le 13 août 2021 ne sont pas reflétées dans l’interface [!UICONTROL Connexions].

#### Panneau Connexion

Lorsqu’aucun jeu de données n’est sélectionné dans le tableau des jeux de données, un panneau sur le côté droit de l’interface Connexions affiche les options et les détails de la connexion.

| Options | Description |
| --- | --- |
| ![Actualiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Actualiser] | Pour actualiser la connexion et permettre la prise en compte des enregistrements récemment ajoutés, sélectionnez ![Actualiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Actualiser]**. |
| ![Supprimer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Supprimer]** | [Supprimez](#delete-a-connection) cette connexion. |
| ![Ajouter une vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Créer une vue de données]** | [Créez une vue de données](#create-a-data-view) basée sur cette connexion. Pour plus d’informations, consultez [Vues de données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/data-views). |
| **[!UICONTROL Nom de la connexion]** | Nom convivial de la connexion. |
| **[!UICONTROL Description de la connexion]** | Description plus détaillée concernant lʼobjectif de cette connexion. |
| **[!UICONTROL Sandbox]** | [Sandbox Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/sandbox/home) à partir duquel cette connexion tire son ou ses jeux de données. Ce sandbox a été sélectionné lorsque vous avez créé la connexion pour la première fois. Il ne peut pas être modifié. |
| **[!UICONTROL ID de connexion]** | Cet identifiant est généré par le système dans Experience Platform. Vous pouvez utiliser ![Copier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) pour copier l’ID. |
| **[!UICONTROL Vues de données utilisant la connexion]** | Répertorie toutes les vues de données qui utilisent cette connexion. |
| **[!UICONTROL Importer de nouvelles données]** | Statut de l’import de nouvelles données pour les jeux de données : <p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _activés]**pour le nombre de jeux de données configurés pour importer de nouvelles données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _x désactivés_]** pour le nombre de jeux de données pour lesquels le nouvel import de données est désactivé. |
| **[!UICONTROL Renvoyer les données]** | Statut des données de renvoi pour les jeux de données.<p>![Statut rouge](assets/status-red.svg) **[!UICONTROL _x _renvois ayant échoué]**pour le nombre de renvois ayant échoué dans les jeux de données,<p>![Statut rouge](assets/status-orange.svg) **[!UICONTROL _x _renvois en cours de traitement]**pour le nombre de renvois en cours de traitement dans les jeux de données,<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _renvois terminés]**pour le nombre de renvois terminés pour les jeux de données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _Désactivé_]** au cas où aucun renvoi n’est défini pour les jeux de données dans la connexion. |
| **[!UICONTROL Transformer les données]** | Statut de transformation des jeux de données de recherche B2B applicables. Voir [Transformer des jeux de données pour les recherches B2B](transform-datasets-b2b-lookups.md) pour plus d’informations.<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _activés]**pour le nombre de jeux de données activés pour la transformation. |
| **[!UICONTROL Créé par]** | Nom de la personne qui a créé la connexion. |
| **[!UICONTROL Dernière modification]** | Date et heure de la dernière modification apportée à la connexion. |
| **[!UICONTROL Dernière modification par]** | Personne ayant modifié la connexion pour la dernière fois. |

#### Panneau du jeu de données

Lorsqu’une ligne de jeu de données est sélectionnée dans le tableau des jeux de données, un panneau situé sur le côté droit de l’interface Connexions affiche les détails du jeu de données sélectionné.

| Détails | Description |
| --- | --- |
| **[!UICONTROL ID de personne]** | Identité qui a été définie dans le schéma du jeu de données dans Experience Platform. Cette identité est lʼID de personne que vous avez choisi lors de la création de la connexion. Si vous créez une connexion qui comprend des jeux de données avec des ID différents, les rapports le reflèteront. Pour fusionner des jeux de données, vous devez utiliser le même ID de personne dans tous les jeux de données. |
| **[!UICONTROL Clé]** | Clé que vous avez spécifiée pour un jeu de données de recherche. |
| **[!UICONTROL Clé correspondante]** | Clé correspondante que vous avez spécifiée pour un jeu de données de recherche. |
| **[!UICONTROL Date et heure]** | Horodatage défini pour un jeu de données d’événement. |
| **[!UICONTROL Enregistrements disponibles]** | Nombre total de lignes ingérées pour ce jeu de données, au cours de la période sélectionnée dans le calendrier. Une fois ajoutées, les données apparaissent dans le compte rendu des performances sans aucune latence. Cependant, lorsque vous créez une toute nouvelle connexion, il y a [latence](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-faq). |
| **[!UICONTROL Enregistrements ajoutés]** | Nombre de lignes ajoutées au cours de la période sélectionnée. |
| **[!UICONTROL Enregistrements supprimés]** | Nombre dʼenregistrements supprimés au cours de la période sélectionnée. |
| **[!UICONTROL Lots ajoutés]** | Nombre de lots de données ajoutés à ce jeu de données. |
| **[!UICONTROL Enregistrements ignorés]** | Nombre de lignes ignorées lors de lʼingestion au cours de la période sélectionnée.<p>Les raisons pour lesquelles des enregistrements sont ignorés sont les suivantes : dates et heures manquantes, ID de personne ou ID de compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} manquant ou non valide, etc. Mise à jour toutes les 10 minutes.<p>Les identifiants non valides (tels que `undefined` ou `00000000`, ou toute combinaison de chiffres et de lettres dans un [!UICONTROL ID de personne] qui apparaît dans un événement plus d’un million de fois au cours d’un mois donné) sont des identifiants qui ne peuvent pas être attribués à un utilisateur ou à une personne spécifique. Ces enregistrements ne peuvent pas être ingérés dans le système et entraînent une ingestion et un compte rendu des performances sujets aux erreurs. Pour corriger les ID de personne ou de compte non valides, vous disposez de 3 options :<ul><li>Utilisez le [groupement](/help/stitching/overview.md) pour renseigner les ID d’utilisateur ou d’utilisatrice non définis ou entièrement composés de zéros avec des ID d’utilisateur ou d’utilisatrice valides.</li><li>Effacez l’ID d’utilisateur ou d’utilisatrice, qui sera également ignoré lors de l’ingestion (préférable aux ID d’utilisateur ou d’utilisatrice non valides ou entièrement composés de zéros).</li><li>Corrigez tout ID d’utilisateur ou d’utilisatrice non valide dans votre système avant d’ingérer les données.</li></ul> |
| **[!UICONTROL Dernier ajout]** | Date et heure auxquelles le dernier lot a été ajouté. |
| **[!UICONTROL Importer de nouvelles données]** | Statut de l’import des nouvelles données pour le jeu de données : <p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _ activés]**si le jeu de données est configuré pour importer de nouvelles données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _x désactivés_]** si le jeu de données est configuré pour ne pas importer de nouvelles données. |
| **[!UICONTROL Renvoyer les données]** | Statut des données de renvoi pour le jeu de données.<p>![Statut rouge](assets/status-red.svg) **[!UICONTROL _x _renvois ayant échoué]**pour le nombre de renvois ayant échoué,<p>![Statut rouge](assets/status-orange.svg) **[!UICONTROL _x _renvois en cours de traitement]**pour le nombre de renvois en cours de traitement,<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _renvois terminés]**pour le nombre de renvois terminés, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _Désactivé_]** au cas où aucun renvoi n’est configuré.<p>Pour afficher une boîte de dialogue avec une vue d’ensemble des renvois précédents pour le jeu de données, sélectionnez <img src="./assets/pastbackfill.svg" alt="Renvois précédents" width="15"/> **[!UICONTROL Renvois précédents]**. |
| **[!UICONTROL Type de source de données]** | Type de source de données tel que défini lors de l’ajout du jeu de données à la connexion. |
| **[!UICONTROL Type de jeu de données]** | [!UICONTROL Événement], [!UICONTROL Profil], [!UICONTROL Recherche] ou [!UICONTROL Synthèse]. [En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-connections/create-connection) |
| **[!UICONTROL Schéma]** | Schéma Experience Platform sur lequel est basé ce jeu de données. |
| **[!UICONTROL Identifiant du jeu de données]** | Cet identifiant de jeu de données est généré dans Experience Platform. |


## Utilisation {#connections-usage}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_keyusagemetrics"
>title="Mesures d’utilisation clés"
>abstract="Elles fournissent des données mensuelles et totales pour les lignes principales et historiques sur lesquelles effectuer des rapports."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyingestedrows"
>title="Lignes ingérées par mois"
>abstract="Cette option mesure le nombre total d’enregistrements ajoutés au système chaque mois pour fournir des informations sur la croissance des données et les taux d’ingestion."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyreportablerows"
>title="Lignes mensuelles sur lesquelles effectuer des rapports"
>abstract="Cette option effectue le suivi du nombre de lignes disponibles pour la création de rapports. Les lignes sur lesquelles effectuer des rapports sont les lignes ingérées moins les lignes ignorées et supprimées lors de l’ingestion. Les lignes sur lesquelles effectuer des rapports servent de mesure clé pour la facturation et l’utilisation des données."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_detailbreakdown"
>title="Répartition détaillée."
>abstract="Vous pouvez afficher les mesures détaillées par connexion, jeu de données, sandbox et balises, avec la possibilité de télécharger un fichier CSV des données."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_otherdatasets"
>title="Autres jeux de données"
>abstract="Pour les mois précédant septembre 2024, les données ont été collectées au niveau des jeux de données et s’affichent sous la forme *Autres jeux de données* par souci de clarté. À compter de septembre 2024, les données sont collectées au niveau d’un jeu de données granulaire et l’option *Autres jeux de données* n’apparaît plus."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_unknowndatasetsorconnections"
>title="Jeux de données ou connexions inconnus"
>abstract="Les jeux de données ou les connexions inconnus s’affichent à l’aide de leurs identifiants."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_datanotavailable"
>title="Données non disponibles"
>abstract="Les données historiques antérieures à septembre 2024 ne sont pas disponibles en raison de limitations du système. Les mesures sont collectées et affichées à partir de septembre 2024. Le graphique affiche les 18 derniers mois de la chronologie et les données futures apparaîtront à mesure que les données seront disponibles."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="Lignes principales à déclarer"
>abstract="Affiche le nombre total de lignes disponibles au cours des 13 derniers mois. Par exemple, le 1er février 2024, le nombre affiche le nombre total de lignes disponibles avec un horodatage d’événement de janvier 2023 à janvier 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="Lignes historiques à déclarer"
>abstract="Affiche le nombre total de lignes disponibles pour la période datant de plus de 13 mois. Par exemple, le 1er février 2024, le nombre affiche le nombre total de lignes disponibles avec un horodatage d’événement antérieur à janvier 2023."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="Mesures d’utilisation clés"
>abstract="Elles fournissent des données mensuelles et totales pour les lignes principales et historiques sur lesquelles effectuer des rapports."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="Lignes ingérées par mois"
>abstract="Cette option mesure le nombre total d’enregistrements ajoutés au système chaque mois pour fournir des informations sur la croissance des données et les taux d’ingestion."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="Lignes mensuelles sur lesquelles effectuer des rapports"
>abstract="Cette option effectue le suivi du nombre de lignes disponibles pour la création de rapports. Les lignes sur lesquelles effectuer des rapports sont les lignes ingérées moins les lignes ignorées et supprimées lors de l’ingestion. Les lignes sur lesquelles effectuer des rapports servent de mesure clé pour la facturation et l’utilisation des données."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="Répartition détaillée."
>abstract="Vous pouvez afficher les mesures détaillées par connexion, jeu de données, sandbox et balises, avec la possibilité de télécharger un fichier CSV des données."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="Autres jeux de données"
>abstract="Pour les mois précédant septembre 2024, les données ont été collectées au niveau des jeux de données et s’affichent sous la forme *Autres jeux de données* par souci de clarté. À compter de septembre 2024, les données sont collectées au niveau d’un jeu de données granulaire et l’option *Autres jeux de données* n’apparaît plus."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="Jeux de données ou connexions inconnus"
>abstract="Les jeux de données ou les connexions inconnus s’affichent à l’aide de leurs identifiants."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="Données non disponibles"
>abstract="Les données historiques antérieures à septembre 2024 ne sont pas disponibles en raison de limitations du système. Les mesures sont collectées et affichées à partir de septembre 2024. Le graphique affiche les 18 derniers mois de la chronologie et les données futures apparaîtront à mesure que les données seront disponibles."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="Lignes principales à déclarer"
>abstract="Affiche le nombre total de lignes disponibles au cours des 13 derniers mois. Par exemple, le 1er février 2024, le nombre affiche le nombre total de lignes disponibles avec un horodatage d’événement de janvier 2023 à janvier 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Lignes historiques à déclarer"
>abstract="Affiche le nombre total de lignes disponibles pour la période datant de plus de 13 mois. Par exemple, le 1er février 2024, le nombre affiche le nombre total de lignes disponibles avec un horodatage d’événement antérieur à janvier 2023."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="Lignes principales à déclarer"
>abstract="Les lignes principales sur lesquelles effectuer des rapports sont des valeurs instantanées et non des totaux agrégés. Ces valeurs sont mises à jour de manière dynamique en fonction du dernier mois de la période sélectionnée. Si un client ou une cliente sélectionne Janvier - Mars, les valeurs reflèteront l’instantané de mars."

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="Lignes historiques à déclarer"
>abstract="Les lignes historiques sur lesquelles effectuer des rapports sont des valeurs instantanées et non des totaux agrégés. Ces valeurs sont mises à jour de manière dynamique en fonction du dernier mois de la période sélectionnée. Si un client ou une cliente sélectionne Janvier - Mars, les valeurs reflèteront l’instantané de mars."

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="Lignes cumulées sur lesquelles effectuer des rapports"
>abstract="Les lignes cumulées sur lesquelles effectuer des rapports sont des valeurs instantanées et non des totaux agrégés. Ces valeurs sont mises à jour de manière dynamique en fonction du dernier mois de la période sélectionnée. Si un client ou une cliente sélectionne Janvier - Mars, les valeurs reflèteront l’instantané de mars."

<!-- markdownlint-enable MD034 -->



L’interface [!UICONTROL Utilisation] indique l’utilisation des lignes ingérées et pouvant faire l’objet d’un rapport sur toutes les connexions. Si cette option n’est pas sélectionnée, sélectionnez l’onglet **[!UICONTROL Utilisation]** pour accéder à l’interface.

Cette interface vous permet de déterminer si votre utilisation de Customer Journey Analytics est conforme aux conditions contractuelles. Outre la surveillance, vous pouvez utiliser l’interface Utilisation pour planifier le renouvellement de votre licence Customer Journey Analytics.

L’interface Utilisation utilise les mesures suivantes :

| Nom de la mesure | Description |
|---|---|
| Lignes historiques à déclarer | Nombre de lignes pour la période de plus de 13 mois. |
| Lignes principales à déclarer | Nombre de lignes au cours des 13 derniers mois. |
| Lignes ingérées | Nombre de lignes ingérées pour la période spécifique. |
| Lignes à déclarer | Nombre de lignes de données que vous avez dans le cadre de la connexion pour la période spécifique. |
| Lignes cumulées | Nombre de lignes ingérées jusqu’au mois spécifique. |

>[!NOTE]
>
>Les données sont collectées à partir de juillet 2024 pour les enregistrements principaux, historiques et totaux. Contactez votre gestionnaire de compte pour obtenir des données historiques antérieures.
>



L’interface Utilisation se compose de deux panneaux :

* Panneau **[!UICONTROL Mesures d’utilisation clés]** : fournit des lignes de données principales et historiques à déclarer. Le panneau effectue également le suivi des modifications en pourcentage par rapport au mois précédent pour les lignes de données principales et historiques.

  Le panneau s’affiche dans une visualisation :

   * **[!UICONTROL Lignes de données principales à déclarer]**

     Nombre de lignes à déclarer au cours des 13 derniers mois. La synthèse des chiffres correspond au nombre de lignes principales à déclarer (par exemple, 741 millions) pour le dernier mois (par exemple, décembre 2024).

   * **[!UICONTROL Lignes de données historiques à déclarer]**

     Nombre de lignes à déclarer pour la période de plus de 13 mois. La synthèse des chiffres correspond au nombre de lignes historiques à déclarer (par exemple, 127 millions) pour le dernier mois (par exemple, décembre 2024).

  Lorsque vous pointez sur une barre empilée dans la visualisation, une fenêtre contextuelle affiche le nombre de lignes de cette partie spécifique de la barre (par exemple).


  ![Mesures d’utilisation clés](assets/usage-key-usage-metrics.png)

* Panneau combiné affichant trois sous-panneaux pour les éléments suivants :

+++ Lignes ingérées

  Le sous-panneau **[!UICONTROL Lignes ingérées]** mesure le nombre total d’enregistrements ajoutés au système chaque mois, ce qui fournit des informations sur la croissance des données et les taux d’ingestion. Le sous-panneau fournit un résumé du nombre total de lignes ingérées de ce mois et de la modification par rapport au mois précédent.

  ![Lignes ingérées](assets/usage-ingested-rows.png)

  Vous pouvez pointer sur des points de données dans la visualisation pour afficher une fenêtre contextuelle contenant plus de détails.

+++

+++ Lignes à déclarer

  La visualisation **[!UICONTROL Lignes à déclarer]** effectue le suivi du nombre de lignes disponibles pour la création de rapports en soustrayant les lignes ignorées et supprimées des lignes ingérées, ce qui sert de mesure clé pour la facturation et l’utilisation des données. Le sous-panneau fournit deux synthèses :

   * **[!UICONTROL Total du mois dernier]** : synthèse du total des lignes à déclarer jusqu’à ce mois.
   * **[!UICONTROL Ce mois-ci]** : synthèse du total des lignes à déclarer de ce mois et de la modification par rapport au mois précédent.

  ![Lignes à déclarer](assets/usage-reportable-rows.png)

  Vous pouvez pointer sur des points de données dans les visualisations pour afficher une fenêtre contextuelle contenant plus de détails.

+++

+++ Répartition des détails

  Vous pouvez utiliser le tableau **[!UICONTROL Répartition des détails]** pour afficher les mesures détaillées par connexion, jeu de données, sandbox et balises. Les jeux de données dont l’objet de rapports à l’aide d’identifiants plutôt que de noms, car les noms des jeux de données peuvent être modifiés pendant une période de création de rapports. Les jeux de données ou les connexions inconnus font l’objet de rapport via leurs identifiants.

  Pour les mois précédant septembre 2024, les données ont été collectées au niveau des jeux de données et s’affichent sous la forme [!UICONTROL Autres jeux de données] par souci de clarté. À compter de septembre 2024, les données sont collectées au niveau d’un jeu de données granulaire et l’option [!UICONTROL Autres jeux de données] n’apparaît plus.

   * Pour modifier la répartition, sélectionnez une combinaison pour **[!UICONTROL Afficher par]** et **[!UICONTROL Répartir par]**.

     | Options **[!UICONTROL Afficher par]** | Options **[!UICONTROL Répartir par]** |
     |---|---|
     | **[!UICONTROL Connexion]** | **[!UICONTROL -]** et **[!UICONTROL jeu de données]** |
     | **[!UICONTROL Jeu de données]** | **[!UICONTROL -]** |
     | **[!UICONTROL Sandbox]** | **[!UICONTROL Connexion]** |
     | **[!UICONTROL Étiquette]** | **[!UICONTROL Connexion]** |

  ![Répartition des détails](assets/usage-detail-breakdown.png)

+++

  Vous pouvez définir une **[!UICONTROL Période]** en mois pour créer un rapport. Utilisez ![Calendrier](/help/assets/icons/Calendar.svg) pour sélectionner la période.

>[!MORELIKETHIS]
>
>Tutoriel [Afficher, résoudre les problèmes et modifier les paramètres de connexion](https://experienceleague.adobe.com/fr/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja).
>[Gérez l’utilisation de Customer Journey Analytics](/help/technotes/estimate-usage.md)
>
