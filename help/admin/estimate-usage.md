---
title: Afficher et gérer l’utilisation de Customer Journey Analytics
description: Affiche deux méthodes d’estimation de l’utilisation et une méthode de gestion.
role: Admin
feature: CJA Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 9f2d0d00872ad18c73bf67184e44f687a0b156a3
workflow-type: ht
source-wordcount: '868'
ht-degree: 100%

---

# Afficher et gérer l’utilisation de Customer Journey Analytics

Pour afficher l’utilisation de CJA, vous pouvez utiliser plusieurs méthodes :

* Additionnez les lignes de données d’événement pour chaque connexion. Consultez [Estimer la taille de connexion](#estimer taille) ci-dessous. Il s’agit d’un moyen facile d’afficher les données de ligne d’événement, par connexion, pour un horodatage spécifique.
* Consultez votre utilisation de trois façons, chacune d’entre elles étant décrite plus en détail ci-dessous :
   * Utilisez Analysis Workspace pour créer des rapports sur les événements du mois dernier.
   * Utilisez Report Builder pour créer des rapports sur les événements du mois dernier.
   * Utilisez l’API CJA pour créer un rapport automatisé.

Gérer l’utilisation de CJA :

* Définissez une fenêtre dynamique de données.

## Estimer la taille de connexion {#estimate-size}

Vous devrez peut-être connaître le nombre de lignes de données d’événement actuellement présentes dans [!UICONTROL Customer Journey Analytics]. Pour un compte rendu détaillé de l’utilisation des enregistrements de données d’événement (lignes de données) de votre organisation, procédez comme suit **pour chacune des connexions créées par votre organisation**.

>[!NOTE]
>
>Effectuez cette opération le premier vendredi de chaque mois, car Adobe publie votre dernier rapport d’utilisation ce jour-là.

1. Dans [!UICONTROL Customer Journey Analytics], sélectionnez l’onglet **[!UICONTROL Connexions]**.

   Vous pouvez voir la liste de toutes les connexions actuelles.

1. Cliquez sur chaque nom de connexion pour accéder au gestionnaire de connexions.

1. Additionnez les **[!UICONTROL Enregistrements de données d’événement disponibles]** pour chaque connexion créée par votre organisation. (Selon la taille de votre connexion, le numéro peut mettre un certain temps à apparaître.)

   ![Données d’événement](./assets/event-data.png)

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

## Créer un projet Espace de travail à l’aide de toutes les données d’événement {#workspace-event-data}

Cette méthode vous permet d’effectuer une analyse plus approfondie des données d’utilisation, ainsi que de l’historique de votre utilisation.

1. Avant de créer le projet dans Espace de travail, [créez une vue de données](/help/data-views/create-dataview.md) pour chacune des connexions, sans aucun filtre appliqué.

>[!WARNING]
>
>    Ne créez pas de nouvelle connexion qui englobe toutes les données à des fins de mesure de l’utilisation, car cela doublerait votre utilisation.

1. Dans Espace de travail, créez des projets basés sur chacune des vues de données et extrayez tous les événements (depuis la liste déroulante **[!UICONTROL Mesures]**) jusqu’au premier vendredi du mois, à partir du premier jour de votre contrat CJA actuel.

   ![Événements](./assets/events-usage.png)

   Cela vous donnera une bonne idée de la tendance d’utilisation, mois après mois.

1. Selon vos besoins, vous pouvez effectuer une analyse en profondeur par jeu de données, etc.

## Créer un bloc de données dans Report Builder {#arb}

Dans Report Builder, [créez un bloc de données](/help/report-builder/create-a-data-block.md) pour chaque vue de données, puis additionnez-les.

## Créer un rapport automatisé dans l’API CJA {#api-report}

1. Utilisez l’[API de création de rapports CJA](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) afin de générer un rapport sur toutes les données d’événement, **pour chaque connexion**. Configurez-la pour générer le rapport

   * le premier vendredi de chaque mois ;
   * à partir du premier jour de votre contrat CJA actuel.

   Cela vous donnera une bonne idée de la tendance d’utilisation, mois après mois. Cela vous donnera le nombre total de lignes de toutes les connexions CJA.

1. Utilisez Excel pour personnaliser davantage ce rapport.

## Gérer l’utilisation en définissant une fenêtre dynamique de données {#rolling}

L’[interface utilisateur des connexions](/help/connections/create-connection.md) vous permet de définir la conservation des données CJA sous la forme d’une fenêtre dynamique en mois (1 mois, 3 mois, 6 mois, etc.), au niveau de la connexion afin de gérer l’utilisation.

Lʼavantage principal est que vous ne stockez ou ne créez des rapports que sur les données applicables et utiles, et supprimez les données plus anciennes qui ne sont plus utiles. Elle vous aide à rester dans les limites de votre contrat et réduit le risque de surcoût.

Si vous laissez la valeur par défaut (non cochée), la période de conservation sera remplacée par le paramètre de conservation des données d’Adobe Experience Platform. Si vous avez 25 mois de données dans Experience Platform, CJA obtiendra 25 mois de données par renvoi. Si vous avez supprimé 10 de ces mois dans Platform, CJA conservera les 15 mois restants.

La conservation des données est basée sur les horodatages des jeux de données dʼévénement et sʼapplique uniquement aux jeux de données dʼévénement. Aucun paramètre de fenêtre dynamique de conservation des données nʼexiste pour les jeux de données de profil ou de recherche, car il nʼexiste aucun horodatage applicable. Si votre connexion inclut des jeux de données de profil ou de recherche, étant donné qu’ils sont associés à des jeux de données d’événement, les données sont conservées dans CJA en fonction de vos paramètres de conservation des données sur les dates et heures du jeu de données d’événement.

