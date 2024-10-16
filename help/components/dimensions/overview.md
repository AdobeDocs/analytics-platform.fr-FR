---
title: Présentation des dimensions
description: Découvrez les dimensions et leur utilisation en Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: d37734ae415722fc609715868c37a36f2becdbf6
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 36%

---

# Présentation des dimensions

Les Dimensions sont un type de composant dans Customer Journey Analytics utilisé pour analyser les données. Par exemple, vous utilisez des dimensions lors de la création de rapports dans [Analysis Workspace](/help/analysis-workspace/home.md) ou dans [Report Builder](/help/report-builder/report-buider-overview.md).

Les dimensions du Customer Journey Analytics sont de type illimité ; les valeurs peuvent être numériques, textuelles, objets, listes ou mélanges de toutes.

Dans Customer Journey Analytics, un rapport de base affiche des lignes de dimensions (généralement des valeurs de chaîne), par rapport à une colonne de mesures (valeurs numériques courantes).

Par exemple, si vous combinez la dimension Page à la mesure Personnes, vous obtenez un rapport de classement indiquant les pages les plus visitées par les personnes :

| Page | Personnes |
| --- | ---: |
| Page d’accueil | 800 |
| Page de produit | 500 |
| Page d’achat | 100 |

{style="table-layout:fixed"}

Chaque dimension représente une partie ou une facette différente de votre site. Vous pouvez combiner l’une de ces dimensions avec une ou plusieurs mesures pour créer un rapport qui cous correspond.


## Création de dimensions

Les administrateurs de Customer Journey Analytics peuvent [créer des dimensions dans une vue de données](/help/data-views/create-dataview.md#components).

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

Les administrateurs de Customer Journey Analytics peuvent ajouter des descriptions pour les dimensions et d’autres composants dans la vue de données ou directement dans Analysis Workspace. Pour plus d’informations sur l’ajout de descriptions aux dimensions, voir [Ajouter des descriptions de composant](/help/components/add-component-descriptions.md).
