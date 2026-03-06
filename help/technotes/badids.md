---
title: ID Customer Journey Analytics incorrects
description: Comprendre les BAVID (Bad ID) dans Customer Journey Analytics Découvrez comment identifier les Mauvais ID dans vos données, pourquoi ils affectent la création de rapports et comment enquêter sur l’exposition aux Mauvais ID dans vos connexions et la résoudre.
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: b7b2a1f3eb1c149caf65ab3e4321e4f4347695cc
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 0%

---


# ID incorrects

Cet article fournit du contexte sur les ID incorrects et sur la manière de détecter leur présence ou leur risque d’occurrence dans vos données à l’aide de Query Service.


>[!INFO]
>
>Les BAVID incorrects sont également appelés BAVID dans l’interface de Customer Journey Analytics (provenant de [Analytics BAVID](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16444)).
>

## Définition

Dans Customer Journey Analytics, un Bad ID est un identifiant qui fait partie de toutes les données définies dans une connexion :

* avec une valeur d’ID spécifique qui provient de
   * depuis un champ d’ID de personne (jeux de données non groupés), **ou**
   * à partir d’un champ d’ID persistant ou d’ID de personne (jeux de données activés pour le groupement),

  **et**
* concerne plus d’un million (1 000 000) d’événements dans les données de connexion (comptabilisés pour tous les jeux de données de la connexion), au cours d’un mois.

Lorsqu’une valeur d’ID est marquée comme ID incorrect, tous les événements futurs contenant cette valeur d’ID sont ignorés des données de connexion et n’apparaissent pas dans les rapports.

### Exemple

Un exemple de scénario avec des ID incorrects est la présence de valeurs personnalisées ou d’espace réservé dans le champ d’ID de personne (par exemple, `undefined` pour le trafic anonyme). Pour un jeu de données activé pour le groupement, cette situation peut avoir un impact encore plus important sur les données de rapport, car la qualité du groupement est probablement affectée. Pour résoudre ce problème, vous devrez peut-être effacer et réactiver la configuration du groupement, y compris la suppression des données historiques des jeux de données dans la connexion.


## Mesures

L’interface de connexion de Customer Journey Analytics offre des informations de mesure **[!UICONTROL ID incorrects]** à plusieurs endroits de l’interface.

* Vous pouvez voir **[!UICONTROL Mauvais ID]** (ou **[!UICONTROL BAVID]**) comme raisons possibles pour ignorer des enregistrements dans la boîte de dialogue **[!UICONTROL Vérifier les détails ignorés]**. Utilisez **[!UICONTROL Vérifier les détails]** (le cas échéant) ci-dessous **[!UICONTROL Enregistrements ignorés]** dans l’écran [détails d’une connexion](/help/connections/create-connection.md).
* Pour un jeu de données activé pour le groupement, l’[**[!UICONTROL Aperçu du jeu de données]**](/help/stitching/use-stitching-ui.md#bad-ids) affiche **[!UICONTROL ID incorrects]** dans le cadre des **[!UICONTROL mesures de groupement]**. Cette mesure peut vous aider à identifier les cas possibles de Mauvais ID. Toutefois, sachez que cette mesure est calculée sur la base d’un ensemble limité de données.

Reportez-vous à la section [&#x200B; Exposition des ID incorrects &#x200B;](#bad-ids-exposure) pour vous aider à identifier la présence d’ID incorrects pour un jeu de données que vous prévoyez d’utiliser dans une connexion (que le groupement soit activé ou non).


## Exposition

Pour examiner l’exposition aux ID incorrects pour un certain champ de jeu de données, pensez à effectuer la requête suivante dans Experience Platform Query Service. Vérifiez les principales valeurs d’ID renvoyées pour voir s’il existe des candidats pour les ID incorrects. N’oubliez pas que la [définition d’ID incorrect](#definition) prend en compte tous les jeux de données de la connexion.


### Identifier (risque de) ID incorrects dans un champ

Vous pouvez utiliser Experience Platform Query pour effectuer le service d’identification du risque potentiel de Mauvais ID dans un champ.

La requête ci-dessous renvoie les 20 premières valeurs d’identifiant d’un champ. Dans l’ordre décroissant du nombre total d’événements. et où chaque valeur est détectée au cours d’un certain intervalle (par exemple au cours des 30 derniers jours).

Exécutez cette requête pour un champ d’ID de personne spécifique que vous souhaitez analyser. Pour un jeu de données qui nécessite un groupement, vous pouvez également exécuter la requête pour un champ d’identifiant persistant.

```sql
SELECT
    /* INSERT FIELD HERE */,
    COUNT(*) AS occurrences
FROM /* INSERT DATASET TABLE NAME HERE */
WHERE timestamp >= NOW() - INTERVAL '30 days' 
GROUP BY /* INSERT FIELD HERE */
ORDER BY occurrences DESC
LIMIT 20; 
```

Dans la requête, remplacez `INSERT FIELD HERE` selon le type du champ que vous recherchez pour les ID incorrects :

* `full.field.path.from.XDM.schema` (pour les champs de chaîne définis dans le schéma XDM)
* `identityMap['namespace_value'][0].id` (pour les champs définis avec des `namespace_value` dans `identityMap`)

Vérifiez les résultats pour voir s’il existe des valeurs d’ID problématiques. Comme les valeurs personnalisées ou d’espace réservé, ou les valeurs à occurrence élevée qui obtiennent ou pourraient obtenir près d’un million de valeurs en un mois au niveau des données de connexion.
Même si votre implémentation en est toujours à la phase de développement, vous devez évaluer le risque de présence d’ID incorrects une fois la configuration stable et prête pour la production.
