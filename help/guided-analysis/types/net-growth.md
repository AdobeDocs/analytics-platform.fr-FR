---
title: Analyse de la croissance nette
description: Êtes-vous en train de gagner ou de perdre des utilisateurs et utilisatrices ?
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: aff01f4fc3520d461ca800382cc24d8d948d9cbc
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 2%

---

# [!UICONTROL Analyse de la croissance nette]

L’analyse ![NetGrowth](/help/assets/icons/NetGrowth.svg) **[!UICONTROL Net Growth]** fournit des informations sur le taux auquel vous gagnez ou perdez des utilisateurs sur une période spécifique. L’axe horizontal est un intervalle de temps, tandis que l’axe vertical est la mesure de la croissance.

Chaque point de données représente la croissance nette, qui est calculée à l’aide de la formule suivante :

`([New users] + [Return users]) / [Dormant users]`

Le résultat de cette formule est un ratio. Une croissance nette de `1` représente un équilibre ; le produit a obtenu le même nombre d’utilisateurs qu’il a perdu. Une croissance nette supérieure à `1` représente une croissance positive ; il y a eu plus d’utilisateurs + récurrents que d’utilisateurs inactifs. De même, une croissance nette inférieure à `1` représente une perte ; il y avait plus d’utilisateurs inactifs que de nouveaux utilisateurs + réguliers.

Tout comme l’analyse [Active](active-growth.md), les utilisateurs sont définis comme suit :

* **[!UICONTROL Nouveau]** : l’utilisateur était actif pendant la période actuelle, mais pas auparavant. Découvrez jusqu’où l’analyse revient pour déterminer un nouvel utilisateur en pointant la souris sur &quot;[!UICONTROL New users]&quot; dans la légende du graphique. La période de recherche arrière est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **[!UICONTROL Retour]** : l’utilisateur était actif pendant la période actuelle et n’était pas actif pendant la période précédente immédiatement, mais auparavant actif à un moment donné. Découvrez jusqu’où l’analyse revient pour déterminer un utilisateur récurrent en pointant la souris sur &quot;[!UICONTROL Utilisateurs récurrents]&quot; dans la légende du graphique. La période de recherche arrière est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **[!UICONTROL Dormant]** : l’utilisateur était actif pendant la période précédente immédiatement, mais n’est pas actif pendant la période actuelle. Les utilisateurs inactifs ne sont pas pris en compte dans le nombre total d’utilisateurs actifs.

>[!NOTE]
>
>Les utilisateurs réguliers ne sont pas pris en compte dans ce calcul, car ils ne représentent aucun gain ni perte pour les utilisateurs.

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?learn=on)


## Cas d’utilisation

Voici quelques cas pratiques de cette analyse :

* **Évaluation des performances** : vous permet d’évaluer les performances globales de votre produit en termes d’acquisition de nouveaux utilisateurs. En suivant les tendances de croissance, vous pouvez mieux comprendre si votre produit attire et conserve les utilisateurs à un rythme souhaité.
* **Analyse de l’acquisition des utilisateurs** : vous permet d’évaluer l’efficacité de vos stratégies d’acquisition des utilisateurs. L’analyse des sources de croissance des utilisateurs, telles que les moteurs de recherche, les campagnes ou d’autres canaux marketing, vous permet d’identifier les sources de croissance les plus significatives afin que vous puissiez allouer les ressources en conséquence.
* **Analyse de perte de clientèle** : la croissance nette inclut l’attrition dans sa formule (utilisateurs inactifs). Vous pouvez évaluer l’intégrité globale de votre base d’utilisateurs au fil du temps. Si la croissance nette est toujours inférieure à `1`, cela indique une forte attrition qui pourrait inciter à mettre en oeuvre des stratégies de rétention.

## Interface

Voir [Interface](../overview.md#interface) pour un aperçu de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Vue]** : basculez entre cette analyse et la [croissance active](active-growth.md).
* **[!UICONTROL Events]** : événement que vous souhaitez mesurer. Cette analyse étant basée sur les utilisateurs, un utilisateur qui interagit avec l’événement une fois au cours de la période est comptabilisé comme un utilisateur actif. Vous pouvez inclure un événement dans une requête.
* **[!UICONTROL Compté comme]** : méthode de comptage que vous souhaitez appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Nombre d&#39;utilisateurs] et [!UICONTROL Pourcentage d&#39;utilisateurs].
* **[!UICONTROL Segments]** : segment que vous souhaitez mesurer. Vous pouvez inclure un segment dans une requête.

### Comparaison de temps

{{apply-time-comparison}}

### Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Une même période peut comporter des intervalles différents qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
