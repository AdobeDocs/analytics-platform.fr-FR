---
title: Estimation et gestion de votre utilisation CJA
description: Affiche deux méthodes d’estimation de l’utilisation et une méthode de gestion.
role: Admin
feature: CJA Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 9ee3bbfe77d6134bee85d4f1844e40894e16a5c7
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 43%

---

# Estimation et gestion de votre utilisation CJA

Pour comprendre votre utilisation de CJA, vous pouvez utiliser 3 méthodes :

* Ajoutez les lignes de données d’événement pour chaque connexion. (Voir **Estimation de la taille de connexion** ci-dessous) Il s’agit d’un moyen facile d’afficher les données de ligne d’événement, par connexion, pour un horodatage spécifique.
* Utilisez Analysis Workspace pour créer des rapports sur les événements du mois dernier. (Voir **Créer un projet Workspace à l’aide de toutes vos données d’événement** ci-dessous.) Cela vous permet d’effectuer une analyse plus approfondie de vos données d’utilisation, ainsi que de l’historique de votre utilisation.
* Utilisez l’API CJA pour créer un rapport automatisé. (Voir **Création d’un rapport dans l’API CJA** ci-dessous.)

Pour gérer votre utilisation de CJA :

* Définissez une fenêtre de données variable. (Voir **Définition d’une fenêtre de données variable** ci-dessous.)

## Estimation de la taille de connexion {#estimate-size}

Vous devrez peut-être connaître le nombre de lignes de données d’événement actuellement présentes dans [!UICONTROL Customer Journey Analytics]. Pour un compte rendu détaillé de l’utilisation des enregistrements de données d’événement (lignes de données) de votre organisation, procédez comme suit **pour chacune des connexions créées par votre organisation**.

>[!NOTE]
>
>Effectuez cette opération le premier vendredi de chaque mois, car Adobe exécute votre dernier rapport d’utilisation ce jour-là.

1. Dans [!UICONTROL Customer Journey Analytics], sélectionnez l’onglet **[!UICONTROL Connexions]**.

   Vous pouvez voir la liste de toutes les connexions actuelles.

1. Cliquez sur chaque nom de connexion pour accéder au gestionnaire de connexions.

1. Ajoutez la variable **[!UICONTROL Enregistrements de données d’événement disponibles]** pour chaque connexion créée par votre organisation. (Selon la taille de votre connexion, le numéro peut mettre un certain temps à apparaître.)

   ![Données d’événement](assets/event-data.png)

   >[!CAUTION]
   >
   >   Ce nombre s’applique uniquement aux données d’événement, et non aux données de profil ou de recherche. Si vous disposez de données de profil et de recherche, le nombre sera légèrement plus élevé. Cependant, il n’existe actuellement aucun moyen de générer des rapports sur l’utilisation des données de profil et de recherche dans l’interface utilisateur. Cette fonctionnalité est prévue pour 2023.

1. Une fois que vous disposez du nombre de lignes de données d’événement, recherchez le droit de licence « Lignes de données » du contrat Customer Journey Analytics que votre entreprise a signé avec Adobe.

   Vous aurez alors le nombre maximum de lignes de données autorisées dans le bon de commande. Si le nombre de lignes de données de l’étape 3 est supérieur à ce nombre, un dépassement peut vous être reproché.

1. Plusieurs options s’offrent à vous pour remédier à ce problème :

   * Modifiez vos [paramètres de conservation des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=fr#set-rolling-window-for-connection-data-retention).
   * [Supprimez toutes les connexions inutilisées](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=fr#implications-of-deleting-data-components).
   * [Supprimez un jeu de données dans AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=fr#implications-of-deleting-data-components).
   * Contactez votre gestionnaire de compte Adobe pour obtenir une licence supplémentaire.

## Créer un projet Workspace à l’aide de toutes vos données d’événement {#workspace-event-data}

1. Avant de créer le projet dans Workspace, [création d’une vue de données](/help/data-views/create-dataview.md) pour chacune de vos connexions et n’a aucun filtre appliqué.

1. Dans Workspace, créez un projet et extrayez tous les événements (du **[!UICONTROL Mesures]** liste déroulante) jusqu’au premier vendredi du mois, à partir du premier jour de votre contrat CJA actuel.

   ![Événements](assets/events-usage.png)

   Cela vous donnera une bonne idée de la tendance de votre utilisation, mois après mois.

1. Selon vos besoins, vous pouvez effectuer une analyse par jeu de données, etc.


## Création d’un rapport automatisé dans l’API CJA {#api-report}

1. Utilisez la variable [API de création de rapports CJA](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) pour exécuter un rapport sur toutes vos données d’événement, **pour chaque connexion**. Configurez-le pour que le rapport s’exécute.

   * tous les trois vendredis de chaque mois.
   * revenez au premier jour de votre contrat CJA actuel.

   Cela vous donnera une bonne idée de la tendance de votre utilisation, mois après mois. Cela vous donnera le nombre total de lignes sur toutes vos connexions CJA.

1. Utilisez Excel pour personnaliser davantage ce rapport.

## Définition d’une fenêtre de données variable {#rolling}

Pour gérer votre utilisation, la variable [interface utilisateur des connexions](/help/connections/create-connection.md) permet de définir la conservation des données CJA sous la forme d’un créneau variable en mois (1 mois, 3 mois, 6 mois, etc.), au niveau de la connexion.

Lʼavantage principal est que vous ne stockez ou ne créez des rapports que sur les données applicables et utiles, et supprimez les données plus anciennes qui ne sont plus utiles. Elle vous aide à rester dans les limites de votre contrat et réduit le risque de surcoût.

Si vous laissez la valeur par défaut (non cochée), la période de conservation sera remplacée par le paramètre de conservation des données d’Adobe Experience Platform. Si vous avez 25 mois de données dans Experience Platform, CJA obtiendra 25 mois de données par renvoi. Si vous avez supprimé 10 de ces mois dans Platform, CJA conservera les 15 mois restants.

La conservation des données est basée sur les horodatages des jeux de données dʼévénement et sʼapplique uniquement aux jeux de données dʼévénement. Aucun paramètre de fenêtre dynamique de conservation des données nʼexiste pour les jeux de données de profil ou de recherche, car il nʼexiste aucun horodatage applicable. Cependant, si votre connexion inclut un profil ou des jeux de données de recherche (à part un ou plusieurs jeux de données d’événement), ces données seront conservées pendant la même période.

