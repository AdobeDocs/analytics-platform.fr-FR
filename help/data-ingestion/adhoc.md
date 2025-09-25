---
title: Ingérer et utiliser des données ad hoc
description: Explication de l’ingestion et de l’utilisation d’ad hoc dans Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: 17b5842f-dc81-481f-8b21-dc90a133adcf
source-git-commit: edf7bdac87d9bed48244ad80521bbbf83c48f7b6
workflow-type: tm+mt
source-wordcount: '1623'
ht-degree: 23%

---

# Ingérer et utiliser des données ad hoc

Ce guide de démarrage rapide explique comment ingérer des données ad hoc dans Experience Platform, puis les utiliser dans Customer Journey Analytics.

Pour ce faire, effectuez les opérations suivantes :

- **Création d’un jeu de données avec un fichier CSV** dans Experience Platform. Ce workflow définit le modèle (schéma) des données que vous souhaitez collecter et où collecter les données (jeu de données).

- **Configurer une connexion** dans Customer Journey Analytics. Cette connexion doit (au moins) inclure votre jeu de données ad hoc Experience Platform.

- **Configurer une vue de données** dans Customer Journey Analytics pour définir les mesures et les dimensions à partir des champs de vos données ad hoc que vous souhaitez utiliser dans Analysis Workspace.

- **Configurer un projet** dans Customer Journey Analytics pour créer des rapports et des visualisations.



>[!NOTE]
>
>Ce guide de démarrage rapide est un guide simplifié sur la manière d’ingérer des données ad hoc à l’aide d’dans Experience Platform et d’utiliser ces données ad hoc dans Customer Journey Analytics. Il est vivement recommandé d’étudier les informations supplémentaires lorsqu’elles sont mentionnées.


## Création d’un jeu de données à partir d’un fichier CSV

Pour ce démarrage rapide, vous devez utiliser un fichier CSV qui représente les données de recherche et contient des informations similaires à celle affichée ci-dessous.

| _id | tracking_code | ad_group | nom_campagne |
| ---: | :---          | :---        | :---          |
| 1 | abc123 | abc-adgroup | Campagne 123 |
| 2 | def123 | def-adgroup | Campagne 123 |
| 3 | ghi123 | ghi-adgroup | Campagne 123 |
| 4 | abc456 | abc-adgroup | Campagne 456 |
| 5 | def456 | def-adgroup | Campagne 456 |

>[!NOTE]
>
>Utilisez des jeux de données et des schémas ad hoc pour les données basées sur les enregistrements (recherche, profil). Les jeux de données et les schémas ad hoc sont moins adaptés et ne doivent pas être pris en compte pour les données de série temporelle (événement, résumé).

Vous n’avez pas besoin de créer un schéma XDM pour les données ad hoc. Experience Platform prend en charge un workflow qui, en fonction des données du fichier CSV :

1. Crée automatiquement un schéma ad hoc. Ce schéma est conforme aux colonnes du fichier CSV.
1. Crée un jeu de données contenant les données du fichier CSV.

Pour démarrer le workflow :

1. Dans l’interface d’Experience Platform, dans le rail de gauche, sélectionnez **[!UICONTROL Workflows]**.
1. Sélectionnez ![DataAdd](/help/assets/icons/DataAdd.svg) **[!UICONTROL Créer un jeu de données à partir d’un fichier CSV]**.
1. Sélectionnez **[!UICONTROL Launch]** dans le volet de droite.
1. Dans l’assistant **[!UICONTROL Workflows]** > **[!UICONTROL Créer un jeu de données à partir d’un fichier CSV]** :
   1. À l’étape **[!UICONTROL Configurer le jeu de données]** :
      1. Saisissez un **[!UICONTROL Nom]** pour le jeu de données. Par exemple : `Sample Data From CSV`.
      1. Ajoutez une **[!UICONTROL Description]** facultative. Par exemple : `Sample data from a CSV file`.
      1. Ajoutez une ou plusieurs **[!UICONTROL Balises]** facultatives, ou sélectionnez une ou plusieurs **[!UICONTROL Balises]** existantes.

         ![Configurer le jeu de données ad hoc](assets/adhoc-dataset-configure.png)

      1. Sélectionnez **[!UICONTROL Suivant]**.
   1. À l’étape **[!UICONTROL Ajouter des données]** :
      1. Sélectionnez **[!UICONTROL Choisir les fichiers]** pour sélectionner votre fichier CSV depuis votre ordinateur ou votre réseau. Vous pouvez également faire glisser le fichier depuis son emplacement sur votre ordinateur ou réseau vers **[!UICONTROL Glisser-déposer des fichiers]**. Le fichier est chargé et **[!UICONTROL Données d’exemple]** s’affiche.
      1. Activez ou désactivez **[!UICONTROL diagnostics d’erreur]** et **[!UICONTROL activer l’ingestion partielle]** en fonction de vos préférences. Lorsque vous **[!UICONTROL Activer l’ingestion partielle]**, vous pouvez définir un **[!UICONTROL Seuil d’erreur %]**.

         ![Ajouter des données à un jeu de données ad hoc](assets/adhoc-dataset-adddata.png)

      1. Sélectionnez **[!UICONTROL Terminer]**.

Une fois les données préparées et chargées, vous êtes redirigé vers **[!UICONTROL Jeux de données]** dans l’interface d’Experience Platform.<br/> L’activité **[!UICONTROL Jeu de données]** s’affiche pour votre **[!UICONTROL Exemple de données à partir d’un jeu de données CSV]** avec le statut ![StatutOrange](/help/assets/icons/StatusOrange.svg) **[!UICONTROL Traitement]**.

![Activité du jeu de données pour les données ad hoc](assets/datasets-dataset-activity.png)

Pour inspecter les données ad hoc :

1. Dans l’interface d’Experience Platform, dans le rail de gauche, sélectionnez **[!UICONTROL Jeux de données]**.
1. Sélectionnez l’onglet **[!UICONTROL Parcourir]** dans **[!UICONTROL Jeux de données]**. Votre jeu de données devrait être répertorié.
1. Sélectionnez le nom du schéma dans la colonne **[!UICONTROL Schéma]**. Par exemple : **[!UICONTROL Données d’exemple CSV...]**

   ![Sélectionner un schéma pour le jeu de données ad hoc](assets/adhoc-schema-selection.png)

1. Dans la fenêtre contextuelle, sélectionnez le **[!UICONTROL nom du schéma]**. Par exemple : **[!UICONTROL Exemple de données à partir d’un fichier CSV - schéma ad hoc - XXXXXXXXX]**. Vous êtes redirigé vers l’interface **[!UICONTROL Schémas]** > **[!UICONTROL Exemples de données à partir de CSV - schéma ad hoc - XXXXXXXXX]**.

Dans l’interface **[!UICONTROL Schémas]** > **[!UICONTROL Exemples de données à partir du fichier CSV - schéma ad hoc - XXXXXXXXXXX]** :

- Sélectionnez l’objet de nom du client le plus élevé sous **[!UICONTROL Schémas]** > **[!UICONTROL Exemples de données à partir de CSV - schéma ad hoc - XXXXXXXXXXX]** pour afficher les champs dans l’objet . Les champs dans l’objet représentent la structure du fichier CSV. Le schéma est créé automatiquement en fonction du chargement des données ad hoc.

  ![ Schéma ad hoc ](dataset/../assets/adhoc-schema.png)

  >[!NOTE]
  >
  >Le workflow définit tous les champs du schéma comme étant de type Chaîne. Vous ne pouvez pas modifier ce type ultérieurement. Si vous avez besoin de plus de flexibilité dans la définition d’un schéma ad hoc, pensez à [utiliser l’API pour créer un schéma ad hoc](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/tutorials/ad-hoc) puis à utiliser le workflow [Créer un jeu de données à partir d’un schéma](https://experienceleague.adobe.com/fr/docs/experience-platform/catalog/datasets/user-guide#schema).
  > 




## Configurer une connexion

Pour utiliser le jeu de données Experience Platform dans Customer Journey Analytics, vous devez créer une connexion incluant le jeu de données ad hoc résultant du [workflow](#create-a-dataset-with-a-csv-file)

Une connexion vous permet d’intégrer des jeux de données d’Experience Platform dans Workspace. Pour générer des rapports sur ces jeux de données, vous devez d’abord établir une connexion entre les jeux de données dans Experience Platform et Workspace.

Créer une connexion :

1. Dans l’interface utilisateur de Customer Journey Analytics, sélectionnez **[!UICONTROL Connexions]**, éventuellement à partir de **[!UICONTROL Gestion des données]** dans le menu supérieur.

1. Sélectionnez **[!UICONTROL Créer une connexion]**.

1. Sur l’écran **[!UICONTROL Connexion sans titre]** :

   1. Nommez et décrivez la connexion dans **[!UICONTROL Paramètres de connexion]**.

   1. Sélectionnez la sandbox appropriée dans la liste **[!UICONTROL Sandbox]** des **[!UICONTROL Paramètres des données]** et sélectionnez le nombre d’événements quotidiens dans la liste **[!UICONTROL Nombre moyen d’événements quotidiens]**.

      ![Paramètres de connexion](./assets/cja-connections-1.png)

   1. Sélectionnez **[!UICONTROL Ajouter des jeux de données]**.

1. À l’étape **[!UICONTROL Sélectionner des jeux de données]** dans **[!UICONTROL Ajouter des jeux de données]** :

   1. Sélectionnez le jeu de données que vous avez créé précédemment, par exemple **[!UICONTROL Exemple de données à partir d’un fichier CSV]**, ainsi que tout autre jeu de données que vous souhaitez inclure dans votre connexion. Les jeux de données ad hoc ont le type **[!UICONTROL Ad hoc]** [!UICONTROL Jeu de données].

      ![Ajouter des jeux de données](./assets/cja-connections-adhoc-2.png)

   1. Sélectionnez **[!UICONTROL Suivant]**.

1. À l’étape **[!UICONTROL Paramètres des jeux de données]** dans **[!UICONTROL Ajouter des jeux de données]** :

   Pour votre jeu de données ad hoc :

   1. Sélectionnez le type de jeu de données ad hoc. Par exemple : **[!UICONTROL Recherche]**.
   1. Sélectionnez une **[!UICONTROL Clé]** parmi les clés disponibles et définies dans le schéma ad hoc.
   1. Sélectionnez une **[!UICONTROL clé correspondante]** à partir d’un jeu de données d’événement que vous avez ajouté dans le cadre de votre connexion.
   1. Sélectionnez la source de données appropriée dans la liste **[!UICONTROL Type de source de données]**. Si vous spécifiez **[!UICONTROL Autre]**, ajoutez une description pour la source de données.

   1. Définissez **[!UICONTROL Importer toutes les nouvelles données]** et **[!UICONTROL Données existantes de renvoi du jeu de données]** selon vos préférences.

      ![Configurer les jeux de données](./assets/cja-connections-3-adhoc.png)

   1. Sélectionnez **[!UICONTROL Ajouter des jeux de données]**.

   1. Sélectionnez **[!UICONTROL Enregistrer]**.

Consultez [ Paramètres de jeu de données ad hoc ](/help/connections/create-connection.md#adhoc-dataset) pour plus d’informations sur les paramètres disponibles pour les jeux de données ad hoc.

>[!IMPORTANT]
>
>En plus de la recommandation générale de ne pas utiliser de jeux de données et de schémas ad hoc pour les données de série temporelle, vous ne pouvez pas utiliser le workflow **[!UICONTROL Créer un jeu de données à partir de CSV]** pour les données de série temporelle. Ce workflow définit tous les champs comme étant de type Chaîne que vous ne pouvez pas modifier par la suite. Lorsque vous ajoutez un jeu de données basé sur une série temporelle (événement ou résumé) à une connexion, ce type de jeu de données nécessite la définition d’au moins un champ de type DateTime.<br/>Si vous devez utiliser des données de série temporelle ad hoc, pensez à [utiliser l’API pour créer un schéma ad hoc](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/tutorials/ad-hoc#token_type=bearer&expires_in=43197438) puis à utiliser le workflow [Créer un jeu de données à partir d’un schéma](https://experienceleague.adobe.com/fr/docs/experience-platform/catalog/datasets/user-guide#schema).


Après avoir créé une [connexion](/help/connections/overview.md), vous pouvez effectuer diverses tâches de gestion, telles que [sélectionner et combiner des jeux de données](/help/connections/combined-dataset.md), [vérifier le statut des jeux de données d’une connexion et le statut de l’ingestion des données](/help/connections/manage-connections.md) etc.

## Configurer une vue de données

Une vue de données est un conteneur spécifique à Customer Journey Analytics qui vous permet de déterminer comment interpréter les données d’une connexion. Elle spécifie toutes les dimensions et mesures disponibles dans Analysis Workspace et les colonnes dont ces dimensions et mesures obtiennent leurs données. Les vues de données sont définies en vue de la création de comptes rendus des performances dans Analysis Workspace.

Créer une vue de données :

1. Dans l’interface utilisateur de Customer Journey Analytics, sélectionnez **[!UICONTROL Vues de données]**, éventuellement à partir de **[!UICONTROL Gestion des données]** dans le menu supérieur.

1. Sélectionnez **[!UICONTROL Créer une vue de données]**.

1. À l’étape **[!UICONTROL Configurer]** :

   1. Sélectionnez votre [connexion](#set-up-a-connection) dans la liste **[!UICONTROL Connexion]**.

   1. Nommez et décrivez (facultatif) la connexion.

      ![Configuration de la vue de données](./assets/cja-dataview-1.png)

   1. Sélectionnez **[!UICONTROL Enregistrer et continuer]**.

1. À l’étape **[!UICONTROL Composants]** :

   1. Ajoutez n’importe quel champ de schéma et/ou composant standard que vous souhaitez inclure dans les zones de composant **[!UICONTROL MESURES]** ou **[!UICONTROL DIMENSIONS]**. Veillez à ajouter les champs pertinents du jeu de données contenant les données ad hoc. Pour accéder à ces champs :

      1. Sélectionnez **[!UICONTROL Jeux de données d’événement]**.
      1. Sélectionnez **[!UICONTROL Champs ad hoc et basés sur un modèle]**.

         ![Vue de données - Composants ad hoc](assets/cja-dataview-components-adhoc.png)

      1. Faites glisser et déposez des champs des schémas ad hoc sur **[!UICONTROL MESURES]** ou **[!UICONTROL DIMENSIONS]**.



   1. Vous pouvez éventuellement utiliser [champs dérivés](/help/data-views/derived-fields/derived-fields.md) pour modifier l’un des champs ad hoc de son type et de son format de chaîne par défaut à un autre type ou format.

   1. Sélectionnez **[!UICONTROL Enregistrer et continuer]**.

1. À l’étape **[!UICONTROL Paramètres]** :

   Ne modifiez pas les paramètres et sélectionnez **[!UICONTROL Enregistrer et terminer]**.

Consultez [Présentation des vues de données](../data-views/data-views.md) pour plus d’informations sur la création et la modification d’une vue de données. Ainsi que les composants que vous pouvez utiliser dans votre vue de données et la manière d’utiliser les paramètres de segment et de session.


## Configurer un projet

Analysis Workspace est un outil de navigateur flexible qui vous permet de créer rapidement des analyses et de partager des informations basées sur vos données. Les projets Espace de travail vous permettent de combiner des composants de données, des tableaux et des visualisations afin d’élaborer une analyse et de la partager avec tous les membres de l’entreprise.

Créer un projet :

1. Dans l’interface utilisateur de Customer Journey Analytics, sélectionnez **[!UICONTROL Projets]** dans le menu supérieur.

1. Sélectionnez **[!UICONTROL Projets]** dans la barre de navigation de gauche.

1. Sélectionnez **[!UICONTROL Créer un projet]**.

1. Sélectionnez **[!UICONTROL Projet vierge]**.

1. Sélectionnez la [vue de données](#set-up-a-data-view) dans la liste.

1. Pour créer votre premier rapport, commencez à faire glisser et à déposer des dimensions et des mesures sur le [!UICONTROL Tableau à structure libre] dans le [!UICONTROL Panneau]. Inclusion des mesures ou des dimensions basées sur vos données ad hoc.

Consultez [Présentation d’Analysis Workspace](../analysis-workspace/home.md) pour plus d’informations sur la création de projets et d’une analyse à l’aide de composants, de visualisations et de panneaux.

>[!SUCCESS]
>
>Vous avez terminé toutes les étapes. Vous avez commencé par définir les données ad hoc que vous souhaitez collecter (fichier CSV). Vous avez utilisé le workflow pour créer un jeu de données et un schéma ad hoc à partir de ce fichier CSV. Vous avez défini une connexion dans Customer Journey Analytics pour utiliser les données ad hoc et d’autres données ingérées. La définition de la vue de données vous a permis de spécifier la dimension et les mesures à utiliser. Enfin, vous avez créé votre premier projet de visualisation et d’analyse des données.
