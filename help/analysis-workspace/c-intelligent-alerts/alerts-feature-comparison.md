---
description: Découvrez en quoi les alertes intelligentes diffèrent en Customer Journey Analytics par rapport à Adobe Analytics
title: Customer Journey Analytics de comparaison des fonctionnalités des alertes intelligentes et Adobe Analytics
feature: Workspace Basics
role: User, Admin
source-git-commit: 74ad39f6ccc6436f7c8540b7d8b69b20b93d2b5c
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Comparaison des fonctionnalités des alertes intelligentes : Customer Journey Analytics et Adobe Analytics

{{release-limited-testing}}

Le processus d’utilisation des alertes intelligentes dans Customer Journey Analytics est presque identique à celui des alertes intelligentes dans Adobe Analytics. Cependant, il existe des différences importantes.

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

Pour plus d&#39;informations sur la façon d&#39;ajuster le délai et les facteurs à prendre en compte lors de cette opération, voir <!--add link -->.

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->





