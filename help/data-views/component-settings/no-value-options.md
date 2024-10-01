---
title: Paramètres du composant Aucune option de valeur
description: Déterminez comment gérer une dimension si elle est vide.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: a236b2126c4b998b4d97caab014556e3ee3a9e83
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 93%

---

# Paramètres du composant Aucune option de valeur {#no-value-options-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_dimension_novalueoptions"
>title="Pas d’option de valeur"
>abstract="Configurez le comportement par défaut lorsqu’une dimension ne contient aucune valeur."

<!-- markdownlint-enable MD034 -->


Aucune option de valeur vous permet de déterminer comment Analysis Workspace gère les situations dans lesquelles un événement d’un jeu de données contient une mesure, mais où la dimension ne contenait pas de valeur. Vous pouvez choisir le nom de cet élément de dimension, le masquer entièrement ou même le traiter comme une valeur réelle.

![Pas d’option de valeur](../assets/no-value-options.png)

## Paramètres {#settings}

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Si affiché, appeler « Aucune valeur »] | Champ de texte qui permet de renommer l’élément de dimension **[!UICONTROL Aucune valeur]** en autre chose. |
| [!UICONTROL Ne pas afficher No value par défaut] | Nʼaffiche pas cette valeur dans le compte rendu des performances. Les occurrences de mesure non liées à cette dimension ne sont pas visibles dans le rapport. |
| [!UICONTROL Afficher No value par défaut] | Affiche cette valeur dans les rapports. |
| [!UICONTROL Traiter No value comme une valeur] | Ce paramètre remplace les valeurs vides dans les données par le texte que vous avez spécifié sous [!UICONTROL Si affiché, appeler « Aucune valeur »]. Par exemple, si vous aviez des types d’appareil mobile en tant que dimension, vous pouviez renommer lʼélément **[!UICONTROL No value]** en « Bureau ». Lorsque vous remplacez ce champ par une valeur personnalisée, la valeur personnalisée est traitée comme une valeur de chaîne légitime. Par conséquent, si vous entrez la valeur « Rouge » dans ce champ, toutes les instances de la chaîne « Rouge » apparaissant dans les données elles-mêmes sont également reprises sous le même élément de ligne que vous avez spécifié. |

{style="table-layout:auto"}

## Blog post

Voici un article de blog connexe sur la [gestion de &quot;aucune valeur&quot; en Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/handling-quot-no-value-quot-in-customer-journey-analytics/ba-p/597339).
