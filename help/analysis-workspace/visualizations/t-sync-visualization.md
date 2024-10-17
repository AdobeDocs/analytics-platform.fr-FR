---
description: Synchronisez les visualisations pour contrôler quel tableau de données ou source de données correspond à une visualisation.
keywords: Analysis Workspace;Synchroniser une visualisation avec une source de données
title: Gestion des sources de données
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: 388e008f4ee092dd8224bfacd020cdf762d4fb82
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 27%

---

# Gestion des sources de données {#manage-data-sources}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_lockselection"
>title="Verrouiller la sélection"
>abstract="Activez ce paramètre pour verrouiller la visualisation sur les positions ou les éléments sélectionnés dans la source de données."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_lockselection_showtable"
>title="Afficher le tableau"
>abstract="Sélectionnez **[!UICONTROL Afficher le tableau]** pour générer une nouvelle source de données pour votre visualisation actuelle, distincte de la source de données d’origine."

<!-- markdownlint-enable MD034 -->



Synchronisez les visualisations pour contrôler quel tableau de données ou source de données correspond à une visualisation.

>[!TIP]
>
>Vous pouvez déterminer les visualisations qui sont liées par la couleur de ![StatusOrange](/help/assets/icons/StatusOrange.svg) en regard du titre des visualisations. Les mêmes couleurs signifient que les visualisations reposent sur la même source de données.
>

Vous pouvez afficher ou masquer la source de données. Vous pouvez également verrouiller la sélection sur des positions ou des éléments sélectionnés. Ces paramètres déterminent de quelle façon la visualisation change (si elle change) lorsque de nouvelles données se présentent.

![La boîte de dialogue de l’option Source de données affiche les options décrites dans la section suivante.](assets/lock-selection.png)


| Option | Description |
|--- |--- |
| **[!UICONTROL Source de données]** | Sélectionnez la source de données sur laquelle repose la visualisation dans le menu déroulant. |
| **[!UICONTROL Visualisations liées]** | Répertorie toutes les visualisations liées. S’applique à la source de données (tableau à structure libre). |
| **[!UICONTROL Afficher la source de données]** | Permet d’afficher ou de masquer la source de données (tableau à structure libre) qui correspond à la visualisation. |
| **[!UICONTROL Verrouiller la sélection]** | Sélectionnez cette option pour verrouiller la visualisation ![LockClosed](/help/assets/icons/LockClosed.svg) sur les données actuellement sélectionnées dans le tableau de données correspondant. Une fois activé, sélectionnez entre :  <ul><li>**Positions sélectionnées** : la visualisation est verrouillée sur les **positions** sélectionnées dans le tableau de données correspondant. Ces positions continuent d’être visualisées, même si les éléments spécifiques à ces positions changent (par exemple en raison d’un tri ou d’un filtrage). Par exemple, sélectionnez cette option si vous souhaitez afficher les cinq premiers noms de campagne répertoriés en permanence dans la source de données de cette visualisation. Quels que soient les noms de campagne qui apparaissent.</li> <li>**Éléments sélectionnés** : la visualisation est verrouillée sur les **éléments** spécifiques actuellement sélectionnés dans le tableau de données correspondant. Ces éléments continuent d’être visualisés, même s’ils changent leur classement parmi les éléments du tableau. Par exemple, sélectionnez cette option si vous souhaitez afficher les cinq mêmes noms de campagne spécifiques répertoriés en permanence dans la source de données de cette visualisation. Quel que soit le classement de ces noms de campagne.</li></ul>Si la visualisation est verrouillée sur des données qui ne sont plus visibles dans le tableau de données connecté, vous pouvez générer un nouveau tableau. Sélectionnez **[!UICONTROL Afficher le tableau]** pour générer une nouvelle source de données pour votre visualisation actuelle, distincte de la source de données d’origine. |
