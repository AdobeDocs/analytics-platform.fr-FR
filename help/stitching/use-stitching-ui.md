---
title: Activer l’assemblage
description: Découvrez comment activer le groupement dans l’interface utilisateur de connexions.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: 8f7c1f2a89c10be9b33f6e06fcff287e275767cf
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 3%

---

# Activer le rapprochement

Vous pouvez activer le regroupement sur un ou plusieurs jeux de données d’événement que vous avez configurés dans le cadre de votre connexion. Le package Customer Journey Analytics sous licence détermine le nombre de jeux de données d’événement que vous pouvez activer pour le regroupement .

Vous activez le groupement dans le cadre de l’[paramètres du jeu de données](/help/connections/create-connection.md#dataset-settings) pour un jeu de données d’événement lorsque vous [créez une connexion](/help/connections/create-connection.md) ou lorsque vous [modifiez une connexion](/help/connections/manage-connections.md#edit-a-connection).

## Conditions préalables

Vous devez vérifier et respecter les conditions préalables pour la méthode de groupement que vous spécifiez : [groupement basé sur les champs](fbs.md#prerequisites) ou [groupement basé sur les graphiques](gbs.md#prerequisites).


## Contrôles en amont

Si vous remplissez les conditions préalables, vous pouvez effectuer des contrôles en amont sur les données du jeu de données d’événement avant d’activer le regroupement d’identités :

* Si vous prévoyez d’utiliser des champs de schéma XDM pour l’ID persistant ou l’ID de personne, assurez-vous que les identités sont correctement marquées dans le schéma du jeu de données d’événement. [Voir Présentation des espaces de noms d’identité](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/features/namespaces).
* Vérifiez la couverture d’identité pour l’ID persistant et l’ID de personne :

   * **ID persistant**

     Interroger 7 jours de données lorsque le champ de votre identifiant persistant n’est pas nul et le diviser par une requête de 7 jours de données pour tous les événements de votre jeu de données. Ce pourcentage doit être supérieur à 95 %.

     Exemple de requête à utiliser pour la vérification :

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSISTENT_ID_FIELD}) AS events_with_persistentid,
       ROUND(COUNT({PERSISTENT_ID_FIELD}) / COUNT(*), 2) AS percent_with_persistentid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     Où :

      * `{PERSISTENT_ID_FIELD}` est le champ de l’identifiant persistant. Par exemple : `identityMap.ecid[0]`.
      * `{DATASET_TABLE_NAME}` est le nom de la table du jeu de données d’événement.
      * `{FORMAT_STRING}` est la chaîne de format du champ d’horodatage. Par exemple : `MM/DD/YY HH12:MI AM`.
      * `{START_DATE} `est la date de début. Par exemple : `2024-01-01 00:00:00`.
      * `{END_DATE}` est la date de fin au format standard. Par exemple : `2024-01-08 00:00:00`.


   * **ID de personne**
      * Pour le groupement basé sur les graphiques, assurez-vous que le graphique d’identités contient des fragments qui lient les valeurs d’identifiant de l’espace de noms d’identifiant persistant et de l’espace de noms d’identifiant de personne de votre choix. Vous pouvez exécuter un test en accédant à la visionneuse de graphiques d’identité [d’Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer){target="_blank"} et interroger le graphique à l’aide de certaines valeurs d’identifiant persistant de test. Vérifiez si ces valeurs d’ID persistantes sont liées aux valeurs d’ID de personne dans le graphique.
      * Pour le groupement basé sur les champs, interrogez 7 jours de données lorsque le champ de votre ID de personne n’est pas nul et divisez par une interrogation de 7 jours de données pour tous les événements de votre jeu de données. Ce pourcentage devrait idéalement être supérieur à 5 %.

        Exemple de requête à utiliser pour la vérification :

        ```sql
        SELECT
          COUNT(*) AS total_events,
          COUNT({PERSON_ID_FIELD}) AS events_with_personid,
          ROUND(COUNT({PERSON_ID_FIELD}) / COUNT(*), 2) AS percent_with_personid_not_null
        FROM 
          {DATASET_TABLE_NAME}
        WHERE
          TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
          AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
        ```

        Où :

         * `{PERSON_ID_FIELD}` est le champ de l’ID de personne. Par exemple : `identityMap.crmId[0]`.
         * `{DATASET_TABLE_NAME}` est le nom de la table du jeu de données d’événement.
         * `{FORMAT_STRING}` est la chaîne de format du champ d’horodatage. Par exemple : `MM/DD/YY HH12:MI AM`.
         * `{START_DATE}` est la date de début. Par exemple : `2024-01-01 00:00:00`.
         * `{END_DATE}` est la date de fin au format standard. Par exemple : `2024-01-08 00:00:00`.



## Activer l’assemblage d’identités

Pour activer le groupement, dans la section Jeu de données d’événement de la boîte de dialogue **[!UICONTROL Ajouter des jeux de données]** ou **[!UICONTROL Modifier le jeu de données]** :

![Options de combinaison d’identités lorsque vous activez cette fonction](assets/identity-stitching-ui.png)

1. Sélectionnez **[!UICONTROL Activer la combinaison d’identités]**.

   Si vous activez ou désactivez le groupement pour un jeu de données d’événement enregistré dans la connexion, la boîte de dialogue **[!UICONTROL Modifier l’ID de personne]** affiche les implications d’une modification de l’ID de personne. Sélectionnez **[!UICONTROL Continuer]** pour continuer.

   La boîte de dialogue **[!UICONTROL Activer la combinaison d’identités]** résume les conséquences de la combinaison d’identités. Sélectionnez **[!UICONTROL Continuer]** pour continuer.

1. Sélectionnez un ID persistant dans le menu déroulant **[!UICONTROL ID persistant]**.

   Si vous sélectionnez **[!UICONTROL Mappage d’identités]** pour l’identifiant persistant, vous devez sélectionner un espace de noms . Vous disposez de deux options :

   * Activez **[!UICONTROL Utiliser l’espace de noms d’identité principal]** pour utiliser l’espace de noms d’identité principal.
   * Sélectionnez un espace de noms dans le menu déroulant **[!UICONTROL Espace de noms]**.

1. Sélectionnez un ID de personne dans le menu déroulant **[!UICONTROL ID de personne]**.

   Si vous sélectionnez **[!UICONTROL Mappage d’identités]** pour l’ID de personne, vous devez sélectionner un espace de noms. Vous disposez de deux options :

   * Activez **[!UICONTROL Utiliser l’espace de noms d’identité principal]** pour utiliser l’espace de noms d’identité principal.
   * Sélectionnez un espace de noms dans le menu déroulant **[!UICONTROL Espace de noms]**.


   Si vous sélectionnez **[!UICONTROL Graphique d’identités]** pour l’ID de personne (pour utiliser [le groupement basé sur les graphiques](/help/stitching/gbs.md)), vous devez sélectionner un espace de noms.

   >[!NOTE]
   >
   >Assurez-vous que vous êtes autorisé à utiliser le graphique d’identité.
   >

   Avant cela, une boîte de dialogue **[!UICONTROL Modifier le graphique d’identité]** s’affiche pour vous assurer que vous avez terminé la configuration du graphique d’identité pour le jeu de données dans le cadre des conditions préalables basées sur le [graphique](/help/stitching/gbs.md#prerequisites) avant d’utiliser le graphique d’identité pour le groupement. Sélectionnez **[!UICONTROL Continuer]** pour continuer.

   * Sélectionnez un espace de noms dans le menu déroulant **[!UICONTROL Espace de noms]**.


1. Sélectionnez une fenêtre de relecture dans le menu déroulant **[!UICONTROL Fenêtre de relecture]**. Les options disponibles dépendent du package Customer Journey Analytics auquel vous avez droit.

Une fois que vous avez enregistré une connexion, le processus de groupement des jeux de données activés pour le groupement se déclenche lorsque l’ingestion des données de ces jeux de données commence.

>[!CAUTION]
>
>Pour les jeux de données activés pour le groupement dans l’interface Connexions, le statut de renvoi est immédiatement et incorrectement signalé comme ![Statut vert](/help/assets/icons/StatusGreen.svg) **[!UICONTROL _x _renvois terminés]**pour le nombre de renvois terminés. Utilisez d’autres méthodes pour vérifier si les données du jeu de données groupé sont renvoyées.
>


## Limites

En plus des [limitations du groupement basées sur les champs](/help/stitching/fbs.md#limitations) et [limitations du groupement basé sur les graphiques](/help/stitching/gbs.md#limitations), les limitations suivantes s’appliquent lorsque vous activez le groupement dans l’interface Connexions :

* Vous ne pouvez assembler un jeu de données d’événement qu’une seule fois dans le cadre d’une connexion unique. Vous ne pouvez pas définir le même jeu de données d’événement plus d’une fois et utiliser une configuration de groupement distincte pour chaque instance. Si vous souhaitez appliquer différentes configurations de groupement sur le même jeu de données, utilisez une connexion distincte pour chaque configuration.


## Migration

Le groupement activé dans l’interface de connexions peut coexister sans problème avec le groupement basé sur les requêtes.

Par exemple, vous disposez de jeux de données assemblés web dans le lac de données à la suite de requêtes d’assemblage antérieures ou actuelles. Vous pouvez ajouter des données groupées à partir d’un jeu de données de centre d’appels à l’aide de l’interface Connexions pour combiner ces données avec les données web.

À la fin, Adobe migre vos jeux de données groupés basés sur les requêtes vers la nouvelle expérience de groupement dans les connexions .
