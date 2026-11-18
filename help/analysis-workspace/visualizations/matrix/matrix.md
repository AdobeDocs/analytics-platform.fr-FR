---
title: Présentation de la visualisation de la matrice dans Analysis Workspace
description: Découvrez la visualisation de la matrice dans Customer Journey Analytics Analysis Workspace, notamment ce qu’elle indique, quand l’utiliser et comment elle se compare à d’autres visualisations.
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 2%
---

# Présentation de la matrice {#matrix-overview}

La visualisation Matrice dans Analysis Workspace vous permet de visualiser la manière dont les éléments de dimension de deux dimensions se chevauchent ou se corrélent.

Les éléments Dimension d’une dimension sont affichés sous forme de lignes (le long de l’axe Y), tandis que les éléments de dimension de l’autre dimension sont affichés sous forme de colonnes (le long de l’axe X). Chaque cellule qui se croise affiche les données de chevauchement ou de corrélation en fonction de la mesure choisie.

Par exemple, la visualisation de la matrice suivante montre le nombre de chevauchements d’événements pour les noms d’appareils par code de pays.

* Dimension 1 (dimension de ligne) : nom du périphérique

* Dimension 2 (dimension colonne) : code pays

* Mesure : Événements

![Aperçu de la matrice](assets/matrix-overview.png)

## Principales fonctionnalités

* **Comparer deux dimensions différentes** : voir comment les éléments d’une dimension se rapportent aux éléments d’une autre dimension.

* **Comparer une dimension avec elle-même** : voir comment les éléments d’une même dimension se rapportent.

* **Chevauchement** : affichez le chevauchement des éléments de dimension.

* **Corrélation** : observez la tendance des éléments de dimension ensemble, sur une échelle allant de -1 (toujours se déplacer dans des directions opposées) à +1 (toujours se déplacer ensemble).

* **Couleurs de carte thermique** : la couleur de la cellule indique si le chevauchement est élevé ou faible, ou si la corrélation est positive ou négative, et sa force. Le chevauchement et la corrélation ont des palettes de couleurs distinctes.

## Informations potentielles

* Recherchez des motifs et des écarts dans deux dimensions. Par exemple, vous pouvez répondre à des questions telles que :

  * Quelles campagnes ont de bons résultats dans certaines régions, mais pas dans d&#39;autres ?

  * Quels types de contenu sont les plus performants sur chaque type d’appareil ?

* Découvrez la tendance des éléments de dimension les uns par rapport aux autres. Par exemple, vous pouvez répondre à des questions telles que :

  * Quels canaux marketing évoluent ensemble au fil du temps, lesquels évoluent indépendamment et lesquels évoluent dans des directions opposées ?

  * Quelles pages ont un trafic qui monte et descend ensemble ?

* Comparez une dimension avec elle-même. Par exemple, vous pouvez répondre à des questions telles que :

  * Quels produits sont souvent achetés par les mêmes personnes ?

  * Quels appareils les mêmes personnes utilisent-elles ensemble, tels que les téléphones mobiles et les tablettes ?

## Choisissez entre les visualisations Matrice, Tableau à structure libre, Venn ou Nuage de points

La visualisation de la matrice présente des similitudes avec [l’utilisation de plusieurs colonnes de dimensions dans un tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md), la visualisation de Venn [&#128279;](/help/analysis-workspace/visualizations/scatterplot.md)3&rbrace; et la visualisation de dispersion [5&rbrace;. &#x200B;](/help/analysis-workspace/visualizations/venn.md)Chaque visualisation montre comment les composants sont liés les uns aux autres, mais ils diffèrent par les composants qu’ils utilisent et par la manière dont ils affichent les résultats.

### Quand utiliser chaque visualisation

Choisissez la visualisation qui correspond le mieux à votre analyse :

* **Matrice :** pour une mesure donnée, vérifiez la relation entre chaque élément de dimension d’une dimension et chaque élément de dimension d’une autre, y compris les écarts et les éléments de dimension qui suivent une tendance.

* **Tableau à structure libre avec plusieurs colonnes de dimensions :** Vous pouvez ajouter jusqu’à 5 dimensions sous forme de colonnes distinctes à un tableau à structure libre. Les éléments Dimension qui apparaissent dans la même ligne du tableau sont concaténés. Ajoutez un nombre illimité de mesures au tableau pour afficher les données de mesure pour chaque élément de dimension concaténé. Filtrer, trier et ajouter des répartitions aux éléments de dimension concaténés.

* **Venn :** pour une mesure unique, affichez le chevauchement de 3 segments maximum.

* **Dispersion :** comparez les éléments de dimension sur deux ou trois mesures pour trouver des modèles et des valeurs aberrantes.

### Comprendre les différences

<!-- SME CHECK: Confirm the Matrix cells: segments can't be used as rows or columns. Container row: confirm what each Matrix container means for overlap, and that freeform combinations are based on the dimension items that apply to each event. -->

| Fonction | Matrice | Plusieurs colonnes de dimensions dans un tableau à structure libre | Venn | Graphique de dispersion |
| --- | --- | --- | --- | --- |
| **Composants utilisés** | 2 dimensions ; 1 mesure<p>Compare les éléments de dimension de 2 dimensions ou de 1 dimension avec lui-même.</p> | Jusqu’à 5 dimensions ; un nombre illimité de mesures<p>Les éléments Dimension qui apparaissent dans la même ligne sont concaténés et se comportent comme un seul élément de dimension. Les lignes concaténées sont comparées par leurs valeurs de mesure.</p> | Jusqu’à 3 segments ; 1 mesure<p>Compare le chevauchement entre les segments.</p> | 1 dimension ; jusqu’à 3 mesures<p>Compare les éléments de dimension sur plusieurs mesures.</p> |
| **Conteneur** | Défini dans la visualisation : Personne (par défaut), Session ou Événement<p>Détermine si le chevauchement comptabilise les éléments de dimension qui se produisent pour la même personne, dans la même session ou dans le même événement.</p> | Aucun paramètre de conteneur<p>Chaque ligne combine les éléments de dimension qui s’appliquent au même événement. La mesure que vous choisissez, telle que Personnes ou Sessions, détermine ce qui est comptabilisé.</p> | Défini dans chaque segment<p>Chaque segment utilise son propre [conteneur](/help/components/segments/seg-overview.md#containers) (personne, session ou événement). La mesure détermine ce qui est comptabilisé dans chaque chevauchement.</p> | Aucun paramètre de conteneur<p>Les mesures que vous choisissez déterminent ce qui est comptabilisé.</p> |
| **Disposition** | Grille, similaire à un tableau croisé dynamique<p>Les éléments Dimension d’une dimension sont des lignes et les éléments de dimension de l’autre dimension sont des colonnes.</p> | Liste<p>Chaque ligne combine un élément de dimension de chaque colonne de dimension.</p> | Cercles qui se chevauchent | Points sur l’axe X et l’axe Y |
| **Affiche le chevauchement** | Oui<p>Affiche le chevauchement entre chaque élément de dimension dans les lignes et chaque élément de dimension dans les colonnes.</p><p>Utilisez la vue **[!UICONTROL Nombre de chevauchements]**.</p> | Oui<p>Affiche la mesure pour chaque combinaison d’éléments de dimension, une combinaison par ligne.</p> | Oui<p>Affiche le chevauchement entre les segments.</p> | Non |
| **Affiche la corrélation** | Oui, entre les éléments de dimension<p>Indique la tendance des éléments de dimension au fil du temps, sur une échelle allant de -1 (directions opposées) à +1 (ensemble).</p><p>Utilisez la vue **[!UICONTROL Force de corrélation]**.</p> | Non | Non | Oui, entre les mesures<p>Indique comment les mesures sont liées les unes aux autres. Chaque point est un élément de dimension tracé par jusqu’à 3 mesures.</p> |

{style="table-layout:auto"}

