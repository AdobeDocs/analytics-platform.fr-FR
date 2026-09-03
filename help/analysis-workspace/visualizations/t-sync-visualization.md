---
description: Découvrez comment synchroniser un tableau à structure libre ou une source de données avec la visualisation correspondante.
keywords: Analysis Workspace;Synchroniser une visualisation avec une source de données
title: Gérer les sources de données
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
autotag-review: '2026-05-19T08:30:43.942Z'
TQID: 'https://experienceleague.adobe.com/UU1RlISeu-NOFAttolNcjV-p2EgtxBPFy3w7ZrLz-vY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 89%

---

# Gérer des sources de données {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Verrouiller la sélection"
>abstract="Activez ce paramètre pour verrouiller la visualisation sur les positions ou les éléments sélectionnés dans la source de données."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Afficher le tableau"
>abstract="Sélectionnez **[!UICONTROL Afficher le tableau]** pour générer une nouvelle source de données pour votre visualisation actuelle, distincte de la source de données d’origine."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Afficher le tableau"
>abstract="Sélectionnez **[!UICONTROL Afficher le tableau]** pour générer une nouvelle source de données pour votre visualisation actuelle, distincte de la source de données d’origine."

La synchronisation des visualisations vous permet de contrôler le tableau à structure libre ou la source de données qui correspond à une visualisation.

>[!TIP]
>
>Vous pouvez savoir quelles visualisations sont liées d’après la couleur de l’icône ![StatusOrange](/help/assets/icons/StatusOrange.svg) à côté du titre des visualisations. Les mêmes couleurs signifient que les visualisations reposent sur la même source de données.
>

Vous pouvez afficher ou masquer la source de données. Vous pouvez également verrouiller la sélection à des positions ou à des éléments sélectionnés. Ces paramètres déterminent de quelle façon la visualisation change (si elle change) lorsque de nouvelles données se présentent.

![Boîte de dialogue des options de la source de données présentant les options décrites dans la section suivante.](assets/lock-selection.png)


| Option | Description |
|--- |--- |
| **[!UICONTROL Source de données]** | Sélectionnez la source de données sur laquelle est basée la visualisation dans le menu déroulant. |
| **[!UICONTROL Visualisations liées]** | Répertorie toutes les visualisations liées. S’applique à la source de données (tableau à structure libre). |
| **[!UICONTROL Afficher la source de données]** | Permet d’afficher ou de masquer la source de données (tableau à structure libre) correspondant à la visualisation. |
| **[!UICONTROL Verrouiller la sélection]** | Sélectionnez cette option pour verrouiller la visualisation ![LockClosed](/help/assets/icons/LockClosed.svg) sur les données actuellement sélectionnées dans le tableau de données correspondant. Une foi l’activation effectuée, sélectionnez l’une des options ci-après :  <ul><li>**Positions sélectionnées** : la visualisation est verrouillée sur les **positions** sélectionnées dans le tableau de données correspondant. Ces positions continuent à être visualisées, même si les éléments spécifiques de ces positions changent (par exemple en raison d’un tri ou d’un filtrage). Sélectionnez cette option, par exemple, si vous souhaitez afficher en permanence dans cette visualisation les noms des cinq campagnes principales répertoriés dans la source de données. Quels que soient les noms de campagne qui s’affichent.</li> <li>**Éléments sélectionnés** : la visualisation est verrouillée sur les **éléments** spécifiques actuellement sélectionnés dans le tableau de données correspondant. Ces éléments resteront visibles, même si leur classement change parmi les éléments du tableau. Sélectionnez cette option, par exemple, si vous souhaitez afficher en permanence dans cette visualisation les noms des cinq mêmes campagnes spécifiques répertoriés dans la source de données. Quel que soit le classement de ces noms de campagne.</li></ul>Si la visualisation est verrouillée sur des données qui ne sont plus visibles dans le tableau de données connecté, vous pouvez générer un nouveau tableau. Sélectionnez **[!UICONTROL Afficher le tableau]** pour générer une nouvelle source de données pour votre visualisation actuelle, distincte de la source de données d’origine. |
