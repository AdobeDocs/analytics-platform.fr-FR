---
title: Estimation et gestion de votre utilisation CJA
description: Affiche deux méthodes d’estimation de l’utilisation et une méthode de gestion.
role: Admin
feature: CJA Basics
source-git-commit: 2bcf1f805a54581f13f7d08b9ef034535d7959b1
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 42%

---


# Estimation et gestion de votre utilisation CJA

Pour comprendre votre utilisation de CJA, vous pouvez utiliser 2 méthodes :

* Ajoutez les lignes de données d’événement pour chaque connexion. (Voir **Estimation de la taille de connexion** below)
* Utilisez Analysis Workspace pour créer des rapports sur les événements du mois dernier. (Voir **Créer un projet Workspace à l’aide de toutes vos données d’événement** ci-dessous.)

Pour gérer votre utilisation de CJA :

* Utilisez l’API CJA. (Voir **Création d’un rapport dans l’API CJA** ci-dessous.)

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

1. Avant de créer le projet dans Workspace, [création d’une vue de données](/help/data-views/create-dataview.md) qui extrait les données de TOUTES vos connexions et n’a aucun filtre appliqué. En d’autres termes, il contient toutes vos données.

1. Dans Workspace, créez un projet et extrayez tous les événements (du **[!UICONTROL Mesures]** (liste déroulante) pour le mois précédent.

   ![Événements](assets/events-usage.png)

1. effectuer cette opération

## Création d’un rapport dans l’API CJA {#api-report}

Utilisez la variable [API de création de rapports CJA](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) pour exécuter un rapport sur toutes vos données d’événement.