---
title: Ajout du jeu de données du connecteur source Analytics à la connexion
description: Découvrez comment ajouter le jeu de données du connecteur source Analytics à la connexion
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 27%

---

# Ajout du jeu de données du connecteur source Analytics à la connexion

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes de mise à niveau précédentes effectuées. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement pour votre organisation avec le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

## Comprendre comment le connecteur source Analytics peut importer des données historiques dans Customer Journey Analytics

Vous pouvez utiliser le connecteur source Analytics pour importer les données des suites de rapports Adobe Analytics dans Adobe Experience Platform. Ces données peuvent ensuite être utilisées comme données historiques en Customer Journey Analytics.

Ce processus suppose que vous souhaitiez [créer un schéma XDM lors de la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), car vous souhaitez un schéma rationalisé adapté aux besoins de votre organisation et aux applications Platform spécifiques que vous utilisez.

Pour utiliser le connecteur source Analytics afin d’importer des données historiques dans Customer Journey Analytics, vous devez :

1. [Création d’un schéma XDM pour le connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. [Création des champs de mappage et du connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)

1. Ajoutez le jeu de données du connecteur source Analytics à la connexion, comme décrit ci-dessous.

## Ajout du jeu de données du connecteur source Analytics à la connexion

Après avoir [créé un connecteur source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md), un jeu de données est automatiquement créé pour les données Analytics.

Vous devez ajouter ce jeu de données créé automatiquement à la même connexion que celle que vous avez créée pour votre mise en oeuvre du SDK Web. Cela permet d’importer les données Analytics dans la même vue de données en Customer Journey Analytics que les données de votre SDK Web.

Pour ajouter le jeu de données créé automatiquement à la même connexion que celle que vous avez créée pour l’implémentation de votre SDK Web :

1. Dans Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Connexions]**.

1. Sélectionnez la connexion que vous [avez créée pour votre implémentation du SDK Web](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. Sélectionnez **[!UICONTROL Modifier]**.

   ![Modifier la connexion](assets/connection-add-dataset.png)

1. Sélectionnez **[!UICONTROL Ajouter des jeux de données]** dans le coin supérieur droit.

   ![Modifier la connexion](assets/connection-add-dateset2.png)

1. Accédez au jeu de données automatiquement créé lors de la création du connecteur source Analytics ou recherchez-le.

   Le nom de ce jeu de données est le nom de votre suite de rapports, suivi de `midValues`. Par exemple : `My report suite midValues`

1. Cochez la case en regard du nom du jeu de données, puis sélectionnez **[!UICONTROL Suivant]**.

   ![Modifier la connexion](assets/connection-add-dataset3.png)

1. Indiquez les informations suivantes :

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL ID de personne]** | Disponible uniquement pour les jeux de données d’événement et de profil. Sélectionnez un ID de personne dans la liste déroulante des identités disponibles. Ces identités ont été définies dans le schéma du jeu de données d’Experience Platform. Pour plus d’informations sur l’utilisation de la carte des identités en tant qu’ID de personne, reportez-vous à la section ci-dessous.<p>Si aucun ID de personne n’est disponible, cela signifie qu’un ou plusieurs ID de personne n’ont pas été définis dans le schéma. Voir [Définir des champs d’identité dans l’interface utilisateur](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/identity) pour plus d’informations. <p>La valeur de l’ID de personne sélectionné est considérée comme sensible à la casse. Par exemple : `abc123` et `ABC123` sont deux valeurs différentes. |
   | **[!UICONTROL Date et heure]** | Pour les jeux de données d’événements uniquement, ce paramètre est automatiquement défini sur le champ d’horodatage par défaut des schémas basés sur un événement dans Experience Platform. |
   | **[!UICONTROL Fuseau horaire]** | Disponible uniquement pour les données de résumé. Sélectionnez le fuseau horaire approprié pour les données de résumé de série temporelle. |
   | **[!UICONTROL Type de source de données]** | Sélectionnez un type de source de données. <br/>Les types de sources de données incluent les éléments suivants : <ul><li>[!UICONTROL Données web]</li><li>[!UICONTROL Données d’application mobile]</li><li>[!UICONTROL Données de point de vente]</li><li>[!UICONTROL Données CRM]</li><li>[!UICONTROL Données de l’enquête]</li><li>[!UICONTROL Données du centre d’appels]</li><li>[!UICONTROL Données du produit]</li><li> [!UICONTROL Données des comptes]</li><li> [!UICONTROL Données de transaction]</li><li>[!UICONTROL Données de commentaires client]</li><li> [!UICONTROL Autre]</li></ul>Ce champ est utilisé pour interroger les types de sources de données en cours d’utilisation. |

   {style="table-layout:auto"}

1. Dans la section **[!UICONTROL Importer de nouvelles données]**, laissez l&#39;option **[!UICONTROL Importer toutes les nouvelles données]** désactivée.

   Puisque vous utilisez le jeu de données du connecteur source Analytics pour les données historiques, vous ne souhaitez pas importer les données futures collectées dans ce jeu de données.

1. Dans la section **[!UICONTROL Renvoi du jeu de données]**, sélectionnez **[!UICONTROL Renvoi de requête]**.

1. Définissez la période à inclure dans le renvoi en saisissant les dates de début et de fin ou en sélectionnant l’icône de calendrier ![Calendrier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).

   Le connecteur source Analytics importe 13 mois de données (quelle que soit leur taille) pour les environnements de test de production. Le renvoi dans les environnements de test hors production est de 3 mois.

   >[!IMPORTANT]
   >
   >Soyez explicite lorsque vous spécifiez les dates à renvoyer. La date de fin doit être la date à laquelle vous avez commencé à collecter des données avec votre mise en oeuvre du SDK Web.
   >
   >Vous pouvez également choisir une date peu de temps après la date à laquelle vous avez commencé à collecter des données avec votre implémentation du SDK Web, puis utiliser des segments pour filtrer les données qui se chevauchent.

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. Sélectionnez **[!UICONTROL Renvoi de la file d’attente]**.

1. Sélectionnez **[!UICONTROL Ajouter des jeux de données]**, puis **[!UICONTROL Enregistrer]** pour enregistrer la connexion.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [ étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
