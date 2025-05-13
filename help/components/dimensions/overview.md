---
title: Présentation des dimensions
description: Découvrez les dimensions et leur utilisation dans Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 6cabedc5ed58dac450577fc3505be5f95b7a959d
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 25%

---

# Présentation des dimensions

Les dimensions sont un type de composant dans Customer Journey Analytics utilisé pour analyser les données. Par exemple, vous utilisez des dimensions lors de la création de rapports dans [Analysis Workspace](/help/analysis-workspace/home.md) ou dans [Report Builder](/help/report-builder/rb-overview.md).

Les dimensions Customer Journey Analytics sont de type illimité ; les valeurs peuvent être numériques, textuelles, d’objets, de listes ou des mélanges de tous.

Un rapport de base dans Customer Journey Analytics affiche des lignes de dimensions (généralement des valeurs de chaîne) par rapport à une colonne de mesures (généralement des valeurs numériques).

Par exemple, si vous combinez la dimension Page avec la mesure Personnes , vous obtiendrez un rapport avec classement présentant les pages les plus visitées par les personnes :

| Page | Personnes |
| --- | ---: |
| Page d’accueil | 800 |
| Page de produit | 500 |
| Page d’achat | 100 |

{style="table-layout:fixed"}

Chaque dimension représente une partie ou une facette différente de votre site. Vous pouvez combiner l’une de ces dimensions avec une ou plusieurs mesures pour créer un rapport qui cous correspond.


## Création de dimensions

L’administration de Customer Journey Analytics peut [créer des dimensions dans une vue de données](/help/data-views/create-dataview.md#components).

## Dimensions standard

Lorsque vous créez une vue de données, les composants suivants sont ajoutés par défaut en tant que dimensions à votre vue de données :

{{standard-dimensions}}


## Ajouter des descriptions pour les dimensions

Les administrateurs et administratrices de Customer Journey Analytics peuvent ajouter des descriptions pour les dimensions et d’autres composants dans la vue de données ou directement dans Analysis Workspace. Pour plus d’informations sur l’ajout de descriptions aux dimensions, voir [Ajouter des descriptions de composant](/help/components/add-component-descriptions.md).

>[!MORELIKETHIS]
>
>[Découvrez des informations plus précises sur les clients avec la fonctionnalité Profondeur de l’événement](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947#M576)
>

