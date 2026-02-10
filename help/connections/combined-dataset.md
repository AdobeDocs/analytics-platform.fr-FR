---
title: Jeux De Données D’Événements Combinés
description: Découvrez comment Customer Journey Analytics crée une connexion en combinant des jeux de données.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 33%

---


# Jeu de données d’événements combinés

Lorsque vous créez une connexion, Customer Journey Analytics combine tous les jeux de données d’événement en un seul jeu de données. Ce jeu de données d’événement combiné est utilisé par Customer Journey Analytics pour la création de rapports (ainsi que les jeux de données de profil et de recherche). Lorsque vous incluez plusieurs jeux de données d’événements dans une connexion :

* Les données des champs des jeux de données basés sur le **même chemin de schéma** sont fusionnées en une seule colonne dans le jeu de données combiné.
* La colonne ID de personne , spécifiée pour chaque jeu de données, est fusionnée en une seule colonne dans le jeu de données combiné, **quel que soit leur nom**. Cette colonne est la base de l’identification des personnes uniques dans Customer Journey Analytics.
* Les lignes sont traitées selon l’horodatage.
* Les événements sont résolus au niveau de la milliseconde.

## Exemple

Examinez l’exemple suivant. Vous disposez de deux jeux de données d’événements, chacun avec des champs différents contenant des données différentes.

>[!NOTE]
>
>Adobe Experience Platform stocke généralement une date et une heure en millisecondes UNIX®. Pour la lisibilité dans cet exemple, la date et l’heure sont utilisées.

| example_id | timestamp | string_color | string_animal | metric_a |
| --- | --- | --- | --- | ---: |
| user_310 | 1 Jan 7:02 | Rouge | Renard | |
| user_310 | 1 Jan 7:04 | | | 2 |
| user_310 | 1 Jan 7:08 | Bleu | | 3 |
| user_847 | 2 Jan 12:31 PM | | Tortue | 4 |
| user_847 | 2 Jan 12:44 PM | | | 2 |

| différent_id | timestamp | string_color | string_shape | metric_b |
| --- | --- | --- | --- | ---: |
| user_847 | 2 Jan 12:26 PM | Jaune | Cercle | 8,5 |
| user_847 | 2 Jan 13:01 | Rouge | | |
| alternateid_656 | 2 janv. 8:58 PM | Rouge | Square | 4,2 |
| alternateid_656 | 2 Jan 9:03 PM | | Triangle | 3,1 |

Lorsque vous créez une connexion à l’aide de ces deux jeux de données d’événements et que vous avez identifié

* `example_id` comme ID de personne pour le premier jeu de données ; et
* `different_id` comme ID de personne pour le deuxième jeu de données,

le jeu de données combiné suivant est utilisé pour la création de rapports.

| identifiant | timestamp | string_color | string_animal | string_shape | metric_a | metric_b |
| --- | --- | --- | --- | --- | ---: | ---: |
| user_310 | 1 Jan 7:02 | Rouge | Renard | | | |
| user_310 | 1 Jan 7:04 | | | | 2 | |
| user_310 | 1 Jan 7:08 | Bleu | | | 3 | |
| user_847 | 2 Jan 12:26 PM | Jaune | | Cercle | | 8,5 |
| user_847 | 2 Jan 12:31 PM | | Tortue | | 4 | |
| user_847 | 2 Jan 12:44 PM | | | | 2 | |
| user_847 | 2 Jan 13:01 | Rouge | | | | |
| alternateid_656 | 2 janv. 8:58 PM | Rouge | | Square | | 4,2 |
| alternateid_656 | 2 Jan 9:03 PM | | | Triangle | | 3,1 |

Pour illustrer l’importance des chemins de schéma, considérez ce scénario. Dans le premier jeu de données, `string_color` est basé sur le chemin de schéma `_experience.whatever.string_color` et dans le second jeu de données sur le chemin de schéma `_experience.somethingelse.string_color`. Dans ce scénario, les données ne sont **pas** fusionnées en une colonne dans le jeu de données combiné résultant. Au lieu de cela, le résultat se compose de deux colonnes `string_color` dans le jeu de données combiné :

| identifiant | timestamp | _expérience.<br/>peu importe.<br/>string_color | _expérience.<br/> autre chose.<br/>string_color | string_animal | string_shape | metric_a | metric_b |
|---|---|---|---|---|---|---:|---:|
| user_310 | 1 Jan 7:02 | Rouge | | Renard | | | |
| user_310 | 1 Jan 7:04 | | | | | 2 | |
| user_310 | 1 Jan 7:08 | Bleu | | | | 3 | |
| user_847 | 2 Jan 12:26 PM | | Jaune | | Cercle | | 8,5 |
| user_847 | 2 Jan 12:31 PM | | | Tortue |  | 4 | |
| user_847 | 2 Jan 12:44 PM | | | | | 2 | |
| user_847 | 2 Jan 13:01 | | Rouge | | | | |
| alternateid_656 | 2 janv. 8:58 PM | | Rouge | | Square | | 4,2 |
| alternateid_656 | 2 Jan 9:03 PM | | | | Triangle | | 3,1 |

Ce jeu de données d’événements combiné est utilisé dans les rapports. Peu importe le jeu de données d’où provient une ligne. Customer Journey Analytics traite toutes les données comme si elles se trouvaient dans le même jeu de données. Si un ID de personne correspondant apparaît dans les deux jeux de données, ils sont considérés comme la même personne unique. Si un ID de personne correspondant apparaît dans les deux jeux de données avec un horodatage dans les 30 minutes, il est considéré comme faisant partie de la même session. Les champs ayant des chemins de schéma identiques sont fusionnés.

Ce concept s’applique également à l’attribution. Peu importe de quel jeu de données provient une certaine ligne ; l’attribution fonctionne exactement comme si tous les événements provenaient d’un seul jeu de données. Utilisons les tableaux ci-dessus comme exemple :

Si votre connexion incluait uniquement le premier tableau et non le second, l’extraction d’un rapport à l’aide de la dimension `string_color` et de la mesure `metric_a` à l’aide de l’attribution « Dernière touche » afficherait :

| string_color | metric_a |
| --- | ---: |
| Non spécifié | 6 |
| Bleu | 3 |
| Rouge | 2 |

Cependant, si vous avez inclus les deux tableaux dans votre connexion, l’attribution change car `user_847` se trouve dans les deux jeux de données. Une ligne du deuxième jeu de données attribue `metric_a` à « Jaune » alors qu’elles n’étaient pas spécifiées auparavant :

| string_color | metric_a |
| --- | ---: |
| Jaune | 6 |
| Bleu | 3 |
| Rouge | 2 |

>[!NOTE]
>
>Si un champ fusionné est une clé de recherche pour un jeu de données d’événement dans la connexion, le jeu de données de recherche associé enrichit **toutes** les valeurs de ce champ. Peu importe de quel jeu de données d’événement provient une ligne, car la relation de recherche est associée au chemin d’accès au schéma partagé.

## Analyse cross-canal

Le niveau suivant de combinaison des jeux de données est l’analyse cross-canal, où les jeux de données de différents canaux sont combinés en fonction d’un identifiant commun (ID de personne). L’analyse cross-canal peut bénéficier d’une fonctionnalité d’assemblage, vous permettant de recréer l’ID de personne d’un jeu de données afin que le jeu de données soit correctement mis à jour et que vous puissiez combiner plusieurs jeux de données de manière transparente. L’assemblage examine les données utilisateur des sessions authentifiées et non authentifiées afin de générer un identifiant assemblé.

L’analyse cross-canal vous permet de répondre à des questions telles que :

* Combien de personnes commencent leur expérience sur un canal, puis la terminent sur un autre ?
* Combien de personnes interagissent avec ma marque ? Combien de types d’appareils utilisent-elles ? Comment se superposent-elles ?
* À quelle fréquence les utilisateurs commencent-ils une tâche sur un appareil mobile, puis passent-ils ensuite à un PC de bureau pour terminer la tâche ? Les clics publicitaires de la campagne qui arrivent sur un appareil entraînent-ils une conversion ailleurs ?
* Comment ma compréhension de l’efficacité des campagnes change-t-elle si je prends en compte les parcours entre appareils ? Comment mon analyse d’entonnoir change-t-elle ?
* Quels sont les chemins les plus courants empruntés par les utilisateurs d’un appareil à l’autre ? Où abandonnent-ils ? Où réussissent-ils ?
* En quoi le comportement des utilisateurs ayant plusieurs appareils diffère-t-il de celui des utilisateurs disposant d’un seul appareil ?


Pour plus d’informations sur l’analyse cross-canal, consultez le cas d’utilisation spécifique :

* [Analyse cross-canal](../use-cases/cross-channel/cross-channel.md)

Pour plus d’informations sur la fonctionnalité de groupement, rendez-vous sur :

* [Vue d’ensemble du groupement](/help/stitching/overview.md)
* [Questions fréquentes](/help/stitching/faq.md)

