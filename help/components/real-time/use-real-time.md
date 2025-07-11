---
description: Découvrez comment utiliser les rapports en temps réel dans Analysis Workspace.
title: Utilisation Des Rapports En Temps Réel
feature: Filters, Segments
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
source-git-commit: 24834f6a1424a885c6f7b3dcf0ad84375e21b462
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 5%

---


# Utiliser les rapports en temps réel

{{release-limited-testing}}

Pour utiliser les rapports en temps réel, activez le bouton (bascule) **[!UICONTROL Actualisation en temps réel]** sur l’un des panneaux suivants de votre projet Workspace :



* [Panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md)
* [Panneau à structure libre](/help/analysis-workspace/c-panels/freeform-panel.md)
* ...

Un message contenant la date et l’heure de la dernière actualisation des données s’affiche. Par exemple : [!UICONTROL &#x200B; *Dernière actualisation à 19 h 55*].

Sélectionnez la période en temps réel pour laquelle vous souhaitez créer un rapport dans le menu déroulant. Les options disponibles sont les suivantes :

* [!UICONTROL 15 dernières minutes]
* [!UICONTROL 30 dernières minutes]
* [!UICONTROL Dernière heure &#x200B;]
* [!UICONTROL 8 dernières heures]
* [!UICONTROL Dernières 24 heures]

Toutes les visualisations sont désormais mises à jour chaque minute pendant 30 minutes maximum, tandis que l’onglet du navigateur avec le panneau Actualisation en temps réel activé est actif.

![Actualisation en temps réel](assets/real-time-refresh.gif)

Au bout de 30 minutes, ou dès que l’onglet du navigateur devient inactif, le bouton **[!UICONTROL Actualisation en temps réel]** est automatiquement désactivé et les mises à jour en temps réel sont arrêtées.
