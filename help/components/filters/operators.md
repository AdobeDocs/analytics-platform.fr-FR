---
title: Filtrer les opérateurs
description: Déterminez comment un composant interagit avec une valeur dans un filtre.
source-git-commit: 1334e1edb36583ba978936fecbff2657e63a94bf
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 20%

---

# Filtrer les opérateurs

Le Créateur de filtres permet de comparer et de contraindre des valeurs à l’aide d’opérateurs sélectionnés. Il existe deux catégories d&#39;opérateurs : [!UICONTROL Standard] et [!UICONTROL Nombre distinct].

## Opérateurs standard

| Opérateur | Description |
| est égal à | Renvoie les éléments qui correspondent exactement à une valeur numérique ou de chaîne. Si vous utilisez des caractères génériques, utilisez l’opérateur &quot;correspond à&quot;. |
| n’est pas égal à | Renvoie tous les éléments qui ne contiennent pas la correspondance exacte de la valeur saisie.  Si vous utilisez des caractères génériques, utilisez l’opérateur &quot;ne correspond pas à&quot;. |
| contient | Renvoie les éléments qui se comparent aux sous-chaînes des valeurs saisies. Par exemple, si la règle d’une dimension de chaîne contient `"Search"`, elle correspond à toute page qui contient la sous-chaîne `"Search"`, y compris `"Search Results"`, `"Search"` et `"Searching"`. Cet opérateur est sensible à la casse. |
| ne contient pas | Tous les éléments qui correspondent à la valeur saisie sont exclus des résultats. Par exemple, si la règle d’une dimension de chaîne ne contient pas `"Search"`, elle exclut toute page qui contient la sous-chaîne `"Search"`, y compris `"Search Results"`, `"Search"` et `"Searching"`. |
| contient tous les | Renvoie les éléments qui incluent toutes les sous-chaînes (séparées par un espace) dans n’importe quel ordre. Par exemple, la saisie de `"Search Results"` avec cet opérateur correspondrait à `"Search Results"` et `"Results of Search"`, mais pas à `"Search"` ou `"Results"` indépendamment. Cet opérateur prend en charge jusqu’à 100 mots délimités par des espaces. |
| ne contient pas tous les | Tous les éléments qui correspondent à chaque valeur entrée sont exclus des résultats. Par exemple, la saisie de `"Search Results"` avec cet opérateur exclurait `"Search Results"` et `"Results of Search"`, mais pas `"Search"` ni `"Results"`. Cet opérateur prend en charge jusqu’à 100 mots délimités par des espaces. |
| contient n’importe lequel | Renvoie les éléments qui contiennent l’une des sous-chaînes spécifiées. Par exemple, la saisie de `"Search Results"` avec cet opérateur correspondrait à `"Search Results"`, `"Results of Search"`, `"Search"` et `"Results"`. Cet opérateur prend en charge jusqu’à 100 mots délimités par des espaces. |
| ne contient pas n’importe lequel | Tous les éléments qui correspondent à une sous-chaîne sont exclus des résultats. Par exemple, la saisie de `"Search Results"` exclurait `"Search Results"`, `"Results of Search"`, `"Search"` et `"Results"`. Cet opérateur prend en charge jusqu’à 100 mots délimités par des espaces. |
| commence par | Renvoie les éléments qui commencent par le caractère ou les chaînes de la valeur saisie. |
| ne commence pas par | Renvoie tous les éléments qui ne commencent pas par les caractères ou les chaînes des valeurs saisies. |
| se termine par | Renvoie les éléments qui se terminent par le caractère ou les chaînes de la valeur saisie. |
| ne se termine pas par | Renvoie tous les éléments qui ne se terminent pas par les caractères ou les chaînes de la valeur saisie. |
| correspond | Renvoie les éléments qui correspondent exactement à une valeur numérique ou de chaîne donnée. Prend en charge les caractères génériques à l’aide d’un astérisque (`*`). Cet opérateur est sensible à la casse. Par exemple :<ul><li>`a*e` correspond à  `ae`,  `abcde`,  `adobe` et  `a whole sentence`.</li><li>`adob*` correspond à  `adobe`,  `adobe analytics`et  `adobo recipe`</li><li>`*dobe` correspond à  `dobe`,  `adobe` et  `cute little dobe`.</li></ul>|
| ne correspond pas à | Tous les éléments correspondant à la chaîne sont exclus. Prend en charge les caractères génériques à l’aide d’un astérisque (`*`). |
| existe | Renvoie des éléments si la valeur n’est pas nulle. |
| n’existe pas | Renvoie des éléments si la valeur est nulle. |

## Opérateurs Comptage distincts

Vous pouvez segmenter un nombre d’éléments distinct dans une dimension. Vous pouvez, par exemple, créer des filtres pour les visiteurs qui ont consulté plus de 5 produits ou visites distincts où plus de 5 pages distinctes ont été vues.

| Opérateur | Description |
| --- | --- |
| est égal à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est égal à la valeur saisie. |
| n’est pas égal à | Renvoie les éléments de dimension dont le nombre de valeurs uniques n’est pas égal à la valeur saisie. |
| est supérieur à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est supérieur à la valeur saisie. |
| est inférieur à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est inférieur à la valeur saisie. |
| est supérieur ou égal à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est supérieur ou égal à la valeur saisie. |
| est inférieur ou égal à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est inférieur ou égal à la valeur saisie. |
