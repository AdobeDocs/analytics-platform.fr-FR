---
title: Dimensions avec une cardinalité très élevée en Customer Journey Analytics
description: Décrit les meilleures pratiques relatives aux dimensions à cardinalité élevée dans le Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 9af5c74164462851ac4a6cbc4764569789f677fc
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 0%

---


# Dimensions à très grande cardinalité

Le Customer Journey Analytics (CJA) ne limite pas le nombre de valeurs uniques ou d’éléments de dimension pouvant faire l’objet d’un rapport dans une seule dimension. Cependant, dans certaines circonstances, les dimensions présentant un très grand nombre d&#39;éléments uniques, également appelés dimensions à cardinalité élevée, peuvent avoir un impact sur ce sur quoi on peut faire rapport.

## Limites

En fonction du nombre de événements d’une connexion CJA spécifique, les deux limitations suivantes peuvent survenir en association avec des dimensions à cardinalité élevée :

### 1. Le décompte des lignes peut ne pas être précisément déclaré

Le décompte des lignes selon des dimensions de cardinalité élevée peut ne pas être précisément signalé. Dans ce cas, les tableaux à structure libre fourniront l’indication suivante :

![](assets/high-cardinality.png)

### 2. Les mesures calculées peuvent utiliser des estimations pour certaines fonctions et pour l&#39;ordre de tri

Lorsqu’elles sont utilisées avec des dimensions fortement cardinales, certaines fonctions de mesure calculée peuvent renvoyer des estimations, notamment : Nombre maximum de colonnes, Nombre minimum de colonnes, Nombre de lignes, Moyenne, Moyenne, Percentile, Quartile, Écart standard, Variance, Fonctions de régression et Fonctions T et Z.

En outre, le tri d’une colonne de tableau à l’aide d’une mesure calculée peut être basé sur une estimation et ne reflète pas toujours l’ordre de tri exact. Un message d&#39;avertissement s&#39;affiche pour vous avertir que des estimations ont peut-être été utilisées.

Gardez à l’esprit que même si les mesures calculées peuvent parfois renvoyer des estimations, les totaux des colonnes sont toujours exacts et ne sont jamais basés sur des estimations. De même, lorsque vous utilisez des mesures standard, les estimations ne sont jamais utilisées et reflètent toujours les ordres de tri exacts.

### Lorsque toutes les valeurs de dimension sont prises en compte

Même si certaines mesures calculées et le nombre de lignes de dimension sont limités, gardez à l’esprit que les fonctionnalités suivantes tiennent toujours compte de toutes les valeurs uniques dans une dimension, qu’une dimension soit très cardinale ou non :

* Attribution des mesures et attribution des dimensions
* Recherches d’éléments de ligne appliquées à un tableau à structure libre
* Filtres utilisant des dimensions ou des éléments de dimension
* Fonction distincte du nombre approximatif dans les mesures calculées
* Logique Inclure/Exclure appliquée à une mesure ou dimension dans une Vue de données
* Jeu de données de recherche ajouté à une connexion

## Recommandations relatives à l’utilisation de dimensions cardinales élevées

Afin d’éliminer les avertissements ou les estimations qui peuvent survenir lors de l’utilisation de dimensions présentant une cardinalité élevée, nous vous recommandons de réduire le nombre de lignes prises en compte dans votre rapport en utilisant l’une des méthodes suivantes :

* Ajoutez un filtre sur la colonne ou le panneau concerné.
* Appliquez une recherche à votre tableau à structure libre.
* Appliquez une ventilation aux lignes d’intérêt ou utilisez la dimension fortement cardinale comme dimension de ventilation.
* Ajoutez inclure/exclure des critères à la configuration de la Vue de données de la dimension afin de réduire le nombre de valeurs uniques présentes dans la dimension.

L’utilisation de ces techniques peut souvent éliminer les estimations ou avertissements indésirables que vous rencontrez lors de l’utilisation de dimensions cardinales élevées.
