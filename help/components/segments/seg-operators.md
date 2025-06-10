---
title: Opérateurs
description: Déterminez comment un composant interagit avec une valeur dans un segment.
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters, Segments
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 54%

---

# Opérateurs

Le créateur de segments vous permet de comparer et de contraindre des valeurs pour des composants à l’aide d’opérateurs sélectionnés. Il existe deux catégories dʼopérateurs : [[!UICONTROL Standard]](#standard-operators) et [[!UICONTROL Comptage distinct]](#distinct-count-operators).

## Opérateurs standard

| Opérateur | Description |
| --- | --- |
| **[!UICONTROL est égal à]** | Renvoie des éléments qui correspondent exactement à une valeur numérique ou de chaîne. Si vous utilisez des caractères génériques, utilisez l’opérateur de correspondances. |
| **[!UICONTROL n’est pas égal]** | Renvoie les éléments qui ne comportent pas une correspondance exacte avec la valeur saisie.  Si vous utilisez des caractères génériques, utilisez l’opérateur ne correspond pas. |
| **[!UICONTROL est égal à n’importe lequel]** | Renvoie les éléments qui correspondent aux valeurs de sous-chaîne saisies et délimitées par une virgule. |
| **[!UICONTROL contient]** | Renvoie les éléments qui sont comparés aux sous-chaînes des valeurs saisies. Par exemple, si la valeur d’une dimension Nom de page contient `Search`, cet opérateur correspond à toute page dont le nom contient le `Search` de sous-chaîne, y compris `Search Results`, `Search` et `Searching`. Cet opérateur applique le respect de la casse. |
| **[!UICONTROL ne contient pas]** | Tous les éléments qui correspondent à la valeur saisie sont exclus des résultats. Par exemple, si la valeur d’une dimension Nom de page ne contient pas de `Search`, cet opérateur exclut toute page dont le nom contient le `Search` de sous-chaîne, y compris `Search Results`, `Search` et `Searching`. |
| **[!UICONTROL contient tous les]** | Renvoie les éléments qui incluent toutes les sous-chaînes (séparées par un espace) dans nʼimporte quel ordre. Par exemple, la spécification de `Search Results` comme valeur pour cet opérateur doit correspondre à `Search Results` et `Results of Search`, mais pas à `Search` ou `Results` indépendamment. Cet opérateur prend en charge jusquʼà 100 mots délimités par des espaces. |
| **[!UICONTROL ne contient pas tous les]** | Tous les éléments qui correspondent à chaque valeur saisie sont exclus des résultats. Par exemple, la spécification de `Search Results` comme valeur pour cet opérateur exclurait `Search Results` et `Results of Search`, mais pas `Search` ou `Results`. Cet opérateur prend en charge jusquʼà 100 mots délimités par des espaces. |
| **[!UICONTROL contient n’importe lequel]** | Renvoie les éléments qui contiennent l’une des sous-chaînes spécifiées. Par exemple, la spécification de `Search Results` comme valeur pour cet opérateur doit correspondre à `Search Results`, `Results of Search`, `Search` et `Results`. Cet opérateur prend en charge jusquʼà 100 mots délimités par des espaces. |
| **[!UICONTROL ne contient pas n’importe lequel]** | Tous les éléments qui correspondent à n’importe quelle sous-chaîne sont exclus des résultats. Par exemple, la spécification de `Search Results` comme valeur pour cet opérateur exclurait `Search Results`, `Results of Search`, `Search` et `Results`. Cet opérateur prend en charge jusquʼà 100 mots délimités par des espaces. |
| **[!UICONTROL commence par]** | Renvoie les éléments qui commencent par le caractère ou les chaînes de la valeur spécifiée. |
| **[!UICONTROL ne commence pas par]** | Renvoie tous les éléments qui ne commencent pas par les caractères ou les chaînes de la valeur spécifiée. |
| **[!UICONTROL se termine par]** | Renvoie les éléments qui se terminent par le caractère ou les chaînes de la valeur spécifiée. |
| **[!UICONTROL ne se termine pas par]** | Renvoie tous les éléments qui ne se terminent pas par les caractères ou les chaînes de la valeur spécifiée. |
| **[!UICONTROL correspond à]** | Renvoie les éléments qui correspondent exactement à des éléments en fonction d’une valeur numérique ou de chaîne donnée. Prend en charge les fonctions de caractère générique au moyen dʼun astérisque (`*`). Cet opérateur applique le respect de la casse. Par exemple :<ul><li>`a*e` correspond à `ae`, `abcde`, `adobe` et `a whole sentence`.</li><li>`adob*` correspond à `adobe`, `adobe analytics` et `adobo recipe`</li><li>`*dobe` correspond à `dobe`, `adobe` et `cute little dobe`.</li></ul> |
| **[!UICONTROL ne correspond pas à]** | Tous les éléments qui correspondent à la chaîne sont exclus. Prend en charge les fonctions de caractère générique au moyen dʼun astérisque (`*`). |
| **[!UICONTROL existe]** | Renvoie les éléments si la valeur nʼest pas nulle. |
| **[!UICONTROL n’existe pas]** | Renvoie les éléments si la valeur est nulle. |

## Opérateurs Comptage distincts

Vous pouvez segmenter un nombre d’éléments distinct dans une dimension. Par exemple, vous pouvez créer des segments pour les personnes qui ont consulté plus de 5 produits distincts ou les visites où plus de 5 pages distinctes ont été vues.

| Opérateur | Description |
| --- | --- |
| **[!UICONTROL est égal à]** | Renvoie les éléments de dimension dont le nombre de valeurs uniques est égal à la valeur saisie. |
| **[!UICONTROL n’est pas égal]** | Renvoie les éléments de dimension dont le nombre de valeurs uniques n’est pas égal à la valeur saisie. |
| **[!UICONTROL est supérieur à]** | Renvoie les éléments de dimension dont le nombre de valeurs uniques est supérieur à la valeur saisie. |
| **[!UICONTROL est inférieur à]** | Renvoie les éléments de dimension dont le nombre de valeurs uniques est inférieur à la valeur saisie. |
| **[!UICONTROL est supérieur ou égal à]** | Renvoie les éléments de dimension dont le nombre de valeurs uniques est supérieur ou égal à la valeur saisie. |
| **[!UICONTROL est inférieur ou égal à]** | Renvoie les éléments de dimension dont le nombre de valeurs uniques est inférieur ou égal à la valeur saisie. |
