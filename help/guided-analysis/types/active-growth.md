---
title: Analyse de la croissance active
description: Identifiez les nouvelles personnes, celles qui ont été conservées, celles qui reviennent ou celles qui sont inactives.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: ad181b5ba3de1a038c661159a159d234da6c3edf
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 3%

---

# [!UICONTROL Analyse de croissance active]

L&#39;analyse ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL Active Growth]** fournit des informations sur la croissance et l&#39;acquisition d&#39;utilisateurs sur une période spécifique. L’axe horizontal est un intervalle de temps, tandis que l’axe vertical est une mesure des utilisateurs. Les utilisateurs sont répartis en quatre catégories :

* **[!UICONTROL Nouveau]** : l’utilisateur était actif pendant la période actuelle, mais pas auparavant. Découvrez jusqu’où l’analyse revient en survolant _[!UICONTROL Nouveaux utilisateurs]_ dans la légende du graphique. La période de recherche arrière est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **[!UICONTROL Répéter]** : l’utilisateur a été actif pendant la période actuelle et immédiatement précédente.
* **[!UICONTROL Retour]** : l’utilisateur était actif pendant la période actuelle et n’était pas actif pendant la période précédente immédiatement, mais auparavant actif à un moment donné. Découvrez jusqu’où l’analyse revient en survolant _[!UICONTROL Utilisateurs récurrents]_ dans la légende du graphique. La période de recherche arrière est déterminée dynamiquement en fonction de la période et de l’intervalle sélectionnés.
* **[!UICONTROL Dormant]** : l’utilisateur était actif pendant la période précédente immédiatement, mais n’est pas actif pendant la période actuelle. Les utilisateurs inactifs ne sont pas pris en compte dans le nombre total d’utilisateurs actifs.

Tous les utilisateurs actifs (nouveaux + répétition + retour) apparaissent sous la forme d’une nuance de teint au-dessus de l’axe horizontal, tandis que tous les utilisateurs inactifs apparaissent en orange sous l’axe horizontal.

+++ Vidéo de démonstration

>[!VIDEO](https://video.tv.adobe.com/v/3421667/?learn=on)

+++

![Comparaison de l’heure active](../assets/active-growth-compare.png){style="border:1px solid gray"}

## Cas d’utilisation

Voici quelques cas pratiques de cette analyse :

* **Rétention des utilisateurs et perte de clientèle :** fournit une visualisation claire des périodes de forte ou faible rétention des utilisateurs. La reconnaissance de ces périodes de rétention élevée ou faible peut vous aider à prendre des décisions sur les produits pour encourager la rétention élevée ou contribuer à réduire l’attrition.
* **Évaluation de campagne** : l’affichage d’une campagne spécifique peut vous aider à comprendre le volume de trafic généré et l’engagement des utilisateurs.
* **Analyse du cycle de vie des utilisateurs** : l’analyse de la croissance active des utilisateurs tout au long du cycle de vie des utilisateurs peut aider à identifier des étapes spécifiques où l’engagement des utilisateurs s’arrête. Par exemple, s’il existe un taux élevé d’utilisateurs inactifs pour les individus dans une étape d’intégration, cela peut indiquer des problèmes de convivialité ou la nécessité d’une meilleure orientation intégrée au produit.

## Interface

Voir [Interface](../overview.md#interface) pour un aperçu de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Vue]** : basculez entre cette analyse et la [croissance nette](net-growth.md).
* **[!UICONTROL Events]** : événement que vous souhaitez mesurer. Cette analyse étant basée sur les utilisateurs, un utilisateur qui interagit avec l’événement une fois au cours de la période est comptabilisé comme un utilisateur actif. Vous pouvez inclure un événement dans une requête.
* **[!UICONTROL Compté comme]** : méthode de comptage que vous souhaitez appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Nombre d&#39;utilisateurs] et [!UICONTROL Pourcentage d&#39;utilisateurs].
* **[!UICONTROL Segments]** : segment par lequel vous souhaitez filtrer les données. Vous pouvez inclure un segment dans une requête.

### Paramètres du graphique

L’analyse [!UICONTROL Croissance active] offre les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Barre empilée] et [!UICONTROL Zone empilée].

### Comparaison de temps

{{apply-time-comparison}}

### Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Les intervalles peuvent être différents pour une même période, ce qui affecte le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
