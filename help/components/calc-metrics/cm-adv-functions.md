---
title: Fonctions avancées
description: Accédez à ces fonctions en cochant Afficher les options avancées dans le menu déroulant Fonctions .
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '5247'
ht-degree: 99%

---

# Fonctions avancées

Le [créateur de mesures calculées](cm-workflow/cm-build-metrics.md) vous permet d’appliquer des fonctions statistiques et mathématiques. Cet article comprend une liste alphabétique des fonctions avancées ainsi que leurs définitions.

Accédez à ces fonctions en sélectionnant **[!UICONTROL Tout afficher]** ci-dessous dans la liste ![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL Fonctions]** du panneau Composants. Faites défiler la page vers le bas pour afficher la liste des **[!UICONTROL Fonctions avancées]**.

## Fonctions de tableau et fonctions de ligne

Une fonction de tableau consiste à ce que la sortie soit la même pour chaque ligne du tableau. Une fonction de ligne consiste à ce que la sortie soit différente pour chaque ligne du tableau.

Le cas échéant et lorsque c’est utile, une fonction est annotée avec le type de fonction : [!BADGE Tableau]{type="Neutral"} ou [!BADGE Ligne]{type="Neutral"}.

## Que signifie le paramètre d’inclusion de zéros ?

Il indique s’il faut inclure des zéros dans le calcul. Parfois, zéro signifie *rien* mais parfois, c’est important.

Par exemple, en présence d’une mesure Revenus, vous ajoutez une mesure Pages vues au rapport. Soudain, des lignes supplémentaires apparaissent pour vos revenus, qui contiennent toutes zéro. Vous ne souhaitez probablement pas que cette mesure supplémentaire affecte les éléments **[MEAN](cm-functions.md#mean)**, **[ROW MINIMUM](cm-functions.md#row-min)**, **[QUARTILE](cm-functions.md#quartile)** et d’autres calculs que vous avez dans la colonne des revenus. Dans ce cas, vous devez activer le paramètre `include-zeros`.

Un autre scénario consiste à utiliser deux mesures intéressantes, l’une ayant une moyenne ou un minimum supérieur, car certaines lignes sont des zéros.  Dans ce cas, vous pouvez choisir de ne pas activer le paramètre pour inclure des zéros.


## Et {#and}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-and"
>title="Et"
>abstract="Conjonction. Non égal à zéro est considéré comme true et égal à zéro est considéré comme false. La sortie est soit 0 (false) soit 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ET(logical_test)]**

Conjonction. Non égal à zéro est considéré comme true et égal à zéro est considéré comme false. La sortie est soit 0 (false) soit 1 (true).

| Argument | Description |
|---|---|
| logical_test | Nécessite au moins un paramètre, mais peut prendre en charge n’importe quel nombre de paramètres. Toute valeur ou expression pouvant être évaluée avec TRUE ou FALSE |


## Nombre distinct approximatif {#approximate_count_distinct}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-distinct-metric"
>title="Nombre distinct approximatif"
>abstract="Renvoie le nombre approximatif d’éléments distincts pour la dimension sélectionnée."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL NOMBRE APPROXIMATIF DISTINCT(dimension)]**


Renvoie le nombre approximatif d’éléments distincts pour la dimension sélectionnée.


| Argument | Description |
|---|---|
| dimension | Dimension pour laquelle vous souhaitez calculer le nombre distinct approximatif d’éléments. |

### Exemple

Un cas d’utilisation courant de cette fonction est lorsque vous souhaitez obtenir un nombre approximatif de clientes et clients.



## Arc cosinus {#arc-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-acos"
>title="Arc cosinus"
>abstract="Renvoie l’arc cosinus, ou l’inverse du cosinus, d’une mesure. L’arc cosinus d’un nombre est l’angle dont le cosinus vaut ce nombre. L’angle renvoyé est donné en radians dans la plage 0 (zéro) à pi. Si vous souhaitez convertir le résultat de radians en degrés, multipliez-le par 180/PI()."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ARC COSINUS(mesure)]**


[!BADGE Ligne]{type="Neutral"} Renvoie l’arc cosinus, ou l’inverse du cosinus, d’une mesure. L’arc cosinus d’un nombre est l’angle dont le cosinus vaut ce nombre. L’angle renvoyé est donné en radians dans la plage 0 (zéro) à pi. Si vous souhaitez convertir le résultat de radians en degrés, multipliez-le par 180/PI().


| Argument | Description |
|---|---|
| mesure | Cosinus de l’angle que vous souhaitez obtenir de -1 à 1. |



## Arc sinus {#arc-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-asin"
>title="Arc sinus"
>abstract="Renvoie l’arc sinus, ou le sinus inverse, d’un nombre. L’arc sinus d’un nombre est l’angle dont le sinus est un nombre. L’angle renvoyé est donné en radians dans la plage -pi/2 à pi/2. Pour exprimer l’arc sinus en degrés, multipliez le résultat par 180/PI()."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ARC SINUS(mesure)]**


[!BADGE Ligne]{type="Neutral"} Renvoie l’arc sinus, ou le sinus inverse, d’un nombre. L’arc sinus d’un nombre est l’angle dont le sinus est un nombre. L’angle renvoyé est donné en radians dans la plage -pi/2 à pi/2. Pour exprimer l’arc sinus en degrés, multipliez le résultat par 180/PI().


| Argument | Description |
|---|---|
| mesure | Sinus de l’angle que vous souhaitez obtenir de -1 à 1. |



## Arc tangente {#arc-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-atan"
>title="Arc tangente"
>abstract="Renvoie l’arc tangent, ou la tangente inverse, d’un nombre. L’arc tangente d’un nombre est l’angle dont la tangente est un nombre. L’angle renvoyé est donné en radians dans la plage -pi/2 à pi/2. Pour exprimer l’arc tangente en degrés, multipliez le résultat par 180/PI()."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ARC TANGENTE(mesure)]**


[!BADGE Ligne]{type="Neutral"} Renvoie l’arc tangente, ou la tangente inverse, d’un nombre. L’arc tangente d’un nombre est l’angle dont la tangente est un nombre. L’angle renvoyé est donné en radians dans la plage -pi/2 à pi/2. Pour exprimer l’arc tangente en degrés, multipliez le résultat par 180/PI().


| Argument | Description |
|---|---|
| mesure | Tangente de l’angle que vous souhaitez obtenir de -1 à 1. |



## Cdf-T {#cdf-t}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-t"
>title="Cdf-T"
>abstract="Renvoie la probabilité qu’une variable aléatoire avec une loi de Student t à n degrés de liberté ait un score z inférieur à col."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(mesure, nombre)]**

Renvoie la probabilité qu’une variable aléatoire avec une loi de Student t à n degrés de liberté ait un score z inférieur à col.

| Argument | Description |
|---|---|
| mesure | Mesure pour laquelle vous souhaitez utiliser la fonction de distribution cumulée de la loi de Student-t. |
| Nombre | Les degrés de liberté pour la fonction de distribution cumulée de la loi de Student-t |

### Exemple

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z {#cdf-z}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-z"
>title="Cdf-Z"
>abstract="Renvoie la probabilité qu’une variable aléatoire avec une distribution normale ait un score z inférieur à col."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(mesure, nombre)]**

Renvoie la probabilité qu’une variable aléatoire avec une distribution normale ait un score z inférieur à col.

| Argument | Description |
|---|---|
| mesure | Mesure pour laquelle vous souhaitez utiliser la fonction de distribution cumulée de la distribution normale standard. |

### Exemples

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## Plafond {#ceiling}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ceil"
>title="Plafond"
>abstract="Renvoie l’entier le plus petit, non inférieur à une valeur donnée. Par exemple, si vous souhaitez éviter de rapporter les décimales de devise pour le chiffre d’affaires et qu’un produit génère 569,34 $, utilisez la formule CEILING(Revenue) pour arrondir le chiffre d’affaires au dollar le plus proche, soit 570 $."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL PLAFOND(mesure)]**

[!BADGE Ligne]{type="Neutral"} Renvoie l’entier le plus petit, non inférieur à une valeur donnée. Par exemple, si vous souhaitez éviter de rapporter les décimales de devise pour le chiffre d’affaires et qu’un produit génère 569,34 $, utilisez la formule CEILING(Revenue) pour arrondir le chiffre d’affaires au dollar le plus proche, soit 570 $.

| Argument | Description |
|---|---|
| mesure | Mesure que vous souhaitez arrondir. |


## Degré de confiance {#confidence}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence"
>title="Degré de confiance"
>abstract="Calculez le degré de confiance valide à tout moment à l’aide de la méthode WASKR comme décrit dans [Théorie des limites centrales uniformes dans le temps et séquences de confiance asymptotiques](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIANCE(conteneur-normalisation, mesure-succès, contrôle, seuil-importance)]**

Calculez le degré de confiance valide à tout moment à l’aide de la méthode WASKR comme décrit dans [Théorie des limites centrales uniformes dans le temps et séquences de confiance asymptotiques](https://arxiv.org/pdf/2103.06476).

Le degré de confiance est une mesure probabiliste de l’ampleur des preuves sur le fait qu’une variante donnée est identique à la variante de contrôle. Un degré de confiance plus élevé indique moins de preuves relatives à l’hypothèse que la variante de contrôle et la variante de non-contrôle ont des performances similaires.

| Argument | Description |
| --- | --- |
| conteneur-normalisation | La base (Personnes, Sessions ou Événements) sur laquelle un test est exécuté. |
| mesure-succès | La mesure ou les mesures avec lesquelles une personne compare des variantes. |
| contrôle | La variante avec laquelle sont comparées toutes les autres variantes de l’expérience. Saisissez le nom de l’élément de dimension de variante de contrôle. |
| seuil-importance | Le seuil de cette fonction est défini sur une valeur par défaut de 95 %. |


## Confiance (inférieure) {#confidence-lower}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence-interval-lower"
>title="Confiance (inférieure)"
>abstract="Calculez le degré de confiance valide à tout moment **inférieur** à l’aide de la méthode WASKR comme décrit dans [Théorie des limites centrales uniformes dans le temps et séquences de confiance asymptotiques](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIANCE(conteneur-normalisation, mesure-succès, contrôle, seuil-importance)]**

Calculez le degré de confiance valide à tout moment **inférieure** à l’aide de la méthode WASKR comme décrit dans [Théorie des limites centrales uniformes dans le temps et séquences de confiance asymptotiques](https://arxiv.org/pdf/2103.06476).

Le degré de confiance est une mesure probabiliste de l’ampleur des preuves sur le fait qu’une variante donnée est identique à la variante de contrôle. Un degré de confiance plus élevé indique moins de preuves relatives à l’hypothèse que la variante de contrôle et la variante de non-contrôle ont des performances similaires.

| Argument | Description |
| --- | --- |
| conteneur-normalisation | La base (Personnes, Sessions ou Événements) sur laquelle un test est exécuté. |
| mesure-succès | La mesure ou les mesures avec lesquelles une personne compare des variantes. |
| contrôle | La variante avec laquelle sont comparées toutes les autres variantes de l’expérience. Saisissez le nom de l’élément de dimension de variante de contrôle. |
| seuil-importance | Le seuil de cette fonction est défini sur une valeur par défaut de 95 %. |

## Confiance (supérieure) {#confidence-upper}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence-interval-upper"
>title="Confiance (supérieure)"
>abstract="Calculez le degré de confiance valide à tout moment **supérieur** à l’aide de la méthode WASKR comme décrit dans [Théorie des limites centrales uniformes dans le temps et séquences de confiance asymptotiques](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIANCE(conteneur-normalisation, mesure-succès, contrôle, seuil-importance)]**

Calculez le degré de confiance valide à tout moment **supérieure** à l’aide de la méthode WASKR comme décrit dans [Théorie des limites centrales uniformes dans le temps et séquences de confiance asymptotiques](https://arxiv.org/pdf/2103.06476).

Le degré de confiance est une mesure probabiliste de l’ampleur des preuves sur le fait qu’une variante donnée est identique à la variante de contrôle. Un degré de confiance plus élevé indique moins de preuves relatives à l’hypothèse que la variante de contrôle et la variante de non-contrôle ont des performances similaires.

| Argument | Description |
| --- | --- |
| conteneur-normalisation | La base (Personnes, Sessions ou Événements) sur laquelle un test est exécuté. |
| mesure-succès | La mesure ou les mesures avec lesquelles une personne compare des variantes. |
| contrôle | La variante avec laquelle sont comparées toutes les autres variantes de l’expérience. Saisissez le nom de l’élément de dimension de variante de contrôle. |
| seuil-importance | Le seuil de cette fonction est défini sur une valeur par défaut de 95 %. |


## Cosinus {#cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cos"
>title="Cosinus"
>abstract="Renvoie le cosinus de l’angle donné. Si l’angle est en degrés, multipliez l’angle par PI()/180."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL CONSINUS(mesure)]**

[!BADGE Ligne]{type="Neutral"} Renvoie le cosinus de l’angle donné. Si l’angle est en degrés, multipliez l’angle par PI()/180.

| Argument | Description |
|---|---|
| mesure | Angle en radians que vous souhaitez obtenir pour le cosinus. |


## Racine cubique {#cube-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cube-root"
>title="Racine cubique"
>abstract="Renvoie la racine cubique positive d’un nombre. La racine cubique d’un nombre est la valeur de ce nombre élevée à la puissance 1/3."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RACINE CUBIQUE(mesure)]**


Renvoie la racine cubique positive d’un nombre. La racine cubique d’un nombre est la valeur de ce nombre élevée à la puissance 1/3.


| Argument | Description |
|---|---|
| mesure | Mesure pour laquelle vous souhaitez obtenir la racine cubique. |



## Cumulatif {#cumulative}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul"
>title="Cumulatif"
>abstract="Renvoie la somme des n derniers éléments de la colonne x. Si n > 0, additionnez les n derniers éléments ou x. Si n &lt; 0, additionnez les éléments précédents."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIF(nombre, mesure)]**

Renvoie la somme des n derniers éléments de la colonne x. Si n > 0, additionnez les n derniers éléments ou x. Si n &lt; 0, additionnez les éléments précédents.

| Argument | Description |
| --- | --- |
| Nombre | N dernières lignes pour lesquelles renvoyer la somme. Si N &lt;= 0, utilisez toutes les lignes précédentes. |
| mesure | Mesure pour laquelle vous souhaitez obtenir la somme cumulée. |

### Exemples

| Date | Chiffre dʼaffaires | CUMULATIF(0, Chiffre d’affaires) | CUMULATIF(2, Chiffre d’affaires) |
|------|------:|--------------:|--------------:|
| Mai | 500 $ | 500 $ | 500 $ |
| Juin | 200 $ | 700 $ | 700 $ |
| Juillet | $400 | 1 100 $ | $600 |


## Cumulé (moyenne) {#cumulative-average}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul-avg"
>title="Cumulé (moyenne)"
>abstract="Renvoie la moyenne des n derniers éléments de la colonne x. Si n > 0, additionnez les n derniers éléments ou x. Si n &lt; 0, additionnez les éléments précédents."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL MOYENNE CUMULÉE(nombre, mesure)]**

Renvoie la moyenne des n derniers éléments de la colonne x. Si n > 0, additionnez les n derniers éléments ou x. Si n &lt; 0, additionnez les éléments précédents.

| Argument | Description |
| --- | --- |
| Nombre | N dernières lignes pour lesquelles renvoyer la moyenne. Si N &lt;= 0, utilisez toutes les lignes précédentes. |
| mesure | Mesure pour laquelle vous souhaitez obtenir la moyenne cumulée. |

>[!NOTE]
>
>Cette fonction ne fonctionne pas avec les mesures de taux comme le chiffre d’affaires par personne. La fonction effectue une moyenne des taux au lieu d’additionner les revenus sur les N derniers et d’additionner les personnes sur les N derniers puis de les diviser. <br/>Utilisez plutôt [**[!UICONTROL CUMULATIF(chiffre d’affaires)]**](#cumulative) ![Diviser](/help/assets/icons/Divide.svg) [**[!UICONTROL CUMULATIF(personne)]**](#cumulative).
>


## Égal à {#equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-eq"
>title="Égal à"
>abstract="Égal à. La sortie est soit 0 (false) soit 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ÉGAL À()]**

Égal à. La sortie est soit 0 (false) soit 1 (true).


| Argument | Description |
|---|---|
| metric_X | Mesure à utiliser pour la comparaison. |
| metric_Y | Mesure à utiliser comme référence pour comparer. |

### Exemple

`Metric 1 = Metric 2`


## Régression exponentielle : coefficient de corrélation {#exponential-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-exp"
>title="Régression exponentielle : coefficient de corrélation"
>abstract="Régression exponentielle : Y = a exp(X) + b. Renvoie le coefficient de corrélation."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION EXPONENTIELLE : COEFFICIENT DE CORRÉLATION(metric_X, metric_Y, include_zeros)]**


[!BADGE Tableau]{type="Neutral"} Régression exponentielle : Y = a exp(X) + b. Renvoie le coefficient de corrélation.


| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez corréler à metric_Y. |
| metric_Y | Mesure que vous souhaitez corréler à metric_X. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |

## Régression exponentielle : Y prédit {#exponential-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-exp"
>title="Régression exponentielle : Y prédit"
>abstract="Régression exponentielle : Y = a exp(X) + b. Renvoie Y."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION EXPONENTIELLE : PRÉDITE Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Ligne]{type="Neutral"} Régression exponentielle : Y = a exp(X) + b. Renvoie Y.


| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données indépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données dépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Régression exponentielle : ordonnée à l’origine {#exponential-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-exp"
>title="Régression exponentielle : ordonnée à l’origine"
>abstract="Régression exponentielle : Y = a exp(X) + b. Renvoie b."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION EXPONENTIELLE : INTERCEPTER(metric_X, metric_Y, include_zeros)]**


[!BADGE Tableau]{type="Neutral"} Régression exponentielle : Y = a exp(X) + b. Renvoie b.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Régression exponentielle : inclinaison {#exponential-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-exp"
>title="Régression exponentielle : inclinaison"
>abstract="Régression exponentielle : Y = a exp(X) + b. Renvoie a."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION EXPONENTIELLE : PENTE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tableau]{type="Neutral"} Régression exponentielle : Y = a exp(X) + b. Renvoie a.


| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Arrondi à l’inférieur {#floor}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-floor"
>title="Arrondi à l’inférieur"
>abstract="Renvoie l’entier le plus grand, non supérieur à une valeur donnée. Par exemple, si vous souhaitez éviter de rapporter les décimales de devise pour le chiffre d’affaires et qu’un produit génère 569,34 $, utilisez la formule FLOOR(Revenue) pour arrondir le chiffre d’affaires au dollar le plus proche, soit 569 $."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR(metric_X, metric_Y, include_zeros)]**

[!BADGE Ligne]{type="Neutral"} Renvoie l’entier le plus grand, non supérieur à une valeur donnée. Par exemple, si vous souhaitez éviter de rapporter les décimales de devise pour le chiffre d’affaires et qu’un produit génère 569,34 $, utilisez la formule FLOOR(Revenue) pour arrondir le chiffre d’affaires au dollar le plus proche, soit 569 $.

| Argument | Description |
|---|---|
| mesure | Mesure que vous souhaitez arrondir. |


## Supérieur à {#greather-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-gt"
>title="Supérieur à"
>abstract="La sortie est soit 0 (false) soit 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL SUPÉRIEUR À()]**

La sortie est soit 0 (false) soit 1 (true).

| Argument | Description |
|---|---|
| metric_X | Mesure de base à utiliser pour la comparaison. |
| metric_Y | Mesure à utiliser comme référence pour comparer. |

### Exemple

`Metric 1 > Metric 2`


## Supérieur ou égal à {#greater-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ge"
>title="Supérieur ou égal à"
>abstract="Supérieur ou égal à. La sortie est soit 0 (false) soit 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL SUPÉRIEUR OU ÉGAL À()]**

Supérieur ou égal à. La sortie est soit 0 (false) soit 1 (true).

| Argument | Description |
|---|---|
| metric_X | Mesure de base à utiliser pour la comparaison. |
| metric_Y | Mesure à utiliser comme référence pour comparer. |

### Exemple

`Metric 1 >= Metric 2`



## Cosinus hyperbolique {#hyperbolic-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cosh"
>title="Cosinus hyperbolique"
>abstract="Renvoie le cosinus hyperbolique d’un nombre."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL COSINUS HYPERBOLIQUE(mesure)]**


[!BADGE Ligne]{type="Neutral"} Renvoie le cosinus hyperbolique d’un nombre.


| Argument | Description |
|---|---|
| mesure | Angle en radians pour lequel vous souhaitez obtenir le cosinus hyperbolique. |



## Sinus hyperbolique {#hyperbolic-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sinh"
>title="Sinus hyperbolique"
>abstract="Renvoie le sinus hyperbolique d’un nombre."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL SINUS HYPERBOLIQUE(mesure)]**

[!BADGE Ligne]{type="Neutral"} Renvoie le sinus hyperbolique d’un nombre.

| Argument | Description |
|---|---|
| mesure | Angle en radians pour lequel vous souhaitez obtenir le sinus hyperbolique. |


## Tangente hyperbolique {#hyperbolic-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tanh"
>title="Tangente hyperbolique"
>abstract="Renvoie la tangente hyperbolique d’un nombre."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENTE HYPERBOLIQUE(mesure)]**

[!BADGE Ligne]{type="Neutral"} Renvoie la tangente hyperbolique d’un nombre.

| Argument | Description |
|---|---|
| mesure | Angle en radians pour lequel vous souhaitez obtenir la tangente hyperbolique. |


## Si {#if}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-if"
>title="Si"
>abstract="Si la valeur du paramètre de condition est différente de zéro (true), le résultat est la valeur du paramètre value_if_true. Dans le cas contraire, il s’agit de la valeur du paramètre value_if_false."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL SI(logical_test, value_if_true, value_if_false)]**


[!BADGE Ligne]{type="Neutral"} Si la valeur du paramètre de condition est différente de zéro (true), le résultat est la valeur du paramètre value_if_true. Dans le cas contraire, il s’agit de la valeur du paramètre value_if_false.


| Argument | Description |
|---|---|
| logical_test | Obligatoire. Toute valeur ou expression pouvant être évaluée avec TRUE ou FALSE |
| value_if_true | Valeur que vous souhaitez voir renvoyée si l’argument logical_test est évalué sur TRUE. (Cet argument est défini sur la valeur par défaut de 0 si non inclus.) |
| value_if_false | Valeur à renvoyer si l&#39;argument logical_test est évalué sur FALSE. (La valeur par défaut de cet argument est 0 s&#39;il n&#39;est pas inclus.) |


## Inférieur à {#less-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-lt"
>title="Inférieur à"
>abstract="La sortie est soit 0 (false) soit 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL INFÉRIEUR À()]**

La sortie est soit 0 (false) soit 1 (true).

| Argument | Description |
|---|---|
| metric_X | Mesure à utiliser pour la comparaison. |
| metric_Y | Mesure à utiliser comme référence pour comparer. |

### Exemple

`Metric 1 < Metric 2`


## Inférieur ou égal à {#less-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-le"
>title="Inférieur ou égal à"
>abstract="Inférieur ou égal à. La sortie est soit 0 (false) soit 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL INFÉRIEUR OU ÉGAL À()]**

Inférieur ou égal à. La sortie est soit 0 (false) soit 1 (true).

| Argument | Description |
|---|---|
| metric_X | Mesure à utiliser pour la comparaison. |
| metric_Y | Mesure à utiliser comme référence pour comparer. |

### Exemple

`Metric 1 <= Metric 2`



## Effet élévateur {#lift}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-lift"
>title="Effet élévateur"
>abstract="Effet élévateur du ratio par rapport à la valeur de contrôle."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL ÉLÉVATEUR(conteneur-normalisation, mesure-succès, contrôle)]**

Effet élévateur du ratio par rapport à la valeur de contrôle.

| Argument | Description |
| --- | --- |
| conteneur-normalisation | La base (Personnes, Sessions ou Événements) sur laquelle un test est exécuté. |
| mesure-succès | La mesure ou les mesures avec lesquelles une personne compare des variantes. |
| contrôle | La variante avec laquelle sont comparées toutes les autres variantes de l’expérience. Saisissez le nom de l’élément de dimension de variante de contrôle. |



## Régression linéaire : coefficient de corrélation {#linear-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-linear"
>title="Régression linéaire : coefficient de corrélation"
>abstract="Régression linéaire : Y = a X + b. Renvoie le coefficient de corrélation."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION LINÉAIRE : COEFFICIENT DE CORRÉLATION(metric_X, metric_Y, include_zeros)]**


[!BADGE Tableau]{type="Neutral"} Régression linéaire : Y = a X + b. Renvoie le coefficient de corrélation.


| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez corréler à metric_Y. |
| metric_Y | Mesure que vous souhaitez corréler à metric_X. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Régression linéaire : ordonnée à l’origine {#linear-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-linear"
>title="Régression linéaire : ordonnée à l’origine"
>abstract="Régression linéaire : Y = a X + b. Renvoie b."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION LINÉAIRE : INTERCEPTER(metric_X, metric_Y, include_zeros)]**


[!BADGE Tableau]{type="Neutral"} Régression linéaire : Y = a X + b. Renvoie b.


| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Régression linéaire : Y prédit {#linear-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-linear"
>title="Régression linéaire : Y prédit"
>abstract="Régression linéaire : Y = a X + b. Renvoie Y."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION LINÉAIRE : PRÉDITE Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Ligne]{type="Neutral"} Régression linéaire : Y = a X + b. Renvoie Y.


| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Régression linéaire : inclinaison {#linear-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-linear"
>title="Régression linéaire : inclinaison"
>abstract="Régression linéaire : Y = a X + b. Renvoie a."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION LINÉAIRE : PENTE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tableau]{type="Neutral"} Régression linéaire : Y = a X + b. Renvoie a.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Base logarithmique 10 {#log-base-ten}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log10"
>title="Base logarithmique 10"
>abstract="Renvoie le logarithme de base 10 d’un nombre."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL LOGARITHME BASE 10(mesure)]**


[!BADGE Ligne]{type="Neutral"} Renvoie le logarithme de base 10 d’un nombre.


| Argument | Description |
|---|---|
| mesure | Nombre réel positif pour lequel vous souhaitez obtenir le logarithme base 10. |


## Régression logarithmique : coefficient de corrélation {#log-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-log"
>title="Régression logarithmique : coefficient de corrélation"
>abstract="Régression logarithmique : Y = a ln(X) + b. Renvoie le coefficient de corrélation."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION LOGARITHMIQUE : COEFFICIENT DE CORRÉLATION(metric_X, metric_Y, include_zeros)]**

[!BADGE Tableau]{type="Neutral"} Régression logarithmique : Y = a ln(X) + b. Renvoie le coefficient de corrélation.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez corréler à metric_Y. |
| metric_Y | Mesure que vous souhaitez corréler à metric_X. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Régression logarithmique : ordonnée à l’origine {#log-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-log"
>title="Régression logarithmique : ordonnée à l’origine"
>abstract="Régression logarithmique : Y = a ln(X) + b. Renvoie b."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION LOGARITHMIQUE : INTERCEPTER(metric_X, metric_Y, include_zeros)]**

[!BADGE Tableau]{type="Neutral"} Régression logarithmique : Y = a ln(X) + b. Renvoie b.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Régression logarithmique : Y prédit {#log-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-log"
>title="Régression logarithmique : Y prédit"
>abstract="Régression logarithmique : Y = a ln(X) + b. Renvoie Y."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION LOGARITHMIQUE : PRÉDITE Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Ligne]{type="Neutral"} Régression logarithmique : Y = a ln(X) + b. Renvoie Y.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Régression logarithmique : inclinaison {#log-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-log"
>title="Régression logarithmique : inclinaison"
>abstract="Régression logarithmique : Y = a ln(X) + b. Renvoie a."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION LOGARITHMIQUE : PENTE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tableau]{type="Neutral"} Régression logarithmique : Y = a ln(X) + b. Renvoie a.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Logarithme népérien {#natural-log}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log"
>title="Logarithme népérien"
>abstract="Renvoie le logarithme népérien d’un nombre. Les logarithmes népériens sont basés sur la constante e (2,71828182845904). LN est l’inverse de la fonction EXP."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL LOGARITHME NÉPÉRIEN(mesure)]**

Renvoie le logarithme népérien d’un nombre. Les logarithmes népériens sont basés sur la constante e (2,71828182845904). LN est l’inverse de la fonction EXP.

| Argument | Description |
|---|---|
| mesure | Nombre réel positif pour lequel vous souhaitez obtenir le logarithme népérien. |



## Non {#not}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-not"
>title="Non"
>abstract="Négation en tant que booléen. La sortie est soit 0 (false) soit 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL NON(logique)]**

Négation en tant que booléen. La sortie est soit 0 (false) soit 1 (true).

| Argument | Description |
|---|---|
| logique | Obligatoire. Toute valeur ou expression qui peut être évaluée sur TRUE ou FALSE. |



## Non égal à {#not-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ne"
>title="Non égal à"
>abstract="Non égal à. La sortie est soit 0 (false) soit 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL DIFFÉRENT()]**


Non égal à. La sortie est soit 0 (false) soit 1 (true).


| Argument | Description |
|---|---|
| metric_X | Mesure à utiliser pour la comparaison. |
| metric_Y | Mesure à utiliser comme référence pour comparer. |

### Exemple

`Metric 1 != Metric 2`


## Ou {#or}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-or"
>title="Ou"
>abstract="Disjonction. Non égal à zéro est considéré comme true et égal à zéro est considéré comme false. La sortie est soit 0 (false) soit 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL OU(logical_test)]**


[!BADGE Ligne]{type="Neutral"} Disjonction. Non égal à zéro est considéré comme true et égal à zéro est considéré comme false. La sortie est soit 0 (false) soit 1 (true).


| Argument | Description |
|---|---|
| logical_test | Nécessite au moins un paramètre, mais peut prendre en charge n’importe quel nombre de paramètres. Toute valeur ou expression pouvant être évaluée avec TRUE ou FALSE |


>[!NOTE]
>
>0 (zéro) signifie False, et toute autre valeur est True.


## Pi {#pi}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pi"
>title="Pi"
>abstract="Renvoie Pi : 3,14159..."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

Renvoie Pi : 3,14159...


## Régression puissance : coefficient de corrélation {#power-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-power"
>title="Régression puissance : coefficient de corrélation"
>abstract="Régression puissance : Y = b X ^ a. Renvoie le coefficient de corrélation."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION DE PUISSANCE : COEFFICIENT DE CORRÉLATION(metric_X, metric_Y, include_zeros)]**

[!BADGE Tableau]{type="Neutral"} Régression de puissance : Y = b X ^ a. Renvoie le coefficient de corrélation.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez corréler à metric_Y. |
| metric_Y | Mesure que vous souhaitez corréler à metric_X. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Régression puissance : ordonnée à l’origine {#power-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-power"
>title="Régression puissance : ordonnée à l’origine"
>abstract="Régression puissance : Y = b X ^ a. Renvoie b."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION DE PUISSANCE : INTERCEPTER(metric_X, metric_Y, include_zeros)]**


[!BADGE Tableau]{type="Neutral"} Régression de puissance : Y = b X ^ a. Renvoie b.


| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Régression puissance : Y prédit {#power-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-power"
>title="Régression puissance : Y prédit"
>abstract="Régression puissance : Y = b X ^ a. Renvoie Y."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION DE PUISSANCE : PRÉDITE Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Ligne]{type="Neutral"} Régression de puissance : Y = b X ^ a. Renvoie Y.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Régression puissance : inclinaison {#power-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-power"
>title="Régression puissance : inclinaison"
>abstract="Régression puissance : Y = b X ^ a. Renvoie a."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION DE PUISSANCE : PENTE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tableau]{type="Neutral"} Régression de puissance : Y = b X ^ a. Renvoie a.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Régression quadratique : coefficient de corrélation {#quadratic-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-quadratic"
>title="Régression quadratique : coefficient de corrélation"
>abstract="Régression quadratique : Y = (a + bX) ^ 2. Renvoie le coefficient de corrélation."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION QUADRATIQUE : COEFFICIENT DE CORRÉLATION(metric_X, metric_Y, include_zeros)]**

[!BADGE Tableau]{type="Neutral"} Régression quadratique : Y = (a + bX) ^ 2. Renvoie le coefficient de corrélation.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez corréler à metric_Y. |
| metric_Y | Mesure que vous souhaitez corréler à metric_X. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |

## Régression quadratique : ordonnée à l’origine {#quadratic-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-quadratic"
>title="Régression quadratique : ordonnée à l’origine"
>abstract="Régression quadratique : Y = (a + bX) ^ 2. Renvoie a."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION QUADRATIQUE : INTERCEPTER(metric_X, metric_Y, include_zeros)]**

[!BADGE Tableau]{type="Neutral"} Régression quadratique : Y = (a + bX) ^ 2. Renvoie a.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Régression quadratique : Y prédit {#quadratic-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-quadratic"
>title="Régression quadratique : Y prédit"
>abstract="Régression quadratique : Y = (a + bX) ^ 2. Renvoie Y."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION QUADRATIQUE : PRÉDITE Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Ligne]{type="Neutral"} Régression quadratique : Y = (a + bX) ^ 2. Renvoie Y.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Régression quadratique : inclinaison {#quadratic-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-quadratic"
>title="Régression quadratique : inclinaison"
>abstract="Régression quadratique : Y = (a + bX) ^ 2. Renvoie b."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION QUADRATIQUE : PENTE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tableau]{type="Neutral"} Régression quadratique : Y = (a + bX) ^ 2. Renvoie b.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Régression réciproque : coefficient de corrélation {#reciprocal-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-reciprocal"
>title="Régression réciproque : coefficient de corrélation"
>abstract="Régression réciproque : Y = a + b X ^ -1. Renvoie le coefficient de corrélation."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION RÉCIPROQUE : COEFFICIENT DE CORRÉLATION(metric_X, metric_Y, include_zeros)]**

[!BADGE Tableau]{type="Neutral"} Régression réciproque : Y = a + b X ^ -1. Renvoie le coefficient de corrélation.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez corréler à metric_Y. |
| metric_Y | Mesure que vous souhaitez corréler à metric_X. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Régression réciproque : ordonnée à l’origine {#reciprocal-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-reciprocal"
>title="Régression réciproque : ordonnée à l’origine"
>abstract="Régression réciproque : Y = a + b X ^ -1. Renvoie a."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION RÉCIPROQUE : INTERCEPTER(metric_X, metric_Y, include_zeros)]**

[!BADGE Tableau]{type="Neutral"} Régression réciproque : Y = a + b X ^ -1. Renvoie a.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Régression réciproque : Y prédit {#reciprocal-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-reciprocal"
>title="Régression réciproque : Y prédit"
>abstract="Régression réciproque : Y = a + b X ^ -1. Renvoie Y."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION RÉCIPROQUE : PRÉDITE Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Ligne]{type="Neutral"} Régression réciproque : Y = a + b X ^ -1. Renvoie Y.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Régression réciproque : inclinaison {#reciprocal-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-reciprocal"
>title="Régression réciproque : inclinaison"
>abstract="Régression réciproque : Y = a + b X ^ -1. Renvoie b."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL RÉGRESSION RÉCIPROQUE : PENTE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tableau]{type="Neutral"} Régression réciproque : Y = a + b X ^ -1. Renvoie b.

| Argument | Description |
|---|---|
| metric_X | Mesure que vous souhaitez désigner comme données dépendantes. |
| metric_Y | Mesure que vous souhaitez désigner comme données indépendantes. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |



## Variance de l’échantillon

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-variance-estimate"
>title="Variance de l’échantillon"
>abstract="Calcule une estimation de la variance de l’échantillon à l’aide de la formule (sum(metric^2) / (N - 1)) - (sum(metric))^2/(N*(N-1)). où N est le nombre du conteneur de normalisation. <br/>Ceci est utilisé dans le cadre des calculs de confiance *valides à tout moment*. En règle générale, cette fonction n’est pas utile seule, mais elle peut être utilisée pour vérifier les calculs ou pour effectuer des calculs de confiance *manuellement*."

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE D’ÉCHANTILLONNAGE(conteneur-normalisation, mesure-succès)]**

Calcule une estimation de la variance d’échantillonnage.

| Argument | Description |
| --- | --- |
| conteneur-normalisation | La base (Personnes, Sessions ou Événements) sur laquelle un test est exécuté. |
| mesure-succès | La mesure ou les mesures avec lesquelles une personne compare des variantes. |

<!-- markdownlint-enable MD034 -->



## Sinus {#sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sin"
>title="Sinus"
>abstract="Renvoie le sinus de l’angle donné. Si l’angle est en degrés, multipliez l’angle par PI()/180."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL SINUS(mesure)]**


[!BADGE Ligne]{type="Neutral"} Renvoie le sinus de l’angle donné. Si l’angle est en degrés, multipliez l’angle par PI()/180.


| Argument | Description |
|---|---|
| mesure | Angle en radians pour lequel vous souhaitez obtenir le sinus. |




## Score normalisé {#t-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-score"
>title="Score normalisé"
>abstract="Écart par rapport à la [MOYENNE](cm-functions.md#mean), divisé par l’écart type. Alias pour [Score centré](#z-score)."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL SCORE NORMALISÉ(mesure, include_zeros)]**

Écart par rapport à la [MOYENNE](cm-functions.md#mean), divisé par l’écart type. Alias pour [Score centré](#z-score).

| Argument | Description |
|---|---|
| mesure | Mesure pour laquelle vous souhaitez obtenir le score normalisé. |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |


## Test en t {#t-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-test"
>title="Test en t"
>abstract="Exécute un test t m-latéral avec un score-t de x et n degrés de liberté."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL TEST EN T(mesure, degrés, queues)]**

Exécute un test t m-latéral avec un score-t de x et n degrés de liberté.

| Argument | Description |
|---|---|
| mesure | Mesure sur laquelle vous souhaitez effectuer un test en t. |
| degrees | Degrés de liberté |
| queues | Longueur de la queue à utiliser pour effectuer le test en t |

### Détails

La signature est TEST EN T(mesure, degrés, queues). En dessous, il appelle simplement ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)**. Cette fonction est similaire à la fonction **[TEST Z](#z-test)**, qui exécute ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)**.

- ***m*** est le nombre de queues.
- ***n*** représente les degrés de liberté et doit être un nombre constant pour l’ensemble du rapport, c’est-à-dire qu’il ne change pas ligne par ligne.
- ***X*** est la statistique du test en t. Il s’agira généralement d’une formule (zscore **[SCORE CENTRÉ](#z-score)**, par exemple) basée sur une mesure et évaluée sur chaque ligne.

La valeur renvoyée est la probabilité de voir la statistique de test x, étant donné les degrés de liberté et le nombre de queues.

### Exemples

1. Utilisez la fonction pour trouver des valeurs aberrantes :

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. Combinez la fonction à **[SI](#if)** pour ignorer les taux de rebond très élevés ou très bas, et comptabiliser les sessions dans tous les autres cas :

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```



## Tangente {#tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tan"
>title="Tangente"
>abstract="Renvoie la tangente de l’angle donné. Si l’angle est en degrés, multipliez l’angle par PI()/180."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENTE(mesure)]**

Renvoie la tangente de l’angle donné. Si l’angle est en degrés, multipliez l’angle par PI()/180.

| Argument | Description |
|---|---|
| mesure | Angle en radians pour lequel vous souhaitez obtenir la tangente. |



## Score centré {#z-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-score"
>title="Score centré"
>abstract="Écart par rapport à la moyenne divisé par l’écart-type."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL SCORE CENTRÉ(mesure, include_zeros)]**

[!BADGE Ligne]{type="Neutral"} Écart par rapport à la moyenne divisé par l’écart-type.

| Argument | Description |
|---|---|
| mesure | Mesure pour laquelle vous souhaitez obtenir le score centré/ |
| include_zeros | Inclut ou non des valeurs nulles dans les calculs. |

Un score centré réduit de 0 (zéro) signifie que le score est le même que la moyenne. Un score centré réduit peut être positif ou négatif, indiquant s’il est au-dessus ou en-dessous de la moyenne et par quel nombre d’écarts types.

L’équation pour le score centré réduit est la suivante :

![](assets/z_score.png)

où ***[!DNL x]*** est le score brut, ***[!DNL μ]*** la moyenne de la population et ***[!DNL σ]*** l’écart type de la population.

>[!NOTE]
>
>***[!DNL μ]*** (mu) et ***[!DNL σ]*** (sigma) sont automatiquement calculés à partir de la mesure.



## Test Z {#z-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-test"
>title="Test Z"
>abstract="Exécute un test z n-latéral avec un score-z de x."

<!-- markdownlint-enable MD034 -->

![Effet](/help/assets/icons/Effect.svg) **[!UICONTROL TEST Z(metric_tails)]**

Exécute un test z n-latéral avec un score-z de x.

| Argument | Description |
|---|---|
| mesure | Mesure sur laquelle vous souhaitez effectuer un test Z. |
| queues | Longueur de la queue à utiliser pour effectuer le test Z |

>[!NOTE]
>
>Présume que les valeurs sont distribuées normalement.




<!--



## AND

Returns the value of its argument. Use NOT to make sure that a value is not equal to one particular value.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
AND(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Approximate Count Distinct (dimension)

Returns the approximated distinct count of dimension items for the selected dimension. The function uses the HyperLogLog (HLL) method of approximating distinct counts.&nbsp; It is configured to guarantee the value is within 5% of the actual value 95% of the time.

```
Approximate Count Distinct (dimension)
```

|  Argument  |  |
|---|---|
|  *dimension* | The dimension for which you want the approximate distinct item count.  |

### Example Use Case

Approximate Count Distinct (customer ID eVar) is a common use case for this function.

Definition for a new 'Approximate Customers' calculated metric:

![Approximate county distinct new dimension definition showing Customer ID (eVar1)](assets/approx-count-distinct.png)

This is how the "Approximate Customers" metric could be used in reporting:

![Freeform Table showing Unique Visitors and Approximate Customers ](assets/approx-customers.png)

### Comparing Count Functions

Approximate Count Distinct() is an improvement over Count() and RowCount() functions because the metric created can be used in any dimensional report to render an approximated count of items for a separate dimension. For example, a count of customer IDs used in a Mobile Device Type report.

This function will be marginally less accurate than Count() and RowCount() because it uses the HLL method, whereas Count() and RowCount() are exact counts.

## Arc Cosine (Row)

Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).

```
ACOS(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Sine (Row)

Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).

```
ASIN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Tangent (Row)

Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).

```
ATAN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Exponential Regression: Predicted Y (Row)

Calculates the predicted y-values (metric_Y), given the known x-values (metric_X) using the "least squares" method for calculating the line of best fit based on .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Cdf-T

Returns the percentage of values in a student's t-distribution with n degrees of freedom that have a z-score less than x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returns the percentage of values in a normal distribution that have a z-score less than x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499

```

## Exponential Regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Exponential Regression: Slope (Table)

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Floor (Row)

Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric you want to round.  |

## Greater Than

Returns items whose numeric count is greater than the value entered.

## Greater Than or Equal

Returns items whose numeric count is greater than or equal to the value entered.

## Hyperbolic Cosine (Row)

Returns the hyperbolic cosine of a number.

```
COSH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic cosine.  |

## Hyperbolic Sine (Row)

Returns the hyperbolic sine of a number.

```
SINH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic sine.  |

## Hyperbolic Tangent (Row)

Returns the hyperbolic tangent of a number.

```
TANH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic tanget.  |

## IF (Row)

The IF function returns one value if a condition you specify evaluates to TRUE, and another value if that condition evaluates to FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

|  Argument  | Description  |
|---|---|
|  *logical_test* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.)  |
|  *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.)  |

## Less Than

Returns items whose numeric count is less than the value entered.

## Less Than or Equal

Returns items whose numeric count is less than or equal to the value entered.

## Lift

Returns the Lift a particular variant had in conversions over a control variant. It is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage. 

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Description |
| --- | --- |
| Normalizing Container | The basis (People, Sessions, or Events) on which a test will be run. |
| Success Metric | The metric or metrics that a user is comparing variants with. |
| Control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |

{style="table-layout:auto"}

## Linear regression_ Correlation Coefficient

Y = a X + b. Returns the correlation coefficient

## Linear regression_ Intercept

Y = a X + b. Returns b.

## Linear regression_ Predicted Y

Y = a X + b. Returns Y.

## Linear regression_ Slope

Y = a X + b. Returns a.

## Log Base 10 (Row)

Returns the base-10 logarithm of a number.

```
LOG10(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the base-10 logarithm.  |

## Log regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the CORREL equation.

```
CORREL.LOG(metric_X,metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Log regression: Intercept (Table)

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the INTERCEPT equation.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log Regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. It is calculated using the ESTIMATE equation.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. The [!DNL a] values correspond to each x value, and [!DNL b] is a constant value.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the SLOPE equation.

```
SLOPE.LOG(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the independent data.  |

## Natural Log

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the natural logarithm.  |

## NOT

Returns 1 if the number is 0 or returns 0 if another number.

```
NOT(logical)
```

|  Argument  | Description  |
|---|---|
|  *logical* | Required. A value or expression that can be evaluated to TRUE or FALSE.  |

Using NOT requires knowing if the expressions (<, >, =, <> , etc.) return 0 or 1 values.

## Not equal

Returns all items that do not contain the exact match of the value entered.

## Or (Row)

Returns TRUE if any argument is TRUE, or returns FALSE if all arguments are FALSE.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
OR(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Pi

Returns the constant PI, 3.14159265358979, accurate to 15 digits.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Power regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Quadratic regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Reciprocal regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Sine (Row)

Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
SIN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the sine.  |

## T-Score

Alias for Z-Score, namely the deviation from the mean divided by the standard deviation

## T-Test

Performs an m-tailed t-test with t-score of col and n degrees of freedom.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent

Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
TAN (metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the tangent.  |

## Z-Score (Row)

Returns the Z-score, or normal score, based upon a normal distribution. The Z-score is the number of standard deviations an observation is from the mean. A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.

Z-score(metric)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Returns the value of its first non-zero argument. </p> </td>
  </tr>
 </tbody>
</table>

## Z-Test

Performs an n-tailed Z-test with Z-score of A.

Returns the probability that the current row could be seen by chance in the column.

>[!NOTE]
>
>Assumes that the values are normally distributed.

-->