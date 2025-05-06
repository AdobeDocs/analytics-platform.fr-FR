---
title: Présentation des dimensions
description: Découvrez les dimensions et leur utilisation dans Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: ed7e9a6c34c5f8ba9ba4f75be05768409cbc158d
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 36%

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

## Dimensions par défaut

Lorsque vous créez une vue de données, les composants temporels suivants sont ajoutés par défaut en tant que dimensions à votre vue de données :

- 15 minutes
- 30 minutes
- 5 minutes
- Jour
- Jour du mois
- Jour de la semaine
- Jour de l’année
- Heure
- Heure du jour
- Minute
- Minute de l’heure
- Mois
- Mois de l’année
- Trimestre
- Trimestre de l’année
- Seconde
- Semaine de l’année
- Année

## Ajouter des descriptions pour les dimensions

Les administrateurs et administratrices de Customer Journey Analytics peuvent ajouter des descriptions pour les dimensions et d’autres composants dans la vue de données ou directement dans Analysis Workspace. Pour plus d’informations sur l’ajout de descriptions aux dimensions, voir [Ajouter des descriptions de composant](/help/components/add-component-descriptions.md).
