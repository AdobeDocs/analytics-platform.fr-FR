---
description: Panneau qui affiche les éléments de dimension suivants ou précédents pour une dimension spécifique.
title: Panneau d’éléments suivant ou précédent
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: bf5853a1d23d6e648024016a64dc67d09da3fbb4
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 36%

---

# Panneau d’éléments suivant ou précédent {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="Élément suivant ou élément précédent"
>abstract="Créez un panneau pour comprendre les dimensions précédentes des personnes ou la dimension suivante à laquelle ils accèdent."

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="Élément suivant ou précédent"
>abstract="Analysez les endroits les plus courants d’où viennent les visiteurs et visiteuses et ceux où ils vont ensuite.<br/><br/>**Dimension** : sélectionnez une dimension. **Page**, par exemple.<br/>**Élément de dimension** : sélectionnez un élément de dimension. Par exemple **Page d’accueil**.<br/>**Direction** : sélectionnez **Suivant** pour afficher les éléments de dimension juste après l’élément de dimension sélectionné. Sélectionnez **Précédent** pour afficher les éléments de dimension qui mènent vers l’élément de dimension sélectionné.<br/>**Conteneur** : sélectionnez **Session** pour afficher les éléments de dimension suivants/précédents dans la même session, ou sélectionnez **Personne** pour afficher l’élément de dimension suivant/précédent pour la même personne."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

*Cet article documente le panneau Élément suivant ou précédent dans le Customer Journey Analytics ****.<br/>Voir [Panneau d’élément suivant ou précédent](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous) pour la version **Adobe Analytics**de cet article.*

>[!ENDSHADEBOX]

Le panneau **[!UICONTROL Élément suivant ou précédent]** contient un certain nombre de tableaux et de visualisations pour identifier l’élément de dimension suivant ou précédent pour une dimension spécifique. Par exemple, vous pouvez vouloir explorer les pages auxquelles les clients et clientes ont accédé le plus souvent après avoir consulté la page d’accueil.

## Utilisation

Pour utiliser un panneau **[!UICONTROL Élément suivant ou précédent]** :

1. Créez un panneau **[!UICONTROL Élément suivant ou précédent]**. Pour plus d’informations sur la création d’un panneau, consultez [Créer un panneau](panels.md#create-a-panel).

1. Spécifiez l’[entrée](#panel-input) du panneau.

1. Observez la [sortie](#panel-output) du panneau.

### Entrée du panneau

Vous pouvez configurer le panneau [!UICONTROL Élément suivant ou précédent] à l’aide des paramètres de saisie suivants :

![Panneau Élément suivant ou précédent](assets/next-or-previous-item.png)

| Entrée | Description |
| --- | --- |
| **[!UICONTROL Dimension]** | Sélectionnez la dimension pour laquelle vous souhaitez explorer les éléments suivants ou précédents. |
| **[!UICONTROL Élément de dimension]** | Sélectionnez l’élément de dimension spécifique au centre de votre requête suivante/précédente. |
| **[!UICONTROL Direction]** | Indiquez si vous recherchez l’élément de dimension [!UICONTROL Suivant] ou [!UICONTROL Précédent]. |
| **[!UICONTROL Conteneur]** | Sélectionnez le conteneur, [!UICONTROL Session] ou [!UICONTROL Personne] (par défaut), pour déterminer la portée de votre recherche. |

{style="table-layout:auto"}

Sélectionnez **[!UICONTROL Créer]** pour créer le panneau.

### Sortie du panneau

Le panneau [!UICONTROL Élément suivant ou précédent] renvoie un riche ensemble de données et de visualisations pour vous aider à mieux comprendre les occurrences qui suivent ou précèdent des éléments de dimension spécifiques.


![Sortie du panneau Suivant/Précédent](assets/next-or-previous-item-output.png)


| Visualisation | Description |
| --- | --- |
| **[!UICONTROL Barre horizontale]** | Répertorie les éléments suivants (ou précédents) en fonction de l’élément de dimension que vous sélectionnez. Le survol d’une barre individuelle met en surbrillance l’élément correspondant dans le tableau à structure libre. |
| **[!UICONTROL Numéro de résumé]** | Numéro de synthèse de haut niveau de toutes les occurrences d’éléments de dimension suivants ou précédents pour le mois en cours (jusqu’à présent). |
| **[!UICONTROL Tableau à structure libre]** | Répertorie les éléments suivants (ou précédents) en fonction de l’élément de dimension que vous sélectionnez, sous forme de tableau. Par exemple, qui étaient les pages les plus populaires (par occurrences) auxquelles les personnes ont accédé après (ou avant) la page d’accueil ou la page de l’espace de travail. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Créer un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
