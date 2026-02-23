---
description: Découvrez comment utiliser les opérateurs du créateur de segments pour comparer et contraindre des valeurs.
title: Opérateurs
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters, Segments
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 38%

---

# Opérateurs

Le créateur de segments vous permet de comparer et de contraindre des valeurs pour des composants à l’aide d’opérateurs sélectionnés. Il existe trois catégories d’opérateurs : [Standard](#standard-operators), [Data Warehouse](#data-warehouse-operators) et [Nombre distinct](#distinct-count-operators).

Selon l’opérateur sélectionné :

* Vous pouvez saisir une valeur.
* Vous pouvez saisir une partie d’une valeur et sélectionner dans un menu déroulant (le cas échéant).
* Sélectionnez immédiatement une valeur dans le menu déroulant (le cas échéant).

Lorsque vous saisissez une valeur pour un opérateur qui valide les valeurs disponibles, telles que **[!UICONTROL égal à]**, et que la valeur ne correspond pas aux valeurs disponibles pour le composant, une icône ![RougeAlerte](/help/assets/icons/AlertRed.svg) s’affiche. Vous pouvez sélectionner une valeur dans le menu déroulant ou appuyer sur **[!UICONTROL _Entrée_]** pour la saisir.

![Segment égal à](assets/segment-operator-equals.png)

## Caractères génériques

Le seul caractère générique pris en charge pour les opérateurs qui le font est l’astérisque : `*`. Si vous devez rechercher le caractère &#42; spécifique, vous pouvez l’échapper avec une barre oblique inverse, comme `\*`.

Par exemple, vous avez un nom de page appelé *Mon produit cool*.

* La règle de segment **[!UICONTROL Nom de page]** **[!UICONTROL correspond]** `* product` correspond au nom de page ci-dessus.
* Cependant, la règle **[!UICONTROL Nom de la page]** **[!UICONTROL correspond]** `My \* product` correspond uniquement au nom de la page *Mon * Produit*.

## Opérateurs standard

| Opérateur | La dimension, le segment ou l’événement de mesure sélectionné... |
|--- |--- |
| **[!UICONTROL égal à]** | Renvoie des éléments qui correspondent exactement à une valeur numérique ou de chaîne. Remarque : si vous utilisez des caractères génériques, utilisez l’opérateur **[!UICONTROL correspondances]**. |
| **[!UICONTROL différent de]** | Renvoie les éléments qui ne comportent pas une correspondance exacte avec la valeur saisie.  Remarque : si vous utilisez des caractères génériques, utilisez l’opérateur **[!UICONTROL ne correspond pas]**. |
| **[!UICONTROL est égal à n’importe lequel]** | Renvoie les éléments qui correspondent exactement à n’importe quelle valeur du champ de saisie (jusqu’à 500 éléments). Par exemple, la saisie de `Search Results, Homepage` pour la dimension **[!UICONTROL Nom de la page]** avec cet opérateur doit correspondre à *Résultats de la recherche* et *Page d’accueil*, et compter comme 2 éléments. Le champ de saisie de cet opérateur est délimité par des virgules. |
| **[!UICONTROL n’est égal à aucun(e)]** | Identifie les éléments qui correspondent exactement à n’importe quelle valeur du champ de saisie (jusqu’à 500 éléments), puis renvoie uniquement les éléments sans ces valeurs. Par exemple, la saisie de `Search Results, Homepage` avec cet opérateur pour la dimension **[!UICONTROL Nom de page]** identifie *Résultats de la recherche* et *Page d’accueil* puis **exclut** les éléments renvoyés. Cet exemple serait considéré comme deux éléments. Le champ de saisie de cet opérateur est délimité par des virgules. |
| **[!UICONTROL contient]** | Renvoie les éléments qui sont comparés aux sous-chaînes des valeurs saisies. Par exemple, si la règle est **[!UICONTROL Nom de la page]** **[!UICONTROL contient]** `Search`, cette règle correspond à toute page qui contient le `Search` de sous-chaîne, y compris *Résultats de la recherche*, *Rechercher* et *Searching*. La condition « contient » n’est pas sensible à la casse dans Adobe Analytics, mais elle l’est dans Customer Journey Analytics. |
| **[!UICONTROL ne contient pas]** | Renvoie l’inverse de la règle **[!UICONTROL contains]**. Plus précisément, tous les éléments qui correspondent à la valeur entrée seront exclus des valeurs entrées. Par exemple, si la règle est **[!UICONTROL Nom de la page]** **[!UICONTROL ne contient pas]** `Search`, elle ne correspond à aucune page qui contient le `Search` de sous-chaîne, y compris *Résultats de la recherche*, *Rechercher* et *Searching*. Ces valeurs seront exclues des résultats. |
| **[!UICONTROL contient tous les]** | Renvoie les éléments comparés aux sous-chaînes, notamment plusieurs valeurs associées. Par exemple, la saisie de `Search Results` avec cet opérateur pour la dimension **[!UICONTROL Nom de page]** correspondrait à *Résultats de la recherche* et *Résultats de la recherche*, mais pas à *Recherche* ou *Résultats* individuellement. La règle correspondrait à *Recherche* ET *Résultats* trouvés ensemble. Le champ de saisie de cet opérateur est délimité par des espaces (100 mots). |
| **[!UICONTROL ne contient pas tous les]** | Identifie les éléments comparés à des sous-chaînes, y compris plusieurs valeurs jointes, puis renvoie uniquement les éléments sans ces valeurs. Par exemple, la saisie de `Search Results` avec cet opérateur pour la dimension **[!UICONTROL Nom de page]** identifie *Résultats de la recherche* et *Résultats de la recherche* (mais pas *Recherche* ou *Résultats* individuellement), puis exclut ces éléments. Le champ de saisie de cet opérateur est délimité par des espaces (100 mots). |
| **[!UICONTROL contient n’importe lequel]** | Renvoie les éléments comparés aux sous-chaînes, notamment plusieurs valeurs associées ou identifiées indépendamment. Par exemple, la saisie de `Search Results` avec cet opérateur doit correspondre à *Résultats de la recherche*, *Résultats de la recherche*, *Recherche* et *Résultats*. Il correspond soit à *Recherche* SOIT à *Résultats* trouvés ensemble ou séparément. Le champ de saisie de cet opérateur est délimité par des espaces (100 mots). |
| **[!UICONTROL ne contient aucun(e)]** | Identifie les éléments d’après les sous-chaînes, puis renvoie les valeurs qui ne contiennent pas ces sous-chaînes. Il peut y avoir plusieurs valeurs jointes ou des valeurs identifiées individuellement. Par exemple, la saisie de `Search Results` pour la dimension **[!UICONTROL Nom de page]** correspondrait à *Résultats de la recherche* s, *Résultats de la recherche*, *Recherche* et *Résultats* où *Search* ou *Result* sont trouvés ensemble ou indépendamment. Les éléments qui contiennent ces sous-chaînes seraient ensuite exclus. Le champ de saisie de cet opérateur est délimité par des espaces (100 mots). |
| **[!UICONTROL commence par]** | Renvoie les éléments qui commencent par la valeur de chaîne saisie. |
| **[!UICONTROL ne commence pas par]** | Renvoie tous les éléments qui ne commencent pas par la valeur de chaîne saisie. Il s’agit de l’inverse de l’opérateur **[!UICONTROL commence par]**. |
| **[!UICONTROL se termine par]** | Renvoie les éléments qui se terminent par une valeur de chaîne saisie. |
| **[!UICONTROL ne se termine pas par]** | Renvoie tous les éléments qui ne se terminent pas par la valeur de chaîne saisie. Il s’agit de l’inverse de l’opérateur **[!UICONTROL se termine par]**. |
| **[!UICONTROL correspond]** | Renvoie des éléments qui correspondent exactement à une valeur numérique ou de chaîne donnée. La clause **[!UICONTROL correspond]** est sensible à la casse dans Adobe Analytics et dans Customer Journey Analytics. **Remarque** : utilisez cet opérateur lors de l’utilisation des fonctions [caractère générique](#wildcards) (extension métacaractère). Exemples d’« extension métacaractère » :<ul><li>`a*e` correspondrait à `ae`, `abcde`, `adobe` et `a whole sentence`.</li><li>`adob*` correspondrait à `adobe`, `adobe analytics` et `adobo recipe`.</li><li>`*dobe` correspondrait à `dobe`, `adobe` et `cute little dobe`.</li></ul> |
| **[!UICONTROL ne correspond pas]** | Renvoie les éléments qui ne comportent pas une correspondance exacte avec la valeur saisie. Remarque : utilisez cet opérateur lors de l’utilisation des fonctions [caractère générique](#wildcards) (extension métacaractère). |
| **[!UICONTROL existe]** | Renvoie le nombre d’éléments existants. Par exemple, si vous évaluez la dimension **[!UICONTROL Pages introuvables]** à l’aide de l’opérateur **[!UICONTROL exists]**, le nombre de pages d’erreur existantes est renvoyé. |
| **[!UICONTROL n’existe pas]** | Renvoie tous les éléments qui n’existent pas. Par exemple, si vous évaluez la dimension **[!UICONTROL Pages introuvables]** à l’aide de l’opérateur **[!UICONTROL n’existe pas]**, le nombre de pages où cette page d’erreur n’existait pas est renvoyé. |

## Opérateurs Data Warehouse

| Opérateur | La dimension, le segment ou l’événement de mesure sélectionné... |
| --- | --- |
| **[!UICONTROL est inférieur à]** | Renvoie les éléments dont le nombre est inférieur à la valeur saisie. |
| **[!UICONTROL est inférieur ou égal à]** | Renvoie les éléments dont le nombre est inférieur ou égal à la valeur saisie. |
| **[!UICONTROL est supérieur à]** | Renvoie les éléments dont le nombre est supérieur à la valeur saisie. |
| **[!UICONTROL est supérieur ou égal à]** | Renvoie les éléments dont le nombre est supérieur ou égal à la valeur saisie. |

## Opérateurs Comptage distincts

Vous pouvez segmenter un nombre d’éléments distinct dans une dimension. Exemples : *visiteurs et visiteuses ayant consulté plus de 5 produits distincts* ou *visites et visiteuses ayant consulté plus de 5 pages distinctes*.

| Opérateur | La dimension, le segment ou l’événement de mesure sélectionné... |
| --- | --- |
| **[!UICONTROL égal à]** | Renvoie les éléments de dimension dont le nombre de valeurs uniques est égal à la valeur saisie. |
| **[!UICONTROL différent de]** | Renvoie les éléments de dimension dont le nombre de valeurs uniques n’est pas égal à la valeur saisie. |
| **[!UICONTROL est supérieur à]** | Renvoie les éléments de dimension dont le nombre de valeurs uniques est supérieur à la valeur saisie. |
| **[!UICONTROL est inférieur à]** | Renvoie les éléments de dimension dont le nombre de valeurs uniques est inférieur à la valeur saisie. |
| **[!UICONTROL est supérieur ou égal à]** | Renvoie les éléments de dimension dont le nombre de valeurs uniques est supérieur ou égal à la valeur saisie. |
| **[!UICONTROL est inférieur ou égal à]** | Renvoie les éléments de dimension dont le nombre de valeurs uniques est inférieur ou égal à la valeur saisie. |


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Nombre de dimensions distinct](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/components/calculated-metrics/approximate-count-distinct-function-in-calculated-metrics){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]
