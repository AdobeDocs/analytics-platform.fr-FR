---
description: Découvrez comment synchroniser un tableau à structure libre ou une source de données avec la visualisation correspondante.
keywords: Analysis Workspace;Synchroniser une visualisation avec une source de données
title: Gestion des sources de données
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '436'
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
