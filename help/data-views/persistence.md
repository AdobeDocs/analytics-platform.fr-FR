---
title: Quʼest-ce que la persistance des dimensions dans Customer Journey Analytics ?
description: La persistance dʼune dimension varie selon les valeurs dʼattribution et dʼexpiration. Ensemble, elles déterminent si les valeurs des dimensions persistent ou non dʼun événement à lʼautre.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
translation-type: ht
source-git-commit: ffeada325825545ae0ab43f176e5d301cd1761ee
workflow-type: ht
source-wordcount: '574'
ht-degree: 100%

---

# Persistance

La persistance dʼune dimension varie selon les valeurs dʼattribution et dʼexpiration. Ensemble, elles déterminent si les valeurs des dimensions persistent dʼun événement à lʼautre. La persistance des dimensions est configurée sur une dimension dans les vues de données et est rétroactive et non destructive pour les données auxquelles elle est appliquée. La persistance des dimensions est une transformation immédiate des données appliquée à une dimension qui survient avant que le filtrage ou dʼautres opérations dʼanalyse ne soient effectués dans le compte rendu des performances.

* Par défaut, aucune persistance nʼest activée pour une valeur de dimension.
* Par défaut, lorsquʼun modèle dʼattribution est activé pour une dimension, une expiration de [!UICONTROL Session] est utilisée.

## Attribution

Lʼaffectation applique une transformation à la valeur sous-jacente que vous utilisez. Les modèles dʼattribution pris en charge sont les suivants :

* Dernier
* Original
* Toutes

### Affectation [!UICONTROL la plus récente]

Lʼaffectation la plus récente fera persister la valeur la plus récente (par horodatage) présente dans la dimension. Toutes les valeurs suivantes se produisant au sein dʼune même session remplaceront la valeur précédemment persistante. Remarquez que si « Traiter &quot;No Value&quot; comme valeur » a été sélectionné sur cette dimension, les valeurs vides seront remplacées par « No Value » avant lʼapplication de la persistance. Voici un exemple avant-après de lʼaffectation [!UICONTROL la plus récente], en supposant quʼune [!UICONTROL session] soit utilisée pour lʼexpiration et que tous les événements se produisent au sein dʼune [!UICONTROL session] :

| Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
| --- | --- | --- | --- | --- | --- |
| valeurs du jeu de données |  | C | B |  | A |
| Affectation la plus récente |  | C | B | B | A |

### Affectation [!UICONTROL dʼorigine]

Lʼaffectation dʼorigine fera persister la valeur initiale (par horodatage) présente dans la dimension pendant une période dʼexpiration. Voici un exemple avant-après de lʼaffectation [!UICONTROL dʼorigine] :

| Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
| --- | --- | --- | --- | --- | --- |
| valeurs du jeu de données |  | C | B |  | A |
| Affectation dʼorigine |  | C | C | C | C |

### Affectation [!UICONTROL Tous]

Cette affectation de dimension peut être appliquée à la fois aux dimensions basées sur des tableaux ou à une seule valeur. Elle agit de la même manière que le modèle dʼattribution de [!UICONTROL Participation] pour les mesures. Une différence essentielle est que les dimensions avec lʼaffectation Tous peuvent être utilisées dans les définitions de filtre. Par exemple, supposons que le champ de chaîne comporte 5 événements, lʼaffectation étant définie sur « Tous » et lʼexpiration sur 5 minutes :

| Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
| --- | --- | --- | --- | --- | --- |
| valeurs du jeu de données | A | B | C |  | A |
| post-persistance | A | A,B | A, B, C | A, B, C | A, B, C |

## Expiration

Lʼ[!UICONTROL expiration] permet de définir la période de persistance pour une dimension.

Il existe quatre façons de faire expirer une valeur de dimension :

* Session (par défaut) : expire après une session donnée.
* Personne : expire à la fin de votre intervalle de compte rendu des performances.
* Heure : vous pouvez définir la valeur de la dimension pour quʼelle expire après une période spécifiée (jusquʼà 90 jours). Cette option dʼexpiration est disponible uniquement pour les modèles dʼattribution d’origine et La plus récente. Lors de lʼutilisation de lʼexpiration basée sur le temps, les valeurs antérieures au début de votre intervalle de compte rendu des performances (jusquʼà 90 jours) sont prises en compte.
* Mesure : vous pouvez définir une des mesures définies comme fin dʼexpiration pour cette dimension (par exemple, une mesure « Achats »). Cette expiration est uniquement disponible pour les modèles dʼattribution d’origine et La plus récente.

### Quelle est la différence entre lʼaffectation et lʼattribution ?

**Affectation** : considérez lʼaffectation comme une transformation des données vers la dimension. Lʼaffectation se produit avant le filtrage. Si vous créez un filtre, il se basera sur la dimension transformée.

**Attribution** : comment répartir le crédit dʼune mesure à la dimension à laquelle elle est appliquée ? Lʼattribution nʼest pas une transformation de données, elle sʼapplique pendant lʼagrégation des données et nʼa pas dʼincidence sur les données incluses à lʼaide dʼun filtre.
