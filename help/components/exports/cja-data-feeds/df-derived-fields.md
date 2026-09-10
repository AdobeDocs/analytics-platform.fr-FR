---
title: Utilisation de champs dérivés dans les flux de données
description: Découvrez comment utiliser des champs dérivés dans les flux de données.
hide: true
feature: Components
source-git-commit: a9f53472d57a3a26004bd5ca583a43134bbdba7e
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 2%

---

# Utiliser des champs dérivés dans les flux de données

{{release-limited-testing}}

Vous pouvez effectuer des transformations de données sur vos données de flux de données à l’aide de [champs dérivés](/help/data-views/derived-fields/derived-fields.md).

De nombreuses fonctions de champ dérivé effectuent des transformations que vous pouvez également appliquer à l’aide de SQL, comme le remplacement de valeurs, la combinaison de champs ou la conversion du type de données d’un champ. Par conséquent, la méthode que vous choisissez est parfois une question de préférence.

## Champs dérivés par rapport à SQL

Le tableau suivant compare les avantages et les inconvénients de l’utilisation de champs dérivés ou de SQL.

| Méthode | Avantages | Inconvénients |
| --- | --- | --- |
| **Champs dérivés** | <ul><li>La même logique s’applique systématiquement dans Analysis Workspace et dans la sortie de flux de données, car les champs dérivés sont inclus en tant que composants dans votre schéma de flux de données, aux côtés des dimensions et des mesures standard.</li><li>Certaines transformations, en particulier celles qui dépendent d’un paramètre Portée ou qui analysent une URL, sont difficiles à répliquer dans SQL.</li></ul> | Ajoute une surcharge de traitement, qui peut affecter les performances de diffusion des flux de données.<!--Under a future usage-based pricing model, this could also add cost.--> |
| **SQL** | <ul><li>Non limité par les limites de fonction et d’opérateur qui s’appliquent aux champs dérivés.</li><li>N’a aucun effet sur les performances de diffusion des flux de données.</li></ul> | <ul><li>La logique ne s’applique pas à Analysis Workspace. Vous devez donc la dupliquer séparément à cet endroit.</li><li>Certaines transformations, en particulier celles qui dépendent d’un paramètre Portée ou qui analysent une URL, sont difficiles ou impossibles à répliquer.</li></ul> |

{style="table-layout:auto"}

## Fonctions de champ dérivé

Le tableau suivant décrit chaque fonction de champ dérivé, s’il convient le mieux à un champ dérivé ou à SQL, ainsi que les points à garder à l’esprit avant de l’utiliser.

| Fonction de champ dérivé | Difficulté à effectuer une réplication à l’aide de SQL | Ajustement optimal (champ dérivé ou SQL) | Considérations |
| --- | --- | --- | --- |
| [**Cas lorsque**](/help/data-views/derived-fields/derived-fields.md#casewhen)<br/> applique des conditions basées sur des critères d’un ou de plusieurs champs, puis définit la valeur de sortie en fonction de la condition qui correspond. | Facile à modérer | Soit | Reproductible dans SQL, mais en utilisant un champ dérivé, la même logique est appliquée de manière cohérente à la fois dans Analysis Workspace et dans la sortie du flux de données. Cela s’avère particulièrement utile lorsqu’un grand nombre de règles est impliqué, telles qu’une classification de canal marketing. |
| [**Classifier**](/help/data-views/derived-fields/derived-fields.md#classify)<br/> Définit un ensemble de valeurs qui sont remplacées par les valeurs correspondantes dans un nouveau champ dérivé. | Facile à modérer | Soit | Reproductible dans SQL, mais en utilisant un champ dérivé, la même logique est appliquée de manière cohérente à la fois dans Analysis Workspace et dans la sortie du flux de données. |
| [**Concaténer**](/help/data-views/derived-fields/derived-fields.md#concatenate)<br/> Combine les valeurs de champ en un nouveau champ dérivé unique à l’aide de délimiteurs définis (par exemple, le nom de page et le canal marketing). | Facile à modérer | Soit | Reflète la fonctionnalité d’ajout de plusieurs colonnes de dimension à un tableau à structure libre, qui se limite à l’exportation du tableau complet. Un champ dérivé rend une sortie similaire disponible dans un flux de données. |
| [**Date Maths**](/help/data-views/derived-fields/derived-fields.md#datemath)<br/> renvoie la différence entre deux champs de date ou de date-heure (par exemple, les jours entre une date de réservation et une date d’enregistrement), avec une portée d’événement, de session ou de personne. | Difficile | Champs dérivés | Complexe à répliquer en SQL. Cette fonction dépend d’un paramètre Portée . Pour plus d’informations, voir [Comment les paramètres Portée dans les fonctions affectent les flux de données](#scope-settings). |
| [**Dédupliquer**](/help/data-views/derived-fields/derived-fields.md#dedup)<br/> Empêche de compter une valeur plusieurs fois, avec une Portée de personne ou de session (par exemple, de dédupliquer un ID de confirmation de réservation). | Difficile | Champs dérivés | Cette fonction dépend d’un paramètre Portée . Pour plus d’informations, voir [Comment les paramètres Portée dans les fonctions affectent les flux de données](#scope-settings). |
| [**Profondeur**](/help/data-views/derived-fields/derived-fields.md#depth)<br/> renvoie la profondeur d’un champ, similaire à la dimension Profondeur de l’événement standard (par exemple, profondeur de recherche interne). | Difficile | Champs dérivés | Utilise la session comme étendue, et elle n’est pas configurable. <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> Le comportement du compteur lorsqu’une session s’étend sur une limite de diffusion de flux est toujours en cours de confirmation par l’ingénierie. Cette fonction dépend d’un paramètre Portée . Pour plus d’informations, voir [Comment les paramètres Portée dans les fonctions affectent les flux de données](#scope-settings). |
| [**Rechercher et remplacer**](/help/data-views/derived-fields/derived-fields.md#find-and-replace)<br/> Recherche toutes les valeurs d’un champ sélectionné et les remplace par une autre valeur. | Facile à modérer | Soit | Reproductible dans SQL, mais en utilisant un champ dérivé, la même logique est appliquée de manière cohérente à la fois dans Analysis Workspace et dans la sortie du flux de données. |
| [**Recherche**](/help/data-views/derived-fields/derived-fields.md#lookup)<br/> Recherche une valeur d’un jeu de données de recherche à l’aide d’une clé correspondante et la renvoie dans un nouveau champ dérivé. | Facile à modérer | Soit | SQL fonctionne si une table de recherche existe déjà. |
| [**Minuscules**](/help/data-views/derived-fields/derived-fields.md#lowercase)<br/> convertit les valeurs d’un champ en minuscules. | Facile à modérer | Soit | Reproductible dans SQL, mais en utilisant un champ dérivé, la même logique est appliquée de manière cohérente à la fois dans Analysis Workspace et dans la sortie du flux de données. |
| [**Mathématiques**](/help/data-views/derived-fields/derived-fields.md#math)<br/> applique des opérateurs mathématiques de base (ajouter, soustraire, multiplier, diviser ou élever à une puissance) aux champs numériques, évalués coup par coup. | Facile à modérer | Soit | Reproductible dans SQL, mais en utilisant un champ dérivé, la même logique est appliquée de manière cohérente à la fois dans Analysis Workspace et dans la sortie du flux de données. |
| [**Fusionner les champs**](/help/data-views/derived-fields/derived-fields.md#merge)<br/> Vérifie si le premier de deux champs ou plus a une valeur ; dans le cas contraire, utilise le champ suivant, etc. | Facile à modérer | Soit | Aucun |
| [**Suivant ou précédent**](/help/data-views/derived-fields/derived-fields.md#next-previous)<br/> résout la valeur suivante ou précédente d’un champ de tableau Visite ou Événement, avec une Portée de personne ou de session. | Difficile | Champs dérivés | Cette fonction dépend d’un paramètre Portée . Pour plus d’informations, voir [Comment les paramètres Portée dans les fonctions affectent les flux de données](#scope-settings). |
| [**Remplacement d’expression régulière**](/help/data-views/derived-fields/derived-fields.md#regex-replace)<br/> remplace une valeur d’un champ à l’aide d’une expression régulière. | Facile à modérer | Soit | Reproductible dans SQL, mais en utilisant un champ dérivé, la même logique est appliquée de manière cohérente à la fois dans Analysis Workspace et dans la sortie du flux de données. |
| [**Split**](/help/data-views/derived-fields/derived-fields.md#split)<br/> Split une valeur d’un champ en un nouveau champ dérivé (par exemple, en convertissant une liste délimitée en tableau). | Facile à modérer | Soit | Reproductible dans SQL, mais en utilisant un champ dérivé, la même logique est appliquée de manière cohérente à la fois dans Analysis Workspace et dans la sortie du flux de données. |
| [**Résumer**](/help/data-views/derived-fields/derived-fields.md#summarize)<br/> Applique des fonctions d’agrégation (telles que la somme, le nombre ou les plus courantes) à un champ, avec une portée d’événement, de session ou de personne. | Difficile | Champs dérivés | Cette fonction dépend d’un paramètre Portée . Pour plus d’informations, voir [Comment les paramètres Portée dans les fonctions affectent les flux de données](#scope-settings). |
| [**Rogner**](/help/data-views/derived-fields/derived-fields.md#trim)<br/> Rogne les espaces, les caractères spéciaux ou un nombre défini de caractères du début ou de la fin des valeurs d&#39;un champ. | Facile à modérer | Soit | Reproductible dans SQL, mais en utilisant un champ dérivé, la même logique est appliquée de manière cohérente à la fois dans Analysis Workspace et dans la sortie du flux de données. |
| [**Typecast**](/help/data-views/derived-fields/derived-fields.md#typecast)<br/> Modifie le type de données d’un champ afin de le rendre disponible pour des transformations supplémentaires. | Facile à modérer | Soit | Reproductible dans SQL, mais en utilisant un champ dérivé, la même logique est appliquée de manière cohérente à la fois dans Analysis Workspace et dans la sortie du flux de données. |
| [**Analyse d’URL**](/help/data-views/derived-fields/derived-fields.md#urlparse)<br/> analyse les parties d’une URL, y compris le protocole, l’hôte, le chemin, le paramètre de chaîne de requête ou la valeur de hachage. | Difficile | Champs dérivés | SQL nécessite une analyse de chaîne personnalisée pour extraire les mêmes composants. |

{style="table-layout:auto"}

### Comment les paramètres de portée dans les fonctions affectent-ils les flux de données ? {#scope-settings}

Les options [!UICONTROL **Mathématiques des dates**], [!UICONTROL **Dédupliquer**], [!UICONTROL **Suivant ou précédent**] et [!UICONTROL **Résumer**] dépendent chacune d’un paramètre [!UICONTROL **Portée**] d’événement, de session ou de personne (les options disponibles varient selon la fonction). [!UICONTROL **Depth**] ne comporte aucun champ d’étendue configurable, mais est intrinsèquement lié à la session, comme la dimension standard Profondeur de l’événement . Tout champ avec une portée écrit la même valeur sur chaque ligne de cette portée. Cette valeur dépend des données de la période de recherche en amont.
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

Comme la période de recherche en amont glisse vers l’avant avec chaque diffusion de flux de données, le même champ peut renvoyer une valeur différente sur une diffusion ultérieure, même pour les événements qui se sont déjà produits.

Le risque augmente avec la taille de la portée : la portée de la personne comporte plus de risque que la portée de la session, car l’historique d’une personne n’a pas de limite de temps naturelle au cours d’une exécution de flux.

## Modèles de fonction de champ dérivé

[Les modèles de fonction de champ dérivé](/help/data-views/derived-fields/derived-fields.md#templates) vous permettent de créer rapidement un champ dérivé pour un cas d’utilisation spécifique, comme la création de canaux marketing, la détection de robots ou l’extraction d’un paramètre UTM d’une URL. Étant donné qu’un modèle est créé à partir d’une chaîne de règles préconfigurées, son utilisation est presque toujours préférable à la reproduction de la même logique en SQL à partir de zéro.

Si un modèle inclut une fonction qui dépend d’un paramètre Portée , le modèle hérite de la mise en garde relative à la portée de cette fonction. Voir [Comment les paramètres Portée dans les fonctions affectent les flux de données](#scope-settings).

