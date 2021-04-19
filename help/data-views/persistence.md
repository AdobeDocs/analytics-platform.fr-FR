---
title: Qu’est-ce que la persistance des dimensions dans le Customer Journey Analytics ?
description: La persistance des Dimensions est une combinaison d’attribution et d’expiration. Ensemble, ils déterminent comment et si les valeurs de dimension persistent d’un événement à l’autre.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
translation-type: tm+mt
source-git-commit: ffeada325825545ae0ab43f176e5d301cd1761ee
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 9%

---

# Persistance

La persistance des Dimensions est une combinaison d’attribution et d’expiration. Ensemble, ils déterminent comment et si les valeurs de dimension persistent d’un événement à l’autre. La persistance des Dimensions est configurée sur une dimension dans les Vues de données et est rétroactive et non destructive par rapport aux données auxquelles elle est appliquée. La persistance de la Dimension est une transformation de données immédiate appliquée à une dimension qui survient avant que le filtrage ou d’autres opérations d’analyse ne soient effectuées dans le rapports.

* Par défaut, aucune persistance n’est activée pour une valeur de dimension.
* Par défaut, lorsqu’un modèle d’allocation est activé pour une dimension, une expiration de [!UICONTROL Session] est utilisée.

## Attribution

L’affectation applique une transformation à la valeur sous-jacente que vous utilisez. Les modèles d’allocation pris en charge sont les suivants :

* Dernier
* Original
* Toutes

### [!UICONTROL Affectation la plus ] récente

L’attribution la plus récente conserve la valeur la plus récente (par horodatage) présente dans la dimension. Toutes les valeurs suivantes qui se produisent au sein d’une même session remplaceront la valeur précédemment persistante. Notez que si &quot;Traiter &quot;Aucune valeur&quot; comme valeur&quot; a été sélectionné sur cette dimension, les valeurs vides seront remplacées par &quot;Aucune valeur&quot; avant l’application de la persistance. Voici un exemple avant-après de l’attribution [!UICONTROL La plus récente] supposant qu’une [!UICONTROL session] soit utilisée pour l’expiration et que tous les événements se produisent dans une [!UICONTROL session] :

| Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
| --- | --- | --- | --- | --- | --- |
| valeurs de dataset |  | C | B |  | A |
| Affectation la plus récente |  | C | B | B | A |

### [!UICONTROL Affectation ] initiale

L’attribution d’origine conserve la valeur d’origine (par horodatage) présente dans la dimension pendant une période d’expiration. Voici un exemple avant-après de l’attribution [!UICONTROL Original] :

| Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
| --- | --- | --- | --- | --- | --- |
| valeurs de dataset |  | C | B |  | A |
| Affectation initiale |  | C | C | C | C |

###  Allocations

Cette attribution de dimension peut être appliquée à la fois aux dimensions basées sur des baies ou aux dimensions à une seule valeur. Il agit de la même manière que le modèle d’attribution [!UICONTROL Participation] pour les mesures. Une différence essentielle est que les dimensions avec l’attribution Tous peuvent être utilisées dans les définitions de filtre. Par exemple, supposons que le champ de chaîne comporte 5 événements, l’attribution étant définie sur &quot;Tous&quot; et l’expiration sur 5 minutes :

| Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
| --- | --- | --- | --- | --- | --- |
| valeurs de dataset | A | B | C |  | A |
| post-persistance | A | A,B | A, B, C | A, B, C | A, B, C |

## Expiration

[!UICONTROL L’] expiration vous permet de spécifier la fenêtre de persistance d’une dimension.

Il existe quatre façons d’expirer une valeur de dimension :

* Session (par défaut) : expire après une session donnée.
* Personne : expire à la fin de la fenêtre de votre rapports.
* Heure : Vous pouvez définir la valeur de dimension pour qu’elle expire après une période spécifiée (jusqu’à 90 jours). Cette option d’expiration est disponible uniquement pour les modèles d’attribution Original et Le plus récent. Lors de l’utilisation de l’expiration temporelle, les valeurs antérieures au début de la fenêtre de rapports (jusqu’à 90 jours) sont prises en compte.
* Mesure : Vous pouvez spécifier n’importe quelle mesure définie comme fin d’expiration pour cette dimension (par exemple, une mesure &quot;Achat&quot;). Cette expiration est uniquement disponible pour les modèles d’attribution Original et Le plus récent.

### Quelle est la différence entre l’attribution et l’attribution ?

**Affectation** : Considérez l’attribution comme une transformation des données vers la dimension. L’attribution se produit avant le filtrage. Si vous créez un filtre, il déclenchera la dimension transformée.

**Attribution** : Comment répartir le crédit d’une mesure sur la dimension à laquelle elle est appliquée ? L’attribution n’est pas une transformation de données, s’applique pendant l’agrégation des données et n’a aucune incidence sur les données incluses à l’aide d’un filtre.
