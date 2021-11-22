---
title: Filtrage des opérateurs
description: Déterminez la manière dont un composant interagit avec une valeur dans un filtre.
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
source-git-commit: 87da431752c235c442d13fd185c7ab8f6cf20eba
workflow-type: ht
source-wordcount: '575'
ht-degree: 100%

---

# Filtrage des opérateurs

Le créateur de filtres vous permet de comparer et de contraindre les valeurs à lʼaide dʼopérateurs sélectionnés. Il existe deux catégories dʼopérateurs : [!UICONTROL Standard] et [!UICONTROL Comptage distinct].

## Opérateurs standard

| Opérateur | Description |
| --- | --- |
| est égal à | Renvoie des éléments qui correspondent exactement à une valeur numérique ou de chaîne. Si vous utilisez des caractères génériques, utilisez lʼopérateur « correspond à ». |
| n’est pas égal à | Renvoie les éléments qui ne comportent pas une correspondance exacte avec la valeur saisie.  Si vous utilisez des caractères génériques, utilisez lʼopérateur « ne correspond pas à ». |
| contient | Renvoie les éléments qui sont comparés aux sous-chaînes des valeurs saisies. Par exemple, si la règle dʼune dimension de chaîne contient `"Search"`, elle correspond à toute page contenant la sous-chaîne `"Search"`, y compris `"Search Results"`, `"Search"` et `"Searching"`. Cet opérateur applique le respect de la casse. |
| ne contient pas | Tous les éléments qui correspondent à la valeur saisie sont exclus des résultats. Par exemple, si la règle dʼune dimension de chaîne ne contient pas `"Search"`, elle exclut toute page contenant la sous-chaîne `"Search"`, y compris `"Search Results"`, `"Search"` et `"Searching"`. |
| contient tous les | Renvoie les éléments qui incluent toutes les sous-chaînes (séparées par un espace) dans nʼimporte quel ordre. Par exemple, la saisie de `"Search Results"` avec cet opérateur doit correspondre à `"Search Results"` et `"Results of Search"`, mais pas à `"Search"` ou `"Results"` saisis séparément. Cet opérateur prend en charge jusquʼà 100 mots délimités par des espaces. |
| ne contient pas tous les | Tous les éléments qui correspondent à chaque valeur saisie sont exclus des résultats. Par exemple, la saisie de `"Search Results"` avec cet opérateur doit exclure `"Search Results"` et `"Results of Search"`, mais pas `"Search"` ou `"Results"`. Cet opérateur prend en charge jusquʼà 100 mots délimités par des espaces. |
| contient n’importe lequel | Renvoie les éléments qui contiennent l’une des sous-chaînes spécifiées. Par exemple, la saisie de `"Search Results"` avec cet opérateur doit correspondre à `"Search Results"`, `"Results of Search"`, `"Search"` et `"Results"`. Cet opérateur prend en charge jusquʼà 100 mots délimités par des espaces. |
| ne contient pas n’importe lequel | Tous les éléments qui correspondent à n’importe quelle sous-chaîne sont exclus des résultats. Par exemple, la saisie de `"Search Results"` doit exclure `"Search Results"`, `"Results of Search"`, `"Search"` et `"Results"`. Cet opérateur prend en charge jusquʼà 100 mots délimités par des espaces. |
| commence par | Renvoie les éléments qui commencent par le caractère ou les chaînes de la valeur saisie. |
| ne commence pas par | Renvoie tous les éléments qui ne commencent pas par les caractères ou les chaînes des valeurs saisies. |
| se termine par | Renvoie les éléments qui se terminent par le caractère ou les chaînes de la valeur saisie. |
| ne se termine pas par | Renvoie tous les éléments qui ne se terminent pas par les caractères ou les chaînes de la valeur saisie. |
| correspond à | Renvoie des éléments qui correspondent exactement à une valeur numérique ou de chaîne donnée. Prend en charge les fonctions de caractère générique au moyen dʼun astérisque (`*`). Cet opérateur applique le respect de la casse. Par exemple :<ul><li>`a*e` correspond à `ae`, `abcde`, `adobe` et `a whole sentence`.</li><li>`adob*` correspond à `adobe`, `adobe analytics` et `adobo recipe`</li><li>`*dobe` correspond à `dobe`, `adobe` et `cute little dobe`.</li></ul> |
| ne correspond pas à | Tous les éléments qui correspondent à la chaîne sont exclus. Prend en charge les fonctions de caractère générique au moyen dʼun astérisque (`*`). |
| existe | Renvoie les éléments si la valeur nʼest pas nulle. |
| n’existe pas | Renvoie les éléments si la valeur est nulle. |

## Opérateurs Comptage distincts

Vous pouvez segmenter un nombre d’éléments distinct dans une dimension. Vous pouvez, par exemple, créer des filtres pour les visiteurs qui ont consulté plus de 5 produits distincts ou les visites où plus de 5 pages distinctes ont été vues.

| Opérateur | Description |
| --- | --- |
| est égal à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est égal à la valeur saisie. |
| n’est pas égal à | Renvoie les éléments de dimension dont le nombre de valeurs uniques n’est pas égal à la valeur saisie. |
| est supérieur à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est supérieur à la valeur saisie. |
| est inférieur à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est inférieur à la valeur saisie. |
| est supérieur ou égal à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est supérieur ou égal à la valeur saisie. |
| est inférieur ou égal à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est inférieur ou égal à la valeur saisie. |
