---
title: Vue d’ensemble des dimensions
description: Découvrez les dimensions et leur utilisation dans Customer Journey Analytics.
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
TQID: https://experienceleague.adobe.com/bMM7desF2wr71h-SR1mzD7-oSwm-8cPvmeU7SeM7-fU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 253
ht-degree: 100%

---

# Vue d’ensemble des dimensions

Les dimensions sont un type de composant dans Customer Journey Analytics qui sert à analyser les données. Par exemple, vous utilisez des dimensions lors de la création de rapports dans [Analysis Workspace](/help/analysis-workspace/home.md) ou dans [Report Builder](/help/report-builder/rb-overview.md).

Les dimensions Customer Journey Analytics sont illimitées ; les valeurs peuvent être numériques, textuelles, objets, listes ou des mélanges de toutes les valeurs.

Un rapport de base dans Customer Journey Analytics affiche des lignes de dimensions (généralement des valeurs de chaîne) par rapport à une colonne de mesures (généralement des valeurs numériques).

Par exemple, si vous combinez la dimension Page à la mesure Personnes, vous obtenez un rapport classant les pages les plus visitées par personnne :

| Page | Personnes |
| --- | ---: |
| Page d’accueil | 800 |
| Page produit | 500 |
| Page d’achat | 100 |

{style="table-layout:fixed"}

Chaque dimension représente une partie ou une facette différente de votre site. Vous pouvez combiner l’une de ces dimensions avec une ou plusieurs mesures pour créer un rapport qui cous correspond.


## Créer des dimensions

Les administrateurs ou les administratrices de Customer Journey Analytics peuvent [créer des dimensions dans une vue de données](/help/data-views/create-dataview.md#components).

## Dimensions standard

Lorsque vous créez une vue de données, les composants suivants sont ajoutés par défaut en tant que dimensions à votre vue de données :

{{standard-dimensions}}


## Ajouter des descriptions pour les dimensions

Les administrateurs ou les administratrices de Customer Journey Analytics peuvent ajouter des descriptions pour les dimensions et d’autres composants dans la vue de données ou directement dans Analysis Workspace. Pour plus d’informations sur l’ajout de descriptions aux dimensions, voir [Ajouter des descriptions de composant](/help/components/add-component-descriptions.md).

>[!MORELIKETHIS]
>
>[Découvrez des informations précises sur les clients et les clientes avec la fonctionnalité Profondeur de l’événement](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947#M576).
>

