---
title: Jeux de données combinés
description: Découvrez comment CJA crée une connexion en combinant des jeux de données.
translation-type: tm+mt
source-git-commit: fa354af31237c4963ba0affa89652bfdeae45ea0
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 5%

---


# Jeux de données combinés

Lorsque vous créez une connexion, CJA combine tous les schémas et jeux de données en un seul jeu de données. Ce &quot;jeu de données combiné&quot; est ce que CJA utilise pour le rapports. Lorsque vous incluez plusieurs schémas ou jeux de données dans une connexion :

* Les Schémas sont combinés. Les champs de schéma de Duplicata sont fusionnés.
* La colonne &quot;Identifiant personnel&quot; de chaque jeu de données est fusionnée en une seule colonne, quel que soit leur nom. Cette colonne est le fondement de l&#39;identification des visiteurs uniques dans la MCJ.
* Les lignes sont traitées selon l’horodatage.

## Exemple

Examinez l&#39;exemple suivant. Vous disposez de deux jeux de données, chacun avec des champs différents contenant des données différentes.

>[!NOTE] Adobe Experience Platform stocke généralement l’horodatage en millisecondes Unix. Pour des raisons de lisibilité dans cet exemple, la date et l’heure sont utilisées.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |
| `user_310` | `1 Jan 7:04 AM` |  |  | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  | `3` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` |  |  | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  | `Triangle` | `3.1` |

Lorsque vous créez une connexion à l&#39;aide de ces deux jeux de données, le tableau suivant est utilisé pour le rapports.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |  |  |
| `user_310` | `1 Jan 7:04 AM` |  |  |  | `2` |  |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  |  | `3` |  |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` |  | `Circle` |  | `8.5` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` |  | `4` |  |
| `user_847` | `2 Jan 12:44 PM` |  |  |  | `2` |  |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` |  | `Square` |  | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  |  | `Triangle` |  | `3.1` |

Ce jeu de données combiné est utilisé dans le rapports. Peu importe de quel jeu de données provient une ligne ; CJA traite toutes les données comme si elles se trouvaient dans le même jeu de données. Si un ID de personne correspondant apparaît dans les deux jeux de données, il est considéré comme le même visiteur unique. Si un ID de personne correspondant apparaît dans les deux jeux de données avec un horodatage dans les 30 minutes, il est considéré comme faisant partie de la même session.

Ce concept s&#39;applique également à l&#39;attribution. Peu importe de quel jeu de données provient une ligne ; l’attribution fonctionne exactement comme si tous les événements provenaient d’un seul jeu de données. Utilisation des tableaux ci-dessus comme exemple :

Si votre connexion incluait uniquement le premier tableau et non le second, l’extraction d’un rapport à l’aide de la `string_color` dimension et de la `metric_a` mesure à l’aide de l’attribution Dernière touche présenterait :

| string_color | metric_a |
| --- | --- |
| Non spécifié | 6 |
| Bleu  | 3 |
| Rouge  | 2 |

Cependant, si vous avez inclus les deux tableaux dans votre connexion, l’attribution change car elle `user_847` se trouve dans les deux jeux de données. Une ligne du deuxième jeu de données s’attribue `metric_a` à &quot;Jaune&quot; où elles n’étaient pas spécifiées auparavant :

| string_color | metric_a |
| --- | --- |
| Jaune | 6 |
| Bleu  | 3 |
| Rouge  | 2 |
