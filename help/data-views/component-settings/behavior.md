---
title: 'Paramètres des composants : comportement'
description: Définissez le comportement dʼune dimension ou dʼune mesure dans le reporting.
exl-id: 170f445f-1eac-4b70-8956-1afb0cb2d611
solution: Customer Journey Analytics
feature: Data Views
role: Admin
TQID: 'https://experienceleague.adobe.com/ra-O8TGxS6ByFEClZR7FtOnJ70YwclBiVMh9vubmGxk'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: e1471301-a189-438e-8d48-264a8db508a6
    internal-label: Data views
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 100%
---
# Paramètres des composants : comportement {#behavior-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_behavior"
>title="Comportement"
>abstract="Applicable aux composants de dimension et de mesure. Déterminez la façon dont les éléments de ligne de cette mesure sont agrégés. Indiquez si les valeurs de chaîne de cette dimension doivent être en minuscules ou non."

<!-- markdownlint-enable MD034 -->


Les paramètres de comportement sont disponibles pour les dimensions et les mesures. Les paramètres disponibles dépendent du type de composant et du type de données du schéma.

![Paramètres de comportement](../assets/behavior-settings.png)

## Paramètres de comportement des dimensions

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Minuscules] | Déduplique les lignes ayant la même valeur mais une casse différente. Si cette option est activée, toutes les instances dʼune dimension ayant la même valeur sont signalées en minuscules. Par exemple, supposons que vos données contiennent les valeurs `"liverpool"`, `"Liverpool"` et `"LIVERPOOL"` dans une dimension de chaîne. Si les [!UICONTROL Minuscules] sont activées, les trois valeurs deviennent toutes `"liverpool"`. Si cette option est désactivée, les trois valeurs sont traitées comme des valeurs distinctes. |

{style="table-layout:auto"}

>[!NOTE]
>
>Si les [!UICONTROL Minuscules] sont activées sur une dimension du jeu de données de recherche, plusieurs valeurs de recherche peuvent exister pour le même identifiant. Si ce conflit se produit, Customer Journey Analytics utilise la première valeur ASCII assemblée (les valeurs en majuscules précèdent les valeurs en minuscules). Adobe ne recommande pas lʼutilisation de jeux de données de recherche qui contiennent la même valeur lorsque les [!UICONTROL Minuscules] sont activées.

![Dimension sensible à la casse](../assets/case-sens-workspace.png)

## Paramètres de comportement des mesures

| Paramètre | Description/Cas d’utilisation |
| --- | --- |
| [!UICONTROL Compter les valeurs] | Visible sur les types de données des schémas entier et double. Permet dʼaugmenter la valeur de la mesure par le nombre spécifié. Par exemple, la valeur de la mesure augmente de 50 si la valeur de la colonne est `50`. |
| [!UICONTROL Compter les instances] | Visible sur les types de données des schémas entier et double. Permet dʼaugmenter la valeur de la mesure de un, quelle que soit sa valeur. La présence de toute valeur augmente la mesure. Par exemple, la valeur de la mesure augmente de un si la valeur de la colonne est `50`. |
| [!UICONTROL Valeurs à compter] | Visible sur les types de données du schéma booléen. Permet de déterminer si la valeur de la mesure augmente en comptant `true`, `false`, ou les deux. |

{style="table-layout:auto"}

Vous pouvez générer à la fois une mesure « Commandes » et « Chiffre dʼaffaires » dans Analysis Workspace à lʼaide de la même colonne du jeu de données dʼévénement avec des comportements différents. Faites glisser deux fois la colonne de jeu de données « Revenus » dans la vue de données et définissez lʼune sur « Compter les valeurs » et lʼautre sur « Compter les instances ». La mesure « Commandes » compte les instances, tandis que la mesure « Chiffre dʼaffaires » compte les valeurs.
