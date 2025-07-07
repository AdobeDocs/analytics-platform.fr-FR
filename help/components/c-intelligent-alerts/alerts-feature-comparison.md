---
description: Découvrez en quoi les alertes diffèrent d’Adobe Analytics dans Customer Journey Analytics
title: Comparaison des fonctionnalités d’alertes dans Customer Journey Analytics et Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
source-git-commit: 9e07dfc84bc06aef987d99c225cefb4e0406f552
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 24%

---

# Comparaison des fonctionnalités des alertes

Le processus d’utilisation des alertes dans Customer Journey Analytics est presque identique à celui des alertes dans Adobe Analytics. Cependant, il existe des différences importantes. Les sections suivantes décrivent les principales différences.

## Les alertes horaires ne sont pas disponibles

Les alertes horaires ne sont **pas disponibles** Customer Journey Analytics tandis que les alertes horaires sont disponibles dans Adobe Analytics. Dans Customer Journey Analytics, les alertes peuvent être configurées tous les jours, toutes les semaines ou tous les mois.

Vous pouvez ingérer des données dans Adobe Experience Platform de différentes manières. Par conséquent, l’exhaustivité et la disponibilité des données ne peuvent pas être atteintes de manière fiable dans les contraintes d’une heure.  La flexibilité de l’ingestion de données implique que les alertes horaires ne sont pas pratiques en raison du risque élevé de données incomplètes. Pour plus d’informations, voir [Les délais d’ingestion des données varient](#data-ingestion-times-vary-in-customer-journey-analytics).

## Les délais d’ingestion des données varient

Le temps nécessaire pour que les données soient complètes et disponibles pour faire l’objet de rapports dans Customer Journey Analytics varie selon l’entreprise.

Cela est dû aux raisons suivantes :

* La capacité de Platform à contenir tous les types de schémas et de données

  Contrairement à Adobe Analytics (qui crée des rapports uniquement sur les données web), [de nombreux types de données différents peuvent être ingérés dans Adobe Experience Platform](/help/data-ingestion/data-ingestion.md) pour faire l’objet de rapports dans Customer Journey Analytics, et tous les types de données ne peuvent pas être envoyés de manière séquentielle et en temps réel.

* Un retard dans la diffusion des données par lots aux jeux de données Platform

  Bien que certaines données puissent être disponibles pour générer des rapports plus tôt, toutes les données [ par lots sont ingérées dans un jeu de données Platform](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.), généralement entre 3 et 9 heures après l’heure de l’événement de données. Pour que les alertes soient exactes, l’ingestion des données doit être terminée et toutes les données par lot disponibles dans le jeu de données . <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Pour ces raisons, l’ingestion des données des différents types de données d’événement pouvant être ingérées n’est terminée qu’après un certain délai, généralement entre 3 et 9 heures après l’heure de l’événement de données. Pour que les alertes soient précises, les données d’événement d’une plage d’événements donnée doivent être complètes, ce qui signifie qu’Adobe ne reçoit plus de données d’événement pour la plage d’événements spécifiée.

Pour tenir compte de ce délai d’ingestion, les alertes sont envoyées avec un délai par défaut de 9 heures.

Vous pouvez régler le délai par défaut de 9 heures sur une valeur comprise entre 0 et 24 heures. Toutefois, si vous réduisez le délai en dessous de 9 heures, cela peut signifier que vous signalez des données incomplètes, ce qui entraîne des informations d’alerte inexactes.

Pour plus d’informations sur la manière d’ajuster le délai et sur les facteurs à prendre en compte lorsque vous le faites, consultez la section [Créer des alertes](/help/components/c-intelligent-alerts/alert-builder.md).

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## Création d’une alerte

Dans Analysis Workspace d’Adobe Analytics, vous pouvez [créer des alertes depuis Analysis Workspace de plusieurs façons](https://experienceleague.adobe.com/fr/docs/analytics/components/alerts/alert-builder). Dans Customer Journey Analytics, vous pouvez uniquement [créer une alerte](alert-builder.md) dans Analysis Workspace à partir d’une sélection dans un tableau à structure libre.

Adobe Analytics et Customer Journey Analytics prennent en charge la création d’alertes par le biais du [gestionnaire d’alertes](alert-manager.md)
