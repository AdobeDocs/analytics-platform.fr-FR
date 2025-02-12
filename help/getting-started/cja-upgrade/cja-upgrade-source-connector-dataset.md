---
title: Ajouter le jeu de données du connecteur source Analytics à la connexion
description: Découvrez comment ajouter le jeu de données du connecteur source Analytics à la connexion
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '960'
ht-degree: 25%

---

# Ajouter le jeu de données du connecteur source Analytics à la connexion {#upgrade-source-connector-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-dataset"
>title="Ajouter le jeu de données du connecteur source Analytics à votre connexion"
>abstract="Maintenant que les données historiques de votre suite de rapports Analytics se trouvent dans Adobe Experience Platform, ajoutez ce jeu de données à la connexion existante que vous avez créée lors de la configuration initiale de Customer Journey Analytics. Une fois cette étape terminée, les données historiques dans Customer Journey Analytics sont disponibles.<br><br>L’ajout d’un jeu de données à une connexion dans Customer Journey Analytics est simple et ne prend que quelques minutes."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement après avoir effectué toutes les étapes de mise à niveau précédentes. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou suivre les étapes de mise à niveau qui ont été générées dynamiquement pour votre organisation à l’aide du [questionnaire de mise à niveau d’Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois les étapes de cette page terminées, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

## Comprendre comment le connecteur source Analytics peut importer des données historiques dans Customer Journey Analytics

Vous pouvez utiliser le connecteur source Analytics pour importer les données des suites de rapports Adobe Analytics dans Adobe Experience Platform. Ces données peuvent ensuite être utilisées comme données historiques dans Customer Journey Analytics.

Ce processus suppose que vous souhaitez [créer un schéma XDM lors de la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), car vous souhaitez un schéma rationalisé et adapté aux besoins de votre organisation et aux applications Platform spécifiques que vous utilisez.

Pour utiliser le connecteur source Analytics afin d’importer des données historiques dans Customer Journey Analytics, vous devez :

1. [Créer un schéma XDM pour le connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Si vous ne disposez pas déjà d’un connecteur source Analytics, [créez le connecteur source Analytics et mappez les champs à votre schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Ou

   Si vous disposez déjà d’un connecteur source Analytics, [mappez les champs du connecteur source à votre schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. Ajoutez le jeu de données du connecteur source Analytics à la connexion, comme décrit ci-dessous.

## Ajouter le jeu de données du connecteur source Analytics à la connexion

Après avoir [créé un connecteur source Analytics pour les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md), un jeu de données est automatiquement créé pour les données Analytics.

Vous devez ajouter ce jeu de données créé automatiquement à la même connexion que celle que vous avez créée pour votre implémentation de Web SDK. Les données Analytics sont ainsi intégrées dans la même vue de données dans Customer Journey Analytics que les données de votre SDK Web.

Pour ajouter le jeu de données créé automatiquement à la même connexion que celle que vous avez créée pour votre implémentation de Web SDK :

1. Dans Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Connexions]**.

1. Sélectionnez la connexion que vous [avez créée pour votre implémentation de Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. Sélectionnez **[!UICONTROL Modifier]**.

   ![Modifier la connexion](assets/connection-add-dataset.png)

1. Sélectionnez **[!UICONTROL Ajouter des jeux de données]** dans le coin supérieur droit.

   ![Modifier la connexion](assets/connection-add-dateset2.png)

1. Faites défiler l’écran jusqu’au jeu de données automatiquement créé lors de la création du connecteur source Analytics ou recherchez-le.

   Le nom de ce jeu de données est le nom de votre suite de rapports, suivi de `midValues`. Par exemple : `My report suite midValues`

1. Cochez la case en regard du nom du jeu de données, puis sélectionnez **[!UICONTROL Suivant]**.

   ![Modifier la connexion](assets/connection-add-dataset3.png)

1. Spécifiez les informations suivantes :

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL ID de personne]** | Disponible uniquement pour les jeux de données d’événement et de profil. Sélectionnez un ID de personne dans la liste déroulante des identités disponibles. Ces identités ont été définies dans le schéma du jeu de données d’Experience Platform. Pour plus d’informations sur l’utilisation de la carte des identités en tant qu’ID de personne, reportez-vous à la section ci-dessous.<p>Si aucun ID de personne n’est disponible, cela signifie qu’un ou plusieurs ID de personne n’ont pas été définis dans le schéma. Voir [Définir des champs d’identité dans l’interface utilisateur](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/identity) pour plus d’informations. <p>La valeur de l’ID de personne sélectionné est considérée comme sensible à la casse. Par exemple : `abc123` et `ABC123` sont deux valeurs différentes. |
   | **[!UICONTROL Date et heure]** | Pour les jeux de données d’événements uniquement, ce paramètre est automatiquement défini sur le champ d’horodatage par défaut des schémas basés sur un événement dans Experience Platform. |
   | **[!UICONTROL Fuseau horaire]** | Disponible uniquement pour les données de résumé. Sélectionnez le fuseau horaire approprié pour les données de résumé de série temporelle. |
   | **[!UICONTROL Type de source de données]** | Sélectionnez un type de source de données. <br/>Les types de sources de données incluent les éléments suivants : <ul><li>[!UICONTROL Données web]</li><li>[!UICONTROL Données d’application mobile]</li><li>[!UICONTROL Données de point de vente]</li><li>[!UICONTROL Données CRM]</li><li>[!UICONTROL Données de l’enquête]</li><li>[!UICONTROL Données du centre d’appels]</li><li>[!UICONTROL Données du produit]</li><li> [!UICONTROL Données des comptes]</li><li> [!UICONTROL Données de transaction]</li><li>[!UICONTROL Données de commentaires client]</li><li> [!UICONTROL Autre]</li></ul>Ce champ est utilisé pour interroger les types de sources de données en cours d’utilisation. |

   {style="table-layout:auto"}

1. Dans la section **[!UICONTROL Importer de nouvelles données]** , laissez l&#39;option **[!UICONTROL Importer toutes les nouvelles données]** désactivée.

   Comme vous utilisez le jeu de données du connecteur source Analytics pour les données historiques, vous ne souhaitez pas importer les données futures collectées dans ce jeu de données.

1. Dans la section **[!UICONTROL Renvoi du jeu de données]** , sélectionnez **[!UICONTROL Demander un renvoi]**.

1. Définissez la période que vous souhaitez inclure dans le renvoi de la connexion à Customer Journey Analytics en saisissant les dates de début et de fin ou en sélectionnant l’icône de calendrier ![Calendrier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).

   Soyez explicite lors de la spécification des dates de renvoi que vous demandez. Selon plusieurs facteurs, vous pouvez effectuer l’une des opérations suivantes :

   * Choisissez une date de fin identique à celle de votre première collecte de données avec votre implémentation de Web SDK.

   * Sélectionnez une date de fin peu après la date à laquelle vous avez commencé à collecter des données avec votre implémentation de Web SDK, puis utilisez les segments de vue de données pour filtrer les données qui se chevauchent.

   * Choisissez une date de fin qui entraîne un plus grand chevauchement des données, puis utilisez des segments de vue de données pour filtrer les données qui se chevauchent.

     **Remarque :** cette option entraînerait une augmentation des coûts, car il y aurait plus de lignes dans la connexion.

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. Sélectionnez **[!UICONTROL Renvoi de la file d’attente]**.

1. Sélectionnez **[!UICONTROL Ajouter des jeux de données]**, puis sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer la connexion.

1. (Conditionnel) Si vous utilisez des jeux de données de recherche, vous devez créer le jeu de données de recherche et l’ajouter à votre connexion. Pour plus d’informations, voir [Création de jeux de données de recherche pour classer les données dans Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

   Cela n’est nécessaire que si vous ne l’avez pas déjà fait lors de la configuration de votre implémentation de Web SDK.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
