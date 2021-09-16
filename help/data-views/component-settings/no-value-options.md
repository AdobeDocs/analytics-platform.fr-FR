---
title: Aucun paramètre de composant Options de valeur
description: Déterminez comment gérer une dimension si elle est vide.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 35%

---


# Paramètres du composant No Value Options

Aucune option de valeur vous permet de déterminer comment Analysis Workspace gère les situations dans lesquelles un événement d’un jeu de données contient une mesure, mais où la dimension ne contenait pas de valeur. Vous pouvez choisir le nom de cet élément de dimension, le masquer entièrement ou même le traiter comme une valeur réelle.

![Pas d’option de valeur](../assets/no-value-options.png)

| Paramètre | Description |
| --- | --- |
| [!UICONTROL S’il est affiché, appelez &quot;No value&quot; (Pas de valeur).] | Champ de texte qui permet de renommer l’élément de dimension **[!UICONTROL Aucune valeur]** à autre chose. |
| [!UICONTROL Ne pas afficher No value par défaut] | Nʼaffiche pas cette valeur dans le compte rendu des performances. Les occurrences de mesure non liées à cette dimension ne sont pas visibles dans le rapport. |
| [!UICONTROL Afficher No value par défaut] | Affiche cette valeur dans les rapports. |
| [!UICONTROL Traiter No value comme une valeur] | Remplace les valeurs vides dans les données par le texte que vous avez spécifié sous [!UICONTROL Si affiché, appelez &quot;Aucune valeur&quot;]. Par exemple, si vous aviez des types dʼéquipement mobile en tant que dimension, vous pouviez renommer lʼélément **[!UICONTROL No value]** en « Bureau ». Lorsque vous définissez ce champ sur une valeur personnalisée, la valeur personnalisée est traitée comme une valeur de chaîne légitime. Par conséquent, si vous entrez la valeur « Rouge » dans ce champ, toutes les instances de la chaîne « Rouge » apparaissant dans les données elles-mêmes sont également reprises sous le même élément de ligne que vous avez spécifié. |
