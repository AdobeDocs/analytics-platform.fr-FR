---
title: Paramètres du composant de regroupement de valeurs
description: Combinez des valeurs numériques dans une dimension.
exl-id: 52f9abf6-69f1-47d0-86ab-57123bc178d5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
autotag-review: '2026-05-19T09:10:00.872Z'
TQID: 'https://experienceleague.adobe.com/LHEk3h9utGW73kSo2-SgY5NgKi11uktKR0ucPxw9IcY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 100%

---

# Paramètres du composant [!UICONTROL Regroupement de valeurs] {#value-bucketing-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_value_bucketing"
>title="Groupement des valeurs"
>abstract="Regroupez les valeurs dans des plages spécifiques. Ces plages apparaissent comme des éléments de dimension dans les rapports."

<!-- markdownlint-enable MD034 -->


Lors de la création ou de la modification d’une vue de données, le regroupement de valeurs permet de combiner des valeurs numériques en fonction d’une plage de données. Elle n’est disponible que pour les dimensions utilisant des types de données de schéma entier ou double.

![Classification des valeurs](../assets/value-bucketing.png)

Le regroupement de valeurs est utile lorsque vous souhaitez regrouper des plages au lieu de traiter chaque nombre unique comme un élément de dimension distinct. Par exemple, un regroupement de valeurs « de 5 à 10 » sʼaffiche en tant quʼélément de ligne « 5 à 10 » dans Analysis Workspace.

Si vous souhaitez bénéficier de la flexibilité de création de comptes rendus de performances sur une dimension regroupée et non regroupée, faites glisser deux copies du composant dans la liste des dimensions disponibles. Activez le regroupement sur une dimension et désactivez-la sur l’autre.

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Valeur du compartiment] | Case à cocher qui vous permet d’activer le regroupement. |
| [!UICONTROL Inférieur à] | La limite supérieure du premier intervalle de dimension. |
| [!UICONTROL incluant] [!UICONTROL et inférieur à] | Limites des regroupements suivants. |
| [!UICONTROL Supérieur ou égal à] | Limite inférieure du dernier regroupement de dimension. |
| [!UICONTROL Ajouter le compartiment] | Permet dʼajouter un autre regroupement au regroupement des dimensions numériques. Vous pouvez ajouter jusqu’à 20 regroupements dans une seule dimension. |

{style="table-layout:auto"}
