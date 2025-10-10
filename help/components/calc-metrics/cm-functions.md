---
title: Fonctions de base
description: Découvrez les fonctions de base des mesures calculées.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1868'
ht-degree: 100%

---

# Fonctions de base


Le [créateur de mesures calculées](cm-workflow/cm-build-metrics.md) vous permet d’appliquer des fonctions statistiques et mathématiques. Cet article comprend une liste alphabétique des fonctions ainsi que leurs définitions.

>[!NOTE]
>
>Lorsque [!DNL metric] est identifié en tant qu’argument d’une fonction, d’autres expressions des mesures sont également autorisées. Par exemple, [COLUMN MAXIMUM(metrics)](#column-maximum) autorise également [COLUMN MAXIMUM(PageViews + Visits)](#column-maximum).



## Fonctions de tableau et fonctions de ligne

Une fonction de tableau consiste à ce que la sortie soit la même pour chaque ligne du tableau. Une fonction de ligne consiste à ce que la sortie soit différente pour chaque ligne du tableau.

Le cas échéant et lorsque c’est utile, une fonction est annotée avec le type de fonction : [!BADGE Tableau]{type="Neutral"} ou [!BADGE Ligne]{type="Neutral"}.

## Que signifie le paramètre d’inclusion de zéros ?

Il indique s’il faut inclure des zéros dans le calcul. Parfois, zéro signifie *rien* mais parfois, c’est important.

Par exemple, en présence d’une mesure Revenus, vous ajoutez une mesure Pages vues au rapport. Soudain, des lignes supplémentaires apparaissent pour vos revenus, qui contiennent toutes zéro. Vous ne souhaitez probablement pas que cette mesure supplémentaire affecte les éléments **[MEAN](cm-functions.md#mean)**, **[ROW MINIMUM](cm-functions.md#row-min)**, **[QUARTILE](cm-functions.md#quartile)** et d’autres calculs que vous avez dans la colonne des revenus. Dans ce cas, vous devez activer le paramètre `include-zeros`.

Un autre scénario consiste à utiliser deux mesures intéressantes, l’une ayant une moyenne ou un minimum supérieur, car certaines lignes sont des zéros.  Dans ce cas, vous pouvez choisir de ne pas activer le paramètre pour inclure des zéros.



## Valeur absolue {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-abs"
>title="Valeur absolue"
>abstract="Renvoie la valeur absolue d’un nombre. La valeur absolue d’un nombre est le nombre doté d’une valeur positive."

<!-- markdownlint-enable MD034 -->


![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ABSOLUTE VALUE(metric)]**

[!BADGE Row]{type="Neutral"} renvoie la valeur absolue d’un nombre. La valeur absolue d’un nombre est le nombre doté d’une valeur positive.

| Argument | Description |
|---|---|
| metric | Mesure pour laquelle vous souhaitez calculer la valeur absolue. |


## Column Maximum {#column-maximum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-max"
>title="Max. colonne"
>abstract="Renvoie la valeur la plus grande d’un ensemble d’éléments de dimension pour une colonne de mesures. MAXV évalue verticalement dans une seule colonne (mesure) sur l’ensemble des éléments de dimension."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MAXIMUM(metric, include_zeros)]**

Renvoie la valeur la plus grande d’un ensemble d’éléments de dimension pour une colonne de mesures. MAXV évalue verticalement dans une seule colonne (mesure) sur l’ensemble des éléments de dimension.

| Argument | Description |
|---|---|
| metric | Nécessite au moins une mesure, mais peut prendre n’importe quel nombre de mesures en tant que paramètres. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Column Minimum {#column-minimum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-min"
>title="Min. colonne"
>abstract="Renvoie la valeur la plus petite d’un ensemble d’éléments de dimension pour une colonne de mesures. MINV évalue verticalement dans une seule colonne (mesure) sur l’ensemble des éléments de dimension."

<!-- markdownlint-enable MD034 -->


![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MINIMUM(metric, include_zeros)]**

Renvoie la valeur la plus petite d’un ensemble d’éléments de dimension pour une colonne de mesures. MINV évalue verticalement dans une seule colonne (mesure) sur l’ensemble des éléments de dimension.

| Argument | Description |
|---|---|
| metric | Nécessite au moins une mesure, mais peut prendre n’importe quel nombre de mesures en tant que paramètres. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Column Sum {#column-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-sum"
>title="Column Sum"
>abstract="Ajoute toutes les valeurs numériques d’une mesure dans une colonne (sur l’ensemble des éléments d’une dimension)."

<!-- markdownlint-enable MD034 -->


![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN SUM(metric)]**

Ajoute toutes les valeurs numériques d’une mesure dans une colonne (sur l’ensemble des éléments d’une dimension).

| Argument | Description |
|---|---|
| metric | Nécessite au moins une mesure, mais peut prendre n’importe quel nombre de mesures en tant que paramètres. |


## Count {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="Count"
>abstract="Renvoie le nombre, ou le décompte, des valeurs différentes de zéro pour une mesure dans une colonne (le nombre d’éléments uniques signalés dans une dimension)."

<!-- markdownlint-enable MD034 -->


![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(metric)]**

[!BADGE Table]{type="Neutral"} renvoie le nombre, ou le décompte, des valeurs différentes de zéro pour une mesure dans une colonne (le nombre d’éléments uniques signalés dans une dimension).

| Argument | Description |
|---|---|
| metric | Mesure que vous souhaitez compter. |


## Exponent {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="Exponent"
>abstract="Renvoie e élevé à la puissance d’un nombre donné. La constante e est égale à 2,71828182845904, la base du logarithme népérien. EXPONENT est l’inverse de LN, le logarithme népérien d’un nombre."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(metric)]**

[!BADGE Row]{type="Neutral"} renvoie e élevé à la puissance d’un nombre donné. La constante e est égale à 2,71828182845904, la base du logarithme népérien. EXPONENT est l’inverse de LN, le logarithme népérien d’un nombre.

| Argument | Description |
|---|---|
| metric | Exposant appliqué à la base e. |


## Mean {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="Mean"
>abstract="Renvoie la moyenne arithmétique, ou moyenne, d’une mesure dans une colonne."

<!-- markdownlint-enable MD034 -->


![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric, include_zeros)]**

[!BADGE Table]{type="Neutral"} renvoie la moyenne arithmétique, ou moyenne, pour une mesure dans une colonne.

| Argument | Description |
|---|---|
| metric | Mesure pour laquelle vous souhaitez obtenir la moyenne. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Median {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="Median"
>abstract="Renvoie la médiane pour une mesure dans une colonne. La médiane est le nombre qui se situe au milieu d’un ensemble de nombres. En d’autres termes, la moitié des nombres ont des valeurs supérieures ou égales à la médiane, et l’autre moitié est inférieure ou égale à la médiane."

<!-- markdownlint-enable MD034 -->


![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric, include_zeros)]**

[!BADGE Table]{type="Neutral"} renvoie la médiane pour une mesure dans une colonne. La médiane est le nombre qui se situe au milieu d’un ensemble de nombres. En d’autres termes, la moitié des nombres ont des valeurs supérieures ou égales à la médiane, et l’autre moitié est inférieure ou égale à la médiane.

| Argument | Description |
|---|---|
| metric | Mesure pour laquelle vous souhaitez calculer la médiane. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Modulo {#modulo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-modulo"
>title="Modulo"
>abstract="Renvoie le reste après la division de x par y à l’aide d’une division euclidienne. "

<!-- markdownlint-enable MD034 -->


![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X, metric_Y)]**

Renvoie le reste après la division de x par y à l’aide d’une division euclidienne.

| Argument | Description |
|---|---|
| metric_X | Première mesure que vous souhaitez diviser. |
| metric_Y | Deuxième mesure que vous souhaitez diviser. |

### Exemples

La valeur de renvoi comporte le même signe que l’entrée (ou est égale à zéro).

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

Pour obtenir systématiquement un nombre positif, utilisez ce qui suit :

```
MODULO(MODULO(x,y)+y,y)
```

## Percentile {#percentile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-percentile"
>title="Percentile"
>abstract="Renvoie le énième percentile, qui est une valeur comprise entre 0 et 100. Lorsque n &lt; 0, la fonction utilise zéro. Lorsque n > 100, la fonction renvoie 100."

<!-- markdownlint-enable MD034 -->


![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE(metric, k, include_zeros)]**

[!BADGE Table]{type="Neutral"} renvoie le énième percentile, qui est une valeur comprise entre 0 et 100. Lorsque n &lt; 0, la fonction utilise zéro. Lorsque n > 100, la fonction renvoie 100.

| Argument | Description |
|---|---|
| metric | Percentile dans la plage de 0 à 100, inclusif. |
| k | Colonne de mesures qui définit l’étendue relative. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Power Operator {#power-operator}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pow"
>title="Power Operator"
>abstract="Renvoie x élevé à la puissance y."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL POWER OPERATOR(metric_X, metric_Y)]**

Renvoie x élevé à la puissance y.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez augmenter à la puissance metric_Y. |
| metric_Y | Puissance vers laquelle vous souhaitez augmenter metric_X. |


## Quartile {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="Quartile"
>abstract="Renvoie le quartile des valeurs pour une mesure. Par exemple, les quartiles peuvent être utilisés pour trouver les 25 % de produits générant le plus de chiffre d’affaires."

<!-- markdownlint-enable MD034 -->


![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric, quartile, include_zeros)]**

[!BADGE Table]{type="Neutral"} renvoie le quartile des valeurs pour une mesure. Par exemple, les quartiles peuvent être utilisés pour trouver les 25 % de produits générant le plus de recettes. [COLUMN MINIMUM](#column-minimum), [MEDIAN](#median), et [COLUMN MAXIMUM](#column-maximum) renvoient la même valeur que [QUARTILE](#quartile) lorsque le quartile est égal à `0` (zéro), `2` et `4`, respectivement.

| Argument | Description |
|---|---|
| metric | Mesure pour laquelle vous souhaitez calculer la valeur du quartile. |
| Quartile | Indique la valeur de quartile à renvoyer. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Round {#round}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-round"
>title="Round"
>abstract="Un arrondi sans paramètre de *nombre* est identique à un paramètre de *nombre* de 0, soit un arrondi au nombre entier le plus proche.  Avec un paramètre de *nombre*, ROUND renvoie le *nombre* de chiffres après la virgule.  Si le *nombre* est négatif, il renvoie des 0 à gauche de la décimale."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(metric, number)]**

Un arrondi sans paramètre de *nombre* est identique à un paramètre de *nombre* de 0, soit un arrondi au nombre entier le plus proche.  Avec un paramètre de *nombre*, ROUND renvoie le *nombre* de chiffres après la virgule.  Si le *nombre* est négatif, il renvoie des 0 à gauche de la décimale.

| Argument | Description |
|---|---|
| mesure | Mesure que vous souhaitez arrondir. |
| Number | Nombre de chiffres après la virgule à renvoyer. (Si négatif, renvoie des 0 à gauche de la décimale.) |

### Exemples

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```

## Row Count {#row-count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-rows"
>title="Row Count"
>abstract="Renvoie le nombre de lignes pour une colonne donnée (nombre d’éléments uniques signalés dans une dimension). L’option *Valeurs uniques dépassées* est comptabilisée en tant que 1."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ROW COUNT()]**

Renvoie le nombre de lignes pour une colonne donnée (nombre d’éléments uniques signalés dans une dimension). L’option *Valeurs uniques dépassées* est comptabilisée en tant que 1.


## Row Max {#row-max}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-max"
>title="Row Max"
>abstract="Maximum des colonnes de chaque ligne."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MAX(metric, include_zeros)]**

Maximum des colonnes de chaque ligne.

| Argument | Description |
|---|---|
| metric | Nécessite au moins une mesure, mais peut prendre n’importe quel nombre de mesures en tant que paramètres. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Row Min {#row-min}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-min"
>title="Row Min"
>abstract="Minimum des colonnes de chaque ligne."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MIN(metric, include_zeros)]**

Minimum des colonnes de chaque ligne.

| Argument | Description |
|---|---|
| metric | Nécessite au moins une mesure, mais peut prendre n’importe quel nombre de mesures en tant que paramètres. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Row Sum {#row-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-sum"
>title="Row Sum"
>abstract="Somme des colonnes de chaque ligne."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ROW SUM(metric, include_zeros)]**

Somme des colonnes de chaque ligne.

| Argument | Description |
|---|---|
| metric | Nécessite au moins une mesure, mais peut prendre n’importe quel nombre de mesures en tant que paramètres. |


## Square Root {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="Square Root"
>abstract="Renvoie la racine carrée positive d’un nombre. La racine carrée d’un nombre est la valeur de ce nombre élevée à la puissance 1/2."

<!-- markdownlint-enable MD034 -->


![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT(metric, include_zeros)]**

[!BADGE Row]{type="Neutral"} renvoie la racine carrée positive d’un nombre. La racine carrée d’un nombre est la valeur de ce nombre élevée à la puissance 1/2.

| Argument | Description |
|---|---|
| metric | Mesure pour laquelle vous souhaitez obtenir la racine carrée. |


## Standard Deviation {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="Standard Deviation"
>abstract="Renvoie l’écart type, ou la racine carrée de l’écart, selon l’échantillon de population de données."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL STANDARD DEVIATION(metric, include_zeros)]**

[!BADGE Table]{type="Neutral"} renvoie l’écart type, ou la racine carrée de l’écart, selon l’échantillon de population de données.

| Argument | Description |
|---|---|
| | Mesure pour laquelle vous souhaitez calculer l’écart type. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Variance {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="Variance"
>abstract="Renvoie la variance basée sur un échantillon de population de données."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric, include_zeros)]**

[!BADGE Table]{type="Neutral"} renvoie la variance basée sur un échantillon de population de données.

| Argument | Description |
|---|---|
| metric | Mesure pour laquelle vous souhaitez calculer la variance. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


L’équation pour la VARIANCE est la suivante :

![](assets/variance_eq.png){width="100"}

Où *x* est la moyenne de l’échantillon, [MEAN(*metric*)](#mean) et *n* est la taille de l’échantillon.


Pour calculer une variance, vous prenez une colonne entière de nombres. Vous calculez d’abord la moyenne de cette série de nombres. Une fois que vous avez obtenu la moyenne, vous effectuez les opérations suivantes avec chaque entrée :

1. Vous soustrayez la moyenne du nombre.

1. Vous calculez le carré du résultat.

1. Vous ajoutez ce résultat au total.

Une fois que vous avez effectué ces opérations sur la colonne entière, vous obtenez un total unique. Vous divisez ensuite ce total par le nombre d’éléments de la colonne. Ce nombre est la variance de la colonne. Il s’agit d’un seul nombre. Il est toutefois présenté sous la forme d’une colonne de nombres.

Dans l’exemple de la colonne à trois éléments suivante :

| Colonne |
|:---:|
| 1 |
| 2 |
| 3 |

La moyenne de cette colonne est 2. La variance de la colonne est ((1-2)<sup>2</sup>+(2-2)<sup>2</sup>+(3-2)<sup>2</sup>/3)=2/3.

<!--

## Absolute Value (Row)

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum 

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum 

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) 

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) 

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation 

Power Operator


pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)


## Mean (Table) 

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) 

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo 

The remainder of col1 / col2, using Euclidean division.

Returns the remainder after dividing x by y.

```
x = floor(x/y) + modulo(x,y)
```

The return value has the same sign as the input (or is zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

To always get a positive number, use 

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) 

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric column that defines relative standing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> The percentile value in the range 0 to 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) 

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric for which you want the quartile value. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indicates which *value to return. </td> 
  </tr> 
 </tbody> 
</table>

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round 

Returns the nearest integer for a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. A product reporting $569.51 will be round to the nearest dollar, or $570.

```
ROUND(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric you want to round.  |

Round without a digits parameter is the same as round with a digits parameter of 0, namely round to the nearest integer. With a digits parameter it returns that many digits to the right of the decimal. If digits is negative, it returns 0's to the left of the decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count 

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max 

The maximum of the columns in each row.

## Row Min 

The minimum of the columns in each row.

## Row Sum

The sum of the columns of each row.

## Square Root (Row) 

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric for which you want the square root.  |

## Standard Deviation (Table) 

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> The metric for which you want for standard deviation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) 

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the variance.  |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.

2. Square the result.

3. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In case of a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

-->