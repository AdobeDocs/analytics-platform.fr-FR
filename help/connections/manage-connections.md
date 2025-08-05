---
title: Comment gérer les connexions dans Customer Journey Analytics
description: Décrit la manière de gérer des connexions aux jeux de données Experience Platform dans Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 27e09c893c45f445d9344c1cc5132960060bf032
workflow-type: tm+mt
source-wordcount: '4606'
ht-degree: 63%

---

# Gérer des connexions {#manage-connections}

>[!CONTEXTUALHELP]
>id="connections_use_ajo"
>title="Utiliser la connexion Journey Optimizer"
>abstract="Tire parti des fonctionnalités avancées de création de rapports de Customer Journey Analytics avec Journey Optimizer."

>[!CONTEXTUALHELP]
>id="connections_cancel_ajo"
>title="Annuler la connexion Journey Optimizer"
>abstract="Annule les fonctionnalités avancées de création de rapports de Customer Journey Analytics avec Journey Optimizer."


Une fois que vous avez [créé ou modifié une ou plusieurs connexions](/help/connections/create-connection.md), vous pouvez les gérer dans **[!UICONTROL Connexions]**. L’interface [!UICONTROL Connexions] vous permet d’effectuer les opérations suivantes :

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

L’interface **[!UICONTROL Liste]** est l’interface par défaut pour Connexions. Si cette option n’est pas sélectionnée, sélectionnez l’onglet **[!UICONTROL Liste]** pour accéder à l’interface.

![Vue en liste](assets/list-view.png)

L’interface [!UICONTROL Liste] affiche un tableau de toutes les connexions disponibles.

### Rechercher une connexion

Vous pouvez rechercher rapidement une connexion à l’aide de la zone Rechercher ![Rechercher](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

### Appliquer un filtre sur la liste des connexions

Pour appliquer un filtre à la liste des connexions, sélectionnez l&#39;icône de filtre puis choisissez l&#39;une des options de filtre suivantes :

| Option de filtre | Description |
|---------|----------|
| **[!UICONTROL Jeux de données]** | Seules les connexions associées aux jeux de données que vous sélectionnez s’affichent. |
| **[!UICONTROL Propriétaire]** | Seules les connexions appartenant aux personnes que vous sélectionnez s’affichent. |
| **[!UICONTROL Sandbox]** | Seules les connexions disponibles dans les sandbox que vous sélectionnez s’affichent. |
| **[!UICONTROL Utilisation dans CJA]** | Sélectionnez **[!UICONTROL Activé]** pour afficher uniquement les connexions activées pour une utilisation avec Customer Journey Analytics. Sélectionnez **[!UICONTROL Désactivé]** pour afficher uniquement les connexions qui ne sont pas encore activées pour une utilisation avec Customer Journey Analytics. |

### Colonnes disponibles

Les colonnes ou icônes suivantes sont disponibles dans le tableau.

| Colonne ou icône | Description |
| --- | --- |
| **[!UICONTROL _Nom_]** | Nom convivial de la connexion. Sélectionnez le nom du lien hypertexte pour afficher les [détails de la connexion](#connection-details). |
| ![Informations](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Pour afficher des informations sur [!UICONTROL Jeux de données inclus], [!UICONTROL Sandbox], [!UICONTROL Propriétaire], etc., sélectionnez ![Informations](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) en regard du nom de la connexion.<p>Une fenêtre contextuelle affiche des détails sur le jeu de données. <p>![Fenêtre contextuelle d’informations de connexion](assets/connection-info-popup.png) |
| ![Vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Pour [créer une vue de données](#create-a-data-view) pour la connexion, sélectionnez ![Vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). Cette icône s’affiche uniquement lorsqu’aucune vue de données n’est déjà associée à la connexion. |
| ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Sélectionnez ![ Plus ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) pour ouvrir un menu contextuel. Vous pouvez sélectionner : <p>![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier]** pour [modifier](#edit-a-connection) une connexion.<p>![Supprimer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Supprimer]** pour [supprimer](#delete-a-connection) une connexion.<p>![Vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Créer une vue de données]** pour [créer une vue de données](#create-a-data-view) pour la connexion.<p>![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL mappage de connexion]** pour afficher un [mappage de connexion](#map-a-connection) pour la connexion. |
| [!BADGE Type de connexion &#x200B;]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL &#x200B; B2B edition &#x200B;]** | Type de connexion : connexion basée sur **[!UICONTROL Personne]** ou **[!UICONTROL Compte]**. |
| **[!UICONTROL Jeux de données]** | Un ou plusieurs liens vers les jeux de données qui font partie de la connexion. Vous pouvez sélectionner le lien hypertexte du jeu de données pour afficher le jeu de données dans la connexion. Si d’autres jeux de données font partie de la connexion sélectionnée, sélectionnez **[!UICONTROL +*x* plus]** pour afficher un panneau **[!UICONTROL Jeux de données inclus]**. Ce panneau affiche des liens vers tous les jeux de données et une option permettant de ![Rechercher](/help/assets/icons/Search.svg) rechercher des jeux de données spécifiques qui font partie de la connexion.<p>![ Jeux de données inclus ](assets/datasets-included.png)<p>Sélectionnez un nom de jeu de données pour l’ouvrir dans un nouvel onglet de l’interface d’Experience Platform. |
| **[!UICONTROL Sandbox]** | [Sandbox Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/sandbox/home) dʼoù cette connexion tire ses jeux de données. Vous sélectionnez ce sandbox lorsque vous avez créé la connexion. Vous ne pouvez pas modifier le sandbox une fois qu’une connexion est enregistrée. |
| **[!UICONTROL Propriétaire]** | Personne qui a créé la connexion. |
| **[!UICONTROL Importer de nouvelles données]** | Statut de l’import de nouvelles données pour les jeux de données : <p>![Statut vert](assets/status-green.svg)   **[!UICONTROL _x _On]**&#x200B;pour les jeux de données configurés afin d’importer de nouvelles données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _x désactivés_]** pour les jeux de données non configurés pour importer de nouvelles données. |
| **[!UICONTROL Date de création]** | Date et heure auxquelles la connexion a été créée. |
| **[!UICONTROL Dernière modification]** | Date et heure de la dernière mise à jour de la connexion. |
| **[!UICONTROL Renvoyer les données]** | Statut des données de renvoi dans les jeux de données.<p>![Statut rouge](assets/status-red.svg) **[!UICONTROL _x _renvois ont échoué]**&#x200B;pour le nombre de renvois ayant échoué dans les jeux de données,<p>![Statut orange](assets/status-orange.svg) **[!UICONTROL _x _ renvois en cours de traitement]**&#x200B;pour le nombre de renvois en cours de traitement dans les jeux de données,<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _ renvois terminés]**&#x200B;pour le nombre de renvois terminés pour les jeux de données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _Désactivé_]** au cas où aucun renvoi n’est défini pour les jeux de données dans la connexion. |
| **[!UICONTROL Intégrations]** | Affiche toutes les applications Experience Platform activées avec la connexion. |
| **[!UICONTROL Utilisation dans CJA]** | Indique si la connexion a été activée pour une utilisation avec Customer Journey Analytics. |

Pour configurer les colonnes à afficher dans le tableau, sélectionnez ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Dans la boîte de dialogue Personnaliser le tableau , sélectionnez les colonnes à afficher.

### Modifier une connexion

Pour modifier une connexion, procédez comme suit :

1. Sélectionnez ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) en regard du nom de la connexion.
1. Sélectionnez ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier]** dans le menu contextuel.

Vous pouvez également effectuer les opérations suivantes :

1. Sélectionnez la ligne de connexion.

1. Sélectionnez ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier]** dans la barre d’actions bleue.

Consultez [Créer ou modifier une connexion](create-connection.md) pour plus d’informations.


### Supprimer une connexion {#connections-delete}

Pour supprimer une connexion, procédez comme suit :

1. Sélectionnez ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) en regard du nom de la connexion.
1. Sélectionnez ![Supprimer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Supprimer]**.

Vous pouvez également effectuer les opérations suivantes :

1. Sélectionnez la ligne de connexion.

1. Sélectionnez ![Supprimer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Supprimer]** dans la barre d’actions bleue.

Lorsque vous supprimez une connexion, un panneau **[!UICONTROL Supprimer la connexion]** indique quelles vues de données sont supprimées et quels projets d’espace de travail sont affectés.

* Dans ➊ **[!UICONTROL Info]**, les implications de la suppression de la connexion s’affichent.

  ![Supprimer la connexion](assets/delete-connection.png)

  Sélectionnez **[!UICONTROL Continuer]** pour confirmer la suppression.

* Dans ➋ **[!UICONTROL Confirmation]**, saisissez le nom de la connexion dans **[!UICONTROL Saisir le nom de la connexion]**, puis sélectionnez **[!UICONTROL Supprimer]** pour supprimer la connexion. Sélectionnez **[!UICONTROL Annuler]** pour annuler.

Pour plus d’informations sur la suppression d’une connexion, consultez [Conséquences de la suppression](/help/technotes/deletion.md).


### Créer une vue de données à partir d’une connexion

Pour créer une vue de données pour une connexion :

1. Sélectionnez ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) en regard du nom de la connexion.
1. Sélectionnez ![Ajouter une vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Créer une vue de données]**.

Vous pouvez également effectuer les opérations suivantes :

1. Sélectionnez la ligne de connexion.

1. Sélectionnez ![Ajouter une vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Créer une vue de données]** dans la barre d’actions bleue.

Consultez [Créer ou modifier une vue de données](/help/data-views/create-dataview.md) pour plus d’informations.

### Utiliser une connexion Journey Optimizer dans Customer Journey Analytics {#use-connection-in-cja}

>[!IMPORTANT]
>
>Lorsque vous activez une connexion Journey Optimizer à utiliser avec Customer Journey Analytics comme décrit dans cette section, chaque ligne de données de la connexion est comptabilisée dans les lignes de données sous licence chaque mois pour Customer Journey Analytics et apparaît dans l’interface utilisateur d’utilisation des connexions. Sélectionnez l’option **[!UICONTROL Utiliser dans CJA]** sur la connexion uniquement si vous êtes à l’aise avec l’utilisation supplémentaire de Lignes de données dans Customer Journey Analytics.
>
>**Si vous aviez droit à Customer Journey Analytics et Journey Optimizer entre octobre 2024 et octobre 2025, consultez le document suivant concernant les [Connexions activées pour AJO](https://view.adobe.com/viewer/1ed94fc35c7860b260766c620889e7a0#1)**.

Vous pouvez utiliser une connexion Journey Optimizer dans Customer Journey Analytics pour apporter la valeur supplémentaire suivante à votre connexion :

* Effectuez une analyse approfondie des données Journey Optimizer dans Customer Journey Analytics (à l’aide du bouton **[!UICONTROL Analyser dans CJA]** dans Journey Optimizer).

  Pour plus d’informations, voir [Analyser dans Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/channel-report/report-cja-manage#cja-template) dans la documentation de Journey Optimizer.

* Modifiez la connexion Journey Optimizer et les vues de données associées.

  Pour plus d’informations sur la modification des options, voir [Modifier une connexion](#edit-a-connection).

Pour activer cette fonctionnalité, votre entreprise doit avoir accès à Customer Journey Analytics. Si vous n’y avez pas accès, contactez votre représentant commercial Adobe.

Une fois que vous avez accès à Customer Journey Analytics, vous devez autoriser l’utilisation de la connexion Journey Optimizer dans Customer Journey Analytics :

1. Recherchez la connexion Journey Optimizer à utiliser avec Customer Journey Analytics.

   1. Sélectionnez l’icône Filtre dans l’onglet **[!UICONTROL Connexions]**.

   1. Dans la section **[!UICONTROL Utiliser dans CJA]**, sélectionnez **[!UICONTROL Désactivé]**.

      Toutes les connexions qui ne sont pas actuellement configurées pour être utilisées dans Customer Journey Analytics s’affichent.

   1. Sélectionnez la connexion Journey Optimizer à utiliser dans Customer Journey Analytics.

1. Dans la connexion Journey Optimizer, sélectionnez **[!UICONTROL Utiliser dans CJA]**.

   La boîte de dialogue suivante **[!UICONTROL Utiliser cette connexion dans Customer Journey Analytics]** s’affiche :

   <!-- add screenshot -->

1. Activez le bouton (bascule) **[!UICONTROL Utiliser la connexion dans CJA]**.

1. Sélectionnez **[!UICONTROL Utiliser la connexion]**. <!-- double-check these dialog button names -->

#### Supprimer la connexion de Customer Journey Analytics {#remove-connection-in-cja}

Vous pouvez supprimer la connexion Journey Optimizer de Customer Journey Analytics à tout moment. Toutefois, la suppression de la connexion de Customer Journey Analytics après son utilisation entraîne les éléments suivants :

* La connexion Journey Optimizer et les vues de données associées sont réinitialisées à leur état par défaut et ne peuvent plus être modifiées

* Tous les champs dérivés personnalisés associés à la connexion sont supprimés

* Vous ne pouvez plus effectuer d’analyse approfondie des données Journey Optimizer dans Customer Journey Analytics

  Cela signifie que le bouton **[!UICONTROL Analyser dans CJA]** dans Journey Optimizer est désactivé

>[!IMPORTANT]
>
>La facturation de la connexion dans Customer Journey Analytics inclut le mois complet au cours duquel la connexion est supprimée.


Pour supprimer la connexion de Customer Journey Analytics :

1. Lors de la modification d’une connexion Journey Optimizer, sélectionnez **[!UICONTROL Supprimer de CJA]**.

   La boîte de dialogue **[!UICONTROL Supprimer cette connexion de Customer Journey Analytics]** suivante s’affiche :

   <!-- add screenshot -->

1. Désactivez l’option **[!UICONTROL Supprimer la connexion de CJA]**.

1. Sélectionnez **[!UICONTROL Supprimer la connexion]**.

### Créer une carte de connexion

Pour afficher une [carte de la connexion](/help/connections/create-connection.md#connection-map) qui détaille les relations entre ses jeux de données :

1. Sélectionnez ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) en regard du nom de la connexion.
1. Sélectionnez ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Carte de la connexion]**.

### Détails de la connexion {#connection-detail}

Pour accéder aux détails d’une connexion, sélectionnez un nom de connexion lié par un lien hypertexte dans le tableau des connexions.

![Fenêtre Tous les jeux de données présentant les widgets et les paramètres](assets/conn-details.png)

L’interface Détails des connexions vous offre une vue très détaillée du statut dʼune connexion. Vous pouvez :

* Vérifier le statut des jeux de données de votre connexion et du processus dʼingestion.
* Identifiez les problèmes de configuration qui provoquent des enregistrements ignorés ou supprimés.
* Voir quand les données sont disponibles pour le compte rendu des performances.

| Interface utilisateur | Description |
| --- | --- |
| ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier la connexion]** | Pour modifier les détails d’une connexion, sélectionnez ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier la connexion]**. Consultez [Créer ou modifier une connexion](create-connection.md) pour plus d’informations. |
| **[!UICONTROL *Sélecteur de jeu de données *]** | Sélectionnez un ou tous les jeux de données pour lesquels afficher les détails dans la connexion. Vous ne pouvez pas sélectionner plusieurs jeux de données. La valeur par défaut est **[!UICONTROL Tous les jeux de données]**. |
| **[!UICONTROL *Sélecteur de périodes *]** | Sélectionnez une plage de données pour laquelle afficher les détails dans la connexion. Modifiez la date de début ou de fin, ou sélectionnez ![Calendrier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) pour ouvrir le sélecteur de période. Dans le sélecteur de période, sélectionnez une période à l’aide de l’une des périodes prédéfinies (par exemple, **[!UICONTROL 6 derniers mois]**) ou utilisez le calendrier pour sélectionner les dates de début et de fin. Sélectionnez **[!UICONTROL Appliquer]** pour appliquer la nouvelle période aux détails de la connexion. |
| **[!UICONTROL Enregistrements de données d’événement disponibles]** | Affiche le nombre total de lignes de jeux de données dʼévénement disponibles pour la création de rapports, **sur lʼensemble de la connexion**. Ce nombre est indépendant de toute période ou sélection de jeu de données. |
| [!UICONTROL **[!UICONTROL Mesures]**] | Résumez les enregistrements de jeux de données d’événement, de recherche, de profil et de synthèse qui sont ajoutés, ignorés et supprimés, ainsi que le nombre de lots ajoutés. Ces mesures sont basées sur **le jeu de données et la période que vous avez sélectionnés**.<p>Sélectionnez **[!UICONTROL Vérifier les détails]** pour afficher la fenêtre contextuelle **[!UICONTROL Vérifier les détails ignorés]**. La fenêtre contextuelle répertorie le nombre d’enregistrements ignorés et la raison pour tous les jeux de données d’événement ou du jeu de données sélectionné.<p>![Enregistrements ignorés](assets/skipped-records.png)<p>Sélectionnez la fenêtre contextuelle ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) avec plus d’informations. Pour certaines raisons ignorées, comme [!UICONTROL ID de visiteur vide], la fenêtre contextuelle affiche **[!UICONTROL Exemple de PSQL pour EQS]** (Experience Platform pour Query Service) que vous pouvez utiliser dans [Query Service](https://experienceleague.adobe.com/fr/docs/experience-platform/query/home) pour rechercher les enregistrements ignorés dans le jeu de données. Sélectionnez ![Copier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copier l’exemple de PSQL pour EQS]** pour copier le code SQL. |
| **[!UICONTROL Enregistrements ajoutés]** | Une visualisation qui indique le nombre de lignes ajoutées au cours de la période sélectionnée, **pour le jeu de données et la période sélectionnés**. Mises à jour toutes les 10 minutes. |
| **[!UICONTROL Enregistrements ignorés]** | Une visualisation indiquant le nombre de lignes ignorées au cours de la période sélectionnée, **pour le jeu de données et la période sélectionnés**. Les raisons pour lesquelles des enregistrements sont ignorés sont les suivantes : dates et heures manquantes, ID de personne ou ID de compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} manquant ou non valide, etc. Mises à jour toutes les 10 minutes. <p>Un ID non valide (par exemple, `undefined` ou `00000000` ou toute combinaison de nombres et de lettres dans un [!UICONTROL ID de personne] qui apparaît dans un événement plus d’un million de fois au cours d’un mois) ne peut pas être attribué à un utilisateur ou une utilisatrice ou à une personne spécifique. Ces lignes ne peuvent pas être ingérées dans le système et entraînent une ingestion et un reporting sujets aux erreurs. Pour corriger les ID de personne ou de compte non valides [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, vous disposez de 3 options :<ul><li>Utilisez le [Groupement](/help/stitching/overview.md) pour renseigner les ID d’utilisateur ou d’utilisatrice non définis ou composés entièrement de zéros avec des ID d’utilisateur ou d’utilisatrice valides.</li><li>Videz les ID utilisateur, qui sont ensuite ignorés lors de l’ingestion (préférable aux ID utilisateur non valides ou entièrement nuls).</li><li>Corrigez tout ID d’utilisateur ou d’utilisatrice non valide dans votre système avant d’ingérer les données.</li></ul> |
| **[!UICONTROL Enregistrements supprimés]** | Une visualisation qui indique le nombre de lignes supprimées au cours de la période sélectionnée, **pour le jeu de données et la période sélectionnés**. Une personne peut avoir supprimé un jeu de données dans [!DNL Experience Platform], par exemple. Mises à jour toutes les 10 minutes.<p>Dans certains scénarios, cette valeur peut également inclure des enregistrements remplacés, comme avec le groupement ou certaines mises à jour des jeux de données de recherche. Prenons cet exemple :</p><ul><li>Vous chargez un enregistrement dans un jeu de données de profil individuel XDM, que Customer Journey Analytics est configuré pour ingérer en tant que données de recherche de profil. Dans les détails de la connexion, ce jeu de données affiche 1 enregistrement ajouté.</li><li>Vous chargez un doublon de l’enregistrement d’origine dans le même jeu de données AEP, qui contient désormais deux enregistrements. Customer Journey Analytics ingère l’enregistrement supplémentaire à partir du jeu de données de recherche du profil ou du compte [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}. Puisqu’un enregistrement de profil ou de compte est déjà ingéré dans la connexion pour cet ID de personne ou de compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, Customer Journey Analytics supprime sa version antérieure et ajoute les nouvelles données de profil. Dans les détails de la connexion, cette action représenterait 1 enregistrement ajouté et 1 enregistrement supprimé, car Customer Journey Analytics ne conserve que les données de recherche de profil les plus récentes pour tout ID de personne ou ID de compte ingéré [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}.</li><li>Au total, le jeu de données AEP contient deux enregistrements qui se trouvent être identiques. Séparément, les détails de la connexion Customer Journey Analytics affichent le statut de ses données ingérées : 2 enregistrements ajoutés et 1 enregistrement supprimé pour ce jeu de données de profil. </li></ul> |
| ![Recherche](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Champ de recherche de jeux de données. Vous pouvez rechercher le tableau des jeux de données par nom ou par identifiant de jeu de données. |
| [!UICONTROL Tableau des jeux de données] | Jeux de données qui font partie de la connexion. Voir le tableau ci-dessous pour plus d’explications. Sélectionnez ![SelectBox](/help/assets/icons/SelectBox.svg) un seul jeu de données pour afficher uniquement les détails de connexion du jeu de données sélectionné. Cela équivaut à sélectionner un jeu de données à partir du **[!UICONTROL _sélecteur de jeu de données_]**. |

Le tableau des jeux de données affiche les colonnes suivantes pour chaque jeu de données :

| Colonne | Description |
| --- | --- |
| **[!UICONTROL Jeux de données]** | Nom du jeu de données. Vous pouvez sélectionner le lien hypertexte pour ouvrir le jeu de données dans l’interface d’utilisation d’Experience Platform dans un nouvel onglet. Vous pouvez sélectionner la ligne ou la case à cocher pour afficher les détails du jeu de données sélectionné uniquement. |
| **[!UICONTROL Identifiant du jeu de données]** | Identifiant du jeu de données, généré par Experience Platform. |
| **[!UICONTROL Enregistrements ajoutés]** | Le nombre d’enregistrements du jeu de données (lignes) ajoutés à une connexion au cours de la période sélectionnée. |
| **[!UICONTROL Enregistrements ignorés]** | Le nombre d’enregistrements de jeux de données (lignes) ignorés pendant un transfert de données pour une connexion pendant la période sélectionnée. |
| **[!UICONTROL Enregistrements supprimés]** | Le nombre d’enregistrements du jeu de données (lignes) supprimés d’une connexion pendant la période sélectionnée. |
| **[!UICONTROL Lots ajoutés]** | Nombre de lots qui ont été ajoutés à une connexion au cours de la période sélectionnée. |
| **[!UICONTROL Dernier ajout]** | La date et l’heure du dernier lot ajouté à une connexion. |
| **[!UICONTROL Type de source de données]** | Type de source. Vous définissez le type de source lorsque vous ajoutez un jeu de données à une connexion. |
| **[!UICONTROL Type de jeu de données]** | Le [ type de jeu de données ](create-connection.md#dataset-types). Le type peut être [!UICONTROL Événement], [!UICONTROL Profil], [!UICONTROL Recherche] ou [!UICONTROL Résumé]. |
| **[!UICONTROL Schéma]** | Schéma Experience Platform sur lequel est basé ce jeu de données. |
| **[!UICONTROL Importer de nouvelles données]** | Statut de l’import des nouvelles données pour le jeu de données : <p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _ activés]**&#x200B;si le jeu de données est configuré pour importer de nouvelles données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _x désactivés_]** si le jeu de données est configuré pour ne pas importer de nouvelles données. |
| **[!UICONTROL Transformer les données]** | Statut de transformation des jeux de données de recherche B2B applicables. Voir [Transformer des jeux de données pour les recherches B2B](transform-datasets-b2b-lookups.md) pour plus d’informations.<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _activés]**&#x200B;pour les jeux de données applicables activés pour la transformation, <p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _x désactivés_]** pour les jeux de données applicables non activés pour la transformation, et<p>**[!UICONTROL N/A]** pour tous les autres jeux de données, non applicables pour la transformation. |
| **[!UICONTROL Renvoyer les données]** | Statut des données de renvoi pour le jeu de données.<p>![Statut rouge](assets/status-red.svg) **[!UICONTROL _x _renvois ayant échoué]**&#x200B;pour le nombre de renvois ayant échoué,<p>![Statut rouge](assets/status-orange.svg) **[!UICONTROL _x _renvois en cours de traitement]**&#x200B;pour le nombre de renvois en cours de traitement,<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _renvois terminés]**&#x200B;pour le nombre de renvois terminés, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _Désactivé_]** au cas où les renvois ne sont pas configurés. |

>[!IMPORTANT]
>
>Les données ingérées avant le 13 août 2021 ne sont pas reflétées dans l’interface [!UICONTROL Connexions].
>

#### Panneau Connexion

Lorsqu’aucun jeu de données individuel n’est sélectionné dans le tableau des jeux de données, le panneau de droite affiche les options et les détails de la connexion.

| Options | Description |
| --- | --- |
| ![Actualiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Actualiser]** | Pour actualiser la connexion et permettre la prise en compte des enregistrements récemment ajoutés, sélectionnez ![Actualiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Actualiser]**. |
| ![Supprimer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Supprimer]** | [Supprimez](#delete-a-connection) cette connexion. |
| ![Ajouter une vue de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Créer une vue de données]** | [Créez une vue de données](#create-a-data-view) basée sur cette connexion. Pour plus d’informations, consultez [Vues de données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/data-views). |
| **[!UICONTROL Utilisation dans CJA]** | Utilisez une connexion Journey Optimizer dans Customer Journey Analytics pour ajouter de la valeur à votre connexion Journey Optimizer. Pour plus d’informations, voir [Utiliser une connexion Journey Optimizer dans Customer Journey Analytics](#use-a-journey-optimizer-connection-in-customer-journey-analytics). |
| **[!UICONTROL Nom de la connexion]** | Nom convivial de la connexion. |
| **[!UICONTROL Description de la connexion]** | Description plus détaillée concernant lʼobjectif de cette connexion. |
| **[!UICONTROL Sandbox]** | [Sandbox Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/sandbox/home) dʼoù cette connexion tire ses jeux de données. Vous sélectionnez ce sandbox lorsque vous avez créé la connexion. Vous ne pouvez pas modifier le sandbox une fois qu’une connexion est enregistrée. |
| **[!UICONTROL ID de connexion]** | Identifiant généré pour la connexion. Vous pouvez utiliser ![Copier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) pour copier la valeur. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Type d’ID de Principal &#x200B;]** | Type d’identifiant principal pour la connexion : **[!UICONTROL Personne]** pour une connexion basée sur une personne, **[!UICONTROL Compte]** pour une connexion basée sur un compte. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Containers &#x200B;]** | Conteneurs configurés pour la connexion. |
| **[!UICONTROL Vues de données utilisant la connexion]** | Vues de données qui utilisent cette connexion. |
| **[!UICONTROL Importer de nouvelles données]** | Statut de l’import de nouvelles données pour les jeux de données : <p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _activés]**&#x200B;pour le nombre de jeux de données configurés pour importer de nouvelles données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _x désactivés_]** pour le nombre de jeux de données pour lesquels le nouvel import de données est désactivé. |
| **[!UICONTROL Renvoyer les données]** | Statut des données de renvoi pour les jeux de données.<p>![Statut rouge](assets/status-red.svg) **[!UICONTROL _x _renvois ayant échoué]**&#x200B;pour le nombre de renvois ayant échoué dans les jeux de données,<p>![Statut rouge](assets/status-orange.svg) **[!UICONTROL _x _renvois en cours de traitement]**&#x200B;pour le nombre de renvois en cours de traitement dans les jeux de données,<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _renvois terminés]**&#x200B;pour le nombre de renvois terminés pour les jeux de données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _Désactivé_]** au cas où aucun renvoi n’est défini pour les jeux de données dans la connexion. |
| **[!UICONTROL Transformer les données]** | Statut de transformation des jeux de données de recherche B2B applicables. Voir [Transformer des jeux de données pour les recherches B2B](transform-datasets-b2b-lookups.md) pour plus d’informations.<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _activés]**&#x200B;pour le nombre de jeux de données activés pour la transformation. |
| **[!UICONTROL Créé par]** | Nom de la personne qui a créé la connexion. |
| **[!UICONTROL Dernière modification]** | Date et heure de la dernière modification apportée à la connexion. |
| **[!UICONTROL Dernière modification par]** | Nom de la personne qui a modifié la connexion pour la dernière fois. |

#### Panneau du jeu de données

Lorsqu’une ligne de jeu de données est sélectionnée dans le tableau des jeux de données, un panneau situé sur le côté droit de l’interface Connexions affiche les détails du jeu de données sélectionné.

| Détails | Description |
| --- | --- |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL ID de compte global &#x200B;]** | Identité que vous avez spécifiée comme ID de compte global pour la connexion. Applicable uniquement pour une connexion basée sur un compte pour laquelle un conteneur Compte global est configuré. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL ID de compte &#x200B;]** | Identité que vous avez spécifiée comme ID de compte pour la connexion. Applicable uniquement pour une connexion basée sur un compte pour laquelle aucun conteneur de compte global n’est configuré. |
| **[!UICONTROL ID de personne]** | Identité que vous avez spécifiée comme ID de personne pour la connexion. |
| **[!UICONTROL Clé]** | Clé que vous avez spécifiée pour un jeu de données de recherche. |
| **[!UICONTROL Clé correspondante]** | Clé correspondante que vous avez spécifiée pour un jeu de données de recherche. |
| **[!UICONTROL Date et heure]** | Horodatage défini pour un jeu de données d’événement. |
| **[!UICONTROL Enregistrements disponibles]** | Nombre total de lignes ingérées pour ce jeu de données, au cours de la période sélectionnée dans le calendrier. Une fois ajoutées, les données apparaissent dans le compte rendu des performances sans aucune latence. Cependant, lorsque vous créez une toute nouvelle connexion, il y a [latence](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-faq). |
| **[!UICONTROL Enregistrements ajoutés]** | Le nombre d’enregistrements du jeu de données (lignes) ajoutés à une connexion au cours de la période sélectionnée. |
| **[!UICONTROL Enregistrements ignorés]** | Le nombre d’enregistrements de jeux de données (lignes) ignorés pendant un transfert de données pour une connexion pendant la période sélectionnée. |
| **[!UICONTROL Lots ajoutés]** | Nombre de lots qui ont été ajoutés à une connexion. |
| **[!UICONTROL Enregistrements supprimés]** | Le nombre d’enregistrements du jeu de données (lignes) supprimés d’une connexion pendant la période sélectionnée. |
| **[!UICONTROL Dernier ajout]** | La date et l’heure du dernier lot ajouté à une connexion. |
| **[!UICONTROL Importer de nouvelles données]** | Statut de l’import des nouvelles données pour le jeu de données : <p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _ activés]**&#x200B;si le jeu de données est configuré pour importer de nouvelles données, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _x désactivés_]** si le jeu de données est configuré pour ne pas importer de nouvelles données. |
| **[!UICONTROL Renvoyer les données]** | Statut des données de renvoi pour le jeu de données.<p>![Statut rouge](assets/status-red.svg) **[!UICONTROL _x _renvois ayant échoué]**&#x200B;pour le nombre de renvois ayant échoué,<p>![Statut rouge](assets/status-orange.svg) **[!UICONTROL _x _renvois en cours de traitement]**&#x200B;pour le nombre de renvois en cours de traitement,<p>![Statut vert](assets/status-green.svg) **[!UICONTROL _x _renvois terminés]**&#x200B;pour le nombre de renvois terminés, et<p>![Statut gris](assets/status-gray.svg) **[!UICONTROL _Désactivé_]** au cas où aucun renvoi n’est configuré.<p>Pour afficher une boîte de dialogue avec une vue d’ensemble des renvois précédents pour le jeu de données, sélectionnez <img src="./assets/pastbackfill.svg" alt="Renvois précédents" width="15"/> **[!UICONTROL Renvois précédents]**. |
| **[!UICONTROL Type de source de données]** | Type de source de données tel que défini lorsque le jeu de données a été ajouté à la connexion. |
| **[!UICONTROL Type de jeu de données]** | Le [ type de jeu de données ](create-connection.md#dataset-types). |
| **[!UICONTROL Schéma]** | Schéma Experience Platform sur lequel est basé ce jeu de données. |
| **[!UICONTROL Identifiant du jeu de données]** | Identifiant du jeu de données tel qu’il est généré dans Experience Platform. |


## Utilisation {#connections-usage}

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="Mesures d’utilisation clés"
>abstract="Elles fournissent des données mensuelles et totales pour les lignes principales et historiques sur lesquelles effectuer des rapports."

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="Lignes ingérées par mois"
>abstract="Cette option mesure le nombre total d’enregistrements ajoutés au système chaque mois pour fournir des informations sur la croissance des données et les taux d’ingestion."

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="Lignes mensuelles sur lesquelles effectuer des rapports"
>abstract="Cette option effectue le suivi du nombre de lignes disponibles pour la création de rapports. Les lignes sur lesquelles effectuer des rapports sont les lignes ingérées moins les lignes ignorées et supprimées lors de l’ingestion. Les lignes sur lesquelles effectuer des rapports servent de mesure clé pour la facturation et l’utilisation des données."

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="Répartition détaillée."
>abstract="Vous pouvez afficher les mesures détaillées par connexion, jeu de données, sandbox et balises, avec la possibilité de télécharger un fichier CSV des données."

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="Autres jeux de données"
>abstract="Pour les mois précédant septembre 2024, les données ont été collectées au niveau des jeux de données et s’affichent sous la forme *Autres jeux de données* par souci de clarté. À compter de septembre 2024, les données sont collectées au niveau d’un jeu de données granulaire et l’option *Autres jeux de données* n’apparaît plus."

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="Jeux de données ou connexions inconnus"
>abstract="Les jeux de données ou les connexions inconnus s’affichent à l’aide de leurs identifiants."

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="Données non disponibles"
>abstract="Les données historiques antérieures à septembre 2024 ne sont pas disponibles en raison de limitations du système. Les mesures sont collectées et affichées à partir de septembre 2024. Le graphique affiche les 18 derniers mois de la chronologie et les données futures apparaissent à mesure que les données sont disponibles."

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="Lignes principales à inclure dans un rapport"
>abstract="Nombre total de lignes disponibles au cours des 13 derniers mois. Par exemple, le 1er février 2024, le nombre affiche le nombre total de lignes disponibles avec un horodatage d’événement de janvier 2023 à janvier 2024."

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Lignes historiques à inclure dans un rapport"
>abstract="Nombre total de lignes disponibles pour la période datant de plus de 13 mois. Par exemple, le 1er février 2024, le nombre affiche le nombre total de lignes disponibles avec un horodatage d’événement antérieur à janvier 2023."


>[!CONTEXTUALHELP]
>id="connections_averagerowsize"
>title="Taille moyenne des lignes"
>abstract="Taille moyenne d’une ligne de données pour le mois en cours avec une modification en pourcentage par rapport au mois précédent."


>[!CONTEXTUALHELP]
>id="connections_coredatavolume"
>title="Volume des données principales"
>abstract="Volume des données principales pour le mois en cours. *Nécessite une confirmation sur la définition exacte.*"


>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="Lignes principales à inclure dans un rapport"
>abstract="Les lignes principales sur lesquelles effectuer des rapports sont des valeurs instantanées et non des totaux agrégés. Ces valeurs sont mises à jour de manière dynamique en fonction du dernier mois de la période sélectionnée. Si un client ou une cliente sélectionne Janvier - Mars, les valeurs reflètent l’instantané de mars."

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="Lignes historiques à inclure dans un rapport"
>abstract="Les lignes historiques sur lesquelles effectuer des rapports sont des valeurs instantanées et non des totaux agrégés. Ces valeurs sont mises à jour de manière dynamique en fonction du dernier mois de la période sélectionnée. Si un client ou une cliente sélectionne Janvier - Mars, les valeurs reflètent l’instantané de mars."

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="Lignes cumulées sur lesquelles effectuer des rapports"
>abstract="Les lignes cumulées sur lesquelles effectuer des rapports sont des valeurs instantanées et non des totaux agrégés. Ces valeurs sont mises à jour de manière dynamique en fonction du dernier mois de la période sélectionnée. Si un client ou une cliente sélectionne Janvier - Mars, les valeurs reflètent l’instantané de mars."


L’interface [!UICONTROL Utilisation] indique l’utilisation des lignes ingérées et pouvant faire l’objet d’un rapport sur toutes les connexions. Si cette option n’est pas sélectionnée, sélectionnez l’onglet **[!UICONTROL Utilisation]** pour accéder à l’interface.

Cette interface vous permet de déterminer si votre utilisation de Customer Journey Analytics est conforme aux conditions contractuelles. Outre la surveillance, vous pouvez utiliser l’interface Utilisation pour planifier le renouvellement de votre licence Customer Journey Analytics.

L’interface d’utilisation utilise les mesures suivantes :

| Nom de la mesure | Description |
|---|---|
| Lignes historiques à inclure dans un rapport | Nombre de lignes pour la période de plus de 13 mois. |
| Lignes principales à inclure dans un rapport | Nombre de lignes au cours des 13 derniers mois. |
| Lignes ingérées | Nombre de lignes ingérées pour la période spécifique. |
| Lignes à déclarer | Nombre de lignes de données que vous avez dans le cadre de la connexion pour la période spécifique. |
| Lignes cumulées | Nombre de lignes ingérées jusqu’au mois spécifique. |

>[!NOTE]
>
>Les données sont collectées à partir de juillet 2024 pour les enregistrements principaux, historiques et totaux. Contactez votre gestionnaire de compte pour obtenir des données historiques antérieures.
>



L’interface Utilisation se compose de deux panneaux :

* Panneau **[!UICONTROL Mesures d’utilisation clés]** : fournit des lignes de données principales et historiques à déclarer. Le panneau effectue également le suivi des modifications en pourcentage par rapport au mois précédent pour les lignes de données principales et historiques.

  Le panneau affiche une visualisation qui contient les éléments suivants :

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

  Pour les mois précédant septembre 2024, les données ont été collectées au niveau des jeux de données et s’affichent sous la forme [!UICONTROL Autres jeux de données] par souci de clarté. À compter de septembre 2024, les données seront collectées au niveau d’un jeu de données granulaire et [!UICONTROL autres jeux de données] n’apparaîtront plus.

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
>&#x200B;>[Gérer l’utilisation de Customer Journey Analytics](/help/technotes/estimate-usage.md)
>
