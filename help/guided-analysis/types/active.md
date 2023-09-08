---
title: Vue active
description: Identifier les nouvelles personnes, celles qui ont été consrvées, celles qui reviennent ou celles qui sont inactives.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
keywords: analytics du produit
source-git-commit: 35e009ca6c21754fe7127fe63eea41f8ed00943d
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 2%

---

# [!UICONTROL Actif] view

La variable **Actif** La vue fournit des informations sur la croissance et l’acquisition d’utilisateurs au cours d’une période spécifique. L’axe horizontal est un intervalle de temps, tandis que l’axe vertical est une mesure des utilisateurs. Les utilisateurs sont répartis en quatre catégories :

* **[!UICONTROL Nouveau]**: l’utilisateur était actif pendant la période en cours, mais pas auparavant. Déterminer jusqu’où l’analyse revient en survolant[!UICONTROL Nouveaux utilisateurs]&quot; dans la légende du graphique. La période de recherche arrière est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **[!UICONTROL Répéter]**: l’utilisateur était actif pendant la période en cours et immédiatement avant.
* **[!UICONTROL Retour]**: l’utilisateur était actif dans la période en cours et n’était pas actif dans la période précédente immédiatement, mais auparavant actif à un moment donné. Déterminer jusqu’où l’analyse revient en survolant[!UICONTROL Utilisateurs réguliers]&quot; dans la légende du graphique. La période de recherche arrière est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **[!UICONTROL Dormant]**: l’utilisateur était actif pendant la période précédente immédiatement, mais n’est pas actif pendant la période en cours. Les utilisateurs inactifs ne sont pas pris en compte dans le nombre total d’utilisateurs actifs.

Tous les utilisateurs actifs (nouveaux + répétition + retour) apparaissent sous la forme d’une nuance de teint au-dessus de l’axe horizontal, tandis que tous les utilisateurs inactifs apparaissent en orange sous l’axe horizontal.

>[!VIDEO](https://video.tv.adobe.com/v/3421667/?learn=on)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Rétention et perte de clientèle :** Fournit une visualisation claire des périodes de forte ou faible rétention des utilisateurs. La reconnaissance de ces périodes de rétention élevée ou faible peut vous aider à prendre des décisions sur les produits pour encourager la rétention élevée ou contribuer à réduire l’attrition.
* **Évaluation des campagnes**: l’affichage d’une campagne spécifique peut vous aider à comprendre non seulement le volume de trafic généré, mais également la manière dont la campagne a aidé les utilisateurs à rester actifs.
* **Analyse du cycle de vie des utilisateurs**: l’analyse de la croissance active des utilisateurs tout au long du cycle de vie de l’utilisateur peut aider à identifier les étapes spécifiques où l’engagement de l’utilisateur diminue. Par exemple, s’il existe un taux élevé d’utilisateurs inactifs pour les individus dans une étape d’intégration, cela peut indiquer des problèmes de convivialité ou la nécessité d’une meilleure orientation intégrée au produit.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Événements]**: événement que vous souhaitez mesurer. Ce type d’affichage étant basé sur l’utilisateur, un utilisateur qui interagit avec l’événement une fois au cours de la période est comptabilisé comme utilisateur actif. Vous pouvez inclure un événement dans une requête.
* **[!UICONTROL Personnes]**: segment que vous souhaitez mesurer. Vous pouvez inclure un segment dans une requête.

## Paramètres du graphique

La variable [!UICONTROL Actif] La vue propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Mesure]**: mesure que vous souhaitez mesurer. Les options disponibles sont Nombre d’utilisateurs et Pourcentage d’utilisateurs.
* **[!UICONTROL Type de graphique]**: type de visualisation que vous souhaitez utiliser. Les options disponibles sont Barre empilée et Zone empilée.

## Appliquer la comparaison des temps

{{apply-time-comparison}}

![Comparaison des heures actives](../assets/active-compare.png)

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de tendances. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Une même période peut comporter des intervalles différents qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **[!UICONTROL Date]**: date de début et date de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
