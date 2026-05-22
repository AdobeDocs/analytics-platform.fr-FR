---
description: Découvrez comment utiliser les rapports en temps réel dans Analysis Workspace.
title: Utilisation Des Rapports En Temps Réel
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
autotag-review: '2026-05-19T08:47:15.932Z'
TQID: 'https://experienceleague.adobe.com/t20pdV4qS-FIBGrxOXAD5xAD58f4gtN74uheJ94sK4s'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: d1779026-aeed-458e-a1c7-839d4acac922
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 12%

---

# Utiliser la création de rapports en temps réel {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="Actualisation en temps réel"
>abstract="Activez pour actualiser les données et les visualisations de ce panneau en temps réel."

Pour utiliser les rapports en temps réel, activez le bouton (bascule) **[!UICONTROL Actualisation en temps réel]** sur l’un des panneaux suivants de votre projet Workspace :

* [Panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md)
* [Tableau à structure libre](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Attribution](/help/analysis-workspace/c-panels/attribution.md)
* [Élément suivant ou précédent](/help/analysis-workspace/c-panels/next-previous.md)

Un message contenant la date et l’heure de la dernière actualisation des données s’affiche. Par exemple : [!UICONTROL &#x200B; *Dernière actualisation à 19 :55*].

Sélectionnez la période en temps réel sur laquelle vous souhaitez créer des rapports dans le menu déroulant. Les options disponibles sont les suivantes :

* [!UICONTROL 15 dernières minutes]
* [!UICONTROL 30 dernières minutes]
* [!UICONTROL Dernière heure &#x200B;]
* [!UICONTROL 8 dernières heures]
* [!UICONTROL Dernières 24 heures]

Toutes les visualisations du panneau sont désormais mises à jour chaque minute pendant 30 minutes maximum, tandis que l’onglet du navigateur avec le panneau Actualisation en temps réel activé est actif.

À titre d’exemple, consultez ci-dessous un instantané d’un **[!UICONTROL panneau de création de rapports en temps réel]** qui actualise la visualisation de la barre **[!UICONTROL Chiffre d’affaires total/heure]** et le tableau à structure libre **[!UICONTROL Chiffre d’affaires total/heure]** à mesure que le temps passe de **[!UICONTROL *06:26pm*]** à **[!UICONTROL *06:27 pm *]**.

![Actualisation en temps réel](assets/real-time-refresh.gif)

Au bout de 30 minutes, ou dès que l’onglet du navigateur devient inactif, le bouton **[!UICONTROL Actualisation en temps réel]** est automatiquement désactivé et les mises à jour en temps réel sont arrêtées.

Dès que le bouton (bascule) Actualisation en temps réel est désactivé, le panneau (et toutes les visualisations qu’il contient) revient à [utiliser les données et fonctionnalités de création de rapports standard de Customer Journey Analytics](real-time.md#how-it-works).
