---
description: Panneau qui affiche les éléments de dimension précédents ou suivants pour une dimension spécifique.
title: Panneau d’éléments suivant ou précédent
feature: Panels
role: User, Admin
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 31%

---

# Panneau d’éléments suivant ou précédent {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_button"
>title="Élément suivant ou précédent"
>abstract="Créez un panneau pour comprendre les dimensions précédentes des personnes ou la dimension suivante à laquelle ils accèdent."

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_panel"
>title="Élément suivant ou précédent"
>abstract="Analysez les endroits les plus courants d’où viennent les visiteurs et visiteuses et ceux où ils vont ensuite.<br/><br/>**Dimension** : sélectionnez une dimension. **Page**, par exemple.<br/>**Élément de dimension** : sélectionnez un élément de dimension. Par exemple **Page d’accueil**.<br/>**Direction** : sélectionnez **Suivant** pour afficher les éléments de dimension juste après l’élément de dimension sélectionné. Sélectionnez **Précédent** pour afficher les éléments de dimension qui mènent vers l’élément de dimension sélectionné.<br/>**Conteneur** : sélectionnez **Session** pour afficher les éléments de dimension suivants/précédents dans la même session, ou sélectionnez **Personne** pour afficher l’élément de dimension suivant/précédent pour la même personne."

<!-- markdownlint-enable MD034 -->



Le panneau **[!UICONTROL Élément suivant ou précédent]** contient un certain nombre de tableaux et de visualisations pour identifier l’élément de dimension suivant ou précédent pour une dimension spécifique. Par exemple, vous souhaitez peut-être explorer les pages les plus consultées par les clients après avoir visité la page d’accueil.

## Sélectionnez l’option  

Pour utiliser un panneau **[!UICONTROL Elément suivant ou précédent]** :

1. Créez un panneau **[!UICONTROL Élément suivant ou précédent]**. Pour plus d’informations sur la création d’un panneau, voir [Création d’un panneau](panels.md#create-a-panel).

1. Spécifiez la [entrée](#panel-input) pour le panneau.

1. Observez la [sortie](#panel-output) pour le panneau.

### Entrée de panneau

Vous pouvez configurer le panneau [!UICONTROL Élément suivant ou précédent] à l’aide des paramètres d’entrée suivants :

![Panneau d’élément suivant ou précédent](assets/next-or-previous-item.png)

| Entrée | Description |
| --- | --- |
| **[!UICONTROL Dimension]** | Sélectionnez la dimension pour laquelle vous souhaitez explorer les éléments suivants ou précédents. |
| **[!UICONTROL Élément de dimension]** | Sélectionnez l’élément de dimension spécifique au centre de votre requête suivante/précédente. |
| **[!UICONTROL Direction]** | Indiquez si vous recherchez l’élément de dimension [!UICONTROL Suivant] ou [!UICONTROL Précédent] . |
| **[!UICONTROL Conteneur]** | Sélectionnez le conteneur, [!UICONTROL Session] ou [!UICONTROL Personne] (par défaut), pour déterminer la portée de votre requête. |

{style="table-layout:auto"}

Sélectionnez **[!UICONTROL Build]** pour créer le panneau.

### Sortie de panneau

Le panneau [!UICONTROL Elément suivant ou précédent] renvoie un vaste ensemble de données et de visualisations pour vous aider à mieux comprendre les occurrences qui suivent ou précèdent des éléments de dimension spécifiques.


![Sortie de panneau suivante/précédente](assets/next-or-previous-item-output.png)


| Visualisation | Description |
| --- | --- |
| **[!UICONTROL Barre horizontale]** | Répertorie les éléments suivants (ou précédents) en fonction de l’élément de dimension que vous sélectionnez. Le survol d’une barre individuelle met en surbrillance l’élément correspondant dans le tableau à structure libre. |
| **[!UICONTROL Numéro de résumé]** | Numéro de résumé de haut niveau de toutes les occurrences d’élément de dimension précédente ou suivante pour le mois en cours (à ce jour). |
| **[!UICONTROL Tableau à structure libre]** | Répertorie les éléments suivants (ou précédents) en fonction de l’élément de dimension que vous sélectionnez, au format tableau. Par exemple, les pages les plus populaires (par occurrence) sur lesquelles les utilisateurs se sont rendus après (ou avant) la page d’accueil ou la page de l’espace de travail. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Créer un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>