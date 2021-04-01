---
title: Qu’est-ce que la persistance des dimensions dans le Customer Journey Analytics ?
description: La persistance des Dimensions est une combinaison d’attribution et d’expiration. Ensemble, ils déterminent les valeurs de dimension qui persistent.
translation-type: tm+mt
source-git-commit: efe92e25229addadf57bff3f2ba73d831a3161ea
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 18%

---


# Persistance

La persistance des Dimensions est une combinaison d’attribution et d’expiration. Ensemble, ils déterminent les valeurs de dimension qui persistent. L’Adobe vous recommande vivement de discuter au sein de votre organisation de la manière dont plusieurs valeurs pour chaque dimension sont gérées (attribution) et de la manière dont les valeurs de dimension cessent d’être conservées (expiration).

* Par défaut, une valeur de dimension utilise ? allocation.
* Par défaut, une valeur de dimension utilise une expiration de [!UICONTROL Session].

## Attribution

L’affectation applique une transformation à la valeur sous-jacente que vous utilisez. Les modèles d’allocation pris en charge sont les suivants :

* Dernier
* Original
* Toutes
* Préconnu
* Dernier connu

### [!UICONTROL Affectation la plus ] récente

Voici un exemple avant-après de l’attribution [!UICONTROL la plus récente] :

| Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valeurs d’origine |  | C | B |  | A |
| Affectation la plus récente |  | C | B | B | A |

### [!UICONTROL Affectation ] initiale

Voici un exemple avant-après de l’attribution [!UICONTROL Original] :

| Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valeurs d’origine |  | C | B |  | A |
| Affectation initiale |  | C | C | C | C |

###  Allocations

Cette nouvelle attribution de dimension peut être appliquée à la fois aux dimensions basées sur des baies ou aux dimensions à une seule valeur. Il agit de la même manière que le modèle d’attribution [!UICONTROL Participation] pour les mesures. La différence est que les valeurs individuelles du champ peuvent expirer à différents moments. Par exemple, supposons que le champ de chaîne comporte 5 événements, l’attribution étant définie sur &quot;Tous&quot; et l’expiration sur 5 minutes. Nous nous attendons à ce que le comportement suivant soit :

| Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 3 | 2 | 1 | 6 | 7 |
| valeurs d’origine | A | B | C |  | A |
| post-persistance | A | A,B | A, B, C | B,C | A,C |

Notez que la valeur de A persiste jusqu’à ce qu’elle atteigne la limite de 5 min, tandis que B et C persistent dans Accès 4 car 5 minutes n’ont pas encore été passées pour ces valeurs. Notez que cette attribution créera une dimension à plusieurs valeurs à partir d’un champ à une seule valeur. Ce modèle doit également être pris en charge sur les dimensions basées sur les baies :

| Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valeurs d’origine | A, B | C | B,C |  | A |
| post-persistance | A, B | A, B, C | A, B, C | B,C | A, B, C |

### Affectations &quot;Première connue&quot; et &quot;Dernière connue&quot;

Ces deux nouveaux modèles d’allocation prennent la première ou la dernière valeur observée pour une dimension dans une plage de persistance spécifiée (session, personne ou période personnalisée avec recherche) et l’appliquent à tous les événements de la portée spécifiée. Exemple :

| Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valeurs d’origine |  | C | B |  | A |
| premier connu | C | C | C | C | C |
| dernier connu | A | A | A | A | A |

La première ou la dernière valeur connue peut être appliquée uniquement à une session ou à l’étendue de la personne (fenêtre de rapports) ou à une étendue personnalisée ou temporelle (essentiellement une plage de personnes avec une fenêtre de recherche ajoutée).

## Expiration

[!UICONTROL L’] expiration vous permet de spécifier la fenêtre de persistance d’une dimension.

Il existe quatre façons d’expirer une valeur de dimension :

* Session (par défaut) : expire après une session donnée.
* Personne: ?
* Heure : Vous pouvez définir la valeur de dimension pour qu’elle arrive à expiration après une période ou un événement spécifié.
* Mesure : Vous pouvez spécifier n’importe quelle mesure définie comme fin d’expiration pour cette dimension (par exemple, une mesure &quot;Achat&quot;).
* Personnalisé:

### Quelle est la différence entre l’attribution et l’attribution ?

**Affectation** : Considérez l’attribution comme une &quot;transformation des données&quot; de la dimension. L’allocation a lieu avant le filtrage. Si vous créez un filtre, il déclenchera la dimension transformée.

**Attribution** : Comment répartir le crédit d’une mesure sur la dimension à laquelle elle est appliquée ? L’attribution se produit après le filtrage.

