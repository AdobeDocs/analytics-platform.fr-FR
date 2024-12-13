---
title: Analyse de la croissance nette
description: Êtes-vous en train de gagner ou de perdre des utilisateurs et utilisatrices ?
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 6%

---

# Analyse de la [!UICONTROL croissance nette] {#net-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_netgrowth_button"
>title="Croissance nette"
>abstract="Êtes-vous en train de gagner ou de perdre des utilisateurs et utilisatrices ?"

<!-- markdownlint-enable MD034 -->

L’analyse ![NetGrowth](/help/assets/icons/NetGrowth.svg) **[!UICONTROL Net growth]** fournit des informations sur le taux auquel vous gagnez ou perdez des utilisateurs sur une période spécifique. L’axe horizontal est un intervalle de temps, tandis que l’axe vertical est la mesure de la croissance.

Chaque point de données représente la croissance nette, qui est calculée à l’aide de la formule suivante :

`([New users] + [Return users]) / [Dormant users]`

Le résultat de cette formule est un ratio. Une croissance nette de `1` représente un équilibre ; le produit a gagné le même nombre d&#39;utilisateurs qu&#39;il a perdu. Une croissance nette supérieure à `1` représente une croissance positive ; il y avait plus de nouveaux utilisateurs et d’utilisateurs récurrents que d’utilisateurs inactifs. De même, une croissance nette inférieure à `1` représente une perte ; il y avait plus d&#39;utilisateurs inactifs que d&#39;utilisateurs nouveaux + récurrents.

De la même manière que pour l’analyse [Active](active-growth.md), les utilisateurs et utilisatrices sont définis comme suit :

* **[!UICONTROL Nouveau]** : l&#39;utilisateur était actif pendant la période en cours, mais pas avant. Découvrez jusqu’où l’analyse revient pour déterminer un nouvel utilisateur en pointant la souris sur « [!UICONTROL Nouveaux utilisateurs] » dans la légende du graphique. La période de recherche en amont est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **[!UICONTROL Retour]** : l’utilisateur était actif au cours de la période en cours et non au cours de la période précédente, mais il était auparavant actif à un moment donné. Découvrez jusqu’où l’analyse revient pour déterminer un utilisateur récurrent en pointant sur « [!UICONTROL  Utilisateurs récurrents ] » dans la légende du graphique. La période de recherche en amont est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **[!UICONTROL Inactif]** : l’utilisateur était actif au cours de la période précédente, mais ne l’est pas au cours de la période en cours. Les utilisateurs inactifs ne sont pas comptabilisés dans le nombre total d’utilisateurs actifs.

>[!NOTE]
>
>Les utilisateurs et utilisatrices réguliers ne sont pas pris en compte dans ce calcul, car ils ne représentent aucun gain ni aucune perte pour les utilisateurs et utilisatrices.

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?learn=on)


## Cas d’utilisation

Les cas d’utilisation de cette analyse sont les suivants :

* **Évaluation des performances** : permet d’évaluer les performances globales de votre produit en termes d’acquisition de nouveaux utilisateurs. En suivant les tendances de croissance, vous pouvez mieux comprendre si votre produit attire et fidélise les utilisateurs à un rythme souhaité.
* **Analyse d’acquisition d’utilisateurs** : permet d’évaluer l’efficacité de vos stratégies d’acquisition d’utilisateurs. L’analyse des sources de croissance des utilisateurs et utilisatrices, telles que les moteurs de recherche, les campagnes ou d’autres canaux marketing, vous permet d’identifier les sources de croissance les plus importantes afin d’allouer les ressources en conséquence.
* **Analyse de l’attrition** : la croissance nette inclut l’attrition dans sa formule (utilisateurs inactifs). Vous pouvez évaluer l’intégrité globale de votre base d’utilisateurs au fil du temps. Si la croissance nette est constamment inférieure à `1`, cela indique un taux élevé d&#39;attrition qui pourrait inciter à la mise en œuvre de stratégies de fidélisation.

## Interface

Voir [Interface](../overview.md#interface) pour une présentation de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Afficher]** : basculer entre cette analyse et [Croissance active](active-growth.md).
* **[!UICONTROL Événements]** : événement que vous souhaitez mesurer. Cette analyse étant basée sur l’utilisateur, un utilisateur qui interagit avec l’événement une fois au cours de la période est comptabilisé comme un utilisateur actif. Vous pouvez inclure un événement dans une requête.
* **[!UICONTROL Compté comme]** : méthode de comptage à appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Nombre d’utilisateurs] et [!UICONTROL Pourcentage d’utilisateurs].
* **[!UICONTROL Segments]** : segment que vous souhaitez mesurer. Vous pouvez inclure un segment dans une requête.

### Comparaison de temps

{{apply-time-comparison}}

### Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont Horaire, Quotidien, Hebdomadaire, Mensuel et Trimestriel. Une même période peut avoir différents intervalles qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse s’étendant sur trois jours avec une granularité quotidienne n’affiche que trois points de données, tandis qu’une analyse s’étendant sur trois jours avec une granularité horaire affiche 72 points de données.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les périodes personnalisées enregistrées précédemment sont disponibles pour votre commodité. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une période fixe.

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
