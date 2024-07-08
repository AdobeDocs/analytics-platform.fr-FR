---
title: Jeu de données d’événements combinés
description: Découvrez comment Customer Journey Analytics crée une connexion en combinant des jeux de données.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 3389c141105ff71ed26abe4384fe3bb930448d43
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 35%

---


# Jeu de données d’événements combinés

Lorsque vous créez une connexion, Customer Journey Analytics combine tous les jeux de données d’événement en un seul jeu de données. Ce jeu de données d’événement combiné est utilisé par Customer Journey Analytics pour la création de rapports (ainsi que les jeux de données de profil et de recherche). Lorsque vous incluez plusieurs jeux de données d’événement dans une connexion :

* Les données des champs des jeux de données en fonction de la variable **même chemin de schéma** sont fusionnés en une seule colonne dans le jeu de données combiné.
* La colonne ID de personne, spécifiée pour chaque jeu de données, est fusionnée en une seule colonne dans le jeu de données combiné, **quel que soit leur nom**. Cette colonne est le fondement de l’identification des personnes uniques en Customer Journey Analytics.
* Les lignes sont traitées selon l’horodatage.
* Les événements sont résolus au niveau de la milliseconde.

## Exemple

Examinez l’exemple suivant. Vous disposez de deux jeux de données d’événements, chacun avec des champs différents contenant des données différentes.

>[!NOTE]
>
>Adobe Experience Platform stocke généralement un horodatage dans UNIX® millisecondes. Pour des raisons de lisibilité dans cet exemple, la date et l’heure sont utilisées.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | |
| `user_310` | `1 Jan 7:04 AM` | | | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | `3` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` | | | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | `Triangle` | `3.1` |

Lorsque vous créez une connexion à l’aide de ces deux jeux de données d’événement et que vous avez identifié

* `example_id` comme ID de personne pour le premier jeu de données, et
* `different_id` comme ID de personne pour le deuxième jeu de données,

le jeu de données combiné suivant est utilisé pour la création de rapports.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | | | |
| `user_310` | `1 Jan 7:04 AM` | | | | `2` | |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | | `3` | |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | | `Circle` | | `8.5` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | | `4` | |
| `user_847` | `2 Jan 12:44 PM` | | | | `2` | |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | | `Square` | | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | | `Triangle` | | `3.1` |

Pour illustrer l’importance des chemins de schéma, prenez ce scénario en compte. Dans le premier jeu de données, `string_color` est basé sur le chemin du schéma `_experience.whatever.string_color` et dans le deuxième jeu de données sur le chemin du schéma  `_experience.somethingelse.string_color`. Dans ce scénario, les données sont **not** fusionné dans une colonne du jeu de données combiné obtenu. Au lieu de cela, le résultat est deux : `string_color` colonnes du jeu de données combiné.

Ce jeu de données d’événements combiné est utilisé dans les rapports. Peu importe de quel jeu de données provient une ligne. Customer Journey Analytics traite toutes les données comme si elles se trouvaient dans le même jeu de données. Si un ID de personne correspondant apparaît dans les deux jeux de données, il est considéré comme la même personne unique. Si un ID de personne correspondant apparaît dans les deux jeux de données avec un horodatage dans les 30 minutes, il est considéré comme faisant partie de la même session. Les champs avec des chemins de schéma identiques sont fusionnés.

Ce concept s’applique également à l’attribution. Peu importe de quel jeu de données provient une certaine ligne ; l’attribution fonctionne exactement comme si tous les événements provenaient d’un seul jeu de données. Utilisons les tableaux ci-dessus comme exemple :

Si votre connexion incluait uniquement le premier tableau et non le second, l’extraction d’un rapport à l’aide de la dimension `string_color` et de la mesure `metric_a` à l’aide de l’attribution « Dernière touche » afficherait :

| string_color | metric_a |
| --- | --- |
| Non spécifié | 6 |
| Bleu | 3 |
| Rouge | 2 |

Cependant, si vous avez inclus les deux tableaux dans votre connexion, l’attribution change car `user_847` se trouve dans les deux jeux de données. Une ligne du deuxième jeu de données attribue `metric_a` à « Jaune » alors qu’elles n’étaient pas spécifiées auparavant :

| string_color | metric_a |
| --- | --- |
| Jaune | 6 |
| Bleu | 3 |
| Rouge | 2 |

>[!NOTE]
>
>Si un champ fusionné est une clé de recherche pour un jeu de données d’événement dans la connexion, le jeu de données de recherche associé s’enrichit. *all* de ce champ. Peu importe de quel jeu de données d’événement provient une ligne, car la relation de recherche est associée au chemin du schéma partagé.

## Analyse cross-canal

Le niveau suivant de combinaison des jeux de données est l’analyse cross-canal, où les jeux de données de différents canaux sont combinés, sur la base d’un identifiant commun (ID de personne). L’analyse cross-canal peut bénéficier de la fonctionnalité de regroupement, ce qui vous permet de recomposer l’ID de personne d’un jeu de données afin que le jeu de données soit correctement mis à jour pour permettre une combinaison transparente de plusieurs jeux de données. L’assemblage examine les données utilisateur des sessions authentifiées et non authentifiées pour générer un identifiant assemblé.

L’analyse cross-canal vous permet de répondre à des questions telles que :

* Combien de personnes commencent leur expérience sur un canal, puis la terminent sur un autre ?
* Combien de personnes interagissent avec ma marque ? Combien de types d’appareils utilisent-elles ? Comment se superposent-elles ?
* À quelle fréquence les utilisateurs commencent-ils une tâche sur un appareil mobile, puis passent-ils ensuite à un PC de bureau pour terminer la tâche ? Les clics publicitaires de campagne qui arrivent sur un appareil génèrent-ils une conversion ailleurs ?
* Comment ma compréhension de l’efficacité des campagnes change-t-elle si je considère les parcours entre appareils ? Comment mon analyse d’entonnoir change-t-elle ?
* Quels sont les chemins les plus courants empruntés par les utilisateurs d’un appareil à l’autre ? Où abandonnent-ils ? Où réussissent-ils ?
* En quoi le comportement des utilisateurs ayant plusieurs appareils diffère-t-il de celui des utilisateurs disposant d’un seul appareil ?


Pour plus d’informations sur l’analyse cross-canal, reportez-vous au cas pratique spécifique :

* [Analyse cross-canal](../use-cases/cross-channel/cross-channel.md)

Pour une discussion plus approfondie sur la fonctionnalité de groupement, accédez à :

* [Présentation de l’assemblage](/help/stitching/overview.md)
* [Questions fréquentes ](/help/stitching/faq.md)

