---
title: Paramètres du composant de regroupement de valeurs
description: Combinez des valeurs numériques dans une dimension.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 12%

---


# Paramètres du composant de remontée de valeurs

Lors de la création ou de la modification d’une vue de données, le regroupement de valeurs permet de combiner des valeurs numériques basées sur une plage. Elle n’est disponible que pour les dimensions utilisant des types de données de schéma entier ou double.

Le regroupement de valeurs est utile lorsque vous souhaitez regrouper des plages au lieu de traiter chaque nombre unique comme un élément de dimension distinct. Par exemple, un compartiment de &quot;Entre 5 et 10&quot; apparaît comme une ligne &quot;5 à 10&quot; dans Analysis Workspace.

![Classification des valeurs](../assets/value-bucketing.png)

Si vous souhaitez bénéficier de la flexibilité de création de rapports sur une dimension regroupée et non regroupée, faites glisser deux copies du composant dans la liste des dimensions disponibles. Activez le regroupement sur une dimension et désactivez-la sur l’autre.

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Valeur du compartiment] | Case à cocher qui vous permet d’activer le regroupement. |
| [!UICONTROL Inférieur à] | La limite supérieure du premier compartiment de dimension. |
|  [!UICONTROL Inclusion et inférieur à] | Limites des intervalles suivants. |
| [!UICONTROL Supérieur ou égal à] | Limite inférieure du dernier compartiment de dimension. |
| [!UICONTROL Ajouter le compartiment] | Permet dʼajouter un autre regroupement au regroupement des dimensions numériques. Vous pouvez ajouter jusqu’à 20 intervalles dans une seule dimension. |
