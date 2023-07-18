---
title: Principale vue
description: Identifier les nouvelles personnes, celles qui ont été consrvées, celles qui reviennent ou celles qui sont inactives.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
source-git-commit: 4cae5968e2ae1b6048522b9eb065d4b6e2272938
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 2%

---

# [!UICONTROL Principal] view

Le **Principal** La vue fournit des informations sur la croissance et l’acquisition d’utilisateurs au cours d’une période spécifique. L’axe horizontal est un intervalle de temps, tandis que l’axe vertical est une mesure des utilisateurs. Les utilisateurs sont répartis en quatre catégories :

* **[!UICONTROL Nouveau]**: L’utilisateur était principal pendant la période actuelle, mais pas auparavant. Déterminer jusqu’où l’analyse revient en survolant[!UICONTROL Nouveaux utilisateurs]&quot; dans la légende du graphique. La période de recherche arrière est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **[!UICONTROL Répéter]**: L’utilisateur était principal pendant la période en cours et immédiatement précédent.
* **[!UICONTROL Retour]**: L’utilisateur était principal dans la période actuelle et non principal dans la période précédente immédiatement, mais auparavant principal à un moment donné. Déterminer jusqu’où l’analyse revient en survolant[!UICONTROL Utilisateurs récurrents]&quot; dans la légende du graphique. La période de recherche arrière est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **[!UICONTROL Dormant]**: L’utilisateur était principal dans la période précédente immédiatement, mais n’est pas principal dans la période actuelle. Les utilisateurs inactifs ne sont pas pris en compte dans le nombre total d’utilisateurs principaux.

Tous les utilisateurs principaux (nouveaux + répétition + retour) apparaissent sous la forme d’une nuance de teint au-dessus de l’axe horizontal, tandis que tous les utilisateurs inactifs apparaissent en orange sous l’axe horizontal.

>[!VIDEO](https://video.tv.adobe.com/v/3421667/?learn=on)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **[!UICONTROL Rétention et entretien des utilisateurs]n :** Fournit une visualisation claire des périodes de forte ou faible rétention des utilisateurs. La reconnaissance de ces périodes de rétention élevée ou faible peut vous aider à prendre des décisions sur les produits pour encourager la rétention élevée ou contribuer à réduire l’attrition.
* **[!UICONTROL Évaluation des campagnes]**: L’affichage d’une campagne spécifique peut vous aider à comprendre non seulement le volume de trafic généré, mais également la manière dont la campagne a aidé les utilisateurs à rester engagés.
* **[!UICONTROL Analyse du cycle de vie des utilisateurs]**: L’analyse de la principale croissance des utilisateurs tout au long du cycle de vie de l’utilisateur peut aider à identifier les étapes spécifiques où l’engagement de l’utilisateur diminue. Par exemple, s’il existe un taux élevé d’utilisateurs inactifs pour les individus dans une étape d’intégration, cela peut indiquer des problèmes de convivialité ou la nécessité d’une meilleure orientation intégrée au produit.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Événements]**: L’événement que vous souhaitez mesurer. Ce type de vue étant basé sur l’utilisateur, un utilisateur qui interagit avec l’événement une fois au cours de la période est comptabilisé comme un utilisateur principal. Vous pouvez inclure un événement dans une requête.
* **[!UICONTROL Personnes]**: Le segment que vous souhaitez mesurer. Vous pouvez inclure un segment dans une requête.

## Paramètres du graphique

Le [!UICONTROL Principal] La vue propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Mesure]**: Mesure que vous souhaitez mesurer. Les options disponibles sont Nombre d’utilisateurs et Pourcentage d’utilisateurs.
* **[!UICONTROL Type de graphique]**: Type de visualisation que vous souhaitez utiliser. Les options disponibles sont Barre empilée et Zone empilée.

## Appliquer la comparaison des temps

{{apply-time-comparison}}

![Principale comparaison du temps](../assets/active-compare.png)

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: Granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Une même période peut comporter des intervalles différents qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **[!UICONTROL Date]**: Les dates de début et de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
