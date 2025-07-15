---
description: Découvrez comment utiliser les rapports en temps réel dans Analysis Workspace.
title: Utilisation Des Rapports En Temps Réel
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
source-git-commit: 82aefce30834d6400d338896dc1968e37596393e
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 9%

---

# Utiliser les rapports en temps réel

{{release-limited-testing}}

Pour utiliser les rapports en temps réel, activez le bouton (bascule) **[!UICONTROL Actualisation en temps réel]** sur l’un des panneaux suivants de votre projet Workspace :



* [Panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md)
* [Tableau à structure libre](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Attribution](/help/analysis-workspace/c-panels/attribution.md)
* [Élément suivant ou précédent](/help/analysis-workspace/c-panels/next-previous.md)
* [Aperçu rapide](/help/analysis-workspace/c-panels/quickinsight.md)

Un message contenant la date et l’heure de la dernière actualisation des données s’affiche. Par exemple : [!UICONTROL &#x200B; *Dernière actualisation à 19 h 55*].

Sélectionnez la période en temps réel pour laquelle vous souhaitez créer un rapport dans le menu déroulant. Les options disponibles sont les suivantes :

* [!UICONTROL 15 dernières minutes]
* [!UICONTROL 30 dernières minutes]
* [!UICONTROL Dernière heure &#x200B;]
* [!UICONTROL 8 dernières heures]
* [!UICONTROL Dernières 24 heures]

Toutes les visualisations du panneau sont désormais mises à jour chaque minute pendant 30 minutes maximum, tandis que l’onglet du navigateur avec le panneau Actualisation en temps réel activé est actif.

![Actualisation en temps réel](assets/real-time-refresh.gif)

Au bout de 30 minutes, ou dès que l’onglet du navigateur devient inactif, le bouton **[!UICONTROL Actualisation en temps réel]** est automatiquement désactivé et les mises à jour en temps réel sont arrêtées.
