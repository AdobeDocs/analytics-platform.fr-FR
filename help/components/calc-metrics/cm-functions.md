---
title: Fonctions de base
description: Le créateur de mesures calculées permet d’appliquer des fonctions statistiques et mathématiques afin de créer des mesures calculées avancées.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 1a84fc71eb29ceabf3a3c5c3e333b78b882ea966
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 29%

---

# Fonctions de base


Le [créateur de mesures calculées](cm-workflow/cm-build-metrics.md) vous permet d’appliquer des fonctions statistiques et mathématiques. Cet article présente la liste alphabétique des fonctions et leurs définitions.

>[!NOTE]
>
>Lorsque [!DNL metric] est identifié en tant qu’argument d’une fonction, d’autres expressions des mesures sont également autorisées. Par exemple, [COLUMN MAXIMUM(metrics)](#column-maximum) autorise également [COLONMN MAXIMUM(PageViews + Visits)](#column-maximum).



## Fonctions de tableau et fonctions de ligne

Une fonction de tableau consiste à ce que la sortie soit la même pour chaque ligne du tableau. Une fonction de ligne consiste à ce que la sortie soit différente pour chaque ligne du tableau.

Le cas échéant, une fonction est annotée avec le type de fonction : [!BADGE Table]{type="Neutral"}[!BADGE Ligne]{type="Neutral"}

## Que signifie le paramètre d’inclusion de zéros ?

Il indique s’il faut inclure des zéros dans le calcul. Parfois, zéro signifie *rien*, mais parfois, c’est important.

Par exemple, si vous disposez d’une mesure Recettes, puis que vous ajoutez une mesure Pages vues au rapport, vous obtenez soudainement plus de lignes pour vos recettes, qui sont toutes nulles. Vous ne souhaitez probablement pas que cette mesure supplémentaire affecte les **[MOYENNE](cm-functions.md#mean)**, **[LIGNE MINIMUM](cm-functions.md#row-min)**, **[QUARTILE](cm-functions.md#quartile)** et d’autres calculs que vous avez dans la colonne des recettes. Dans ce cas, vous devez vérifier le paramètre `include-zeros` .

Un autre scénario consiste à utiliser deux mesures intéressantes, l’une ayant une moyenne ou un minimum supérieur, car certaines lignes sont des zéros.  Dans ce cas, vous pouvez choisir de ne pas vérifier le paramètre pour inclure des zéros.



## Valeur absolue

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL VALEUR ABSOLUE(metric)]**

[!BADGE Ligne]{type="Neutral"}

| Argument | Description |
|---|---|
| mesure | Mesure pour laquelle vous souhaitez calculer la valeur absolue. |


## Max. colonne

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL COLONNE MAXIMUM(mesure, include_zeros)]**

Renvoie la valeur la plus grande d’un ensemble d’éléments de dimension pour une colonne de mesures. MAXV évalue verticalement dans une seule colonne (mesure) sur l’ensemble des éléments de dimension.

| Argument | Description |
|---|---|
| mesure | Nécessite au moins une mesure, mais peut prendre n’importe quel nombre de mesures en tant que paramètres. |
| include_zeros | Inclure ou non des valeurs nulles dans les calculs. |


## Min. colonne

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL COLONNE MINIMUM(mesure, include_zeros)]**

Renvoie la valeur la plus petite d’un ensemble d’éléments de dimension pour une colonne de mesures. MINV évalue verticalement dans une seule colonne (mesure) sur l’ensemble des éléments de dimension.

| Argument | Description |
|---|---|
| mesure | Nécessite au moins une mesure, mais peut prendre n’importe quel nombre de mesures en tant que paramètres. |
| include_zeros | Inclure ou non des valeurs nulles dans les calculs. |


## Somme de la colonne

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL COLONNE SUM(metric)]**

Ajoute toutes les valeurs numériques d’une mesure dans une colonne (sur l’ensemble des éléments d’une dimension).

| Argument | Description |
|---|---|
| mesure | Nécessite au moins une mesure, mais peut prendre n’importe quel nombre de mesures en tant que paramètres. |


## Nombre

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(metric)]**

[!BADGE Tableau]{type="Neutral"}

| Argument | Description |
|---|---|
| mesure | Mesure que vous souhaitez comptabiliser. |


## Exposant

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(metric)]**

[!BADGE Ligne]{type="Neutral"}

| Argument | Description |
|---|---|
| mesure | Exposant appliqué à la base e. |


## Moyenne

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric, include_zeros)]**

[!BADGE Tableau]{type="Neutral"}

| Argument | Description |
|---|---|
| mesure | Mesure pour laquelle vous souhaitez calculer la moyenne. |
| include_zeros | Inclure ou non des valeurs nulles dans les calculs. |


## Médiane

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric, include_zeros)]**

[!BADGE Tableau]{type="Neutral"}

| Argument | Description |
|---|---|
| mesure | Mesure pour laquelle vous souhaitez calculer la médiane. |
| include_zeros | Inclure ou non des valeurs nulles dans les calculs. |


## Modulo

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X, metric_Y)]**

Renvoie le reste après la division de x par y à l’aide de la division euclidienne.

| Argument | Description |
|---|---|
| metric_X | Première mesure que vous souhaitez diviser. |
| metric_Y | La deuxième mesure que vous souhaitez diviser. |

### Exemples

La valeur de renvoi comporte le même signe que l’entrée (ou est égale à zéro).

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

Pour obtenir toujours un nombre positif, utilisez

```
MODULO(MODULO(x,y)+y,y)
```

## Percentile

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE(mesure, k, include_zeros)]**

[!BADGE Tableau]{type="Neutral"}

| Argument | Description |
|---|---|
| mesure | Percentile dans la plage de 0 à 100, inclusif. |
| k | Colonne de mesures qui définit l’étendue relative. |
| include_zeros | Inclure ou non des valeurs nulles dans les calculs. |



## Opérateur de puissance

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL OPÉRATEUR DE POUVOIR(metric_X, metrix_Y)]**

Renvoie x élevé à la puissance y.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez augmenter jusqu’à la puissance metric_Y. |
| metric_Y | Puissance vers laquelle vous souhaitez augmenter metric_X. |


## Quartile

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(mesure, quartile, include_zeros)]**

[!BADGE Tableau]{type="Neutral"}[COLONNE MINIMUM](#column-minimum), [MEDIAN](#median) et [COLONNE MAXIMUM](#column-maximum) renvoient la même valeur que [QUARTILE](#quartile) lorsque le quartile est égal à `0` (zéro), `2` et `4`, respectivement.

| Argument | Description |
|---|---|
| mesure | Mesure pour laquelle vous souhaitez calculer la valeur du quartile. |
| quartile | Indique la valeur du quartile à renvoyer. |
| include_zeros | Inclure ou non des valeurs nulles dans les calculs. |


## Tour

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(metric, number)]**

Un arrondi sans paramètre *number* est identique à un arrondi avec un paramètre *number* de 0, à savoir arrondi à l’entier le plus proche.  Avec un paramètre *number* , ROUND renvoie les *chiffres* situés à droite de la décimale.  Si *number* est négatif, il renvoie des 0 à gauche de la décimale.

| Argument | Description |
|---|---|
| mesure | Mesure que vous souhaitez arrondir. |
| number | Nombre de chiffres à droite de la décimale à renvoyer. (Si la valeur est négative, elle renvoie des zéros à gauche de la décimale). |

### Exemples

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```


## Décompte de lignes

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ROW COUNT()]**

Renvoie le nombre de lignes pour une colonne donnée (nombre d’éléments uniques signalés dans une dimension). *Les valeurs uniques dépassées* sont comptabilisées comme 1.


## Max. ligne

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MAX(metric, include_zeros)]**

Nombre maximal de colonnes de chaque ligne.

| Argument | Description |
|---|---|
| mesure | Nécessite au moins une mesure, mais peut prendre n’importe quel nombre de mesures en tant que paramètres. |
| include_zeros | Inclure ou non des valeurs nulles dans les calculs. |

## Min. ligne

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MIN(metric, include_zeros)]**

Minimum des colonnes de chaque ligne.

| Argument | Description |
|---|---|
| mesure | Nécessite au moins une mesure, mais peut prendre n’importe quel nombre de mesures en tant que paramètres. |
| include_zeros | Inclure ou non des valeurs nulles dans les calculs. |



## Somme de la ligne

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ROW SUM(metric, include_zeros)]**

Somme des colonnes de chaque ligne.

| Argument | Description |
|---|---|
| mesure | Nécessite au moins une mesure, mais peut prendre n’importe quel nombre de mesures en tant que paramètres. |


## Racine carrée

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RACINE CARRÉE(mesure, include_zeros)]**

[!BADGE Ligne]{type="Neutral"}

| Argument | Description |
|---|---|
| mesure | Mesure pour laquelle vous souhaitez calculer la racine carrée. |


## Écart type

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ÉCART STANDARD(mesure, include_zeros)]**

[!BADGE Tableau]{type="Neutral"}

| Argument | Description |
|---|---|
| | Mesure pour laquelle vous souhaitez calculer l’écart type. |
| include_zeros | Inclure ou non des valeurs nulles dans les calculs. |


## Variance

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(mesure, include_zeros)]**

[!BADGE Tableau]{type="Neutral"}

| Argument | Description |
|---|---|
| mesure | Mesure pour laquelle vous souhaitez calculer la variance. |
| include_zeros | Inclure ou non des valeurs nulles dans les calculs. |


L’équation pour la VARIANCE est la suivante :

![](assets/variance_eq.png){width="100"}

Où *x* est l’exemple de moyenne, [MEAN(*metric*)](#mean) et *n* est l’exemple de taille.


Pour calculer une variance, vous observez une colonne entière de nombres. Vous calculez d’abord la moyenne de cette série de nombres. Une fois la moyenne atteinte, vous accédez à chaque entrée et procédez comme suit :

1. Vous soustrayez la moyenne du nombre.

1. Vous calculez le carré du résultat.

1. Vous ajoutez ce résultat au total.

Une fois que vous avez effectué une itération sur l’ensemble de la colonne, vous disposez d’un total unique. Vous divisez ensuite ce total par le nombre d’éléments de la colonne. Ce nombre est la variance de la colonne. Il s’agit d’un seul nombre. Il est toutefois présenté sous la forme d’une colonne de nombres.

Dans l’exemple de la colonne à trois éléments suivante :

| colonne |
|:---:|
| 1 |
| 2 |
| 3 |

La moyenne de cette colonne est 2. La variance de la colonne est ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3.




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