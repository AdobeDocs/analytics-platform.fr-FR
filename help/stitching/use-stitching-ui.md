---
title: Activer l’assemblage
description: Activez la combinaison d’identités pour les jeux de données d’événements dans Customer Journey Analytics. Découvrez comment configurer les identifiants persistants, les identifiants de personne et les fenêtres de relecture dans l’interface utilisateur de Connexions pour regrouper les données.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: 1ad1698f10dd026b0bd5e67599ef35ab3c552286
workflow-type: tm+mt
source-wordcount: '1800'
ht-degree: 6%

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
      * Pour le groupement basé sur les graphiques, assurez-vous que le graphique d’identités contient des fragments qui lient les valeurs d’identifiant de l’espace de noms d’identifiant persistant et de l’espace de noms d’identifiant de personne de votre choix. Vous pouvez exécuter un test en accédant à la visionneuse de graphiques d’identités [d’Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/features/identity-graph-viewer){target="_blank"} et interroger le graphique à l’aide d’exemples de valeurs d’ID persistantes. Vérifiez si ces valeurs d’ID persistantes sont liées aux valeurs d’ID de personne dans le graphique.
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



## Activer l’assemblage d’identités {#enable-identity-stitching}

Vous pouvez activer la combinaison d’identités lorsque vous [ajoutez](/help/connections/create-connection.md#add-datasets) ou [modifiez](/help/connections/create-connection.md#edit-a-dataset) un jeu de données d’événement dans une connexion basée sur une personne. L’assemblage des identités n’est pas disponible pour les connexions basées sur des comptes.

>[!CONTEXTUALHELP]
>id="connection_changeto_identitygraph"
>title="Modification du graphique d’identité"
>abstract="Assurez-vous d’avoir terminé la configuration du graphique d’identité avant d’utiliser le graphique d’identité pour l’assemblage."
>additional-url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/stitching/gbs" text="Groupement basé sur les graphiques"

>[!CONTEXTUALHELP]
>id="connection_stitching_personid"
>title="ID de personne"
>abstract="Sélectionnez un ID de personne (l’identifiant unique d’une personne) parmi les identités disponibles. Si votre licence comprend un groupement basé sur des graphiques et que vous souhaitez utiliser cette méthode de groupement, sélectionnez **[!UICONTROL Graphique d’identité]**."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics"
>title="Assemblage des mesures"
>abstract="Les mesures d’assemblage sont calculées à l’aide d’un exemple de jeu de données avec des horodatages d’événement des 7 derniers jours.<br>Cet exemple de jeu de données diffère généralement des exemples de données utilisés dans le tableau **[!UICONTROL Aperçu]**."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_gbs_personidcoverage"
>title="Couverture de l’ID de personne"
>abstract="Couverture de l’ID de personne sélectionné utilisé pour l’identification pendant le processus de groupement (en direct et en relecture).<br/>Pour de meilleurs résultats d’assemblage, une relation (ID persistant, ID de personne) doit être présente dans le graphique d’identité pour chaque ID persistant."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_fbs_personidcoverage"
>title="Couverture de l’ID de personne"
>abstract="Couverture de l’ID de personne sélectionné utilisé pour l’identification pendant le processus de groupement (en direct et en relecture).<br/>Pour de meilleurs résultats d’assemblage, l’ID de personne (informations utilisateur) doit être envoyé sur au moins un événement pour chaque ID persistant (informations sur l’appareil)."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_persistentidcoverage"
>title="Couverture de l’ID persistant"
>abstract="Cette valeur est utilisée pour l’identification pendant le processus de groupement (en direct et en relecture), au cas où une valeur d’ID de personne ne peut pas être détectée. <br/>Les événements sans ID persistant et sans ID de personne sont supprimés des données. Pour de meilleurs résultats d’assemblage, un identifiant persistant doit être présent sur tous les événements."


>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_badids"
>title="ID incorrects"
>abstract="Les identifiants incorrects sont des valeurs d’identifiant qui affectent considérablement les données de rapport."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/technotes/badids" text="ID incorrects"


### Paramètres des jeux de données

Pour activer le groupement, dans la section Jeu de données d’événement **[!UICONTROL Paramètres des jeux de données]** de la boîte de dialogue **[!UICONTROL Ajouter des jeux de données]** ou **[!UICONTROL Modifier le jeu de données]** :

![Options de combinaison d’identités lorsque vous activez cette fonction](assets/identity-stitching-ui.png)

1. Sélectionnez **[!UICONTROL Activer la combinaison d’identités]**.

   Si vous activez ou désactivez le groupement pour un jeu de données d’événement enregistré dans la connexion, la boîte de dialogue **[!UICONTROL Modifier l’ID de personne]** affiche les implications d’une modification de l’ID de personne. Sélectionnez **[!UICONTROL Continuer]** pour continuer.

   La boîte de dialogue **[!UICONTROL Activer la combinaison d’identités]** résume les conséquences de la combinaison d’identités. Sélectionnez **[!UICONTROL Continuer]** pour continuer.

1. Sélectionnez un ID persistant dans le menu déroulant **[!UICONTROL ID persistant]**.

   Si vous sélectionnez **[!UICONTROL Mappage d’identités]** pour l’identifiant persistant, vous devez sélectionner un espace de noms . Vous disposez de deux options :

   * Sélectionnez **[!UICONTROL Utiliser l’espace de noms d’identité principal]** pour utiliser l’espace de noms d’identité principal.
   * Sélectionnez un espace de noms dans le menu déroulant **[!UICONTROL Espace de noms]**.

1. Sélectionnez un ID de personne dans le menu déroulant **[!UICONTROL ID de personne]**.

   Si vous sélectionnez **[!UICONTROL Mappage d’identités]** pour l’ID de personne, vous devez sélectionner un espace de noms. Vous disposez de deux options :

   * Sélectionnez **[!UICONTROL Utiliser l’espace de noms d’identité principal]** pour utiliser l’espace de noms d’identité principal.
   * Sélectionnez un espace de noms dans le menu déroulant **[!UICONTROL Espace de noms]**.


   Si vous sélectionnez **[!UICONTROL Graphique d’identités]** pour l’ID de personne (pour utiliser [le groupement basé sur les graphiques](/help/stitching/gbs.md)), vous devez sélectionner un espace de noms.

   >[!NOTE]
   >
   >Assurez-vous que vous êtes autorisé à utiliser le graphique d’identité.
   >

   Avant cela, une boîte de dialogue **[!UICONTROL Modifier en graphique d’identité]** s’affiche pour vous assurer que vous avez terminé la configuration du graphique d’identité pour le jeu de données. Cette configuration fait partie des [conditions préalables basées sur les graphiques](/help/stitching/gbs.md#prerequisites) avant de pouvoir utiliser le graphique d’identités pour le groupement. Sélectionnez **[!UICONTROL Continuer]** pour continuer.

   * Sélectionnez un espace de noms dans le menu déroulant **[!UICONTROL Espace de noms]**.

1. Sélectionnez une fenêtre de relecture dans le menu déroulant **[!UICONTROL Fenêtre de relecture]**. Les options disponibles dépendent du package Customer Journey Analytics auquel vous avez droit.

1. Sélectionnez **[!UICONTROL Suivant]** pour afficher un aperçu du jeu de données d’événement sujet au groupement.


### Aperçu des jeux de données

>[!AVAILABILITY]
>
>L’interface améliorée **[!UICONTROL Aperçu du jeu de données]** (y compris les **[!UICONTROL Mesures d’assemblage]** et **[!UICONTROL ID incorrects]**) décrite dans cette section se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. S’il n’est pas disponible, l’aperçu du jeu de données s’affiche dans l’interface **[!UICONTROL Paramètres du jeu de données]**. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de mise à jour de Customer Journey Analytics, consultez [Mise à jour des fonctionnalités de Customer Journey Analytics](/help/release-notes/releases.md).
>

Outre l’interface standard **[!UICONTROL Aperçu des jeux de données]**, deux panneaux d’informations supplémentaires sont disponibles lors de l’[ajout](/help/connections/create-connection.md#add-datasets) ou de la [modification](/help/connections/create-connection.md#edit-a-dataset) de jeux de données dans une connexion basée sur une personne.

>[!NOTE]
>Pour les clients pour lesquels Customer Journey Analytics est déployé sur AWS, cette fonctionnalité est en attente de publication.
>

![Options de combinaison d’identités lorsque vous activez cette fonction](assets/identity-stitching-ui-preview.png)

#### Assemblage des mesures

Les **[!UICONTROL mesures d’assemblage]** sont calculées à l’aide d’un échantillon de données avec des horodatages d’événement des 7 derniers jours. Cet exemple de jeu de données diffère généralement des exemples de données utilisés dans le tableau **[!UICONTROL Aperçu]**. Les mesures d’assemblage fournissent des détails sur :

* **[!UICONTROL Couverture de l’ID de personne]** : couverture de l’ID de personne sélectionné utilisé pour l’identification pendant le processus de groupement (en direct et en relecture).
   * Pour obtenir de meilleurs résultats d’assemblage basés sur les champs, un ID de personne (informations utilisateur) doit être envoyé sur au moins un événement pour chaque ID persistant (informations sur l’appareil).
   * Pour obtenir de meilleurs résultats d’assemblage basés sur des graphiques, une relation (identifiant persistant, ID de personne) doit être présente dans le graphique d’identité pour chaque identifiant persistant.

  La couverture de l’ID de personne s’affiche sous forme de pourcentage et est comparée à ce qui est recommandé dans une configuration de développement stable ou de production. Plus cette valeur de couverture est élevée, meilleurs sont les résultats du groupement avec l’ID de personne sélectionné.

* **[!UICONTROL Couverture d’ID persistante]** : cette valeur est utilisée à des fins d’identification pendant le processus de groupement (en direct et en lecture), au cas où une valeur d’ID de personne ne peut pas être détectée. Les événements sans ID persistant et sans ID de personne sont supprimés des données. Pour de meilleurs résultats d’assemblage, un identifiant persistant doit être présent sur tous les événements.

  La couverture de l’ID persistant s’affiche sous la forme d’un pourcentage et est comparée à la valeur minimale recommandée pour une configuration de développement stable ou de production.


#### ID incorrects

>[!INFO]
>
>Dans l’interface de Customer Journey Analytics, les BAVID sont également appelés BAVID.
> 

Dans Customer Journey Analytics, un ID incorrect est un identifiant :

* avec une valeur d’ID spécifique qui provient d’un ID persistant ou d’un champ d’ID de personne dans les jeux de données activés pour le groupement, **et**
* est sur plus d’un million (1 000 000) d’événements dans les données de connexion, au cours d’un mois.

Lorsqu’une valeur d’ID est marquée comme ID incorrect, tous les événements futurs contenant cette valeur d’ID sont ignorés des données de connexion et n’apparaissent pas dans les rapports.

Exemples de cas d’utilisation d’ID incorrects :

* Le champ d’ID de personne (par exemple, `undefined`) contient des valeurs personnalisées ou d’espace réservé. Ces valeurs peuvent également affecter [l’assemblage et la qualité des données de rapport](/help/stitching/faq.md#undefined-person-id-values).
* Dans une configuration d’assemblage basée sur les champs, si plusieurs personnes partagent un appareil et que le nombre total de transitions entre les utilisateurs dépasse 50 000. Dans ce scénario, le processus de groupement s’arrête pour utiliser les informations d’ID de personne pour cet appareil et utilise uniquement les informations d’ID persistantes à la place. Par conséquent, tous les événements du jeu de données de cet appareil sont envoyés dans des données de connexion avec l’identité d’identifiant persistante, avec un risque élevé de provoquer une situation d’ID incorrects.


>[!NOTE]
>Les **[!UICONTROL mesures d’assemblage]**, y compris les **[!UICONTROL ID incorrects]** sont calculées sur la base d’un ensemble limité de données. Pour identifier la présence d’ID incorrects pour un jeu de données que vous prévoyez d’utiliser pour le groupement, reportez-vous à la note technique [ID incorrects](/help/technotes/badids.md).
>


### Enregistrer

Une fois que vous avez enregistré une connexion, le processus de groupement pour les jeux de données activés est lancé dès que l’ingestion des données de ces jeux de données commence.

>[!CAUTION]
>
>Pour les jeux de données activés pour le groupement dans l’interface Connexions, le statut de renvoi est immédiatement et incorrectement signalé comme ![Statut vert](/help/assets/icons/StatusGreen.svg) **[!UICONTROL _x _renvois terminés]**&#x200B;pour le nombre de renvois terminés. Utilisez d’autres méthodes pour vérifier si les données du jeu de données groupé sont renvoyées.
>


## Limites

En plus des [limitations du groupement basées sur les champs](/help/stitching/fbs.md#limitations) et [limitations du groupement basé sur les graphiques](/help/stitching/gbs.md#limitations), les limitations suivantes s’appliquent lorsque vous activez le groupement dans l’interface Connexions :

* Vous ne pouvez assembler un jeu de données d’événement qu’une seule fois dans le cadre d’une connexion unique. Vous ne pouvez pas définir le même jeu de données d’événement plus d’une fois et utiliser une configuration de groupement distincte pour chaque instance. Si vous souhaitez appliquer différentes configurations de groupement sur le même jeu de données, utilisez une connexion distincte pour chaque configuration.


## Migration

Le groupement activé dans l’interface de connexions peut coexister sans problème avec le groupement basé sur les requêtes.

Par exemple, vous disposez de jeux de données assemblés web dans le lac de données à la suite de requêtes d’assemblage antérieures ou actuelles. Vous pouvez ajouter des données groupées à partir d’un jeu de données de centre d’appels à l’aide de l’interface Connexions pour combiner ces données avec les données web.

À la fin, Adobe migre vos jeux de données groupés basés sur les requêtes vers la nouvelle expérience de groupement dans les connexions .
