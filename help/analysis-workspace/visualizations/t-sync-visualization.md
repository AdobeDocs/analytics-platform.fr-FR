---
description: Découvrez comment lier des visualisations à une source de données de tableau à structure libre.
keywords: Analysis Workspace;Synchroniser une visualisation avec une source de données
title: Gestion des sources de données de visualisation dans Analysis Workspace
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
autotag-review: '2026-05-19T08:30:43.942Z'
TQID: 'https://experienceleague.adobe.com/UU1RlISeu-NOFAttolNcjV-p2EgtxBPFy3w7ZrLz-vY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: f7d853a3b658328f952b675f838ce314b7c30fb1
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 18%
---
# Gérer des sources de données {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Verrouiller la sélection"
>abstract="Activez ce paramètre pour verrouiller la visualisation sur les positions ou les éléments sélectionnés dans la source de données."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Afficher le tableau"
>abstract="Sélectionnez **[!UICONTROL Afficher le tableau]** pour générer une nouvelle source de données pour la visualisation actuelle, distincte de la source de données d’origine."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Afficher le tableau"
>abstract="Sélectionnez **[!UICONTROL Afficher le tableau]** pour générer une nouvelle source de données pour votre visualisation actuelle, distincte de la source de données d’origine."

Dans Analysis Workspace, chaque visualisation repose sur une source de données, généralement un tableau à structure libre. La synchronisation des visualisations vous permet de contrôler quel tableau à structure libre ou quelle source de données correspond à une visualisation, et si la visualisation reste verrouillée sur des lignes spécifiques dans ce tableau.

>[!TIP]
>
>Vous pouvez savoir quelles visualisations sont liées d’après la couleur de l’icône ![StatusOrange](/help/assets/icons/StatusOrange.svg) à côté du titre des visualisations. Les mêmes couleurs signifient que les visualisations reposent sur la même source de données.
>

## Configurer les paramètres de la source de données {#configure}

1. Dans Analysis Workspace, accédez à la visualisation dont vous souhaitez configurer les paramètres de source de données ou de verrouillage.

1. Pointez sur la visualisation, puis sélectionnez l’icône **[!UICONTROL Paramètres]** ![Paramètre](/help/assets/icons/Setting.svg).

1. Sélectionnez l’onglet **[!UICONTROL Source de données]**.

   ![Onglet Source de données affichant la source de données, la visualisation liée et les paramètres de sélection de verrouillage.](assets/lock-selection.png)

1. Configurez l’un des paramètres suivants :

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL Source de données]** | Sélectionnez la source de données sur laquelle la visualisation est basée. |
   | **[!UICONTROL Visualisations liées]** | Répertorie toutes les visualisations liées à la source de données (tableau à structure libre). |
   | **[!UICONTROL Afficher la source de données]** | Afficher ou masquer la source de données (tableau à structure libre) correspondant à la visualisation. |
   | **[!UICONTROL Verrouiller la sélection]** | Verrouillez la visualisation sur les lignes actuellement sélectionnées dans la source de données, puis sélectionnez **[!UICONTROL Positions sélectionnées]** ou **[!UICONTROL Éléments sélectionnés]**. Voir [Verrouiller la sélection](#lock-selection). |

## Verrouiller la sélection {#lock-selection}

Le verrouillage de la sélection permet de garder une visualisation axée sur les lignes sélectionnées dans sa source de données, même lorsque le tableau change. Par exemple, le tableau change lorsque vous le triez ou le filtrez, modifiez sa période ou appliquez un segment. Une visualisation verrouillée affiche ![LockClosed](/help/assets/icons/LockClosed.svg) en regard de son titre.

Si les segments, dimensions ou mesures de la source de données changent et que les données verrouillées ne sont plus visibles, sélectionnez **[!UICONTROL Afficher le tableau]** pour générer une nouvelle source de données pour la visualisation, distincte de la source de données d’origine.

Lorsque vous verrouillez la sélection, choisissez l’une des options suivantes :

| Option | Description |
| --- | --- |
| **[!UICONTROL Postes sélectionnés]** | Verrouille la visualisation aux **positions** des lignes sélectionnées dans la source de données. Ces postes continuent d&#39;être visualisés, même si les éléments qui les composent changent. Par exemple, sélectionnez cette option pour toujours afficher les cinq premiers noms de campagne dans la source de données, quelles que soient les campagnes.<br><br>Si vous verrouillez des lignes de répartition qui ne figurent plus dans le tableau, la visualisation ne s’affiche pas. Pour le réafficher, mettez à jour le tableau (par exemple, sa période, ses segments ou ses filtres) ou mettez à jour la sélection du verrouillage. |
| **[!UICONTROL Éléments sélectionnés]** | Verrouille la visualisation sur les **éléments** spécifiques sélectionnés dans la source de données. Ces éléments continuent à être visualisés, même si leur classement dans le tableau change. Par exemple, sélectionnez cette option pour afficher toujours les cinq mêmes noms de campagne, quel que soit leur classement. |
