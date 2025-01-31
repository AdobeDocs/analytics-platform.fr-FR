---
title: Analyse de croissance active
description: Identifiez les nouvelles personnes, celles qui ont été conservées, celles qui reviennent ou celles qui sont inactives.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 7%

---

# Analyse de la [!UICONTROL croissance active] {#active-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_activegrowth_button"
>title="Croissance active"
>abstract="Identifiez les nouvelles personnes, celles qui ont été conservées, celles qui reviennent ou celles qui sont inactives."

<!-- markdownlint-enable MD034 -->


L’analyse ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL Croissance active]** fournit des informations sur la croissance et l’acquisition d’utilisateurs sur une période spécifique. L’axe horizontal est un intervalle de temps, tandis que l’axe vertical est une mesure des utilisateurs. Les utilisateurs sont répartis en quatre catégories :

* **[!UICONTROL Nouveau]** : l&#39;utilisateur était actif pendant la période en cours, mais pas avant. Observez l’étendue de l’analyse en pointant sur _[!UICONTROL Nouveaux utilisateurs]_ dans la légende du graphique. La période de recherche en amont est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **[!UICONTROL Répéter]** : l’utilisateur ou l’utilisatrice était actif(e) pendant la période actuelle et la période précédente.
* **[!UICONTROL Retour]** : l’utilisateur était actif au cours de la période en cours et non au cours de la période précédente, mais il était auparavant actif à un moment donné. Observez l’étendue de l’analyse en pointant sur _[!UICONTROL Utilisateurs récurrents]_ dans la légende du graphique. La période de recherche en amont est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **[!UICONTROL Inactif]** : l’utilisateur était actif au cours de la période précédente, mais ne l’est pas au cours de la période en cours. Les utilisateurs inactifs ne sont pas comptabilisés dans le nombre total d’utilisateurs actifs.

Tous les utilisateurs actifs (nouveau + répétition + retour) apparaissent en teinte de sarcelle au-dessus de l’axe horizontal, tandis que tous les utilisateurs inactifs apparaissent en orange au-dessous de l’axe horizontal.


>[!VIDEO](https://video.tv.adobe.com/v/3421667/?quality=12&learn=on)

## Cas d’utilisation

Les cas d’utilisation de cette analyse sont les suivants :

* **Rétention et attrition des utilisateurs :** permet de visualiser clairement les périodes de rétention élevée ou faible des utilisateurs. Reconnaître ces périodes de rétention élevée ou faible peut vous aider à prendre des décisions concernant le produit afin d’encourager une rétention élevée ou de minimiser le taux de perte de clientèle.
* **Évaluation de la campagne** : l’affichage d’une campagne spécifique peut vous aider à comprendre le volume de trafic généré et à déterminer dans quelle mesure elle a permis aux utilisateurs et utilisatrices de rester engagés.
* **Analyse du cycle de vie des utilisateurs** : l’analyse de la croissance des utilisateurs et utilisatrices actifs tout au long de leur cycle de vie peut aider à identifier les étapes spécifiques où l’engagement des utilisateurs et utilisatrices diminue. Par exemple, s’il existe un taux élevé d’utilisateurs inactifs pour les individus en phase d’intégration, cela peut indiquer des problèmes d’utilisation ou un besoin de meilleurs conseils intégrés au produit.

## Interface

Voir [Interface](../overview.md#interface) pour une présentation de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Vue]** : basculer entre cette analyse et [Croissance nette](net-growth.md).
* **[!UICONTROL Événements]** : événement que vous souhaitez mesurer. Cette analyse étant basée sur l’utilisateur, un utilisateur qui interagit avec l’événement une fois au cours de la période est comptabilisé comme un utilisateur actif. Vous pouvez inclure un événement dans une requête.
* **[!UICONTROL Compté comme]** : méthode de comptage à appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Nombre d’utilisateurs] et [!UICONTROL Pourcentage d’utilisateurs].
* **[!UICONTROL Segments]** : segment en fonction duquel vous souhaitez filtrer les données. Vous pouvez inclure un segment dans une requête.

### Paramètres du graphique

L’analyse [!UICONTROL Croissance active] propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : le type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Barre empilée] et [!UICONTROL Zone empilée].

### Comparaison de temps

{{apply-time-comparison}}

### Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont Horaire, Quotidien, Hebdomadaire, Mensuel et Trimestriel. Une même période peut avoir des intervalles différents, ce qui affecte le nombre de points de données dans le graphique et le nombre de colonnes du tableau. Par exemple, l’affichage d’une analyse s’étendant sur trois jours avec une granularité quotidienne n’affiche que trois points de données, tandis qu’une analyse s’étendant sur trois jours avec une granularité horaire affiche 72 points de données.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les périodes personnalisées enregistrées précédemment sont disponibles pour votre commodité. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une période fixe.

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
