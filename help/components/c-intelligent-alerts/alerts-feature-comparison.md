---
description: Découvrez en quoi les alertes diffèrent en Customer Journey Analytics par rapport à Adobe Analytics
title: Customer Journey Analytics de comparaison des fonctionnalités d’alertes et Adobe Analytics
feature: Workspace Basics
role: User, Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---

# Comparaison des fonctionnalités des alertes : Customer Journey Analytics et Adobe Analytics

Le processus d’utilisation des alertes en Customer Journey Analytics est presque identique à celui d’Adobe Analytics. Cependant, il existe des différences importantes.

Les sections suivantes décrivent les principales différences.

## Les alertes horaires ne sont pas disponibles dans Customer Journey Analytics

Les alertes horaires ne sont pas disponibles en Customer Journey Analytics comme dans Adobe Analytics. Dans Customer Journey Analytics, les alertes peuvent être configurées tous les jours, toutes les semaines ou tous les mois.

Cela est dû aux différentes façons dont les données peuvent être ingérées dans Adobe Experience Platform avant d’être signalées dans Customer Journey Analytics. L’exhaustivité et la disponibilité des données ne peuvent pas être obtenues de manière fiable en moins d’une heure, ce qui rend les alertes horaires impraticables en raison du fort potentiel de données incomplètes. Pour plus d’informations, voir [Les délais d’ingestion des données varient](#data-ingestion-times-vary-in-customer-journey-analytics).

## Les délais d’ingestion des données varient selon le Customer Journey Analytics

Le temps nécessaire pour que les données soient complètes et disponibles pour générer des rapports dans Customer Journey Analytics varie selon l’organisation.

Cela est dû aux raisons suivantes :

* Capacité de Platform à contenir tous types et schémas de données

  Contrairement à Adobe Analytics (qui ne crée des rapports que sur les données web), [de nombreux types de données différents peuvent être ingérés dans Adobe Experience Platform](/help/data-ingestion/data-ingestion.md) pour faire l’objet de rapports dans Customer Journey Analytics. De plus, tous les types de données ne peuvent pas être envoyés de manière séquentielle et en temps réel.

* Retard de la diffusion des données par lots vers les jeux de données Platform

  Bien que certaines données puissent être disponibles pour la génération de rapports plus tôt, toutes les [données de lot sont ingérées dans un jeu de données Platform](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.), généralement entre 3 et 9 heures après l’heure de l’événement de données. Pour que les alertes soient exactes, l’ingestion des données doit être terminée, avec toutes les données de lot disponibles dans le jeu de données. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Pour ces raisons, l’ingestion de données pour les différents types de données d’événement pouvant être ingérés n’est terminée qu’après un certain délai, généralement entre 3 et 9 heures au-delà de l’heure de l’événement de données. Pour que les alertes soient exactes, les données d’événement d’une période donnée doivent être complètes, ce qui signifie que l’Adobe ne reçoit plus de données d’événement pour la période spécifiée.

Pour tenir compte de ce délai d’ingestion, les alertes ont un délai par défaut de 9 heures avant leur envoi.

Vous pouvez ajuster le délai par défaut de 9 heures entre 0 et 24 heures. Cependant, réduire le délai en dessous de 9 heures peut signifier que vous signalez des données incomplètes, ce qui entraîne des informations d’alerte inexactes.

Pour plus d’informations sur la façon d’ajuster le délai et les facteurs à prendre en compte lors de cette opération, voir [Créer des alertes](/help/components/c-intelligent-alerts/alert-builder.md).

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## L’option de création d’une alerte à partir d’Analysis Workspace n’est pas disponible

Dans Analysis Workspace dans Adobe Analytics, vous pouvez créer des alertes à partir d’Analysis Workspace de l’une des façons décrites ci-dessous. Dans Customer Journey Analytics, les options de création d’alertes à partir d’Analysis Workspace ne sont pas encore disponibles. Accédez plutôt au Générateur d’alertes, comme décrit dans la section [Créer des alertes](/help/components/c-intelligent-alerts/alert-builder.md).

Dans Adobe Analytics, les options suivantes sont disponibles :

* Sélectionnez un ou plusieurs éléments de ligne dans un tableau à structure libre, puis cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Créer une alerte d’après la sélection]**.

  Le créateur d’alertes est ainsi prérempli instantanément afin de créer une alerte avec les mesures et filtres corrects.

* Ouvrez un projet dans Analysis Workspace, puis sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Créer une alerte]**.

* Ouvrez un projet dans Analysis Workspace, puis utilisez le raccourci suivant :

  `ctrl (or cmd) + shift + a`






